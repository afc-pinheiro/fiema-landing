# Proposta Comercial — Novo Portal Institucional FIEMA

**Cliente:** Federação das Indústrias do Estado do Maranhão (FIEMA)  
**Proponente:** ACDEV Consultoria (André Felipe Carvalho Pinheiro)  
**Website:** [www.acdev.com.br](https://www.acdev.com.br/)  
**Data de Emissão:** 06 de Julho de 2026  
**Validade da Proposta:** 15 dias  

---

## 1. Objetivo do Projeto

Esta proposta visa à migração e ao desenvolvimento do **Novo Portal Institucional da FIEMA**, evoluindo a arquitetura atual baseada em sistemas legados para uma infraestrutura moderna de alta performance, focada em otimização de velocidade (Core Web Vitals), conversão de leads, acessibilidade e autonomia operacional para a equipe interna. 

O projeto terá como referência estética e de navegação o **modelo visual pré-aprovado**, disponível em:  
[www.acdev.com.br/fiema](https://www.acdev.com.br/fiema)

---

## 2. Escopo de Serviços e Migração de Conteúdo

O desenvolvimento engloba as seguintes atividades, explicadas de forma executiva e funcional:

1. **Desenvolvimento do Portal Público**: Criação de todas as páginas públicas (Home, Sobre, Serviços, Notícias, Editais, Unidades e Contato) com foco em velocidade de carregamento, navegação mobile intuitiva e indexação no Google.
2. **Painel de Controle e Autonomia (CMS)**: Configuração de um painel administrativo protegido (Strapi) para que a equipe de comunicação e marketing da FIEMA gerencie, edite e publique conteúdos sem necessidade de suporte técnico.
3. **Central de Newsletter Open Source**: Implantação de um sistema próprio de envio de e-mails corporativos (Listmonk) integrado ao site público para capturar novos inscritos e disparar boletins informativos.
4. **Migração do Conteúdo Legado**:
   - Mapeamento e extração de dados do site Yii legado.
   - Importação automatizada de: **notícias antigas**, **arquivos e editais**, **galerias de fotos** e históricos institucionais para o novo sistema.
   - Otimização de imagens antigas para formatos modernos e leves de internet.
5. **Treinamento e Capacitação**:
   - Sessão de treinamento prático de **4 horas** para a equipe de TI e comunicação da FIEMA sobre a gestão do Strapi CMS e operação do sistema de e-mails Listmonk (inclui gravação em vídeo para consultas futuras).
   - Fornecimento de um Guia de Operação Rápida.

---

## 3. Pré-requisitos de Início (Responsabilidades da FIEMA)

Para o cumprimento do cronograma de desenvolvimento, a FIEMA deverá disponibilizar na primeira semana de projeto:

* **Infraestrutura**: Acesso SSH temporário ao servidor de destino configurado, ou acesso ao painel do **Coolify** (com permissão de implantação via chave SSH) para o provisionamento dos serviços.
* **Dados para Migração**: Cópia de segurança (dump) do banco de dados antigo e arquivos de mídia legados para a realização da migração de conteúdo.
* **Domínios e Redirecionamentos**: Acesso para configuração das chaves de rastreamento do Google Analytics 4 (GA4) e controle de DNS para publicação final.

---

## 4. Limitação de Responsabilidade (Datacenter Próprio)

Dado que a aplicação será executada em infraestrutura própria de servidores sob a responsabilidade e controle da FIEMA:

* A **ACDEV Consultoria** compromete-se com a entrega do código em conformidade técnica, configuração correta das aplicações no Coolify e estabilidade do software em ambiente normal de uso.
* A **ACDEV Consultoria** **não se responsabiliza** por prejuízos ou indisponibilidade decorrentes de:
  - Quedas de fornecimento de energia elétrica ou problemas de infraestrutura local do datacenter da FIEMA.
  - Interrupções ou oscilações na operadora de conectividade/link de internet da instituição.
  - Falhas físicas de hardware (discos rígidos, memória, etc.) dos servidores da entidade.
  - Modificações de configuração do sistema operacional do servidor feitas por técnicos internos da FIEMA.

---

## 5. Garantia, LGPD e Propriedade Intelectual

Visando à conformidade jurídica e segurança institucional da FIEMA, estabelecem-se as seguintes diretrizes:

* **Período de Garantia**: A ACDEV Consultoria fornece uma garantia técnica de **90 dias** (em conformidade com o Art. 26 do Código de Defesa do Consumidor) a contar da entrega final do projeto. Durante este período, qualquer erro ou comportamento inesperado do software (bugs) será corrigido sem custo adicional.
* **Propriedade e Licenciamento**: Após a quitação integral do projeto, a FIEMA receberá uma **licença de uso perpétua, não exclusiva, transferível para suas unidades e livre de royalties** sobre todo o código-fonte desenvolvido para o portal (Next.js, Strapi CMS e rotinas de migração em Java). A FIEMA terá total liberdade para hospedar, manter, modificar e atualizar o código internamente. A ACDEV Consultoria retém a propriedade intelectual sobre suas bibliotecas base, arquiteturas de código (boilerplates) e métodos genéricos desenvolvidos, sendo livre para reutilizá-los em outros projetos. Fica expressamente proibido à FIEMA revender, sublicenciar ou comercializar o código-fonte desenvolvido para terceiros externos.
* **Conformidade com a LGPD**: Os formulários de contato e assinatura de newsletter serão desenvolvidos seguindo as regras da Lei Geral de Proteção de Dados (Lei nº 13.709/2018), incluindo caixas de seleção de consentimento explícito e links diretos para descadastro automatizado (opt-out) nas newsletters enviadas.

---

## 6. Detalhamento Técnico da Solução (Para Equipe de TI)

Esta seção detalha a arquitetura técnica proposta para a sustentação do portal:

* **Frontend (Next.js)**: Utilização do Next.js para renderização rápida, otimização de imagens em tempo real e estrutura compatível com acessibilidade digital (WCAG).
* **CMS (Strapi)**: Sistema de gerenciamento de conteúdo headless (desacoplado), rodando sob Node.js, com banco de dados independente e API REST/GraphQL.
* **Backend de Migração (Java + Spring Boot)**: Microsserviço robusto desenvolvido em Java para atuar temporariamente como a ferramenta de extração, transformação e carga (ETL), garantindo a migração segura dos dados legados para a nova estrutura.
* **Plataforma de Newsletter (Listmonk)**: Aplicação autohospedada escrita em Go, conectada ao banco de dados PostgreSQL. Utilizada para gerenciar contatos e disparar campanhas por e-mail com interface visual traduzida em português (PT-BR).
* **PaaS (Coolify) & Docker**: Plataforma de gerenciamento de containers instalada no servidor da FIEMA que orquestra Next.js, Strapi, Java, Listmonk e bancos de dados em containers Docker isolados e seguros.
* **Telemetria & Observabilidade (Grafana)**: Dashboards para visualização de logs, latência de requisições, métricas de consumo de CPU/Memória e integridade das aplicações.
* **Google Analytics (GA4)**: Integração do frontend com ferramentas de análise de comportamento do usuário.

---

## 7. Cronograma e Prazos (6 Meses)

O cronograma de desenvolvimento é baseado na metodologia ágil Scrum, composto por **12 Sprints de 15 dias** (2 semanas cada):

| Fase | Período | Sprints | Detalhamento das Entregas e Marcos de Newsletter |
|---|---|---|---|
| **Fase 1: Setup & DevOps** | Mês 1 | Sprints 1 a 2 | Instalação do Coolify no servidor FIEMA, setup dos bancos de dados, do Strapi CMS e **instalação inicial da infraestrutura do Listmonk**. Estruturação base do Next.js. |
| **Fase 2: Frontend & Templates** | Mês 2 | Sprints 3 a 4 | Codificação Next.js das páginas públicas baseadas no modelo homologado, **incluindo o design visual e comportamento dos formulários de newsletter no frontend**. |
| **Fase 3: Backend de Migração** | Mês 3 | Sprints 5 a 6 | Desenvolvimento do microsserviço Java (Spring Boot) para extração de dados e mapeamento das tabelas do site legado. |
| **Fase 4: Importação & Integração** | Mês 4 | Sprints 7 a 8 | Execução da migração de dados antigos para o Strapi. **Integração completa dos formulários de newsletter do Next.js com a API do Listmonk para cadastro automático de leads**. |
| **Fase 5: Métricas & Analytics** | Mês 5 | Sprint 9 | Conexão do Google Analytics (GA4), setup de dashboards no Grafana e **testes de disparo de campanhas, layouts de e-mail e fluxos de descadastro no Listmonk**. |
| **Fase 5.5: Ajustes do Cliente** | Mês 5 | Sprint 10 | **Sprint de Ajustes do Cliente**: Ciclo de 15 dias dedicado inteiramente a melhorias visuais, refinamento de fluxos, ajustes estéticos e alterações pontuais sugeridas pela FIEMA após as primeiras homologações do portal. |
| **Fase 6: Homologação & Treinamento** | Mês 6 | Sprints 11 a 12 | Testes de aceitação (UAT), **treinamento prático de operação do Strapi CMS e da ferramenta de envio de newsletter Listmonk**, homologação e publicação final. |

---

## 8. Investimento e Condições Financeiras

Para o desenvolvimento integral do escopo proposto e a entrega das aplicações funcionando em produção, estabelece-se o valor de:

* **Investimento Total do Projeto:** **R$ 80.000,00 (oitenta mil reais)**.

### Cronograma de Faturamento (3 Parcelas):
Os pagamentos serão efetuados via transferência bancária ou PIX, divididos nos seguintes marcos de entrega física:

1. **Parcela 1 — 30% (R$ 24.000,00)**: Faturada e devida ao **final da Sprint 2** (Mês 1), após o setup inicial da infraestrutura de servidores (Coolify instalado e rodando com Strapi e Listmonk ativos) e validação da estrutura Next.js.
2. **Parcela 2 — 30% (R$ 24.000,00)**: Faturada e devida ao **final da Sprint 4** (Mês 2), após a conclusão e homologação das telas e templates do Frontend (Next.js) em ambiente de homologação.
3. **Parcela 3 (Entrega Final) — 40% (R$ 32.000,00)**: Faturada e devida na **homologação e entrega final do projeto** (final da Sprint 12), com o portal publicado no domínio definitivo, migração concluída, equipe treinada e observabilidade operacional ativa.

---

## 9. Manutenção e Suporte Pós-Entrega

Após o encerramento do desenvolvimento e a publicação definitiva do portal, inicia-se o período de manutenção:

* **Valor Mensal de Manutenção:** **R$ 250,00 / mês**.
* **Escopo do Suporte Mensal:**
  - Monitoramento preventivo de saúde da aplicação no Grafana.
  - Verificação de rotinas de backup do banco de dados (Strapi, Listmonk e logs de integração).
  - Aplicação de patches de segurança críticos e atualizações de dependências das ferramentas (Next.js, Strapi, Spring Boot e Coolify).
  - Restabelecimento do serviço em caso de travamentos de software locais.

---

## 10. Aceite da Proposta

Para formalizar o início dos trabalhos sob as condições técnicas e comerciais estipuladas nesta proposta comercial, assinale a data e firme as assinaturas digitais:

São Luís - MA, ______ de ________________ de 2026.

__________________________________________________
**Federação das Indústrias do Estado do Maranhão (FIEMA)**  
Representante Técnico / Legal

__________________________________________________
**ACDEV Consultoria**  
André Felipe Carvalho Pinheiro
