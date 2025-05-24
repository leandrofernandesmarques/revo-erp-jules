# Análise do Módulo Configurações dos Contratos - ERP Revo

## Estrutura Geral

O módulo "Configurações dos Contratos" do ERP Revo apresenta uma interface para configurar os parâmetros e comportamentos relacionados aos contratos no sistema. A página exibe diferentes opções de configuração que podem ser ajustadas pelo usuário através de switches (interruptores) que ativam ou desativam funcionalidades específicas.

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
    <span class="breadcrumb-item-atual">Contratos</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Configurações dos contratos</h1>
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

### Opções de Configuração

A página apresenta três opções de configuração principais, cada uma com um switch (interruptor) para ativar ou desativar a funcionalidade:

**Estrutura HTML:**

```html
<div class="configuracoes-container">
  <div class="opcao-configuracao">
    <div class="opcao-texto">
      <label for="considerar-data-termino" class="opcao-label"
        >Considerar a data de término na geração das cobranças</label
      >
    </div>
    <div class="opcao-controle">
      <label class="switch">
        <input
          type="checkbox"
          id="considerar-data-termino"
          name="considerar_data_termino"
        />
        <span class="slider round"></span>
      </label>
    </div>
  </div>

  <div class="opcao-configuracao">
    <div class="opcao-texto">
      <label for="agrupar-contratos" class="opcao-label"
        >Agrupar contratos com mesmo cliente, dia de vencimento, vendedor e
        alíquota de comissão</label
      >
    </div>
    <div class="opcao-controle">
      <label class="switch">
        <input
          type="checkbox"
          id="agrupar-contratos"
          name="agrupar_contratos"
        />
        <span class="slider round"></span>
      </label>
    </div>
  </div>

  <div class="opcao-configuracao">
    <div class="opcao-texto">
      <label for="receber-copia-email" class="opcao-label"
        >Receber cópia do email do boleto</label
      >
    </div>
    <div class="opcao-controle">
      <label class="switch">
        <input
          type="checkbox"
          id="receber-copia-email"
          name="receber_copia_email"
        />
        <span class="slider round"></span>
      </label>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.configuracoes-container {
  padding: 16px 24px;
}

.opcao-configuracao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 0;
  border-bottom: 1px solid #f0f0f0;
}

.opcao-configuracao:last-child {
  border-bottom: none;
}

.opcao-texto {
  flex: 1;
}

.opcao-label {
  font-size: 14px;
  color: #333333;
  cursor: pointer;
}

.opcao-controle {
  margin-left: 16px;
}

/* Switch (interruptor) */
.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 24px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 18px;
  width: 18px;
  left: 3px;
  bottom: 3px;
  background-color: white;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #1890ff;
}

input:focus + .slider {
  box-shadow: 0 0 1px #1890ff;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 24px;
}

.slider.round:before {
  border-radius: 50%;
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

### Alternar Switches (Interruptores)

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Obter referências aos switches
  const considerarDataTermino = document.getElementById(
    "considerar-data-termino"
  );
  const agruparContratos = document.getElementById("agrupar-contratos");
  const receberCopiaEmail = document.getElementById("receber-copia-email");

  // Adicionar event listeners para os switches
  if (considerarDataTermino) {
    considerarDataTermino.addEventListener("change", function () {
      console.log("Considerar data de término:", this.checked);
    });
  }

  if (agruparContratos) {
    agruparContratos.addEventListener("change", function () {
      console.log("Agrupar contratos:", this.checked);
    });
  }

  if (receberCopiaEmail) {
    receberCopiaEmail.addEventListener("change", function () {
      console.log("Receber cópia do email:", this.checked);
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
      // Coleta os valores dos switches
      const considerarDataTermino = document.getElementById(
        "considerar-data-termino"
      ).checked;
      const agruparContratos =
        document.getElementById("agrupar-contratos").checked;
      const receberCopiaEmail = document.getElementById(
        "receber-copia-email"
      ).checked;

      // Cria o objeto com os dados
      const configuracoes = {
        considerarDataTermino,
        agruparContratos,
        receberCopiaEmail,
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
  .opcao-configuracao {
    flex-direction: column;
    align-items: flex-start;
  }

  .opcao-controle {
    margin-left: 0;
    margin-top: 8px;
  }

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

1. **Acesso às Configurações dos Contratos**:

   - O usuário acessa o módulo "Configurações" do menu de Serviços
   - Clica na opção "Configurações dos contratos"
   - O sistema exibe a tela de configurações dos contratos

2. **Alteração das Configurações**:

   - O usuário ativa ou desativa os switches conforme necessário
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

O módulo "Configurações dos Contratos" do ERP Revo apresenta uma interface simples e direta para configurar os parâmetros relacionados aos contratos no sistema. A página utiliza switches (interruptores) para ativar ou desativar funcionalidades específicas, tornando a interação intuitiva para o usuário.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo alternar os switches e salvar as configurações.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar a configuração dos contratos.
