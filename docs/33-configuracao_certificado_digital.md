# Análise do Módulo Configuração do Certificado Digital - ERP Revo

## Estrutura Geral

O módulo "Configuração do Certificado Digital" do ERP Revo apresenta uma interface para configurar o certificado digital utilizado na emissão de notas fiscais eletrônicas de serviços (NFSe). A página permite ao usuário escolher entre dois tipos de certificados digitais: A1 (arquivo digital) e A3 (cartão ou token).

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Navegação

A seção superior contém o título da página e links de navegação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/configuracoes" class="breadcrumb-item">Configurações</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual"
      >Configuração do certificado digital</span
    >
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Configurações do certificado digital</h1>
  </div>

  <div class="cabecalho-acoes">
    <a
      href="/configuracoes"
      class="botao-acao botao-secundario"
      id="btn-voltar"
    >
      <span class="icone icone-voltar"></span>
      <span class="texto">Voltar</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.cabecalho-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.breadcrumb {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  font-size: 14px;
}

.breadcrumb-item {
  color: #1890ff;
  text-decoration: none;
}

.breadcrumb-item:hover {
  text-decoration: underline;
}

.breadcrumb-separador {
  margin: 0 8px;
  color: #d9d9d9;
}

.breadcrumb-item-atual {
  color: #666666;
}

.cabecalho-titulo {
  margin-bottom: 16px;
}

.titulo-pagina {
  font-size: 24px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.cabecalho-acoes {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
}

.botao-acao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
  text-decoration: none;
}

.botao-secundario {
  background-color: #ffffff;
  color: #666666;
  border: 1px solid #d9d9d9;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
}
```

### Área de Alerta

A página exibe um alerta informativo sobre compatibilidade de dispositivos:

**Estrutura HTML:**

```html
<div class="alerta-container">
  <div class="alerta alerta-info">
    <div class="alerta-icone">
      <span class="icone icone-info"></span>
    </div>
    <div class="alerta-conteudo">
      <h3 class="alerta-titulo">Atenção</h3>
      <p class="alerta-texto">
        Para dispositivos móveis e computadores que possuem sistema operacional
        Mac OS ou Linux somente é possível utilizar certificados no modelo A1 -
        Armazenado em nosso servidor.
      </p>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-container {
  margin-bottom: 24px;
}

.alerta {
  display: flex;
  padding: 16px;
  border-radius: 4px;
  border-left: 4px solid;
}

.alerta-info {
  background-color: #e6f7ff;
  border-left-color: #1890ff;
}

.alerta-icone {
  margin-right: 12px;
  font-size: 20px;
  color: #1890ff;
}

.alerta-conteudo {
  flex: 1;
}

.alerta-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
  margin-bottom: 8px;
}

.alerta-texto {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.icone-info::before {
  content: "ℹ️";
}
```

### Área de Seleção de Certificado

A área principal da página apresenta as opções de certificado digital:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="certificado-selecao">
    <p class="certificado-pergunta">
      Leandro F. Marques, qual o tipo do seu certificado digital?
    </p>

    <div class="certificado-opcoes">
      <button type="button" class="certificado-opcao" id="certificado-a1">
        <div class="certificado-opcao-icone">
          <span class="icone icone-arquivo"></span>
        </div>
        <div class="certificado-opcao-conteudo">
          <h3 class="certificado-opcao-titulo">Certificado arquivo A1</h3>
          <p class="certificado-opcao-descricao">Arquivo digital</p>
        </div>
      </button>

      <button type="button" class="certificado-opcao" id="certificado-a3">
        <div class="certificado-opcao-icone">
          <span class="icone icone-cartao"></span>
        </div>
        <div class="certificado-opcao-conteudo">
          <h3 class="certificado-opcao-titulo">Certificado A3</h3>
          <p class="certificado-opcao-descricao">Cartão ou Token</p>
        </div>
      </button>
    </div>
  </div>

  <div class="separador"></div>

  <div class="certificado-info">
    <h2 class="certificado-info-titulo">Saiba mais sobre certificados</h2>

    <p class="certificado-info-texto">
      O Sistema ERP é compatível com os modelos de certificado digital A1
      (arquivo digital) e A3 (cartão ou token).
    </p>

    <p class="certificado-info-texto">
      O certificado digital <strong>modelo A1</strong> é um arquivo digital, que
      permite a emissão de notas fiscais através de qualquer dispositivo, desde
      que esteja armazenado em nossos servidores.
    </p>

    <p class="certificado-info-texto">
      Já o <strong>modelo A3</strong> é uma mídia física que precisa estar
      conectada em seu computador no momento da emissão da nota fiscal
      eletrônica.
    </p>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  background-color: #ffffff;
}

.certificado-selecao {
  margin-bottom: 32px;
}

.certificado-pergunta {
  font-size: 16px;
  color: #333333;
  margin: 0;
  margin-bottom: 16px;
}

.certificado-opcoes {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.certificado-opcao {
  display: flex;
  align-items: center;
  padding: 16px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  background-color: #ffffff;
  cursor: pointer;
  transition: all 0.2s ease;
  width: 300px;
  text-align: left;
}

.certificado-opcao:hover {
  border-color: #1890ff;
  box-shadow: 0 2px 8px rgba(24, 144, 255, 0.15);
}

.certificado-opcao.selecionado {
  border-color: #1890ff;
  background-color: #e6f7ff;
}

.certificado-opcao-icone {
  margin-right: 16px;
  font-size: 24px;
  color: #1890ff;
}

.certificado-opcao-conteudo {
  flex: 1;
}

.certificado-opcao-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
  margin-bottom: 4px;
}

.certificado-opcao-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.separador {
  height: 1px;
  background-color: #f0f0f0;
  margin: 32px 0;
}

.certificado-info {
  margin-bottom: 32px;
}

.certificado-info-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
  margin-bottom: 16px;
}

.certificado-info-texto {
  font-size: 14px;
  color: #666666;
  margin: 0;
  margin-bottom: 12px;
}

.certificado-info-texto strong {
  font-weight: 600;
  color: #333333;
}

.icone-arquivo::before {
  content: "📄";
}

.icone-cartao::before {
  content: "💳";
}
```

### Rodapé

O rodapé contém um link para a ajuda do ERP:

**Estrutura HTML:**

```html
<div class="rodape-container">
  <div class="rodape-ajuda">
    <a href="#" class="rodape-link">
      <span class="icone icone-ajuda"></span>
      <span class="texto">Acesse a ajuda do ERP.</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.rodape-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #f0f0f0;
}

.rodape-ajuda {
  display: flex;
  align-items: center;
}

.rodape-link {
  display: inline-flex;
  align-items: center;
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.rodape-link:hover {
  text-decoration: underline;
}

.rodape-link .icone {
  margin-right: 8px;
  font-size: 16px;
}

.icone-ajuda::before {
  content: "❓";
}
```

## Formulário de Configuração do Certificado A1

Quando o usuário seleciona a opção "Certificado arquivo A1", é exibido um formulário para upload e configuração do certificado:

**Estrutura HTML:**

```html
<div class="formulario-certificado" id="formulario-a1" style="display: none;">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Configuração do Certificado A1</h2>
  </div>

  <div class="formulario-corpo">
    <div class="campo-grupo">
      <label for="arquivo-certificado" class="campo-label"
        >Arquivo do Certificado Digital (.pfx)</label
      >
      <div class="campo-arquivo">
        <input
          type="file"
          id="arquivo-certificado"
          name="arquivo_certificado"
          class="campo-arquivo-input"
          accept=".pfx"
        />
        <label for="arquivo-certificado" class="campo-arquivo-label">
          <span class="icone icone-upload"></span>
          <span class="texto">Selecionar arquivo</span>
        </label>
        <span class="campo-arquivo-nome" id="arquivo-certificado-nome"
          >Nenhum arquivo selecionado</span
        >
      </div>
      <p class="campo-descricao">
        Selecione o arquivo do certificado digital no formato .pfx
      </p>
    </div>

    <div class="campo-grupo">
      <label for="senha-certificado" class="campo-label"
        >Senha do Certificado</label
      >
      <div class="campo-senha">
        <input
          type="password"
          id="senha-certificado"
          name="senha_certificado"
          class="campo-texto"
        />
        <button
          type="button"
          class="botao-mostrar-senha"
          id="btn-mostrar-senha"
        >
          <span class="icone icone-olho"></span>
        </button>
      </div>
      <p class="campo-descricao">Digite a senha do certificado digital</p>
    </div>

    <div class="campo-grupo">
      <label for="validade-certificado" class="campo-label"
        >Validade do Certificado</label
      >
      <input
        type="text"
        id="validade-certificado"
        name="validade_certificado"
        class="campo-texto"
        readonly
      />
      <p class="campo-descricao">
        A validade será exibida após o upload do certificado
      </p>
    </div>

    <div class="campo-grupo campo-checkbox">
      <input
        type="checkbox"
        id="salvar-certificado"
        name="salvar_certificado"
        class="campo-checkbox-input"
      />
      <label for="salvar-certificado" class="campo-checkbox-label"
        >Salvar certificado no servidor para uso em dispositivos móveis</label
      >
    </div>
  </div>

  <div class="formulario-rodape">
    <button
      type="button"
      class="botao-acao botao-secundario"
      id="btn-cancelar-a1"
    >
      <span class="texto">Cancelar</span>
    </button>

    <button type="button" class="botao-acao botao-primario" id="btn-salvar-a1">
      <span class="texto">Salvar</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-certificado {
  margin-top: 24px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  overflow: hidden;
}

.formulario-cabecalho {
  padding: 16px;
  background-color: #fafafa;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.formulario-corpo {
  padding: 16px;
}

.formulario-rodape {
  padding: 16px;
  background-color: #fafafa;
  border-top: 1px solid #f0f0f0;
  display: flex;
  justify-content: flex-end;
  gap: 8px;
}

.campo-grupo {
  margin-bottom: 16px;
}

.campo-label {
  display: block;
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.campo-texto {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-texto:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-texto[readonly] {
  background-color: #f5f5f5;
  cursor: not-allowed;
}

.campo-descricao {
  font-size: 12px;
  color: #999999;
  margin: 4px 0 0 0;
}

.campo-arquivo {
  display: flex;
  align-items: center;
}

.campo-arquivo-input {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}

.campo-arquivo-label {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border: 1px solid #d9d9d9;
  border-radius: 4px 0 0 4px;
  background-color: #fafafa;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: all 0.2s ease;
}

.campo-arquivo-label:hover {
  background-color: #f0f0f0;
}

.campo-arquivo-nome {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-left: none;
  border-radius: 0 4px 4px 0;
  font-size: 14px;
  color: #666666;
  background-color: #ffffff;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.campo-senha {
  position: relative;
}

.botao-mostrar-senha {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 40px;
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999999;
}

.botao-mostrar-senha:hover {
  color: #666666;
}

.campo-checkbox {
  display: flex;
  align-items: center;
}

.campo-checkbox-input {
  margin: 0;
  margin-right: 8px;
}

.campo-checkbox-label {
  font-size: 14px;
  color: #333333;
  cursor: pointer;
}

.icone-upload::before {
  content: "📤";
}

.icone-olho::before {
  content: "👁️";
}

.icone-olho-fechado::before {
  content: "👁️‍🗨️";
}
```

## Formulário de Configuração do Certificado A3

Quando o usuário seleciona a opção "Certificado A3", é exibido um formulário para configuração do certificado em cartão ou token:

**Estrutura HTML:**

```html
<div class="formulario-certificado" id="formulario-a3" style="display: none;">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Configuração do Certificado A3</h2>
  </div>

  <div class="formulario-corpo">
    <div class="alerta alerta-aviso">
      <div class="alerta-icone">
        <span class="icone icone-aviso"></span>
      </div>
      <div class="alerta-conteudo">
        <h3 class="alerta-titulo">Importante</h3>
        <p class="alerta-texto">
          Para utilizar o certificado A3, é necessário que o dispositivo (cartão
          ou token) esteja conectado ao computador e que o driver esteja
          instalado corretamente.
        </p>
      </div>
    </div>

    <div class="campo-grupo">
      <label class="campo-label">Certificados Disponíveis</label>
      <div class="certificados-lista" id="certificados-lista">
        <div class="certificado-item certificado-carregando">
          <span class="icone icone-carregando"></span>
          <span class="texto">Carregando certificados disponíveis...</span>
        </div>
      </div>
    </div>

    <div class="campo-grupo">
      <label for="senha-certificado-a3" class="campo-label"
        >Senha do Certificado</label
      >
      <div class="campo-senha">
        <input
          type="password"
          id="senha-certificado-a3"
          name="senha_certificado_a3"
          class="campo-texto"
        />
        <button
          type="button"
          class="botao-mostrar-senha"
          id="btn-mostrar-senha-a3"
        >
          <span class="icone icone-olho"></span>
        </button>
      </div>
      <p class="campo-descricao">Digite a senha do certificado digital</p>
    </div>

    <div class="campo-grupo">
      <label for="validade-certificado-a3" class="campo-label"
        >Validade do Certificado</label
      >
      <input
        type="text"
        id="validade-certificado-a3"
        name="validade_certificado_a3"
        class="campo-texto"
        readonly
      />
      <p class="campo-descricao">
        A validade será exibida após a seleção do certificado
      </p>
    </div>
  </div>

  <div class="formulario-rodape">
    <button
      type="button"
      class="botao-acao botao-secundario"
      id="btn-cancelar-a3"
    >
      <span class="texto">Cancelar</span>
    </button>

    <button type="button" class="botao-acao botao-primario" id="btn-salvar-a3">
      <span class="texto">Salvar</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-aviso {
  background-color: #fff7e6;
  border-left-color: #fa8c16;
  margin-bottom: 16px;
}

.alerta-aviso .alerta-icone {
  color: #fa8c16;
}

.certificados-lista {
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  max-height: 200px;
  overflow-y: auto;
}

.certificado-item {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-bottom: 1px solid #f0f0f0;
  cursor: pointer;
}

.certificado-item:last-child {
  border-bottom: none;
}

.certificado-item:hover {
  background-color: #f5f5f5;
}

.certificado-item.selecionado {
  background-color: #e6f7ff;
}

.certificado-item .icone {
  margin-right: 12px;
  font-size: 16px;
}

.certificado-carregando {
  cursor: default;
  color: #999999;
}

.certificado-carregando:hover {
  background-color: transparent;
}

.icone-carregando {
  animation: girar 1s linear infinite;
}

.icone-carregando::before {
  content: "🔄";
}

.icone-certificado::before {
  content: "🔐";
}

.icone-aviso::before {
  content: "⚠️";
}

@keyframes girar {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```

## Interações JavaScript

### Seleção de Tipo de Certificado

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const btnCertificadoA1 = document.getElementById("certificado-a1");
  const btnCertificadoA3 = document.getElementById("certificado-a3");
  const formularioA1 = document.getElementById("formulario-a1");
  const formularioA3 = document.getElementById("formulario-a3");

  // Função para selecionar o certificado A1
  function selecionarCertificadoA1() {
    btnCertificadoA1.classList.add("selecionado");
    btnCertificadoA3.classList.remove("selecionado");

    formularioA1.style.display = "block";
    formularioA3.style.display = "none";
  }

  // Função para selecionar o certificado A3
  function selecionarCertificadoA3() {
    btnCertificadoA3.classList.add("selecionado");
    btnCertificadoA1.classList.remove("selecionado");

    formularioA3.style.display = "block";
    formularioA1.style.display = "none";

    // Carregar certificados disponíveis
    carregarCertificadosA3();
  }

  // Adicionar event listeners
  if (btnCertificadoA1) {
    btnCertificadoA1.addEventListener("click", selecionarCertificadoA1);
  }

  if (btnCertificadoA3) {
    btnCertificadoA3.addEventListener("click", selecionarCertificadoA3);
  }
});
```

### Manipulação do Certificado A1

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const arquivoCertificado = document.getElementById("arquivo-certificado");
  const arquivoCertificadoNome = document.getElementById(
    "arquivo-certificado-nome"
  );
  const senhaCertificado = document.getElementById("senha-certificado");
  const btnMostrarSenha = document.getElementById("btn-mostrar-senha");
  const validadeCertificado = document.getElementById("validade-certificado");
  const btnCancelarA1 = document.getElementById("btn-cancelar-a1");
  const btnSalvarA1 = document.getElementById("btn-salvar-a1");

  // Função para atualizar o nome do arquivo selecionado
  if (arquivoCertificado && arquivoCertificadoNome) {
    arquivoCertificado.addEventListener("change", function () {
      if (this.files && this.files.length > 0) {
        arquivoCertificadoNome.textContent = this.files[0].name;

        // Simular a verificação da validade do certificado
        // Em um cenário real, isso seria feito após o upload do arquivo
        setTimeout(() => {
          validadeCertificado.value = "31/12/2023";
        }, 1000);
      } else {
        arquivoCertificadoNome.textContent = "Nenhum arquivo selecionado";
        validadeCertificado.value = "";
      }
    });
  }

  // Função para mostrar/ocultar a senha
  if (senhaCertificado && btnMostrarSenha) {
    btnMostrarSenha.addEventListener("click", function () {
      if (senhaCertificado.type === "password") {
        senhaCertificado.type = "text";
        this.querySelector(".icone").classList.remove("icone-olho");
        this.querySelector(".icone").classList.add("icone-olho-fechado");
      } else {
        senhaCertificado.type = "password";
        this.querySelector(".icone").classList.remove("icone-olho-fechado");
        this.querySelector(".icone").classList.add("icone-olho");
      }
    });
  }

  // Função para cancelar a configuração
  if (btnCancelarA1) {
    btnCancelarA1.addEventListener("click", function () {
      // Limpar os campos
      if (arquivoCertificado) arquivoCertificado.value = "";
      if (arquivoCertificadoNome)
        arquivoCertificadoNome.textContent = "Nenhum arquivo selecionado";
      if (senhaCertificado) senhaCertificado.value = "";
      if (validadeCertificado) validadeCertificado.value = "";

      // Ocultar o formulário
      document.getElementById("formulario-a1").style.display = "none";

      // Remover a seleção do botão
      document.getElementById("certificado-a1").classList.remove("selecionado");
    });
  }

  // Função para salvar a configuração
  if (btnSalvarA1) {
    btnSalvarA1.addEventListener("click", function () {
      // Validar os campos
      if (!arquivoCertificado.files || arquivoCertificado.files.length === 0) {
        alert("Selecione o arquivo do certificado digital.");
        return;
      }

      if (!senhaCertificado.value) {
        alert("Digite a senha do certificado digital.");
        return;
      }

      // Simular o salvamento
      alert("Certificado A1 configurado com sucesso!");

      // Redirecionar para a página de configurações
      // window.location.href = '/configuracoes';
    });
  }
});
```

### Manipulação do Certificado A3

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const certificadosLista = document.getElementById("certificados-lista");
  const senhaCertificadoA3 = document.getElementById("senha-certificado-a3");
  const btnMostrarSenhaA3 = document.getElementById("btn-mostrar-senha-a3");
  const validadeCertificadoA3 = document.getElementById(
    "validade-certificado-a3"
  );
  const btnCancelarA3 = document.getElementById("btn-cancelar-a3");
  const btnSalvarA3 = document.getElementById("btn-salvar-a3");

  // Função para carregar os certificados A3 disponíveis
  function carregarCertificadosA3() {
    if (certificadosLista) {
      // Simular o carregamento dos certificados
      setTimeout(() => {
        certificadosLista.innerHTML = `
          <div class="certificado-item" data-certificado="1">
            <span class="icone icone-certificado"></span>
            <span class="texto">Certificado A3 - Token - Empresa XYZ Ltda</span>
          </div>
          <div class="certificado-item" data-certificado="2">
            <span class="icone icone-certificado"></span>
            <span class="texto">Certificado A3 - Cartão - Empresa XYZ Ltda (Filial)</span>
          </div>
        `;

        // Adicionar event listeners aos certificados
        const certificadoItems =
          certificadosLista.querySelectorAll(".certificado-item");
        certificadoItems.forEach((item) => {
          item.addEventListener("click", function () {
            // Remover a seleção de todos os itens
            certificadoItems.forEach((i) => i.classList.remove("selecionado"));

            // Adicionar a seleção ao item clicado
            this.classList.add("selecionado");

            // Simular a verificação da validade do certificado
            validadeCertificadoA3.value = "31/12/2023";
          });
        });
      }, 1500);
    }
  }

  // Função para mostrar/ocultar a senha
  if (senhaCertificadoA3 && btnMostrarSenhaA3) {
    btnMostrarSenhaA3.addEventListener("click", function () {
      if (senhaCertificadoA3.type === "password") {
        senhaCertificadoA3.type = "text";
        this.querySelector(".icone").classList.remove("icone-olho");
        this.querySelector(".icone").classList.add("icone-olho-fechado");
      } else {
        senhaCertificadoA3.type = "password";
        this.querySelector(".icone").classList.remove("icone-olho-fechado");
        this.querySelector(".icone").classList.add("icone-olho");
      }
    });
  }

  // Função para cancelar a configuração
  if (btnCancelarA3) {
    btnCancelarA3.addEventListener("click", function () {
      // Limpar os campos
      if (certificadosLista) {
        certificadosLista.innerHTML = `
          <div class="certificado-item certificado-carregando">
            <span class="icone icone-carregando"></span>
            <span class="texto">Carregando certificados disponíveis...</span>
          </div>
        `;
      }

      if (senhaCertificadoA3) senhaCertificadoA3.value = "";
      if (validadeCertificadoA3) validadeCertificadoA3.value = "";

      // Ocultar o formulário
      document.getElementById("formulario-a3").style.display = "none";

      // Remover a seleção do botão
      document.getElementById("certificado-a3").classList.remove("selecionado");
    });
  }

  // Função para salvar a configuração
  if (btnSalvarA3) {
    btnSalvarA3.addEventListener("click", function () {
      // Validar os campos
      const certificadoSelecionado = certificadosLista.querySelector(
        ".certificado-item.selecionado"
      );

      if (!certificadoSelecionado) {
        alert("Selecione um certificado digital.");
        return;
      }

      if (!senhaCertificadoA3.value) {
        alert("Digite a senha do certificado digital.");
        return;
      }

      // Simular o salvamento
      alert("Certificado A3 configurado com sucesso!");

      // Redirecionar para a página de configurações
      // window.location.href = '/configuracoes';
    });
  }

  // Expor a função para uso externo
  window.carregarCertificadosA3 = carregarCertificadosA3;
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .certificado-opcoes {
    flex-direction: column;
  }

  .certificado-opcao {
    width: 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .cabecalho-acoes {
    flex-direction: column;
    align-items: flex-start;
  }

  .cabecalho-acoes .botao-acao {
    width: 100%;
    justify-content: center;
    margin-bottom: 8px;
  }

  .campo-arquivo {
    flex-direction: column;
    align-items: stretch;
  }

  .campo-arquivo-label {
    border-radius: 4px;
    margin-bottom: 8px;
  }

  .campo-arquivo-nome {
    border-radius: 4px;
    border-left: 1px solid #d9d9d9;
  }

  .formulario-rodape {
    flex-direction: column;
  }

  .formulario-rodape .botao-acao {
    width: 100%;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .titulo-pagina {
    font-size: 20px;
  }

  .alerta {
    flex-direction: column;
  }

  .alerta-icone {
    margin-right: 0;
    margin-bottom: 8px;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Laranja (alerta): #fa8c16
- Laranja claro (background): #fff7e6
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (placeholder): #999999
- Cinza muito claro (bordas): #d9d9d9
- Cinza ultra claro (backgrounds): #f5f5f5
- Cinza separador: #f0f0f0
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos grandes: 24px
  - Títulos médios: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

## Fluxos de Navegação

1. **Acesso à Configuração do Certificado Digital**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configuração do certificado digital"
   - O sistema exibe a tela de configuração do certificado digital

2. **Configuração do Certificado A1**:

   - O usuário seleciona a opção "Certificado arquivo A1"
   - O sistema exibe o formulário de configuração do certificado A1
   - O usuário seleciona o arquivo do certificado digital (.pfx)
   - Digita a senha do certificado
   - Opcionalmente, marca a opção para salvar o certificado no servidor
   - Clica em "Salvar" para confirmar
   - O sistema salva a configuração e redireciona para a página de configurações

3. **Configuração do Certificado A3**:

   - O usuário seleciona a opção "Certificado A3"
   - O sistema exibe o formulário de configuração do certificado A3
   - O sistema carrega a lista de certificados disponíveis no dispositivo
   - O usuário seleciona um certificado da lista
   - Digita a senha do certificado
   - Clica em "Salvar" para confirmar
   - O sistema salva a configuração e redireciona para a página de configurações

4. **Cancelamento da Configuração**:
   - Em qualquer momento, o usuário pode clicar em "Cancelar"
   - O sistema limpa os campos e oculta o formulário
   - O usuário pode selecionar outra opção ou retornar à página de configurações

## Conclusão

O módulo "Configuração do Certificado Digital" do ERP Revo apresenta uma interface para configurar o certificado digital utilizado na emissão de notas fiscais eletrônicas de serviços (NFSe). A página permite ao usuário escolher entre dois tipos de certificados digitais: A1 (arquivo digital) e A3 (cartão ou token).

A interface é bem estruturada, com uma área de alerta informativo sobre compatibilidade de dispositivos, uma área de seleção de tipo de certificado e formulários específicos para cada tipo de certificado.

O módulo utiliza componentes interativos para upload de arquivos, seleção de certificados, entrada de senhas e exibição de informações de validade. A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações.

Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma. A responsividade é bem implementada, garantindo uma boa experiência em dispositivos móveis e desktop.
