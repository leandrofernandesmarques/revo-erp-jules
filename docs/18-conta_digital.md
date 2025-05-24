# Análise do Módulo Conta Digital - ERP Revo

## Estrutura Geral

O módulo "Conta Digital" do ERP Revo apresenta uma interface promocional e informativa sobre a conta digital integrada ao sistema. A página é estruturada em seções que destacam os benefícios, funcionalidades e vantagens da conta digital, com elementos visuais e textuais organizados para converter o usuário.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão do módulo Caixa, mantendo a consistência visual do sistema.

### Seção Hero (Principal)

A seção principal apresenta o título e a proposta de valor da conta digital:

**Estrutura HTML:**

```html
<div class="hero-container">
  <div class="hero-content">
    <div class="hero-logo">
      <img src="/assets/images/Revo-logo.svg" alt="Revo Logo" />
    </div>
    <h1 class="hero-title">
      Automatize a rotina financeira do seu negócio com a conta digital da Revo
    </h1>
    <p class="hero-description">
      Controle total para vender, cobrar e receber dentro do seu sistema de
      gestão. Garanta mais praticidade e autonomia para a sua rotina.
    </p>
    <a href="#" class="botao-primario botao-destaque" id="btn-abrir-conta">
      <span class="icone icone-conta"></span>
      <span class="texto">abra sua conta PJ grátis</span>
    </a>
  </div>
  <div class="hero-image">
    <img src="/assets/images/conta-digital-hero.png" alt="Conta Digital Revo" />
  </div>
</div>
```

**Estilos CSS:**

```css
.hero-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 48px 24px;
  background-color: #f0f5ff;
  border-radius: 16px;
  margin: 24px;
}

.hero-content {
  flex: 1;
  max-width: 600px;
}

.hero-logo {
  margin-bottom: 24px;
}

.hero-logo img {
  height: 40px;
  width: auto;
}

.hero-title {
  font-size: 36px;
  font-weight: 700;
  color: #333333;
  margin-bottom: 16px;
  line-height: 1.2;
}

.hero-description {
  font-size: 18px;
  color: #666666;
  margin-bottom: 32px;
  line-height: 1.5;
}

.hero-image {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-image img {
  max-width: 100%;
  height: auto;
  max-height: 400px;
}

.botao-primario {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 24px;
  border-radius: 4px;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
  text-decoration: none;
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao-destaque {
  background-color: #1652f0;
  font-size: 18px;
  padding: 16px 32px;
  border-radius: 8px;
}

.botao-destaque:hover {
  background-color: #0e3fb3;
}

.botao-destaque .icone {
  margin-right: 12px;
  font-size: 20px;
}
```

### Seção de Benefícios

A seção que apresenta os principais benefícios da conta digital:

**Estrutura HTML:**

```html
<div class="beneficios-container">
  <h2 class="secao-titulo">Uma conta em dia com os objetivos do seu negócio</h2>

  <div class="beneficios-grid">
    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-descomplique"></span>
      </div>
      <h3 class="beneficio-titulo">Descomplique a sua rotina fiscal</h3>
      <p class="beneficio-descricao">
        com as emissões e pagamentos automatizados das suas guias GNRE
      </p>
    </div>

    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-pagamento"></span>
      </div>
      <h3 class="beneficio-titulo">Link de Pagamento da Revo</h3>
      <p class="beneficio-descricao">
        Receba com cartão de crédito de forma totalmente integrada ao ERP.
        Antecipe suas vendas quando quiser.
      </p>
      <a href="#" class="beneficio-link">confira este benefício</a>
    </div>

    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-eficiencia"></span>
      </div>
      <h3 class="beneficio-titulo">Aumente a eficiência operacional</h3>
      <p class="beneficio-descricao">
        Automatize a entrada de novos pagamentos com o Buscador de Boletos e
        deixe nosso sistema comparar automaticamente seus registros com o
        extrato bancário.
      </p>
    </div>

    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-complexidade"></span>
      </div>
      <h3 class="beneficio-titulo">Reduza a complexidade</h3>
      <p class="beneficio-descricao">
        Gerencie saldo, extrato, boletos, Pix e contas a pagar em um só lugar.
        Descomplique seu financeiro e mantenha tudo sob controle.
      </p>
    </div>

    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-movimentacao"></span>
      </div>
      <h3 class="beneficio-titulo">Simplifique movimentações financeiras</h3>
      <p class="beneficio-descricao">
        Realize pagamentos, emita boletos e links de Pix sem complicações. Tenha
        acesso a crédito facilitado para investir mais no seu negócio.
      </p>
    </div>

    <div class="beneficio-card">
      <div class="beneficio-icone">
        <span class="icone icone-custos"></span>
      </div>
      <h3 class="beneficio-titulo">Diminua custos e taxas</h3>
      <p class="beneficio-descricao">
        Aproveite serviços financeiros personalizados com taxa zero para Pix e
        TED, e elimine despesas com custos extras.
      </p>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.beneficios-container {
  padding: 48px 24px;
  background-color: #ffffff;
}

.secao-titulo {
  font-size: 32px;
  font-weight: 700;
  color: #333333;
  margin-bottom: 40px;
  text-align: center;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.beneficios-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.beneficio-card {
  background-color: #f9f9f9;
  border-radius: 12px;
  padding: 32px 24px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.beneficio-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
}

.beneficio-icone {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 64px;
  height: 64px;
  background-color: #e6f7ff;
  border-radius: 12px;
  margin-bottom: 24px;
}

.beneficio-icone .icone {
  font-size: 32px;
  color: #1890ff;
}

.beneficio-titulo {
  font-size: 20px;
  font-weight: 600;
  color: #333333;
  margin-bottom: 12px;
}

.beneficio-descricao {
  font-size: 16px;
  color: #666666;
  line-height: 1.5;
  margin-bottom: 16px;
}

.beneficio-link {
  display: inline-block;
  color: #1890ff;
  font-size: 16px;
  font-weight: 500;
  text-decoration: none;
  transition: color 0.2s ease;
}

.beneficio-link:hover {
  color: #40a9ff;
  text-decoration: underline;
}
```

### Seção de Comparação

A tabela comparativa entre a Conta Digital Revo e outros bancos:

**Estrutura HTML:**

```html
<div class="comparacao-container">
  <div class="comparacao-header">
    <div class="comparacao-logo">
      <img src="/assets/images/Revo-logo.svg" alt="Revo Logo" />
    </div>
    <h2 class="comparacao-titulo">
      Tiramos da frente tudo o que é enfeite e deixamos apenas o que você vai
      usar de verdade
    </h2>
  </div>

  <h2 class="secao-titulo">
    Compare e descubra os benefícios de uma conta integrada ao ERP da Revo
  </h2>

  <div class="comparacao-tabela">
    <div class="comparacao-cabecalho">
      <div class="comparacao-coluna-vazia"></div>
      <div class="comparacao-coluna-Revo">
        <h3 class="comparacao-coluna-titulo">Revo Conta Digital</h3>
      </div>
      <div class="comparacao-coluna-outros">
        <h3 class="comparacao-coluna-titulo">Outros bancos *</h3>
      </div>
    </div>

    <div class="comparacao-linha">
      <div class="comparacao-recurso">
        <div class="recurso-icone">
          <span class="icone icone-conta-gratis"></span>
        </div>
        <div class="recurso-info">
          <h4 class="recurso-titulo">Conta digital grátis</h4>
          <p class="recurso-descricao">
            Fique livre das taxas de manutenção da conta.
          </p>
        </div>
      </div>
      <div class="comparacao-coluna-Revo">
        <span class="icone icone-check"></span>
      </div>
      <div class="comparacao-coluna-outros">
        <p class="outros-descricao">
          Custo com cobranças de taxas e manutenção.
        </p>
      </div>
    </div>

    <!-- Outras linhas de comparação seguem o mesmo padrão -->

    <div class="comparacao-linha">
      <div class="comparacao-recurso">
        <div class="recurso-icone">
          <span class="icone icone-conferencia"></span>
        </div>
        <div class="recurso-info">
          <h4 class="recurso-titulo">Conferência de movimentação bancária</h4>
          <p class="recurso-descricao">
            Diga adeus às tarefas manuais de lançamentos e economize 24 horas
            por mês.
          </p>
        </div>
      </div>
      <div class="comparacao-coluna-Revo">
        <span class="icone icone-check"></span>
      </div>
      <div class="comparacao-coluna-outros">
        <p class="outros-descricao">
          Fluxo de caixa comprometido, perda de tempo e alto custo.
        </p>
      </div>
    </div>

    <!-- Mais linhas de comparação... -->
  </div>

  <div class="comparacao-notas">
    <p class="nota">
      * Cenário de acordo com alguns dos principais bancos digitais do mercado.
    </p>
    <p class="nota">** Mediante a aprovação de crédito.</p>
    <p class="nota">
      *** O FGC cobre valores até R$ 250 mil por CNPJ e por instituição
      financeira.
    </p>
  </div>
</div>
```

**Estilos CSS:**

```css
.comparacao-container {
  padding: 48px 24px;
  background-color: #f5f5f5;
}

.comparacao-header {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 48px;
  background-color: #ffffff;
  padding: 32px;
  border-radius: 12px;
  max-width: 1000px;
  margin-left: auto;
  margin-right: auto;
}

.comparacao-logo {
  margin-right: 24px;
}

.comparacao-logo img {
  height: 40px;
  width: auto;
}

.comparacao-titulo {
  font-size: 24px;
  font-weight: 600;
  color: #333333;
  max-width: 600px;
}

.comparacao-tabela {
  max-width: 1200px;
  margin: 0 auto;
  background-color: #ffffff;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.comparacao-cabecalho {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  background-color: #f9f9f9;
}

.comparacao-coluna-titulo {
  padding: 16px;
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  text-align: center;
}

.comparacao-coluna-Revo {
  background-color: #f6e9d7;
}

.comparacao-linha {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  border-bottom: 1px solid #f0f0f0;
}

.comparacao-linha:last-child {
  border-bottom: none;
}

.comparacao-recurso {
  display: flex;
  padding: 24px 16px;
  align-items: center;
}

.recurso-icone {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  margin-right: 16px;
  flex-shrink: 0;
}

.recurso-icone .icone {
  font-size: 24px;
  color: #1890ff;
}

.recurso-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin-bottom: 4px;
}

.recurso-descricao {
  font-size: 14px;
  color: #666666;
  line-height: 1.4;
}

.comparacao-coluna-Revo {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 24px 16px;
}

.icone-check {
  font-size: 24px;
  color: #52c41a;
}

.comparacao-coluna-outros {
  padding: 24px 16px;
}

.outros-descricao {
  font-size: 14px;
  color: #666666;
  line-height: 1.4;
}

.comparacao-notas {
  max-width: 1200px;
  margin: 24px auto 0;
  padding: 0 16px;
}

.nota {
  font-size: 14px;
  color: #999999;
  margin-bottom: 8px;
}
```

### Seção de Depoimentos

A seção que apresenta depoimentos de clientes:

**Estrutura HTML:**

```html
<div class="depoimentos-container">
  <h2 class="secao-titulo">
    É assim que nossos clientes utilizam a Conta Digital da Revo
  </h2>

  <div class="video-container">
    <iframe
      width="100%"
      height="500"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    ></iframe>
  </div>

  <div class="depoimentos-grid">
    <div class="depoimento-card">
      <div class="depoimento-empresa">
        <img
          src="/assets/images/logo-kiss-brasil.png"
          alt="Kiss Brasil"
          class="empresa-logo"
        />
        <div class="empresa-info">
          <h3 class="empresa-nome">Kiss Brasil</h3>
          <p class="empresa-pessoa">Gilberto, CEO</p>
        </div>
      </div>
      <h4 class="depoimento-titulo">É fantástico!</h4>
      <p class="depoimento-texto">
        Antes para pagar uma conta precisava entrar no site do banco, fazer o
        pagamento, salvar o comprovante, ir no Revo Revo, anexar e dar a baixa.
        Com a Conta Digital, é só pagar e tudo já fica salvo.
      </p>
    </div>

    <div class="depoimento-card">
      <div class="depoimento-empresa">
        <img
          src="/assets/images/logo-grupo-auster.png"
          alt="Grupo Auster"
          class="empresa-logo"
        />
        <div class="empresa-info">
          <h3 class="empresa-nome">Grupo Auster</h3>
          <p class="empresa-pessoa">Mauro, CEO</p>
        </div>
      </div>
      <h4 class="depoimento-titulo">Economizamos tempo!</h4>
      <p class="depoimento-texto">
        Dá para perceber que teve agilidade. Já era rápido, mas saímos de 40
        minutos para 20 minutos.
      </p>
    </div>

    <div class="depoimento-card">
      <div class="depoimento-empresa">
        <img
          src="/assets/images/logo-juff-sportswear.png"
          alt="Juff Sportswear"
          class="empresa-logo"
        />
        <div class="empresa-info">
          <h3 class="empresa-nome">Juff Sportswear</h3>
          <p class="empresa-pessoa">Flávio, CEO</p>
        </div>
      </div>
      <h4 class="depoimento-titulo">Brilhante!</h4>
      <p class="depoimento-texto">
        pago as contas e não perco mais tempo controlando o recebimento das
        minhas vendas. Posso dizer que faço o mesmo serviço com 20% do tempo.
      </p>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.depoimentos-container {
  padding: 48px 24px;
  background-color: #ffffff;
}

.video-container {
  max-width: 900px;
  margin: 0 auto 48px;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
}

.depoimentos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.depoimento-card {
  background-color: #ffffff;
  border: 1px solid #f0f0f0;
  border-radius: 12px;
  padding: 24px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.depoimento-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
}

.depoimento-empresa {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
}

.empresa-logo {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  object-fit: cover;
  margin-right: 12px;
}

.empresa-nome {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.empresa-pessoa {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.depoimento-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin-bottom: 12px;
}

.depoimento-texto {
  font-size: 14px;
  color: #666666;
  line-height: 1.5;
}
```

### Seção de Perguntas Frequentes

A seção de FAQ (Perguntas Frequentes):

**Estrutura HTML:**

```html
<div class="faq-container">
  <h2 class="secao-titulo">Perguntas frequentes</h2>

  <div class="faq-lista">
    <div class="faq-item">
      <div class="faq-pergunta" data-toggle="faq-1">
        <h3 class="pergunta-texto">O que é a Conta Digital da Revo?</h3>
        <span class="icone icone-seta"></span>
      </div>
      <div class="faq-resposta" id="faq-1">
        <p>
          A Conta Digital da Revo é uma conta bancária PJ 100% integrada ao ERP
          da Revo, que permite automatizar processos financeiros, reduzir custos
          e simplificar a gestão do seu negócio.
        </p>

        (Content truncated due to size limit. Use line ranges to read in chunks)
      </div>
    </div>
  </div>
</div>
```
