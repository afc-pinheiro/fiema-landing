# Proposta Comercial — Novo Portal Institucional FIEMA

**Cliente:** Federação das Indústrias do Estado do Maranhão (FIEMA)  
**Proponente:** ACDEV Consultoria (André Felipe Carvalho Pinheiro)  
**Website:** [acdev-landing-page.vercel.app](https://acdev-landing-page.vercel.app)  
**Data de Emissão:** 06 de Julho de 2026  
**Validade da Proposta:** 15 dias  

---

## 1. Objetivo do Projeto

Esta proposta visa à migração e ao desenvolvimento do **Novo Portal Institucional da FIEMA**, evoluindo a arquitetura atual baseada em sistemas legados para uma infraestrutura moderna de alta performance, focada em otimização de velocidade (Core Web Vitals), conversão de leads, acessibilidade e autonomia operacional para a equipe interna. 

O projeto consolida as soluções validadas nos protótipos de design em um sistema robusto baseado em **Next.js** no frontend e **Strapi CMS** no gerenciamento de conteúdo, hospedado em servidores próprios da entidade e monitorado com ferramentas de observabilidade líderes de mercado.

---

## 2. Detalhamento Técnico da Solução

Propomos uma arquitetura corporativa moderna e desacoplada (headless):

### A. Frontend (Next.js)
* **Performance & SEO**: Construído utilizando Next.js, aproveitando renderização híbrida (SSG/ISR) para garantir tempos de carregamento inferiores a 1.5 segundo e indexação máxima no Google.
* **Responsividade & Acessibilidade**: Interface totalmente adaptável (Mobile-First) com suporte a padrões de acessibilidade WCAG/eMAG (atalhos de teclado, alto contraste e compatibilidade com leitores de tela).
* **Métricas**: Integração com **Google Analytics 4 (GA4)** para acompanhamento de acessos e tags customizadas de conversão (cliques para o WhatsApp corporativo, formulários preenchidos, etc.).

### B. Gestão de Conteúdo (Strapi CMS)
* **Backoffice Centralizado**: Painel administrativo protegido por senha onde a equipe da FIEMA pode editar, pausar ou publicar de forma autônoma: notícias, editais, banners de destaque, galerias de fotos e dados das unidades regionais.
* **Controle de Permissões**: Níveis de acesso diferenciados para redatores, editores e administradores de TI.

### C. Backend de Migração (Java + Spring Boot)
* **Ferramenta de Migração**: Camada desenvolvida em Java (Spring Boot) utilizada como motor de ETL (Extração, Transformação e Carga) para extrair notícias, editais e mídias do site legado (Yii/PHP) de forma limpa e segura, populando a nova base de dados do Strapi CMS.
* **Foco Inicial**: Nesta fase, o backend servirá exclusivamente como ferramenta técnica facilitadora de migração. Os links para sistemas externos da FIEMA (SGE, RH, Protocolo) serão apontados diretamente na interface pública (frontend), sem integrações de API nesta etapa.

### D. Newsletter Open Source (Listmonk)
* **Autonomia de Disparo**: Instalação e configuração do **Listmonk** (100% traduzido para PT-BR). Trata-se de uma plataforma autohospedada de envio de e-mails, sem cobrança de mensalidades por quantidade de assinantes.
* **Integração com Next.js**: Captação de e-mails integrada direto no frontend que alimenta as listas de transmissão em tempo real.
* **Painel Administrativo**: Gestão de listas (ex: Sindicatos, Associados), editor visual de e-mails com suporte a templates corporativos pré-configurados e relatórios de envio (taxas de abertura e clique).

### E. Observabilidade (Grafana)
* **Monitoramento Ativo**: Configuração de painéis de saúde (dashboards) no **Grafana** para telemetria da aplicação, tempo de resposta das APIs, alertas de instabilidade e monitoramento de logs de segurança tanto do Next.js quanto do backend em Spring.

---

## 3. Escopo de Serviços e Migração de Conteúdo

O desenvolvimento engloba as seguintes atividades:

1. **Desenvolvimento do Frontend e do CMS**: Criação de todas as páginas públicas (Home, Sobre, Serviços, Notícias, Editais, Unidades e Contato) em Next.js e configuração das coleções e painel administrativo do Strapi CMS.
2. **Desenvolvimento da Camada de Migração (Java)**: Criação dos scripts/aplicação Java Spring Boot responsáveis por ler o banco de dados legados do Yii/PHP e importá-los formatados para a API do Strapi.
3. **Migração de Conteúdo Legado**:
   - Mapeamento e extração de dados do site Yii legado.
   - Importação automatizada/assistida de: **notícias antigas**, **arquivos e editais**, **galerias de fotos** e históricos institucionais para o novo Strapi CMS.
   - Otimização automática do formato de imagens antigas (conversão para formatos modernos como WebP/AVIF).
4. **Treinamento e Capacitação**:
   - Sessão de treinamento prático de **4 horas** (dividida em até duas chamadas online) para a equipe de comunicação e TI da FIEMA sobre como gerenciar conteúdos no Strapi e disparar campanhas no Listmonk.
   - Fornecimento de documentação em formato de Guia de Operação Rápida.

---

## 4. Pré-requisitos de Início (Responsabilidades da FIEMA)

Para o cumprimento do cronograma de desenvolvimento, a FIEMA deverá disponibilizar na primeira semana de projeto:

* **Infraestrutura**: Acesso SSH temporário ao servidor de destino configurado, ou acesso ao painel do **Coolify** (com permissão de implantação via chave SSH) para o provisionamento e deploy dos containers Docker da aplicação.
* **Dados para Migração**: Dump do banco de dados antigo e/ou exportação de arquivos XML/JSON contendo as notícias, editais e caminhos das imagens legadas.
* **Domínios e Analytics**: Acesso para configuração das chaves de rastreamento do Google Analytics 4 (GA4) e redirecionamentos de DNS.

---

## 5. Limitação de Responsabilidade (Datacenter Próprio)

Dado que a aplicação será executada em infraestrutura própria de servidores da FIEMA (seja física local, nuvem contratada diretamente pela instituição ou VPS própria gerenciada pelo departamento de TI da entidade):

* A **ACDEV Consultoria** compromete-se com a entrega do código em conformidade técnica, configuração correta dos containers Docker no Coolify e estabilidade da aplicação em ambiente normal de uso.
* A **ACDEV Consultoria** **não se responsabiliza** por prejuízos, indisponibilidades de serviço ou falhas decorrentes de:
  - Quedas de fornecimento de energia elétrica no datacenter da FIEMA.
  - Interrupções ou problemas na operadora de conectividade/link de internet local da FIEMA.
  - Falhas físicas de hardware (discos rígidos, memória, processadores ou placas de rede) dos servidores da entidade.
  - Alterações não autorizadas na configuração do sistema operacional do servidor ou no painel Coolify efetuadas por técnicos internos.

---

## 6. Cronograma e Prazos (6 Meses)

O cronograma de desenvolvimento é baseado na metodologia ágil Scrum, composto por **12 Sprints de 15 dias** (2 semanas cada):

| Fase | Período | Sprints | Principais Entregas |
|---|---|---|---|
| **Fase 1: Setup & DevOps** | Mês 1 | Sprints 1 a 2 | Instalação do Coolify no servidor FIEMA, configuração do banco de dados, setup do Strapi CMS e Listmonk. Configuração da arquitetura base do Next.js. |
| **Fase 2: Frontend & Templates** | Mês 2 | Sprints 3 a 4 | Tradução dos designs visuais aprovados em código Next.js responsivo e criação de todas as estruturas de páginas do site público. |
| **Fase 3: Backend de Migração** | Mês 3 | Sprints 5 a 6 | Desenvolvimento da aplicação Java (Spring Boot) para extração de dados e mapeamento das tabelas do site legado. |
| **Fase 4: Importação & Integração** | Mês 4 | Sprints 7 a 8 | Execução da migração das notícias, editais e fotos do banco de dados antigo para o Strapi. Conexão do Next.js às APIs do Strapi para exibir o conteúdo migrado. |
| **Fase 5: Métricas & Analytics** | Mês 5 | Sprint 9 | Conexão do Google Analytics (GA4) e setup de dashboards no Grafana. |
| **Fase 5.5: Ajustes do Cliente** | Mês 5 | Sprint 10 | **Sprint de Ajustes do Cliente**: Ciclo inteiramente dedicado a melhorias visuais, refinamento de fluxos, ajustes estéticos e alterações pontuais sugeridas pela FIEMA após as primeiras homologações. |
| **Fase 6: Homologação & Treinamento** | Mês 6 | Sprints 11 a 12 | Testes de aceitação com o cliente (UAT), treinamento de operação do Strapi e Listmonk, homologação e publicação final. |

---

## 7. Investimento e Condições Financeiras

Para o desenvolvimento integral do escopo proposto e a entrega das aplicações funcionando em produção, estabelece-se o valor de:

* **Investimento Total do Projeto:** **R$ 80.000,00 (oitenta mil reais)**.

### Cronograma de Faturamento (3 Parcelas):
Os pagamentos serão efetuados via transferência bancária ou PIX, divididos nos seguintes marcos de entrega física:

1. **Parcela 1 — 30% (R$ 24.000,00)**: Faturada e devida ao **final da Sprint 2** (Mês 1), após o setup inicial da infraestrutura de servidores (Coolify instalado e rodando com Strapi e Listmonk ativos) e validação da estrutura Next.js.
2. **Parcela 2 — 30% (R$ 24.000,00)**: Faturada e devida ao **final da Sprint 4** (Mês 2), após a conclusão e homologação das telas e templates do Frontend (Next.js) em ambiente de homologação.
3. **Parcela 3 (Entrega Final) — 40% (R$ 32.000,00)**: Faturada e devida na **homologação e entrega final do projeto** (final da Sprint 12), com o portal publicado no domínio definitivo, migração concluída, equipe treinada e observabilidade operacional ativa.

---

## 8. Manutenção e Suporte Pós-Entrega

Após o encerramento do desenvolvimento e a publicação definitiva do portal, inicia-se o período de manutenção:

* **Valor Mensal de Manutenção:** **R$ 250,00 / mês**.
* **Escopo do Suporte Mensal:**
  - Monitoramento preventivo de saúde da aplicação no Grafana.
  - Verificação de rotinas de backup do banco de dados (Strapi, Listmonk e logs de integração).
  - Aplicação de patches de segurança críticos e atualizações de dependências das ferramentas (Next.js, Strapi, Spring Boot e Coolify).
  - Restabelecimento do serviço em caso de travamentos de software locais.

---

## 9. Aceite da Proposta

Para formalizar o início dos trabalhos sob as condições técnicas e comerciais estipuladas nesta proposta comercial, assinale a data e firme as assinaturas digitais:

São Luís - MA, ______ de ________________ de 2026.

__________________________________________________
**Federação das Indústrias do Estado do Maranhão (FIEMA)**  
Representante Técnico / Legal

__________________________________________________
**ACDEV Consultoria**  
André Felipe Carvalho Pinheiro
