# Análise do Módulo Painel de Automações - ERP Revo

## Estrutura Geral

O módulo "Painel de Automações" do ERP Revo apresenta uma interface organizada para configuração de automações de processos. A tela é composta por um cabeçalho com título e descrição, seguida por uma área de configuração com diferentes automações disponíveis e um botão de salvamento.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção, uma breve descrição e um alerta informativo:

- Título "Painel de automação"
- Descrição "Selecione quais automações deseja configurar. Após selecionar, configure quando deseja que as ações sejam realizadas."
- Alerta informativo sobre salvar as configurações

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Painel de automação</h1>
    <span class="badge badge-novo">Novo</span>
    <p class="descricao-modulo">
      Selecione quais automações deseja configurar. Após selecionar, configure
      quando deseja que as ações sejam realizadas.
    </p>
  </div>
</div>

<div class="alerta alerta-info">
  <span class="icone icone-info"></span>
  <span class="texto"
    >Lembre-se de salvar suas automações para garantir que tudo seja
    configurado!</span
  >
</div>
```

**Estilos CSS:**

```css
.modulo-cabecalho {
  padding: 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.titulo-modulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
  display: inline-flex;
  align-items: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
  margin-left: 8px;
}

.badge-novo {
  background-color: #e6f7ff;
  color: #1890ff;
}

.descricao-modulo {
  font-size: 14px;
  color: #666666;
  margin: 8px 0 0 0;
}

.alerta {
  display: flex;
  align-items: center;
  padding: 16px 24px;
  margin: 0 24px 24px;
  border-radius: 4px;
}

.alerta-info {
  background-color: #fffbe6;
  border: 1px solid #ffe58f;
}

.alerta .icone {
  font-size: 16px;
  margin-right: 8px;
  color: #faad14;
}

.alerta .texto {
  font-size: 14px;
  color: #333333;
}
```

### Área de Configuração de Automações

A área de configuração exibe as automações disponíveis e permite configurar quando cada ação deve ser executada:

**Estrutura HTML:**

```html
<div class="automacoes-container">
  <div class="automacao-item">
    <div class="automacao-acao">
      <div class="switch-container">
        <label class="switch">
          <input type="checkbox" class="switch-input" checked />
          <span class="switch-slider"></span>
        </label>
        <span class="automacao-titulo">Lançar saída de estoque</span>
      </div>
    </div>
    <div class="automacao-condicao">
      <span class="condicao-texto">Quando</span>
      <div class="select-container">
        <select class="select-condicao">
          <option value="">Selecionar ação inicial</option>
          <option value="autorizar_nota">Ao autorizar a nota fiscal</option>
          <option value="salvar_nota">Ao salvar a nota fiscal</option>
          <option value="salvar_pedido">Ao salvar o pedido</option>
          <option value="marcar_enviado">Ao marcar pedido como enviado</option>
        </select>
      </div>
      <button class="botao-desativar">
        <span class="icone icone-pausar"></span>
      </button>
    </div>
  </div>

  <div class="automacao-item">
    <div class="automacao-acao">
      <div class="switch-container">
        <label class="switch">
          <input type="checkbox" class="switch-input" checked />
          <span class="switch-slider"></span>
        </label>
        <span class="automacao-titulo"
          >Emitir Nota Fiscal Eletrônica (NFe)</span
        >
      </div>
    </div>
    <div class="automacao-condicao">
      <span class="condicao-texto">Quando</span>
      <div class="select-container">
        <select class="select-condicao">
          <option value="">Selecionar ação inicial</option>
          <option value="aprovar_pedido">Ao aprovar o pedido</option>
        </select>
      </div>
      <button class="botao-desativar">
        <span class="icone icone-pausar"></span>
      </button>
    </div>
  </div>

  <div class="automacao-item">
    <div class="automacao-acao">
      <div class="switch-container">
        <label class="switch">
          <input type="checkbox" class="switch-input" checked />
          <span class="switch-slider"></span>
        </label>
        <span class="automacao-titulo">Enviar para expedição</span>
      </div>
    </div>
    <div class="automacao-condicao">
      <span class="condicao-texto">Quando</span>
      <div class="select-container">
        <select class="select-condicao">
          <option value="">Selecionar ação inicial</option>
          <option value="autorizar_nota">Ao autorizar a nota fiscal</option>
          <option value="salvar_nota">Ao salvar a nota fiscal</option>
          <option value="salvar_pedido">Ao salvar o pedido</option>
          <option value="aprovar_pedido">Ao aprovar o pedido</option>
        </select>
      </div>
      <button class="botao-desativar">
        <span class="icone icone-pausar"></span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.automacoes-container {
  padding: 0 24px 24px;
}

.automacao-item {
  margin-bottom: 24px;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.automacao-acao {
  padding: 16px;
  background-color: #fafafa;
  border-bottom: 1px solid #f0f0f0;
}

.switch-container {
  display: flex;
  align-items: center;
}

.switch {
  position: relative;
  display: inline-block;
  width: 40px;
  height: 20px;
  margin-right: 12px;
}

.switch-input {
  opacity: 0;
  width: 0;
  height: 0;
}

.switch-slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #e0e0e0;
  transition: 0.4s;
  border-radius: 20px;
}

.switch-slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 2px;
  bottom: 2px;
  background-color: white;
  transition: 0.4s;
  border-radius: 50%;
}

.switch-input:checked + .switch-slider {
  background-color: #1890ff;
}

.switch-input:checked + .switch-slider:before {
  transform: translateX(20px);
}

.automacao-titulo {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.automacao-condicao {
  display: flex;
  align-items: center;
  padding: 16px;
  background-color: #ffffff;
}

.condicao-texto {
  font-size: 14px;
  color: #666666;
  margin-right: 12px;
}

.select-container {
  flex: 1;
}

.select-condicao {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  background-color: #ffffff;
}

.select-condicao:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-desativar {
  width: 32px;
  height: 32px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  color: #666666;
  margin-left: 12px;
  transition: background-color 0.2s ease;
}

.botao-desativar:hover {
  background-color: #f5f5f5;
}
```

### Botão de Salvamento

O botão de salvamento permite salvar as configurações de automação:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <button class="botao botao-primario" id="btn-salvar">
    <span class="icone icone-salvar"></span>
    <span class="texto">Salvar automações</span>
  </button>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
  display: flex;
  justify-content: center;
  padding: 24px;
  border-top: 1px solid #f0f0f0;
}

.botao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao .icone {
  margin-right: 8px;
}
```

## Interações JavaScript

### Ativação/Desativação de Automações

O módulo permite ativar ou desativar automações:

```javascript
// Código para ativação/desativação de automações
document.querySelectorAll(".switch-input").forEach((switchInput) => {
  switchInput.addEventListener("change", function () {
    const automacaoItem = this.closest(".automacao-item");
    const selectCondicao = automacaoItem.querySelector(".select-condicao");

    if (this.checked) {
      // Ativa a automação
      automacaoItem.classList.remove("desativado");
      selectCondicao.disabled = false;
    } else {
      // Desativa a automação
      automacaoItem.classList.add("desativado");
      selectCondicao.disabled = true;
      selectCondicao.value = "";
    }
  });
});

// Código para botão de desativar
document.querySelectorAll(".botao-desativar").forEach((botao) => {
  botao.addEventListener("click", function () {
    const automacaoItem = this.closest(".automacao-item");
    const switchInput = automacaoItem.querySelector(".switch-input");

    // Desativa a automação
    switchInput.checked = false;

    // Dispara o evento change para atualizar a interface
    const event = new Event("change");
    switchInput.dispatchEvent(event);
  });
});
```

### Seleção de Condições

A seleção de condições permite configurar quando cada automação será executada:

```javascript
// Código para seleção de condições
document.querySelectorAll(".select-condicao").forEach((select) => {
  select.addEventListener("change", function () {
    // Verifica se foi selecionada uma condição
    if (this.value) {
      // Adiciona classe de preenchido
      this.classList.add("preenchido");
    } else {
      // Remove classe de preenchido
      this.classList.remove("preenchido");
    }
  });
});
```

### Salvamento de Configurações

O botão de salvamento envia as configurações para o servidor:

```javascript
// Código para salvamento de configurações
document.querySelector("#btn-salvar").addEventListener("click", function () {
  // Coleta as configurações de automação
  const automacoes = [];

  document.querySelectorAll(".automacao-item").forEach((item) => {
    const ativa = item.querySelector(".switch-input").checked;
    const titulo = item.querySelector(".automacao-titulo").textContent;
    const condicao = item.querySelector(".select-condicao").value;

    automacoes.push({
      ativa,
      titulo,
      condicao,
    });
  });

  // Verifica se todas as automações ativas têm condições selecionadas
  const automacoesSemCondicao = automacoes.filter(
    (a) => a.ativa && !a.condicao
  );

  if (automacoesSemCondicao.length > 0) {
    // Exibe alerta para automações sem condição
    exibirAlerta(
      "Selecione uma condição para todas as automações ativas.",
      "erro"
    );
    return;
  }

  // Envia as configurações para o servidor
  fetch("/api/automacoes", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({ automacoes }),
  })
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
      throw new Error("Erro ao salvar automações");
    })
    .then((data) => {
      // Exibe mensagem de sucesso
      exibirAlerta("Automações salvas com sucesso!", "sucesso");
    })
    .catch((error) => {
      // Exibe mensagem de erro
      exibirAlerta(`Erro ao salvar automações: ${error.message}`, "erro");
    });
});

function exibirAlerta(mensagem, tipo) {
  // Remove alertas existentes
  document.querySelectorAll(".alerta-temporario").forEach((alerta) => {
    alerta.remove();
  });

  // Cria o alerta
  const alerta = document.createElement("div");
  alerta.classList.add("alerta", "alerta-temporario");

  if (tipo === "sucesso") {
    alerta.classList.add("alerta-sucesso");
    alerta.innerHTML = `
      <span class="icone icone-sucesso"></span>
      <span class="texto">${mensagem}</span>
    `;
  } else if (tipo === "erro") {
    alerta.classList.add("alerta-erro");
    alerta.innerHTML = `
      <span class="icone icone-erro"></span>
      <span class="texto">${mensagem}</span>
    `;
  }

  // Adiciona o alerta ao DOM
  document
    .querySelector(".modulo-cabecalho")
    .insertAdjacentElement("afterend", alerta);

  // Remove o alerta após 5 segundos
  setTimeout(() => {
    alerta.remove();
  }, 5000);
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 768px) {
  .automacao-condicao {
    flex-direction: column;
    align-items: flex-start;
  }

  .condicao-texto {
    margin-right: 0;
    margin-bottom: 8px;
  }

  .select-container {
    width: 100%;
    margin-bottom: 8px;
  }

  .botao-desativar {
    margin-left: 0;
    align-self: flex-end;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 480px) {
  .modulo-cabecalho {
    padding: 16px;
  }

  .alerta {
    margin: 0 16px 16px;
    padding: 12px 16px;
  }

  .automacoes-container {
    padding: 0 16px 16px;
  }

  .acoes-container {
    padding: 16px;
  }

  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #e6f7ff
- Amarelo (alerta): #fffbe6
- Amarelo claro (borda alerta): #ffe58f
- Amarelo escuro (ícone alerta): #faad14
- Verde (sucesso): #52c41a
- Verde claro (background sucesso): #f6ffed
- Verde muito claro (borda sucesso): #b7eb8f
- Vermelho (erro): #f5222d
- Vermelho claro (background erro): #fff1f0
- Vermelho muito claro (borda erro): #ffa39e
- Cinza escuro (texto): #333333
- Cinza médio (subtexto): #666666
- Cinza claro (bordas): #e0e0e0
- Cinza muito claro (backgrounds): #f5f5f5
- Branco: #ffffff

### Tipografia

- Família de fonte principal: Roboto, sans-serif
- Tamanhos de fonte:
  - Títulos principais: 24px
  - Subtítulos: 18px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Switch

```css
.switch {
  position: relative;
  display: inline-block;
  width: 40px;
  height: 20px;
}

.switch-input {
  opacity: 0;
  width: 0;
  height: 0;
}

.switch-slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #e0e0e0;
  transition: 0.4s;
  border-radius: 20px;
}

.switch-slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 2px;
  bottom: 2px;
  background-color: white;
  transition: 0.4s;
  border-radius: 50%;
}

.switch-input:checked + .switch-slider {
  background-color: #1890ff;
}

.switch-input:checked + .switch-slider:before {
  transform: translateX(20px);
}
```

### Alertas

```css
.alerta {
  display: flex;
  align-items: center;
  padding: 16px 24px;
  margin: 0 24px 24px;
  border-radius: 4px;
}

.alerta-info {
  background-color: #fffbe6;
  border: 1px solid #ffe58f;
}

.alerta-sucesso {
  background-color: #f6ffed;
  border: 1px solid #b7eb8f;
}

.alerta-erro {
  background-color: #fff1f0;
  border: 1px solid #ffa39e;
}

.alerta .icone {
  font-size: 16px;
  margin-right: 8px;
}

.alerta-info .icone {
  color: #faad14;
}

.alerta-sucesso .icone {
  color: #52c41a;
}

.alerta-erro .icone {
  color: #f5222d;
}

.alerta .texto {
  font-size: 14px;
  color: #333333;
}

.alerta-temporario {
  animation: fadeIn 0.3s ease, fadeOut 0.3s ease 4.7s;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
```

## Fluxos de Navegação

1. **Configuração de Automações**:

   - O usuário acessa o Painel de Automações
   - Ativa ou desativa automações usando os switches
   - Seleciona condições para as automações ativas
   - Salva as configurações

2. **Feedback de Salvamento**:
   - Após clicar em "Salvar automações", o sistema exibe um alerta de sucesso ou erro
   - O alerta desaparece automaticamente após 5 segundos

## Conclusão

O módulo "Painel de Automações" do ERP Revo apresenta uma interface simples e funcional, focada na configuração de automações para processos de vendas. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita a configuração.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo ativar/desativar automações, selecionar condições e salvar configurações de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes tipos de alertas. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para automatizar processos de vendas, como lançamento de saída de estoque, emissão de nota fiscal e envio para expedição, atendendo às necessidades de negócios que buscam otimizar suas operações.
