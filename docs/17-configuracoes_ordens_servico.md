# Análise do Módulo Configurações das Ordens de Serviço - ERP Revo

## Estrutura Geral

O módulo "Configurações das Ordens de Serviço" do ERP Revo apresenta uma interface para configurar os parâmetros e comportamentos relacionados às ordens de serviço no sistema. A página exibe diferentes seções de configuração com opções que podem ser ajustadas pelo usuário.

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
    <span class="breadcrumb-item-atual">Ordens de Serviço</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Configurações das ordens de serviço</h1>
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

### Seção de Layout

A primeira seção de configuração permite escolher o layout das ordens de serviço:

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-cabecalho">
    <h2 class="secao-titulo">Layout</h2>
  </div>

  <div class="secao-conteudo">
    <div class="opcoes-grupo">
      <label class="opcao-radio">
        <input
          type="radio"
          name="layout"
          value="assistencia_tecnica"
          id="layout-assistencia-tecnica"
          checked
        />
        <span class="opcao-texto">Assistência técnica</span>
      </label>

      <label class="opcao-radio">
        <input
          type="radio"
          name="layout"
          value="prestadores_servico"
          id="layout-prestadores-servico"
        />
        <span class="opcao-texto">Prestadores de serviço</span>
      </label>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.secao-configuracao {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.secao-cabecalho {
  margin-bottom: 16px;
}

.secao-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.secao-conteudo {
  margin-bottom: 16px;
}

.opcoes-grupo {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.opcao-radio {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.opcao-radio input[type="radio"] {
  margin-right: 8px;
}

.opcao-texto {
  font-size: 14px;
  color: #333333;
}
```

### Seção de Numeração das Ordens de Serviço

Esta seção permite configurar como será a numeração das ordens de serviço:

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-cabecalho">
    <h2 class="secao-titulo">Numeração das ordens de serviço</h2>
  </div>

  <div class="secao-conteudo">
    <div class="opcoes-grupo">
      <label class="opcao-radio">
        <input
          type="radio"
          name="numeracao"
          value="sequencial"
          id="numeracao-sequencial"
          checked
        />
        <span class="opcao-texto">Sequencial</span>
      </label>

      <label class="opcao-radio">
        <input
          type="radio"
          name="numeracao"
          value="manual"
          id="numeracao-manual"
        />
        <span class="opcao-texto">Manual</span>
      </label>
    </div>
  </div>
</div>
```

### Seção de Opções Adicionais

Esta seção contém opções adicionais para as ordens de serviço:

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-conteudo">
    <div class="opcoes-grupo">
      <label class="opcao-checkbox">
        <input
          type="checkbox"
          name="mostrar_assinatura"
          id="mostrar-assinatura"
        />
        <span class="opcao-texto"
          >Mostrar campos para assinatura na impressão da OS</span
        >
      </label>

      <label class="opcao-checkbox">
        <input
          type="checkbox"
          name="importar_desconto"
          id="importar-desconto"
        />
        <span class="opcao-texto"
          >Importar para a ordem de serviço o valor de desconto do pedido de
          venda</span
        >
      </label>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.opcao-checkbox {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.opcao-checkbox input[type="checkbox"] {
  margin-right: 8px;
}
```

### Seção de Observação Padrão

Esta seção permite configurar uma observação padrão para as ordens de serviço:

**Estrutura HTML:**

```html
<div class="secao-configuracao">
  <div class="secao-cabecalho">
    <h2 class="secao-titulo">Observação padrão para as ordens de serviço</h2>
  </div>

  <div class="secao-conteudo">
    <div class="campo-grupo">
      <textarea
        class="campo-textarea"
        id="observacao-padrao"
        name="observacao_padrao"
        rows="5"
        placeholder="Digite aqui a observação padrão que será exibida em todas as ordens de serviço"
      ></textarea>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.campo-grupo {
  margin-bottom: 16px;
}

.campo-textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  resize: vertical;
  min-height: 100px;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-textarea:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-textarea::placeholder {
  color: #999999;
}
```

### Botões de Ação

A seção inferior contém os botões para salvar ou cancelar as alterações:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <div class="acoes-grupo">
    <button type="button" class="botao-acao botao-secundario" id="btn-cancelar">
      <span class="texto">Cancelar</span>
    </button>

    <button type="button" class="botao-acao botao-primario" id="btn-salvar">
      <span class="texto">Salvar</span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-top: 1px solid #f0f0f0;
  position: sticky;
  bottom: 0;
}

.acoes-grupo {
  display: flex;
  justify-content: flex-end;
  gap: 8px;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: 1px solid #1890ff;
}

.botao-primario:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
}
```

## Interações JavaScript

### Alternar entre Opções de Layout

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Opções de layout
  const layoutAssistenciaTecnica = document.getElementById(
    "layout-assistencia-tecnica"
  );
  const layoutPrestadoresServico = document.getElementById(
    "layout-prestadores-servico"
  );

  if (layoutAssistenciaTecnica && layoutPrestadoresServico) {
    layoutAssistenciaTecnica.addEventListener("change", function () {
      if (this.checked) {
        console.log("Layout de Assistência Técnica selecionado");
        // Aqui seria implementada a lógica para atualizar a interface com base na seleção
      }
    });

    layoutPrestadoresServico.addEventListener("change", function () {
      if (this.checked) {
        console.log("Layout de Prestadores de Serviço selecionado");
        // Aqui seria implementada a lógica para atualizar a interface com base na seleção
      }
    });
  }
});
```

### Alternar entre Opções de Numeração

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Opções de numeração
  const numeracaoSequencial = document.getElementById("numeracao-sequencial");
  const numeracaoManual = document.getElementById("numeracao-manual");

  if (numeracaoSequencial && numeracaoManual) {
    numeracaoSequencial.addEventListener("change", function () {
      if (this.checked) {
        console.log("Numeração Sequencial selecionada");
        // Aqui seria implementada a lógica para atualizar a interface com base na seleção
      }
    });

    numeracaoManual.addEventListener("change", function () {
      if (this.checked) {
        console.log("Numeração Manual selecionada");
        // Aqui seria implementada a lógica para atualizar a interface com base na seleção
      }
    });
  }
});
```

### Salvar Configurações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão salvar
  const btnSalvar = document.getElementById("btn-salvar");

  if (btnSalvar) {
    btnSalvar.addEventListener("click", function () {
      // Coleta os valores dos campos
      const layout = document.querySelector(
        'input[name="layout"]:checked'
      ).value;
      const numeracao = document.querySelector(
        'input[name="numeracao"]:checked'
      ).value;
      const mostrarAssinatura =
        document.getElementById("mostrar-assinatura").checked;
      const importarDesconto =
        document.getElementById("importar-desconto").checked;
      const observacaoPadrao =
        document.getElementById("observacao-padrao").value;

      // Cria o objeto com os dados
      const configuracoes = {
        layout,
        numeracao,
        mostrarAssinatura,
        importarDesconto,
        observacaoPadrao,
      };

      // Salva as configurações
      salvarConfiguracoes(configuracoes);
    });

    function salvarConfiguracoes(configuracoes) {
      console.log("Salvando configurações:", configuracoes);

      // Aqui seria implementada a lógica para salvar as configurações no servidor
      // Por exemplo, usando uma requisição AJAX

      // Simula o salvamento bem-sucedido
      setTimeout(() => {
        alert("Configurações salvas com sucesso!");
      }, 1000);
    }
  }
});
```

### Cancelar Alterações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão cancelar
  const btnCancelar = document.getElementById("btn-cancelar");

  if (btnCancelar) {
    btnCancelar.addEventListener("click", function () {
      // Confirma se o usuário deseja cancelar as alterações
      if (
        confirm(
          "Deseja cancelar as alterações? As modificações não salvas serão perdidas."
        )
      ) {
        // Redireciona para a página de configurações
        window.location.href = "/configuracoes";
      }
    });
  }
});
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .cabecalho-acoes {
    flex-wrap: wrap;
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

  .acoes-grupo {
    width: 100%;
  }

  .acoes-grupo .botao-acao {
    flex: 1;
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
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Verde (sucesso): #52c41a
- Verde claro (background): #f6ffed
- Laranja (alerta): #fa8c16
- Laranja claro (background): #fff7e6
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
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

1. **Acesso às Configurações das Ordens de Serviço**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configurações das ordens de serviço"
   - O sistema exibe a tela de configurações das ordens de serviço

2. **Alteração das Configurações**:

   - O usuário seleciona as opções desejadas (layout, numeração, etc.)
   - Preenche a observação padrão, se necessário
   - Clica em "Salvar" para aplicar as alterações
   - O sistema salva as configurações e exibe uma mensagem de sucesso

3. **Cancelamento das Alterações**:

   - O usuário clica em "Cancelar" para descartar as alterações
   - O sistema exibe uma confirmação
   - Se confirmado, o sistema redireciona para a página de configurações sem salvar as alterações

4. **Retorno à Lista de Configurações**:
   - O usuário clica em "Voltar" para retornar à lista de configurações
   - O sistema redireciona para a página de configurações

## Conclusão

O módulo "Configurações das Ordens de Serviço" do ERP Revo apresenta uma interface para configurar os parâmetros e comportamentos relacionados às ordens de serviço no sistema. A página exibe diferentes seções de configuração com opções que podem ser ajustadas pelo usuário.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo alternar entre opções e salvar as configurações.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar a configuração das ordens de serviço.
