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
- case da Estação Café & Prosa (demo conceitual);
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
| 6 | Área de Conteúdos | Concluída |
| 7 | SEO on-page e técnico | Concluída |
| 8 | Formulário e acessibilidade | Concluída |
| 9 | Desempenho e responsividade | Concluída |
| 10 | Validação e documentação final | Concluída |

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
- perf(frontend): otimizar desempenho e responsividade — não criado; a Fase 9 não exigiu alteração de código
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
- execução completa dos testes automatizados do backend, com 28 testes aprovados;
- integração do Cloudflare Turnstile no frontend e no backend;
- validação do token no servidor antes da gravação do contato;
- validação de hostname e action no ambiente de produção;
- omissão de remoteip quando o identificador do visitante não é um IP válido;
- timeout nas requisições do frontend e na consulta ao serviço do Turnstile;
- bloqueio do botão enquanto API e Turnstile não estão disponíveis;
- validação da CSP para scripts e frames do Cloudflare;
- teste local completo com SQLite temporário;
- rejeição em produção de envio sem token, com resposta HTTP 400;
- envio completo e bem-sucedido pelo formulário em produção;
- confirmação da mensagem no painel administrativo;
- exclusão da mensagem utilizada no teste de produção;
- validação dos deploys do backend no Render e do frontend na Vercel.
- auditoria do peso dos arquivos, imagens e recursos carregados pelo frontend;
- Lighthouse da página inicial em produção no mobile: desempenho 99, acessibilidade 100, práticas recomendadas 100 e SEO 100;
- métricas mobile: FCP 1,7 s, LCP 1,7 s, TBT 0 ms e CLS 0;
- Lighthouse da página inicial em produção no desktop: desempenho 100, acessibilidade 100, práticas recomendadas 100 e SEO 100;
- métricas desktop: FCP 0,5 s, LCP 0,5 s, Speed Index 0,8 s, TBT 0 ms e CLS 0;
- análise de Devicon, fontes, cache, recursos externos e solicitações que bloqueiam renderização;
- confirmação de que o Devicon é utilizado dinamicamente e deve ser mantido;
- auditoria estática de breakpoints, overflow, min-width, white-space e elementos com position fixed;
- validação visual responsiva das páginas em 320, 375, 768, 1024 e 1366 px pelo Chrome DevTools Device Mode;
- nenhuma quebra responsiva relevante foi identificada;
- nenhuma alteração de código foi necessária na Fase 9.

## 14. Validação e documentação final

### Validações executadas

- correção da codificação dos metadados SEO nas 13 páginas públicas, commit a4ba4b6;
- validação das 13 páginas públicas em produção, todas respondendo HTTP 200;
- confirmação da ausência dos casos de mojibake identificados nos metadados corrigidos;
- validação dos blocos JSON-LD nas 13 páginas públicas;
- validação do robots.txt;
- validação do sitemap.xml com 13 URLs públicas e sem rotas administrativas;
- confirmação de que /admin, /login e /404 não estão presentes no sitemap;
- validação da página 404 personalizada com resposta HTTP 404;
- inspeção dos 13 destinos internos de navegação, todos respondendo HTTP 200;
- exclusão do endpoint /cdn-cgi/l/email-protection da inspeção de links, por pertencer à proteção de e-mail do Cloudflare;
- validação dos estados de erro do formulário com campos obrigatórios vazios;
- validação da mensagem geral para revisão dos campos;
- confirmação do foco automático no primeiro campo inválido;
- confirmação de que a validação local impede o envio de dados inválidos para a API;
- simulação de indisponibilidade da API no navegador;
- confirmação da mensagem "Serviço temporariamente indisponível" durante a falha simulada;
- confirmação de que o botão de envio permanece desabilitado com a API indisponível;
- restauração do acesso normal à API após o teste;
- deploy do frontend no commit a4ba4b6 validado com sucesso na Vercel.

### Validações não executadas no fechamento

- validação em dispositivo físico — não executada;
- PageSpeed comparativo antes e depois — não executado; a Fase 9 utilizou Lighthouse em produção;
- validação das rotas em Preview Deployment — não executada;
- teste específico de lentidão/timeout da API — não executado por decisão durante a Fase 10.

As validações não executadas acima foram registradas de forma explícita e não são consideradas como aprovadas.

## 15. Produção

A Fase 8 foi publicada e validada em produção em 2026-08-06.

A Fase 9 foi concluída em 2026-08-07 sem alterações de código no frontend e, portanto, sem necessidade de novo deploy.

A Fase 10 foi concluída em 2026-08-08 após as validações finais do frontend e da produção. A correção de codificação dos metadados SEO foi publicada e validada no commit a4ba4b6.

### Backend

- repositório: Souzas-Dev/souzasdevback;
- branch de produção: main;
- commit de merge: e40a316;
- hospedagem: Render;
- API: https://api.souzasdev.com;
- banco em produção: PostgreSQL/Supabase;
- status da API validado como success;
- conexão com o banco validada como connected;
- 28 testes automatizados aprovados antes da publicação.

### Frontend

- repositório: Souzas-Dev/souzasdevfront;
- branch de produção: main;
- commit de integração da Fase 8: c4c6962;
- commit de produção validado na Fase 10: a4ba4b6;
- hospedagem: Vercel;
- domínio validado: https://souzasdev.com;
- widget do Cloudflare Turnstile carregado corretamente;
- formulário validado de ponta a ponta em produção.

### Cloudflare Turnstile

- Site Key pública configurada no frontend;
- Secret Key configurada somente no ambiente do Render;
- hostname esperado: souzasdev.com;
- action esperada: contact_form;
- timeout da validação no backend: 8000 ms;
- envio sem token rejeitado com HTTP 400;
- envio com token válido aceito e gravado;
- mensagem de teste removida após a validação.

Nenhum domínio, serviço, projeto ou banco foi recriado durante a implementação.
