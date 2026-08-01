# Roadmap de evolução do site e SEO

## 1. Identificação

- Projeto: Souzas Dev
- Data da auditoria: 2026-07-29
- Responsável: Eduardo Souza
- Localização oficial: Campo Grande, MS, Brasil
- Site: https://souzasdev.com
- API: https://api.souzasdev.com

## 2. Objetivo

Evoluir o site oficial da Souzas Dev em etapas seguras, com melhorias comerciais, estruturais, técnicas, de acessibilidade, desempenho e SEO.

A evolução não pressupõe garantia de posicionamento, tráfego, indexação, captação de clientes ou resultado comercial.

## 3. Estrutura real identificada

A pasta C:\SouzasDev\01-site não é um repositório Git.

O projeto está dividido em três repositórios independentes:

### Frontend

- Pasta local: C:\SouzasDev\01-site\frontend
- Repositório: Souzas-Dev/souzasdevfront
- Tecnologia: HTML, CSS e JavaScript
- Hospedagem: Vercel
- Branch de produção identificada: main
- Commit-base: 99aa417

### Backend

- Pasta local: C:\SouzasDev\01-site\backend
- Repositório: Souzas-Dev/souzasdevback
- Tecnologia: Node.js
- Hospedagem: Render
- Banco em produção: PostgreSQL/Supabase
- Branch de produção identificada: main
- Commit-base: b64c2ce

### Documentação

- Pasta local: C:\SouzasDev\01-site\documentacao
- Repositório: Souzas-Dev/souzasdev
- Branch de produção identificada: main
- Commit-base: 75d3a35

## 4. Branch de trabalho

A branch local destinada a esta evolução é:

feat/evolucao-site-seo

A mesma identificação será utilizada nos três repositórios para facilitar o acompanhamento das mudanças relacionadas.

Nenhum push, pull request, merge ou deploy foi autorizado nesta etapa.

## 5. Estado inicial

No início da auditoria:

- os três repositórios estavam na branch main;
- os três repositórios estavam limpos;
- as branches locais estavam sincronizadas com origin/main;
- não existiam branches adicionais locais ou remotas;
- nenhum arquivo .env foi aberto ou alterado;
- a produção permaneceu inalterada.

## 6. Funcionalidades existentes

### Site público

- página inicial institucional;
- seção Sobre;
- seção Serviços;
- seção Tecnologias;
- seção Projetos;
- formulário de contato;
- botão e links para WhatsApp;
- case da Souzas Dev;
- case da Cafeteria Conceito;
- navegação móvel;
- favicon;
- metadados básicos;
- Open Graph parcial;
- link para pular ao conteúdo;
- suporte a prefers-reduced-motion.

### Área administrativa

- página de login;
- painel administrativo;
- autenticação com JWT;
- cookie HttpOnly;
- proteção CSRF;
- listagem e gerenciamento de contatos.

### Backend

- endpoint de status;
- autenticação;
- sessão administrativa;
- envio de contato;
- rotas administrativas;
- validação de entrada;
- CORS restrito;
- rate limiting;
- headers de segurança;
- observabilidade;
- testes automatizados.

## 7. Problemas confirmados

### Estrutura e conteúdo

- a primeira dobra dá destaque excessivo ao aprendizado;
- textos essenciais da primeira dobra são inseridos por JavaScript;
- serviços ainda não possuem páginas próprias;
- a navegação principal é baseada majoritariamente em âncoras;
- a área Conteúdos ainda não existe;
- o rodapé e os contatos precisam de revisão comercial.

### SEO

- robots.txt ausente;
- sitemap.xml ausente;
- página 404 própria ausente;
- canonical ausente nas páginas auditadas;
- JSON-LD ausente nas páginas auditadas;
- imagem Open Graph ausente em parte das páginas;
- páginas de serviços ainda não existem;
- conteúdo essencial de projetos depende parcialmente de JavaScript.

### Documentação

- a documentação central ainda descreve uma estrutura antiga;
- há referências a frontend e backend como pastas de um único repositório;
- há referências predominantes ao SQLite, embora a produção utilize PostgreSQL/Supabase;
- existem comandos Bash que deverão ser adaptados para PowerShell;
- há próximos passos documentados que já foram concluídos em produção.

## 8. Hipóteses e verificações pendentes

Os itens abaixo ainda não devem ser tratados como problemas confirmados:

- branch de produção configurada na interface da Vercel;
- comportamento completo com JavaScript desabilitado;
- links quebrados em produção;
- erros de console em todas as páginas;
- funcionamento em navegadores móveis diferentes;
- métricas atuais do Lighthouse e PageSpeed;
- comportamento em rede lenta;
- status HTTP de todas as rotas futuras;
- compatibilidade final da CSP com novos recursos;
- necessidade real de alterações no backend.

## 9. Divergências de informação

Os contatos oficiais precisam ser confirmados antes da Fase 3.

Foram encontradas divergências entre:

- o contexto oficial compartilhado;
- os dados atualmente publicados no frontend;
- os dados informados no novo plano de evolução.

Nenhum telefone ou e-mail principal será substituído sem confirmação.

## 10. Riscos

- os repositórios separados exigem commits e comparações independentes;
- a criação de várias páginas estáticas pode aumentar repetição de HTML;
- alterações em rotas precisam respeitar cleanUrls e trailingSlash da Vercel;
- mudanças na política CSP precisam ser avaliadas com cuidado;
- o formulário e a área administrativa não podem ser afetados pelas mudanças públicas;
- conteúdos dinâmicos precisam ganhar fallback sem quebrar a implementação existente;
- dados fictícios devem permanecer claramente identificados como demonstração ou case conceitual.

## 11. Roadmap

| Fase | Entrega | Status |
| --- | --- | --- |
| 0 | Auditoria, baseline e branches | Concluída |
| 1 | Primeira dobra e posicionamento | Concluída |
| 2 | Serviços concretos | Concluída |
| 3 | Localização, contatos e rodapé | Concluída |
| 4 | Páginas, rotas e navegação | Concluída |
| 5 | Projetos e cases indexáveis | Concluída |
| 6 | Área de Conteúdos | Em andamento |
| 7 | SEO on-page e técnico | Não iniciada |
| 8 | Formulário e acessibilidade | Não iniciada |
| 9 | Desempenho e responsividade | Não iniciada |
| 10 | Validação e documentação final | Não iniciada |

## 12. Commits previstos

- chore: preparar evolução do site e registrar baseline
- feat(home): melhorar primeira dobra e posicionamento
- feat(services): apresentar serviços de forma objetiva
- feat(local): adicionar localização e contatos oficiais
- feat(routes): criar páginas e navegação estruturada
- feat(projects): tornar projetos e cases indexáveis
- feat(content): criar área de conteúdos
- feat(seo): implementar otimizações de busca
- fix(a11y): melhorar acessibilidade e formulário
- perf(frontend): otimizar desempenho e responsividade
- docs: concluir validações e documentação do site

Os commits serão criados somente nos repositórios que realmente tiverem arquivos alterados em cada fase.

## 13. Validações já realizadas

- estado do Git nos três repositórios;
- branches locais e remotas;
- remotes configurados;
- commits-base;
- inventário de páginas HTML;
- contagem de headings;
- presença de titles e descriptions;
- presença de canonical, Open Graph e JSON-LD;
- inventário de recursos públicos;
- validação do vercel.json;
- validação de sintaxe dos principais arquivos JavaScript;
- inventário de scripts e testes do backend;
- identificação das rotas da API;
- confirmação de que o arquivo .env não foi acessado;
- validação estrita da codificação UTF-8 do documento de baseline;
- confirmação de que a acentuação foi preservada.

## 14. Validações ainda pendentes

- execução completa dos testes do backend;
- testes visuais em desktop, tablet e celular;
- Chrome DevTools Device Mode;
- validação em dispositivo físico;
- Lighthouse antes e depois;
- PageSpeed antes e depois;
- validação das rotas em Preview Deployment;
- teste de falha e lentidão da API;
- teste do formulário em diferentes estados;
- inspeção de links e status HTTP;
- validação de dados estruturados;
- validação do sitemap e robots.

## 15. Produção

Nesta etapa:

- nenhuma alteração foi realizada na main;
- nenhum push foi realizado;
- nenhum deploy foi iniciado;
- nenhum domínio foi alterado;
- nenhuma variável de ambiente foi alterada;
- banco, Supabase, Render, Vercel e Cloudflare permaneceram inalterados.
