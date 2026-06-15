# Plano de Redesign — FIEMA Landing Page

**Cliente:** FIEMA (Federação das Indústrias do Estado do Maranhão)  
**Escopo:** Landing page do FIEMA (foco inicial, excluindo SESI/SENAI/IEL/CIEMA)  
**Stack proposta:** HTML + CSS + JS vanilla (mockup) → migrar para Next.js + Strapi (produção)  
**Data do planejamento:** 2026-06-15

---

## Problema Central

O site atual esconde seus próprios serviços. Tem ~25 serviços disponíveis, mas expõe apenas 3 na homepage. O restante está enterrado em mega menus com taxonomia interna confusa ("Competitividade / Expo Indústria Maranhão").

---

## Conceito

**"Encontre o que precisa em 3 segundos"**

Segmentação imediata do usuário em dois perfis principais:
- **Para Você** — pessoa física buscando cursos, seletivos, benefícios, saúde
- **Para Sua Empresa** — pessoa jurídica buscando competitividade, crédito, certificações, sindicatos

---

## Arquitetura da Página

### 1. Header
- Logo FIEMA (esquerda)
- Navegação enxuta: Sobre | Serviços | Notícias | Contato
- Botão de busca
- Links das entidades irmãs como pills discretas (SESI · SENAI · IEL · CIEMA)
- Sticky no scroll

### 2. Hero
- Título institucional forte (sem carrossel)
- Subtítulo com proposta de valor do FIEMA
- **Dois CTAs principais lado a lado:**
  - `→ Para Você` (azul escuro, cheio)
  - `→ Para Sua Empresa` (contorno/ghost)
- Imagem de fundo: `/images/home.png` ou banner existente

### 3. Segmentação "Para Você | Para Sua Empresa"
Seção com toggle/tabs que filtra a grade de serviços por público:

**Para Você:**
- Cursos e Capacitação (`/cursos/agenda-de-cursos`)
- Processos Seletivos - Alunos
- Portal do Aluno
- Hub de Inovação em Saúde
- Eventos (`/eventos/agenda-de-eventos`)
- Benefícios ao Associado

**Para Sua Empresa:**
- Acesso ao Crédito
- Certificado Digital
- Centro Internacional de Negócios (Comércio Exterior)
- Declaração de Funcionamento
- Programa de Desenvolvimento de Fornecedores
- Expo Indústria Maranhão
- Guia Industrial e Empresarial
- Programas de Apoio à Competitividade
- Sindicato Legal / Relações Sindicais
- Centro Judiciário de Solução de Conflitos
- Compliance

### 4. Grade de Serviços (todos visíveis)
- Layout: grid responsivo (3 colunas desktop, 2 tablet, 1 mobile)
- Cada card: ícone + nome do serviço + categoria discreta + link direto
- Filtro visual por categoria (pills clicáveis)
- Sem paginação — tudo visível de uma vez

### 5. Entidades do Sistema
- 4 cards grandes: SESI | SENAI | IEL | CIEMA
- Logo + descrição curta (1 linha) + CTA "Acessar"
- Layout horizontal no desktop, 2x2 no mobile

### 6. Notícias
- 3 cards recentes (não dominante visualmente)
- Foto + título + data + link
- CTA "Ver todas as notícias"

### 7. Newsletter
- Campo de e-mail + botão simples
- Copy direto: "Receba novidades do sistema FIEMA"

### 8. Footer
- Logo + redes sociais
- 4 colunas: Institucional | Serviços | Unidades | Fale Conosco
- Copyright + link de acessibilidade
- Sem duplicar todo o sitemap

---

## Identidade Visual

### Cores (extraídas do CSS original)
- Azul FIEMA/CIEMA: `rgb(22, 65, 148)` → `#164194`
- Laranja SENAI: `rgba(239, 73, 16)` → `#EF4910`
- Verde SESI: `rgba(82, 174, 50)` → `#52AE32`
- Teal IEL: `rgba(108, 194, 186)` → `#6CC2BA`
- Branco: `#FFFFFF`
- Cinza neutro: `#F5F5F5` (background sections)
- Cinza texto: `#333333`

### Tipografia
- Manter Roboto (já usada no site atual)
- Hierarquia mais clara: pesos 300/400/700

### Componentes
- Sem carrosséis
- Cards com sombra sutil (`box-shadow: 0 2px 8px rgba(0,0,0,0.08)`)
- Border-radius: 8px nos cards
- Muito mais espaço em branco
- Ícones: usar SVG inline ou Font Awesome (substituir Fontello)

---

## Responsividade

- Mobile-first
- Breakpoints: 375px / 768px / 1024px / 1280px
- Header: hamburguer menu no mobile
- Grid de serviços: 1 coluna no mobile
- Entidades: scroll horizontal no mobile

---

## Imagens

Referenciar URLs existentes do servidor FIEMA:
- Base URL: `https://www.fiema.org.br`
- Hero: `/images/home.png`
- Logos entidades: `/images/{fiema,sesi,senai,iel,ciema}.png`
- Banners disponíveis em `/uploads/banner/`
- Fotos de notícias em `/uploads/noticia/`

---

## Ordem de Execução (Mockup HTML)

1. [ ] Setup base: reset CSS, variáveis de cor, tipografia
2. [ ] Header + navegação + mobile menu
3. [ ] Hero com CTAs "Para Você / Para Sua Empresa"
4. [ ] Seção de segmentação com toggle e grid de serviços
5. [ ] Seção de entidades (SESI/SENAI/IEL/CIEMA)
6. [ ] Seção de notícias
7. [ ] Newsletter
8. [ ] Footer
9. [ ] Ajustes de responsividade mobile
10. [ ] Revisão final e polish

---

## Sugestões Adicionais (pendentes de aprovação)

- **Barra de busca de serviços** no hero — usuário digita o que precisa e filtra os cards
- **Números/stats institucionais** — ex: "X sindicatos filiados | Y empresas atendidas | Z unidades" — credibilidade
- **Botão flutuante de contato** (WhatsApp ou ouvidoria) — fixo no canto inferior direito
- **Mapa das unidades** — Balsas, Imperatriz, São Luís com cards clicáveis
- **Acessibilidade** — manter atalhos de teclado existentes, garantir contraste WCAG AA
- **Meta SEO** — tags abertas para redes sociais (OG tags)

---

## Decisões Confirmadas

- [x] Cores institucionais mantidas
- [x] Imagens referenciadas via URL existente (sem reupload)
- [x] HTML responsivo (mobile-first)
- [x] Mockup estático antes de migrar para Strapi/Next.js
- [x] Foco no FIEMA (SESI/SENAI/IEL/CIEMA como entidades secundárias)
- [x] Segmentação "Para Você | Para Sua Empresa"

## Decisões Pendentes

- [ ] Cor exata do azul FIEMA (confirmar com cliente ou extrair do CSS original)
- [ ] Lista definitiva de serviços por segmento (Para Você vs Para Sua Empresa)
- [ ] Incluir busca de serviços no hero?
- [ ] Incluir seção de stats/números institucionais?
- [ ] Botão flutuante de contato?
