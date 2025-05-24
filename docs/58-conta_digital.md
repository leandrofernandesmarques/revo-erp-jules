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
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-pergunta" data-toggle="faq-2">
        <h3 class="pergunta-texto">Quanto custa abrir a conta?</h3>
        <span class="icone icone-seta"></span>
      </div>
      <div class="faq-resposta" id="faq-2">
        <p>
          A abertura e manutenção da Conta Digital da Revo é totalmente
          gratuita. Não há taxas de abertura, mensalidade ou anuidade.
        </p>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-pergunta" data-toggle="faq-3">
        <h3 class="pergunta-texto">Como funciona a aprovação?</h3>
        <span class="icone icone-seta"></span>
      </div>
      <div class="faq-resposta" id="faq-3">
        <p>
          O processo de aprovação é simples e rápido. Após preencher o
          formulário com os dados da empresa e do sócio-administrador, nossa
          equipe fará a análise e você receberá o retorno em até 2 dias úteis.
        </p>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-pergunta" data-toggle="faq-4">
        <h3 class="pergunta-texto">Quais são os documentos necessários?</h3>
        <span class="icone icone-seta"></span>
      </div>
      <div class="faq-resposta" id="faq-4">
        <p>
          Para abrir a conta, você precisará dos documentos da empresa (CNPJ,
          contrato social) e do sócio-administrador (RG, CPF, comprovante de
          residência). Todo o processo é digital e você pode enviar os
          documentos pela plataforma.
        </p>
      </div>
    </div>
  </div>

  <div class="faq-cta">
    <div class="faq-cta-logo">
      <img src="/assets/images/Revo-logo.svg" alt="Revo Logo" />
    </div>
    <div class="faq-cta-texto">
      <p>
        Com os documentos da pessoa sócio-administradora e empresa, você abre
        sua conta em menos de 2 minutos
      </p>
    </div>
    <a
      href="#"
      class="botao-primario botao-destaque"
      id="btn-abrir-conta-footer"
    >
      <span class="icone icone-conta"></span>
      <span class="texto">abra sua conta PJ grátis</span>
    </a>
  </div>

  <div class="faq-footer">
    <a href="#" class="link-termos">Termos de uso da Revo Conta Digital</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.faq-container {
  padding: 48px 24px;
  background-color: #f5f5f5;
}

.faq-lista {
  max-width: 800px;
  margin: 0 auto 48px;
}

.faq-item {
  background-color: #ffffff;
  border-radius: 8px;
  margin-bottom: 16px;
  overflow: hidden;
}

.faq-pergunta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 24px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.faq-pergunta:hover {
  background-color: #f9f9f9;
}

.pergunta-texto {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.icone-seta {
  font-size: 16px;
  color: #999999;
  transition: transform 0.2s ease;
}

.faq-pergunta[aria-expanded="true"] .icone-seta {
  transform: rotate(180deg);
}

.faq-resposta {
  padding: 0 24px 20px;
  display: none;
}

.faq-resposta p {
  font-size: 16px;
  color: #666666;
  line-height: 1.5;
  margin: 0;
}

.faq-cta {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #ffffff;
  border-radius: 12px;
  padding: 24px;
  max-width: 1000px;
  margin: 0 auto 24px;
}

.faq-cta-logo img {
  height: 32px;
  width: auto;
}

.faq-cta-texto {
  flex: 1;
  margin: 0 24px;
}

.faq-cta-texto p {
  font-size: 18px;
  color: #333333;
  margin: 0;
}

.faq-footer {
  text-align: center;
}

.link-termos {
  color: #1890ff;
  font-size: 14px;
  text-decoration: none;
}

.link-termos:hover {
  text-decoration: underline;
}
```

### Botão de Ajuda Flutuante

O botão de ajuda flutuante presente na página:

**Estrutura HTML:**

```html
<div class="ajuda-flutuante">
  <a href="#" class="botao-ajuda">
    <span class="icone icone-ajuda">?</span>
  </a>
  <div class="tooltip-ajuda">Precisa de ajuda?</div>
</div>
```

**Estilos CSS:**

```css
.ajuda-flutuante {
  position: fixed;
  bottom: 24px;
  right: 24px;
  z-index: 1000;
}

.botao-ajuda {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background-color: #1652f0;
  color: white;
  text-decoration: none;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transition: background-color 0.2s ease, transform 0.2s ease;
}

.botao-ajuda:hover {
  background-color: #0e3fb3;
  transform: scale(1.05);
}

.icone-ajuda {
  font-size: 24px;
  font-weight: bold;
}

.tooltip-ajuda {
  position: absolute;
  top: -40px;
  right: 0;
  background-color: #333333;
  color: white;
  padding: 8px 12px;
  border-radius: 4px;
  font-size: 14px;
  white-space: nowrap;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.2s ease, visibility 0.2s ease;
}

.tooltip-ajuda::after {
  content: "";
  position: absolute;
  bottom: -6px;
  right: 24px;
  border-width: 6px 6px 0;
  border-style: solid;
  border-color: #333333 transparent transparent;
}

.botao-ajuda:hover + .tooltip-ajuda {
  opacity: 1;
  visibility: visible;
}
```

## Interações JavaScript

### Toggle de Perguntas Frequentes

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Inicializa o FAQ
  const faqPerguntas = document.querySelectorAll(".faq-pergunta");

  faqPerguntas.forEach((pergunta) => {
    pergunta.addEventListener("click", function () {
      const targetId = this.getAttribute("data-toggle");
      const resposta = document.getElementById(targetId);

      // Verifica se a resposta está visível
      const isExpanded = this.getAttribute("aria-expanded") === "true";

      // Fecha todas as respostas
      document.querySelectorAll(".faq-resposta").forEach((item) => {
        item.style.display = "none";
      });

      document.querySelectorAll(".faq-pergunta").forEach((item) => {
        item.setAttribute("aria-expanded", "false");
      });

      // Se não estava expandido, abre a resposta
      if (!isExpanded) {
        resposta.style.display = "block";
        this.setAttribute("aria-expanded", "true");
      }
    });
  });

  // Inicializa com a primeira pergunta aberta
  if (faqPerguntas.length > 0) {
    const primeiraPergunta = faqPerguntas[0];
    const primeiraRespostaId = primeiraPergunta.getAttribute("data-toggle");
    const primeiraResposta = document.getElementById(primeiraRespostaId);

    primeiraPergunta.setAttribute("aria-expanded", "true");
    primeiraResposta.style.display = "block";
  }
});
```

### Botões de Abertura de Conta

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botões de abertura de conta
  const botoesAbrirConta = document.querySelectorAll(
    "#btn-abrir-conta, #btn-abrir-conta-footer"
  );

  botoesAbrirConta.forEach((botao) => {
    botao.addEventListener("click", function (e) {
      e.preventDefault();

      // Abre o modal de abertura de conta
      abrirModalConta();
    });
  });

  function abrirModalConta() {
    // Cria o modal
    const modal = document.createElement("div");
    modal.classList.add("modal-abertura-conta");
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Abra sua conta PJ grátis</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="modal-etapas">
            <div class="etapa etapa-ativa">
              <span class="etapa-numero">1</span>
              <span class="etapa-texto">Dados da empresa</span>
            </div>
            <div class="etapa-separador"></div>
            <div class="etapa">
              <span class="etapa-numero">2</span>
              <span class="etapa-texto">Dados do sócio</span>
            </div>
            <div class="etapa-separador"></div>
            <div class="etapa">
              <span class="etapa-numero">3</span>
              <span class="etapa-texto">Confirmação</span>
            </div>
          </div>
          
          <form class="formulario-abertura">
            <div class="form-grupo">
              <label class="form-label">CNPJ</label>
              <input type="text" class="form-input" id="cnpj" placeholder="00.000.000/0000-00" required>
            </div>
            
            <div class="form-grupo">
              <label class="form-label">Razão Social</label>
              <input type="text" class="form-input" id="razao_social" placeholder="Nome da sua empresa" required>
            </div>
            
            <div class="form-grupo">
              <label class="form-label">Nome Fantasia</label>
              <input type="text" class="form-input" id="nome_fantasia" placeholder="Nome comercial da sua empresa" required>
            </div>
            
            <div class="form-grupo">
              <label class="form-label">E-mail</label>
              <input type="email" class="form-input" id="email" placeholder="email@empresa.com.br" required>
            </div>
            
            <div class="form-grupo">
              <label class="form-label">Telefone</label>
              <input type="tel" class="form-input" id="telefone" placeholder="(00) 00000-0000" required>
            </div>
            
            <div class="acoes-formulario">
              <button type="button" class="botao-secundario" id="btn-cancelar-abertura">Cancelar</button>
              <button type="button" class="botao-primario" id="btn-continuar-abertura">Continuar</button>
            </div>
          </form>
        </div>
      </div>
    `;

    document.body.appendChild(modal);

    // Adiciona eventos
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-cancelar-abertura")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    modal
      .querySelector("#btn-continuar-abertura")
      .addEventListener("click", function () {
        // Aqui seria implementada a validação e o avanço para a próxima etapa
        alert(
          "Funcionalidade em implementação. Em um ambiente real, este formulário enviaria os dados para processamento."
        );
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });

    // Máscaras para os campos
    const cnpjInput = modal.querySelector("#cnpj");
    cnpjInput.addEventListener("input", function () {
      let value = this.value.replace(/\D/g, "");
      if (value.length > 14) value = value.slice(0, 14);

      if (value.length > 12) {
        value = value.replace(
          /^(\d{2})(\d{3})(\d{3})(\d{4})(\d{2})$/,
          "$1.$2.$3/$4-$5"
        );
      } else if (value.length > 8) {
        value = value.replace(/^(\d{2})(\d{3})(\d{3})(\d+)$/, "$1.$2.$3/$4");
      } else if (value.length > 5) {
        value = value.replace(/^(\d{2})(\d{3})(\d+)$/, "$1.$2.$3");
      } else if (value.length > 2) {
        value = value.replace(/^(\d{2})(\d+)$/, "$1.$2");
      }

      this.value = value;
    });

    const telefoneInput = modal.querySelector("#telefone");
    telefoneInput.addEventListener("input", function () {
      let value = this.value.replace(/\D/g, "");
      if (value.length > 11) value = value.slice(0, 11);

      if (value.length > 10) {
        value = value.replace(/^(\d{2})(\d{5})(\d{4})$/, "($1) $2-$3");
      } else if (value.length > 6) {
        value = value.replace(/^(\d{2})(\d{4})(\d+)$/, "($1) $2-$3");
      } else if (value.length > 2) {
        value = value.replace(/^(\d{2})(\d+)$/, "($1) $2");
      }

      this.value = value;
    });
  }
});
```

### Link de Ajuda

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Link de ajuda
  const linkAjuda = document.querySelector(".botao-ajuda");

  linkAjuda.addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o modal de ajuda
    abrirModalAjuda();
  });

  function abrirModalAjuda() {
    // Cria o modal
    const modal = document.createElement("div");
    modal.classList.add("modal-ajuda");
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Central de Ajuda</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="ajuda-opcoes">
            <div class="ajuda-opcao">
              <div class="ajuda-icone">
                <span class="icone icone-chat"></span>
              </div>
              <h3 class="ajuda-titulo">Chat Online</h3>
              <p class="ajuda-descricao">Converse com um de nossos especialistas em tempo real.</p>
              <button class="botao-primario botao-ajuda-acao">Iniciar Chat</button>
            </div>
            
            <div class="ajuda-opcao">
              <div class="ajuda-icone">
                <span class="icone icone-email"></span>
              </div>
              <h3 class="ajuda-titulo">E-mail</h3>
              <p class="ajuda-descricao">Envie sua dúvida por e-mail e responderemos em até 24h.</p>
              <button class="botao-primario botao-ajuda-acao">Enviar E-mail</button>
            </div>
            
            <div class="ajuda-opcao">
              <div class="ajuda-icone">
                <span class="icone icone-telefone"></span>
              </div>
              <h3 class="ajuda-titulo">Telefone</h3>
              <p class="ajuda-descricao">Ligue para nossa central de atendimento.</p>
              <p class="ajuda-telefone">0800 123 4567</p>
              <p class="ajuda-horario">Segunda a sexta, das 9h às 18h</p>
            </div>
          </div>
          
          <div class="ajuda-faq">
            <h3 class="ajuda-faq-titulo">Perguntas Frequentes</h3>
            <ul class="ajuda-faq-lista">
              <li><a href="#">Como abrir minha conta digital?</a></li>
              <li><a href="#">Quais são as taxas cobradas?</a></li>
              <li><a href="#">Como funciona a integração com o ERP?</a></li>
              <li><a href="#">Como emitir boletos?</a></li>
              <li><a href="#">Como solicitar antecipação de recebíveis?</a></li>
            </ul>
            <a href="#" class="ajuda-faq-mais">Ver todas as perguntas</a>
          </div>
        </div>
      </div>
    `;

    document.body.appendChild(modal);

    // Adiciona eventos
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });

    // Botões de ação
    modal.querySelectorAll(".botao-ajuda-acao").forEach((botao) => {
      botao.addEventListener("click", function () {
        alert(
          "Funcionalidade em implementação. Em um ambiente real, esta ação abriria o canal de atendimento correspondente."
        );
      });
    });
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .hero-container {
    flex-direction: column;
    text-align: center;
  }

  .hero-content {
    max-width: 100%;
    margin-bottom: 32px;
  }

  .beneficios-grid {
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  }

  .comparacao-tabela {
    overflow-x: auto;
  }

  .faq-cta {
    flex-direction: column;
    text-align: center;
  }

  .faq-cta-logo,
  .faq-cta-texto {
    margin-bottom: 16px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .secao-titulo {
    font-size: 24px;
  }

  .hero-title {
    font-size: 28px;
  }

  .hero-description {
    font-size: 16px;
  }

  .beneficio-card {
    padding: 24px 16px;
  }

  .comparacao-linha {
    grid-template-columns: 1fr;
  }

  .comparacao-coluna-vazia,
  .comparacao-cabecalho {
    display: none;
  }

  .comparacao-recurso {
    border-top: 1px solid #f0f0f0;
    padding-top: 16px;
  }

  .depoimentos-grid {
    grid-template-columns: 1fr;
  }

  .video-container iframe {
    height: 300px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao-destaque {
    width: 100%;
  }

  .video-container iframe {
    height: 200px;
  }

  .pergunta-texto {
    font-size: 16px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul destaque: #1652f0
- Azul claro (background): #e6f7ff
- Azul muito claro (background): #f0f5ff
- Verde (sucesso): #52c41a
- Verde claro (background sucesso): #f6ffed
- Amarelo (destaque): #faad14
- Amarelo claro (background destaque): #fffbe6
- Bege (background Revo): #f6e9d7
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 32-36px
  - Subtítulos: 24px
  - Títulos de seção: 20px
  - Texto normal: 16px
  - Texto pequeno: 14px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600
  - Negrito: 700

## Componentes Reutilizáveis

### Botões

```css
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

.botao-secundario {
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
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
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
```

### Cards

```css
.card {
  background-color: #ffffff;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
}

.card-titulo {
  font-size: 20px;
  font-weight: 600;
  color: #333333;
  margin-bottom: 12px;
}

.card-descricao {
  font-size: 16px;
  color: #666666;
  line-height: 1.5;
}
```

### Modais

```css
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-conteudo {
  background-color: white;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 600px;
  max-height: 90vh;
  overflow-y: auto;
}

.modal-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.modal-titulo {
  margin: 0;
  font-size: 20px;
  font-weight: 600;
  color: #333333;
}

.botao-fechar {
  background: none;
  border: none;
  font-size: 24px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}
```

### Formulários

```css
.form-grupo {
  margin-bottom: 16px;
}

.form-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.form-input,
.form-select,
.form-textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 16px;
  color: #333333;
}

.form-input:focus,
.form-select:focus,
.form-textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.acoes-formulario {
  display: flex;
  justify-content: flex-end;
  gap: 16px;
  margin-top: 24px;
}
```

## Fluxos de Navegação

1. **Visualização da Página Informativa**:

   - O usuário acessa o módulo "Conta Digital"
   - Visualiza as informações sobre a conta digital
   - Pode rolar a página para ver todas as seções
   - Pode expandir as perguntas frequentes para ver as respostas

2. **Abertura de Conta**:

   - O usuário clica em um dos botões "abra sua conta PJ grátis"
   - Um modal é aberto com o formulário de abertura de conta
   - O usuário preenche os dados da empresa
   - Avança para a próxima etapa com os dados do sócio
   - Confirma as informações
   - Recebe a confirmação de abertura da conta

3. **Acesso à Ajuda**:

   - O usuário clica no botão de ajuda flutuante
   - Um modal é aberto com as opções de ajuda
   - O usuário pode escolher entre chat, e-mail ou telefone
   - Também pode acessar as perguntas frequentes

4. **Visualização de Depoimentos**:
   - O usuário pode assistir ao vídeo de depoimento
   - Pode ler os depoimentos de clientes
   - Pode clicar nos links para saber mais sobre cada benefício

## Conclusão

O módulo "Conta Digital" do ERP Revo apresenta uma interface informativa e promocional sobre a conta digital integrada ao sistema. A página é bem estruturada, com seções claras que destacam os benefícios, funcionalidades e vantagens da conta digital.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo expandir perguntas frequentes, abrir modais e navegar pelas etapas de abertura de conta.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário clara e objetiva, com chamadas para ação bem posicionadas e informações organizadas de forma a converter o usuário para a abertura da conta digital.
