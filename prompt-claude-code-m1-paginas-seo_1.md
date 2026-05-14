# Prompt — Claude Code: Criar 5 Páginas SEO para M1 Service Dedetizadora

## Contexto do projeto

Site estático em HTML/CSS/JS puro da empresa **M1 Service Dedetizadora**, sediada em Taguatinga Centro, Brasília/DF. O site já possui as seguintes páginas (NÃO altere nenhuma delas):

- `index.html` — página inicial
- `servicos.html` — página de serviços (**intocável**, recebe tráfego pago do Google Ads)
- `pragas.html` — página de pragas
- `blog.html` — blog com posts expansíveis
- `contato.html` — página de contato

## Missão

Criar **5 novas páginas HTML** com foco em SEO orgânico, seguindo rigorosamente o padrão visual e técnico do site existente.

---

## Padrão técnico obrigatório (extraído dos arquivos existentes)

### Head — copiar exatamente este bloco em todas as páginas:

```html
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-MCC79LK7');</script>
<!-- End Google Tag Manager -->
```

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=AW-18142747480"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'AW-18142747480');
</script>
```

### Body — logo após `<body>`, copiar exatamente:

```html
<!-- Google Tag Manager (noscript) -->
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-MCC79LK7"
height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
<!-- End Google Tag Manager (noscript) -->
```

### Detecção WebP — copiar no `<head>`:

```html
<script>(function(){var i=new Image();i.onload=function(){if(i.width>0&&i.height>0)document.documentElement.classList.add('webp')};i.src='data:image/webp;base64,UklGRiIAAABXRUJQVlA4IBYAAAAwAQCdASoBAAEADsD+JaQAA3AAAAAA'})();</script>
```

### CSS Variables (`:root`) — usar sempre:

```css
:root {
  --green: #2E7D32;
  --green-dark: #1B5E20;
  --green-light: #4CAF50;
  --green-xlight: #E8F5E9;
  --white: #FFFFFF;
  --gray: #555555;
  --gray-light: #F5F5F5;
  --text-dark: #1A1A1A;
  --text-mid: #444444;
}
```

### Fontes:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@800;900&family=Open+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

### Navegação — usar exatamente este nav em todas as páginas:

```html
<nav id="main-nav">
  <div class="nav-inner">
    <a href="/" class="logo">
      <img src="/assets/images/logo.png" alt="Logotipo M1 Service Dedetizadora" width="140" loading="eager">
    </a>
    <button class="hamburger" id="hamburger" aria-label="Abrir menu de navegacao"><span></span><span></span><span></span></button>
    <ul class="nav-links" id="nav-links">
      <li><a href="/">Inicio</a></li>
      <li><a href="/servicos/">Serviços</a></li>
      <li><a href="/pragas/">Pragas</a></li>
      <li><a href="/blog/">Blog</a></li>
      <li><a href="/contato/">Contato</a></li>
      <li><a href="https://wa.me/5561993263868?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20solicitar%20um%20or%C3%A7amento." class="nav-cta" target="_blank" rel="noopener noreferrer">Solicitar Orçamento</a></li>
    </ul>
  </div>
</nav>
```

Marcar o link da página atual com `class="active"`.

### Footer — usar o mesmo footer do `blog.html` em todas as páginas.

### WhatsApp flutuante — usar o mesmo bloco `.wa-float` do `blog.html`.

### JS mínimo obrigatório no final de cada página:

```javascript
const nav = document.getElementById('main-nav');
window.addEventListener('scroll', () => nav.classList.toggle('scrolled', window.scrollY > 20));
const hbg = document.getElementById('hamburger');
const navLinks = document.getElementById('nav-links');
hbg.addEventListener('click', () => { hbg.classList.toggle('open'); navLinks.classList.toggle('open'); });
const observer = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => { if (e.isIntersecting) { setTimeout(() => e.target.classList.add('visible'), i * 80); observer.unobserve(e.target); } });
}, { threshold: 0.1 });
document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));
var anoEl = document.getElementById('ano-copy'); if(anoEl) anoEl.textContent = new Date().getFullYear();
```

### Schema JSON-LD — usar este bloco base em todas as páginas, ajustando `@type` e campos conforme o conteúdo:

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "M1 Service Dedetizadora",
  "description": "Empresa de controle de pragas com 10 anos de experiência, atendendo todo o Distrito Federal.",
  "telephone": "+55-61-99326-3868",
  "email": "M1serviceDedetizadora@gmail.com",
  "url": "https://www.m1dedetizadora.com.br",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Quadra C12, Edifício São Paulo",
    "addressLocality": "Taguatinga",
    "addressRegion": "DF",
    "postalCode": "72015-600",
    "addressCountry": "BR"
  },
  "areaServed": ["Taguatinga","Ceilândia","Samambaia","Águas Claras","Vicente Pires","Riacho Fundo","Brasília","Distrito Federal"],
  "openingHours": ["Mo-Sa 08:00-18:00"],
  "priceRange": "$$",
  "sameAs": [
    "https://instagram.com/M1_service_Dedetização",
    "https://maps.app.goo.gl/NqzLFTEmuMpHVHU47"
  ]
}
```

---

## Hero interno padrão (para todas as páginas novas)

Usar o padrão `.hero-int` do `blog.html`:

```html
<div class="hero-int">
  <div class="hero-int-inner">
    <nav class="breadcrumb" aria-label="Caminho de navegacao">
      <a href="/">Inicio</a><span>/</span><a href="[pai]">[Pai]</a><span>/</span><span>[Título da página]</span>
    </nav>
    <h1>[Título H1 com keyword principal]</h1>
    <p>[Subtítulo descritivo, 1–2 frases]</p>
  </div>
</div>
```

Background: `linear-gradient(rgba(0,0,0,0.45),rgba(0,0,0,0.45)), url('/assets/images/hero-[nome].png') center/cover no-repeat`

---

## Informações da empresa (usar em todos os conteúdos)

- **Nome:** M1 Service Dedetizadora
- **Telefone/WhatsApp:** (61) 9 9326-3868 → `https://wa.me/5561993263868`
- **E-mail:** M1serviceDedetizadora@gmail.com
- **Endereço:** Quadra C12, Edifício São Paulo, Taguatinga Centro, Brasília/DF
- **Horário:** Segunda a Sábado, 8h às 18h
- **Experiência:** 10 anos no mercado
- **Clientes atendidos:** mais de 1.000
- **Garantia:** 30 dias em todos os serviços
- **Atendimento emergencial:** sim, inclusive fora do horário
- **Área de atendimento:** todo o Distrito Federal
- **Serviços:** dedetização (baratas, aranhas, escorpiões), desratização, descupinização (cupim de madeira e solo), controle de pombos, limpeza de caixa d'água
- **Atende:** residencial, comercial, academia, indústria
- **Produtos:** seguros para pets e crianças após aplicação
- **Instagram:** @M1_service_Dedetização

---

## As 5 páginas a criar

---

### PÁGINA 1 — `dedetizacao-baratas-brasilia/index.html`

**Objetivo:** Página de serviço específico para dedetização de baratas. Alta intenção de contratar.

**URL canônica:** `https://www.m1dedetizadora.com.br/dedetizacao-baratas-brasilia/`

**`<title>`:** `Dedetização de Baratas em Brasília/DF | M1 Service — Garantia de 30 Dias`

**`<meta description>`:** `Elimine baratas de vez em Brasília e no DF. M1 Service Dedetizadora: 10 anos de experiência, produtos seguros para pets e crianças, garantia de 30 dias. Orçamento grátis pelo WhatsApp.`

**Keywords principais:** dedetização de baratas em Brasília, dedetização baratas DF, dedetizadora de baratas Taguatinga, como eliminar baratas profissionalmente

**Nav ativo:** nenhum (página de serviço específico)

**Breadcrumb:** Inicio / Serviços / Dedetização de Baratas

**H1:** `Dedetização de Baratas em Brasília e DF`

**Estrutura de seções:**

1. **Hero** com H1 e subtítulo: "Elimine baratas de vez com método profissional, produtos seguros e garantia de 30 dias."

2. **Por que baratas são um problema sério** — seção com ícones/cards explicando: riscos à saúde (contaminação de alimentos, alergias, leptospirose), reprodução acelerada (uma fêmea gera até 300 filhotes/ano), dificuldade de eliminar sozinho (resistência a produtos comuns de mercado).

3. **Como funciona o serviço de dedetização de baratas da M1** — passo a passo visual:
   - Vistoria e identificação dos focos
   - Escolha do produto adequado para cada espécie (barata alemã, barata americana, barata de esgoto)
   - Aplicação profissional (gel, spray, pó) com equipamentos específicos
   - Orientações pós-aplicação e garantia de 30 dias

4. **Onde atuamos** — lista de regiões: Taguatinga, Ceilândia, Águas Claras, Samambaia, Guará, Vicente Pires, Riacho Fundo, Gama, Sobradinho, Planaltina, todo o DF.

5. **Dúvidas frequentes (FAQ)** — com `FAQPage` schema:
   - "Os produtos são seguros para crianças e pets?" → Sim, após a secagem completa (2 a 4 horas de ventilação).
   - "Preciso sair de casa durante o serviço?" → Recomendado ficar fora por 2 a 4 horas.
   - "A dedetização elimina todos os tipos de barata?" → Sim, incluindo barata alemã, americana e de esgoto.
   - "Quanto tempo dura o efeito?" → Com garantia de 30 dias. Manutenção preventiva recomendada a cada 6 meses.
   - "Atendem apartamentos?" → Sim, residencial e comercial.

6. **CTA final** — verde escuro, texto: "Chame agora e receba seu orçamento gratuito em minutos" + botão WhatsApp.

**Schema adicional:** `FAQPage` para as perguntas frequentes.

---

### PÁGINA 2 — `blog/como-acabar-com-baratas/index.html`

**Objetivo:** Post educativo longo que captura buscas informativas ("como acabar com baratas", "veneno caseiro para barata", "o que mata barata") e converte ao final para o serviço profissional.

**URL canônica:** `https://www.m1dedetizadora.com.br/blog/como-acabar-com-baratas/`

**`<title>`:** `Como Acabar com Baratas de Vez em Casa: Guia Completo 2025`

**`<meta description>`:** `Descubra o que realmente funciona para eliminar baratas em casa. Dicas práticas, o que evitar e quando chamar um profissional. Guia completo da M1 Service Dedetizadora.`

**Keywords principais:** como acabar com baratas, como eliminar baratas em casa, o que mata barata, veneno para barata, como combater baratas

**Nav ativo:** `blog`

**Breadcrumb:** Inicio / Blog / Como Acabar com Baratas

**H1:** `Como Acabar com Baratas de Vez em Casa: o Guia Completo`

**Estrutura — artigo longo (mínimo 800 palavras de conteúdo real):**

Use o layout de artigo de blog com sidebar ou coluna única larga (max-width 800px centralizado), com tipografia confortável para leitura (Open Sans 16px, line-height 1.75).

Seções do artigo (usar `<h2>` e `<h3>` dentro do conteúdo):

1. **Por que é tão difícil acabar com baratas sozinho** — explicar resistência a produtos comuns, ciclo de vida rápido, hábitos noturnos e escondidos.

2. **O que realmente funciona (e o que não funciona)**
   - Gel isca profissional (funciona — mas o do mercado é fraco demais)
   - Pó inseticida em frestas (funciona com produto certo e aplicação correta)
   - Barata-boa, folha de louro, bicarbonato, acetona (não funcionam — desmistificar com empatia, sem ridicularizar quem tenta)
   - Inseticidas em spray (efeito imediato mas sem residual, não resolve a raiz)

3. **Espécies mais comuns no DF e como identificar**
   - Barata alemã (pequena, cozinha, resistente)
   - Barata americana (grande, esgoto, voa às vezes)
   - Barata de esgoto (vem de canos e ralos)

4. **5 medidas preventivas que realmente ajudam**
   - Vedar frestas e ralos
   - Guardar alimentos em potes fechados
   - Não deixar louça suja à noite
   - Limpar atrás da geladeira e fogão mensalmente
   - Descartar lixo orgânico diariamente

5. **Quando o problema está além do que você pode resolver sozinho** — transição suave para o serviço profissional: infestação visível de dia, baratas em vários cômodos, problema recorrente.

6. **Como funciona uma dedetização profissional** — breve (redireciona para página 1).

7. **CTA integrado ao conteúdo** — bloco verde ao final: "Problema persistindo? A M1 Service resolve com garantia de 30 dias." + botão WhatsApp.

**Schema:** `Article` com `author` (M1 Service Dedetizadora), `datePublished`, `dateModified`.

Incluir também CTAs internos ao longo do artigo (não invasivos, no estilo `.post-cta` do `blog.html`).

---

### PÁGINA 3 — `dedetizacao-aguas-claras/index.html`

**Objetivo:** Página local para Águas Claras — o Search Console mostra 3 impressões orgânicas para "dedetização águas claras" sem nenhuma página dedicada ao termo.

**URL canônica:** `https://www.m1dedetizadora.com.br/dedetizacao-aguas-claras/`

**`<title>`:** `Dedetização em Águas Claras e Taguatinga | M1 Service Dedetizadora`

**`<meta description>`:** `Dedetizadora em Águas Claras/DF. A M1 Service atende toda a região com 10 anos de experiência, garantia de 30 dias e orçamento gratuito. Ligue agora: (61) 9 9326-3868.`

**Keywords principais:** dedetização Águas Claras, dedetizadora Águas Claras DF, controle de pragas Águas Claras, dedetização Taguatinga Águas Claras

**Nav ativo:** nenhum

**Breadcrumb:** Inicio / Dedetização em Águas Claras

**H1:** `Dedetização em Águas Claras — M1 Service Dedetizadora`

**Estrutura de seções:**

1. **Hero** — "Atendemos Águas Claras e toda a região com rapidez e garantia."

2. **Por que Águas Claras precisa de atenção especial** — contexto local: região densa com muitos condomínios verticais, alta circulação de pessoas, presença de comércio intenso — fatores que facilitam a proliferação de pragas entre unidades.

3. **Serviços disponíveis em Águas Claras** — grid de cards com: Dedetização (baratas, aranhas, escorpiões), Desratização, Descupinização, Controle de Pombos, Limpeza de Caixa d'Água. Cada card com ícone, nome e link para `/servicos/`.

4. **Atendemos todo o entorno** — mapa ou lista visual de bairros/regiões: Águas Claras, Taguatinga Sul, Taguatinga Norte, Taguatinga Centro, Vicente Pires, Arniqueira, Park Way (nas proximidades), Samambaia.

5. **Diferenciais da M1 em Águas Claras**:
   - Tempo de deslocamento rápido (base em Taguatinga Centro, a minutos de Águas Claras)
   - Atendimento a condomínios e apartamentos
   - Produtos aprovados pela ANVISA, seguros para pets e crianças
   - Garantia de 30 dias
   - Atendimento emergencial

6. **Depoimento fictício verossímil** (não usar nome real, apenas "Moradora de Águas Claras Sul" etc.) — 2 a 3 depoimentos curtos no estilo testemunho.

7. **CTA** — botão WhatsApp + telefone clicável.

**Schema:** `LocalBusiness` com foco em `areaServed: ["Águas Claras", "Taguatinga"]`.

---

### PÁGINA 4 — `blog/quanto-custa-dedetizacao-brasilia/index.html`

**Objetivo:** Post sobre preços — quem busca "quanto custa dedetização" está prestes a contratar. Alta intenção de compra.

**URL canônica:** `https://www.m1dedetizadora.com.br/blog/quanto-custa-dedetizacao-brasilia/`

**`<title>`:** `Quanto Custa uma Dedetização em Brasília? Tabela de Preços 2025`

**`<meta description>`:** `Veja as faixas de preço para dedetização em Brasília e no DF em 2025. Valores por tipo de imóvel, serviço e tamanho. Orçamento gratuito e sem compromisso.`

**Keywords principais:** quanto custa dedetização Brasília, preço dedetização DF, valor dedetização apartamento Brasília, dedetização barata Taguatinga

**Nav ativo:** `blog`

**Breadcrumb:** Inicio / Blog / Quanto Custa Dedetização

**H1:** `Quanto Custa uma Dedetização em Brasília? Tabela de Preços 2025`

**Estrutura — artigo + tabela de preços:**

Layout de artigo (coluna única, max-width 800px).

1. **Introdução** — explicar que o preço varia por tipo de imóvel, serviço e nível de infestação. Não existem preços fixos no mercado, mas há faixas.

2. **Tabela de faixas de preço por tipo de imóvel** — tabela HTML estilizada:

| Tipo de imóvel | Serviço | Faixa de preço estimada |
|---|---|---|
| Apartamento 1–2 quartos | Dedetização geral | R$ 150 – R$ 250 |
| Apartamento 3+ quartos | Dedetização geral | R$ 200 – R$ 350 |
| Casa até 150 m² | Dedetização geral | R$ 200 – R$ 400 |
| Casa acima de 150 m² | Dedetização geral | R$ 300 – R$ 600 |
| Comércio (loja/escritório) | Dedetização geral | A partir de R$ 250 |
| Qualquer imóvel | Descupinização | A partir de R$ 350 |
| Qualquer imóvel | Desratização | A partir de R$ 200 |
| Qualquer imóvel | Limpeza de caixa d'água | A partir de R$ 180 |

Nota abaixo da tabela: *"Valores estimados para referência. O orçamento final depende do tamanho do imóvel, nível de infestação e serviços combinados. Solicite um orçamento gratuito sem compromisso."*

3. **O que está incluso no preço de uma dedetização profissional** — lista: vistoria, mão de obra, produtos, equipamentos, orientações pós-serviço, garantia de 30 dias.

4. **O que influencia o preço** — nível de infestação, tamanho do imóvel, tipo de praga, frequência (preventivo sai mais barato que corretivo).

5. **Vale a pena tentar resolver sozinho antes?** — custo comparativo: produto de mercado (R$ 20–80, sem garantia, efeito temporário) vs. serviço profissional (resultado duradouro, garantia, segurança). Transição natural para o CTA.

6. **CTA** — "Peça seu orçamento gratuito agora. Sem compromisso, resposta em minutos." + botão WhatsApp.

**Schema:** `Article` + considerar `PriceSpecification` se aplicável.

---

### PÁGINA 5 — `dedetizacao-cupim-brasilia/index.html`

**Objetivo:** Página de serviço específico para descupinização — aparece duas vezes no AnswerThePublic, é um serviço de ticket alto.

**URL canônica:** `https://www.m1dedetizadora.com.br/dedetizacao-cupim-brasilia/`

**`<title>`:** `Descupinização em Brasília e DF | M1 Service — Cupim de Madeira e Solo`

**`<meta description>`:** `Elimine cupins em Brasília com a M1 Service Dedetizadora. Tratamos cupim de madeira e solo com produtos eficazes e garantia de 30 dias. Orçamento gratuito.`

**Keywords principais:** descupinização Brasília, dedetização cupim DF, cupim de madeira Taguatinga, cupim de solo DF, eliminar cupim Brasília

**Nav ativo:** nenhum

**Breadcrumb:** Inicio / Serviços / Descupinização

**H1:** `Descupinização em Brasília e DF — Cupim de Madeira e Solo`

**Estrutura de seções:**

1. **Hero** — "Cupins são silenciosos e destrutivos. Aja antes que o dano seja irreversível."

2. **Por que o cupim é diferente de outras pragas** — destroem madeira, papel e tecidos de dentro para fora sem deixar rastros visíveis. Uma colônia pode ter milhões de indivíduos. Em Brasília, o clima quente e seco do cerrado favorece tanto o cupim de madeira seca quanto o subterrâneo.

3. **Tipos de cupim que tratamos**:
   - **Cupim de madeira seca** — ataca móveis, portas, janelas, forros, batentes. Sinais: serragem fina (pó de madeira) e galeria vazia ao bater.
   - **Cupim subterrâneo (de solo)** — vive no solo e ataca a estrutura do imóvel por baixo. Mais agressivo e difícil de eliminar.
   - **Cupim de madeira úmida** — menos comum no DF, associado a umidade e infiltração.

4. **Como funciona o tratamento da M1**:
   - Vistoria e identificação da espécie e extensão do dano
   - Cupim de madeira seca: injeção de produto nas galerias + tratamento superficial
   - Cupim subterrâneo: barreira química no solo (injeção de inseticida no perímetro)
   - Garantia de 30 dias + orientações de prevenção

5. **Sinais de infestação** — lista visual: pó de madeira (serragem) em cantos, bolhas ou manchas escuras em rodapés, madeira que soa oca ao bater, alados (cupins com asas) voando em enxame.

6. **FAQ**:
   - "Preciso retirar móveis para o tratamento?" → Depende do tipo. A equipe orienta no dia.
   - "O produto danifica a madeira tratada?" → Não. O produto é aplicado nas galerias e no solo, não na superfície.
   - "Quanto tempo leva o tratamento?" → De 2 a 6 horas dependendo do tamanho do imóvel.

7. **CTA final** — "Suspeita de cupim? Não espere o dano se agravar." + botão WhatsApp.

**Schema:** `FAQPage` + `LocalBusiness`.

---

## Regras gerais para todas as páginas

1. **Não altere nenhum arquivo existente** — apenas crie os novos.
2. **Estrutura de pastas:** criar cada página como `nome-da-pagina/index.html` para URLs limpas (sem `.html` na URL).
3. **Links internos:** todas as páginas devem linkar entre si quando relevante (ex: página de baratas linka para o artigo do blog, artigo de preços linka para páginas de serviço).
4. **CTA WhatsApp:** usar sempre o link `https://wa.me/5561993263868?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20solicitar%20um%20or%C3%A7amento.` com `target="_blank" rel="noopener noreferrer"`.
5. **Imagens hero:** referenciar como `/assets/images/hero-[slug].png` com fallback WebP via `html.webp` class — o time vai adicionar as imagens depois.
6. **Responsividade:** seguir os mesmos breakpoints do site (`@media (max-width: 768px)`).
7. **Acessibilidade:** `alt` em todas as imagens, `aria-label` em links de ícone, `lang="pt-BR"` no `<html>`.
8. **Ano do copyright** no footer: usar `<span id="ano-copy"></span>` atualizado via JS.
9. **Conteúdo:** escrever em português brasileiro, tom profissional mas acessível, sem jargão excessivo. Mínimo 400 palavras de conteúdo real por página de serviço, mínimo 800 palavras para os artigos de blog.
10. **Não inventar certificações, registros ANVISA ou alvarás** — a empresa ainda não possui esses documentos.
