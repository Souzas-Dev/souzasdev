# Meu Portfólio - Documentação técnica

## Visão geral

Este projeto é um portfólio profissional com frontend estático, backend em Node.js e banco SQLite. A aplicação oferece uma interface pública para apresentação do perfil, um formulário de contato e um painel administrativo protegido para gestão das mensagens recebidas.

Ao longo do desenvolvimento, o projeto recebeu melhorias em segurança, validação, testes, observabilidade e documentação, deixando a estrutura mais próxima de um padrão profissional.

## Objetivo do projeto

O projeto tem como finalidade:

- apresentar o perfil profissional do desenvolvedor;
- permitir que visitantes enviem mensagens por meio do formulário de contato;
- oferecer um painel administrativo para visualizar, filtrar, atualizar e excluir mensagens;
- demonstrar boas práticas de desenvolvimento e segurança em uma aplicação realista.

## Arquitetura

### Frontend

O frontend está localizado em [frontend](frontend) e é composto por páginas estáticas em HTML/CSS/JavaScript para:

- exibir a landing page e o conteúdo do portfólio;
- controlar o formulário de contato em [frontend/js/main.js](frontend/js/main.js);
- realizar login e autenticação em [frontend/js/login.js](frontend/js/login.js);
- listar e gerenciar mensagens no painel em [frontend/js/admin.js](frontend/js/admin.js);
- carregar conteúdo dinâmico a partir de [frontend/js/site-data.js](frontend/js/site-data.js).

### Backend

O backend está localizado em [backend](backend) e é responsável por:

- expor endpoints HTTP para status, autenticação, contato e administração;
- validar entradas de dados;
- autenticar administradores com JWT e cookies HttpOnly;
- persistir mensagens e dados de administração em SQLite;
- aplicar controles de segurança como CSRF, rate limiting, headers e CORS restrito;
- registrar eventos importantes para observabilidade.

## Estrutura de pastas

```text
backend/
  src/
    auth/
      cookies.js
      jwt.js
      password.js
    database/
      database.js
    scripts/
      create-admin.js
      list-contacts.js
    observability.js
    server.js
  tests/
    security.test.js
    integration.test.js
  data/
    logs/
  package.json
  .env.example
  DEPLOY.md

frontend/
  css/
  js/
  assets/
  index.html
  admin.html
  login.html
  case-souzas-dev.html
  BRAND.md
```

## Fluxos principais

### Fluxo público

1. O visitante acessa a página inicial.
2. O formulário de contato é preenchido.
3. O frontend envia os dados para o endpoint de contato.
4. O backend valida o payload e persiste a mensagem.
5. A mensagem fica disponível para visualização administrativa.

### Fluxo administrativo

1. O administrador acessa a tela de login.
2. O backend valida as credenciais e gera um JWT.
3. O token é armazenado em cookie HttpOnly e uma proteção CSRF é aplicada.
4. O painel administrativo carrega as mensagens e estatísticas via API.
5. O administrador pode atualizar status, excluir mensagens e encerrar a sessão.

## Componentes principais

### Backend

- [backend/src/server.js](backend/src/server.js): ponto central da API, roteamento, segurança e lógica de servidor.
- [backend/src/auth/cookies.js](backend/src/auth/cookies.js): criação, leitura e limpeza de cookies de sessão e CSRF.
- [backend/src/auth/jwt.js](backend/src/auth/jwt.js): geração e validação de tokens JWT com issuer e audience.
- [backend/src/auth/password.js](backend/src/auth/password.js): hash seguro de senhas com scrypt.
- [backend/src/database/database.js](backend/src/database/database.js): acesso ao SQLite, criação de tabelas e operações CRUD.
- [backend/src/observability.js](backend/src/observability.js): logging básico em arquivo para eventos de negócio e erros.
- [backend/src/scripts/create-admin.js](backend/src/scripts/create-admin.js): criação ou atualização de administrador.
- [backend/src/scripts/list-contacts.js](backend/src/scripts/list-contacts.js): listagem das mensagens salvas.

### Frontend

- [frontend/index.html](frontend/index.html): página pública de apresentação.
- [frontend/admin.html](frontend/admin.html): painel administrativo.
- [frontend/login.html](frontend/login.html): tela de login.
- [frontend/js/main.js](frontend/js/main.js): formulário de contato e interação pública.
- [frontend/js/login.js](frontend/js/login.js): autenticação e sessão administrativa.
- [frontend/js/admin.js](frontend/js/admin.js): painel administrativo e gestão de mensagens.
- [frontend/js/site-data.js](frontend/js/site-data.js): conteúdo estático da interface.

## Segurança implementada

### Proteção CSRF
- O backend gera e valida um token CSRF para requisições mutantes.
- O frontend envia esse token nas ações administrativas.

### Headers de segurança
- Foram adicionados headers como:
  - X-Content-Type-Options: nosniff
  - X-Frame-Options: DENY
  - Referrer-Policy: no-referrer
  - Permissions-Policy
  - Cross-Origin-Opener-Policy
  - Cross-Origin-Resource-Policy

### CORS e proxy
- A API aceita apenas origens configuradas por variável de ambiente.
- Há suporte opcional para leitura do header X-Forwarded-For quando TRUST_PROXY=true, o que é útil em ambientes com proxy reverso.

### Rate limiting
- Limites foram aplicados a login e envio de mensagens para reduzir abuso.

### Armazenamento de senha
- As senhas são hashadas com scrypt antes de serem salvas.

## Testes

Os testes automatizados foram criados em [backend/tests/security.test.js](backend/tests/security.test.js) e [backend/tests/integration.test.js](backend/tests/integration.test.js) e cobrem:

- hash e verificação de senha;
- criação e leitura de cookies;
- geração e validação de JWT;
- resposta de endpoints principais como /api/status, /api/auth/csrf e /api/contact;
- execução com banco e log temporários para evitar conflitos entre testes.

### Executar testes

```bash
cd backend
npm test
```

## Configuração de ambiente

O arquivo [backend/.env.example](backend/.env.example) contém as variáveis principais, incluindo:

```env
PORT=3000
NODE_ENV=development

JWT_SECRET=substitua-por-um-segredo-forte
JWT_EXPIRES_IN=2h

AUTH_COOKIE_NAME=portfolio_session
AUTH_COOKIE_MAX_AGE=7200
CSRF_COOKIE_NAME=portfolio_csrf

ALLOWED_ORIGIN=http://localhost:5500
TRUST_PROXY=false

RATE_LIMIT_WINDOW_MS=60000
MAX_CONTACT_REQUESTS=15
MAX_AUTH_REQUESTS=10

DATABASE_PATH=
LOG_FILE_PATH=
```

## Como executar localmente

### Backend

```bash
cd backend
npm install
cp .env.example .env
npm start
```

### Frontend

O frontend é estático. Você pode abrir os arquivos HTML diretamente no navegador ou servir a pasta [frontend](frontend) com um servidor local simples.

## Como criar o administrador inicial

```bash
cd backend
npm run admin:create
```

Esse comando usa as variáveis de ambiente ADMIN_NAME, ADMIN_EMAIL e ADMIN_PASSWORD.

## CI/CD e deploy

- Pipeline de CI em [.github/workflows/ci.yml](.github/workflows/ci.yml)
- Guia de deploy em [backend/DEPLOY.md](backend/DEPLOY.md)

## Observabilidade básica

- O backend registra eventos importantes em [backend/src/observability.js](backend/src/observability.js).
- Os logs podem ser direcionados para um caminho customizado via LOG_FILE_PATH.
- Eventos registrados incluem login bem-sucedido, falhas de login, mensagens recebidas e erros do servidor.

## Boas práticas de manutenção

- manter o JWT_SECRET forte e diferente por ambiente;
- nunca versionar arquivos .env com dados reais;
- revisar dependências regularmente com npm audit;
- manter testes e documentação atualizados;
- usar HTTPS em produção;
- fazer backups regulares do arquivo SQLite;
- revisar os logs periodicamente;
- considerar um sistema externo de observabilidade caso o projeto cresça.

## Próximos passos recomendados

- adicionar testes para rotas administrativas autenticadas;
- evoluir a observabilidade com métricas e alertas;
- preparar um ambiente de produção com HTTPS, proxy reverso e backup automatizado;
- migrar a persistência para um banco mais escalável se houver crescimento real de uso.
