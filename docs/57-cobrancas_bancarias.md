# Análise do Módulo Cobranças Bancárias - ERP Revo

## Estrutura Geral

O módulo "Cobranças Bancárias" do ERP Revo apresenta uma interface para gerenciamento de remessas e retornos bancários relacionados a cobranças. A página inicial exibe um estado vazio quando não há itens cadastrados, com opções para inclusão de novas remessas.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Ações e Filtros

A seção superior contém botões de ação e ferramentas de filtragem:

**Estrutura HTML:**

```html
<div class="acoes-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/financas" class="breadcrumb-item">Finanças</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Cobranças Bancárias</span>
  </div>

  <div class="acoes-principais">
    <a
      href="/cobrancas_registradas/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-remessa"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir remessa</span>
    </a>
  </div>

  <div class="filtros-container">
    <div class="pesquisa-container">
      <input
        type="text"
        class="campo-pesquisa"
        placeholder="Pesquise por nome"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>

    <div class="filtros-rapidos">
      <a href="#" class="filtro-item">
        <span class="texto">por banco</span>
      </a>
      <a href="#" class="filtro-item">
        <span class="texto">por período</span>
      </a>
    </div>

    <div class="abas-container">
      <a href="#remessas" class="aba-item aba-ativa">
        <span class="texto">Remessas</span>
      </a>
      <a href="#retornos" class="aba-item">
        <span class="texto">Retornos bancários</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.acoes-container {
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

.acoes-principais {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
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
  background-color: #f5f5f5;
  color: #333333;
  border: 1px solid #d9d9d9;
}

.botao-acao:hover {
  background-color: #e6e6e6;
}

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
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

.filtros-container {
  margin-bottom: 16px;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
}

.campo-pesquisa {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px 0 0 4px;
  font-size: 14px;
  color: #333333;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 36px;
  background-color: #f5f5f5;
  border: 1px solid #d9d9d9;
  border-left: none;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa:hover {
  background-color: #e6e6e6;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  flex-wrap: wrap;
  gap: 8px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 16px;
  font-size: 14px;
  color: #666666;
  background-color: #f5f5f5;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.filtro-item:hover {
  background-color: #e6e6e6;
}

.filtro-ativo {
  background-color: #e6f7ff;
  color: #1890ff;
}

.abas-container {
  display: flex;
  align-items: center;
  border-bottom: 1px solid #f0f0f0;
}

.aba-item {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
}

.aba-item:hover {
  color: #1890ff;
}

.aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}
```

### Conteúdo Vazio

A área principal da página quando não há itens cadastrados:

**Estrutura HTML:**

```html
<div class="conteudo-vazio">
  <div class="conteudo-vazio-container">
    <div class="conteudo-vazio-ilustracao">
      <img
        src="/assets/images/ilustracao-vazio.png"
        alt="Nenhum item cadastrado"
      />
    </div>
    <div class="conteudo-vazio-texto">
      <h2 class="conteudo-vazio-titulo">
        Você não possui nenhum item cadastrado.
      </h2>
      <p class="conteudo-vazio-descricao">
        Para inserir novos registros você pode clicar em incluir remessa.
      </p>
      <button class="botao-acao botao-primario" id="btn-incluir-remessa-vazio">
        <span class="icone icone-adicionar"></span>
        <span class="texto">incluir remessa</span>
      </button>
    </div>
  </div>

  <div class="conteudo-vazio-ajuda">
    <p class="conteudo-vazio-ajuda-texto">Ficou com alguma dúvida?</p>
    <a href="#" class="conteudo-vazio-ajuda-link">Acesse a ajuda do Revo.</a>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  text-align: center;
}

.conteudo-vazio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 600px;
}

.conteudo-vazio-ilustracao {
  margin-bottom: 24px;
}

.conteudo-vazio-ilustracao img {
  max-width: 200px;
  height: auto;
}

.conteudo-vazio-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.conteudo-vazio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px;
}

.conteudo-vazio-ajuda {
  margin-top: 48px;
}

.conteudo-vazio-ajuda-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 8px;
}

.conteudo-vazio-ajuda-link {
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.conteudo-vazio-ajuda-link:hover {
  text-decoration: underline;
}
```

## Interações JavaScript

### Navegação entre Abas

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Navegação entre abas
  const abas = document.querySelectorAll(".aba-item");

  abas.forEach((aba) => {
    aba.addEventListener("click", function (e) {
      e.preventDefault();

      // Remove a classe ativa de todas as abas
      abas.forEach((a) => a.classList.remove("aba-ativa"));

      // Adiciona a classe ativa à aba clicada
      this.classList.add("aba-ativa");

      // Obtém o ID da aba a partir do href
      const abaId = this.getAttribute("href").substring(1);

      // Aqui seria implementada a lógica para mostrar o conteúdo da aba
      console.log("Aba selecionada:", abaId);
    });
  });
});
```

### Botões de Inclusão de Remessa

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botões de inclusão de remessa
  const botaoIncluirRemessa = document.getElementById("btn-incluir-remessa");
  const botaoIncluirRemessaVazio = document.getElementById(
    "btn-incluir-remessa-vazio"
  );

  function abrirFormularioInclusaoRemessa() {
    // Aqui seria implementada a lógica para abrir o formulário de inclusão de remessa
    window.location.href = "/cobrancas_registradas/incluir";
  }

  if (botaoIncluirRemessa) {
    botaoIncluirRemessa.addEventListener("click", function (e) {
      e.preventDefault();
      abrirFormularioInclusaoRemessa();
    });
  }

  if (botaoIncluirRemessaVazio) {
    botaoIncluirRemessaVazio.addEventListener("click", function (e) {
      e.preventDefault();
      abrirFormularioInclusaoRemessa();
    });
  }
});
```

### Filtros Rápidos

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Filtros rápidos
  const filtrosRapidos = document.querySelectorAll(".filtro-item");

  filtrosRapidos.forEach((filtro) => {
    filtro.addEventListener("click", function (e) {
      e.preventDefault();

      // Alterna o estado do filtro
      this.classList.toggle("filtro-ativo");

      // Aqui seria implementada a lógica de filtragem
      console.log("Filtro alterado:", this.textContent.trim());
    });
  });
});
```

## Formulário de Inclusão de Remessa

Embora não esteja visível na tela inicial, o formulário de inclusão de remessa é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Incluir Remessa</h2>
  </div>

  <form class="formulario" id="form-remessa">
    <div class="formulario-grupo">
      <label class="formulario-label" for="banco">Banco</label>
      <select
        class="formulario-campo formulario-select"
        id="banco"
        name="banco"
        required
      >
        <option value="">Selecione um banco</option>
        <option value="001">001 - Banco do Brasil</option>
        <option value="104">104 - Caixa Econômica Federal</option>
        <option value="237">237 - Bradesco</option>
        <option value="341">341 - Itaú</option>
        <option value="033">033 - Santander</option>
        <!-- Outros bancos -->
      </select>
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="carteira">Carteira</label>
      <input
        type="text"
        class="formulario-campo"
        id="carteira"
        name="carteira"
        required
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="agencia">Agência</label>
      <input
        type="text"
        class="formulario-campo"
        id="agencia"
        name="agencia"
        required
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="conta">Conta</label>
      <input
        type="text"
        class="formulario-campo"
        id="conta"
        name="conta"
        required
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="convenio">Convênio</label>
      <input
        type="text"
        class="formulario-campo"
        id="convenio"
        name="convenio"
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label" for="data_geracao">Data de Geração</label>
      <input
        type="date"
        class="formulario-campo"
        id="data_geracao"
        name="data_geracao"
        required
      />
    </div>

    <div class="formulario-grupo">
      <label class="formulario-label">Títulos</label>
      <div class="formulario-tabela-container">
        <table class="formulario-tabela">
          <thead>
            <tr>
              <th class="coluna-selecao">
                <input
                  type="checkbox"
                  class="checkbox-selecionar-todos"
                  id="selecionar-todos-titulos"
                />
              </th>
              <th>Cliente</th>
              <th>Documento</th>
              <th>Vencimento</th>
              <th>Valor</th>
            </tr>
          </thead>
          <tbody>
            <!-- Aqui seriam listados os títulos disponíveis para remessa -->
            <tr class="formulario-tabela-vazio">
              <td colspan="5">Nenhum título disponível para remessa.</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="formulario-acoes">
      <button type="button" class="botao-acao" id="btn-cancelar">
        Cancelar
      </button>
      <button type="submit" class="botao-acao botao-primario" id="btn-salvar">
        Salvar
      </button>
    </div>
  </form>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.formulario-cabecalho {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.formulario {
  padding: 24px;
}

.formulario-grupo {
  margin-bottom: 16px;
}

.formulario-label {
  display: block;
  margin-bottom: 8px;
  font-size: 14px;
  color: #666666;
}

.formulario-campo {
  display: block;
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.formulario-campo:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.formulario-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.formulario-tabela-container {
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  overflow: hidden;
}

.formulario-tabela {
  width: 100%;
  border-collapse: collapse;
}

.formulario-tabela th,
.formulario-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.formulario-tabela-vazio td {
  text-align: center;
  color: #999999;
  padding: 24px 16px;
}

.formulario-acoes {
  display: flex;
  justify-content: flex-end;
  margin-top: 24px;
  gap: 8px;
}
```

## Tela de Retornos Bancários

Embora não esteja visível na tela inicial, a aba de retornos bancários é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="retornos-container">
  <div class="acoes-retornos">
    <button class="botao-acao botao-primario" id="btn-processar-retorno">
      <span class="icone icone-upload"></span>
      <span class="texto">Processar retorno</span>
    </button>
  </div>

  <div class="conteudo-vazio">
    <div class="conteudo-vazio-container">
      <div class="conteudo-vazio-ilustracao">
        <img
          src="/assets/images/ilustracao-vazio.png"
          alt="Nenhum retorno processado"
        />
      </div>
      <div class="conteudo-vazio-texto">
        <h2 class="conteudo-vazio-titulo">
          Você não possui nenhum retorno processado.
        </h2>
        <p class="conteudo-vazio-descricao">
          Para processar um arquivo de retorno bancário, clique no botão acima.
        </p>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.retornos-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  padding: 24px;
}

.acoes-retornos {
  margin-bottom: 24px;
}
```

## Modal de Processamento de Retorno

O modal para processamento de arquivo de retorno bancário:

**Estrutura HTML:**

```html
<div class="modal" id="modal-processar-retorno">
  <div class="modal-conteudo">
    <div class="modal-cabecalho">
      <h3 class="modal-titulo">Processar Arquivo de Retorno</h3>
      <button class="modal-fechar" id="btn-fechar-modal">×</button>
    </div>

    <div class="modal-corpo">
      <form class="formulario" id="form-retorno">
        <div class="formulario-grupo">
          <label class="formulario-label" for="banco_retorno">Banco</label>
          <select
            class="formulario-campo formulario-select"
            id="banco_retorno"
            name="banco_retorno"
            required
          >
            <option value="">Selecione um banco</option>
            <option value="001">001 - Banco do Brasil</option>
            <option value="104">104 - Caixa Econômica Federal</option>
            <option value="237">237 - Bradesco</option>
            <option value="341">341 - Itaú</option>
            <option value="033">033 - Santander</option>
            <!-- Outros bancos -->
          </select>
        </div>

        <div class="formulario-grupo">
          <label class="formulario-label" for="arquivo_retorno"
            >Arquivo de Retorno</label
          >
          <input
            type="file"
            class="formulario-campo formulario-arquivo"
            id="arquivo_retorno"
            name="arquivo_retorno"
            required
          />
          <p class="formulario-ajuda">Formatos aceitos: .RET, .TXT</p>
        </div>
      </form>
    </div>

    <div class="modal-rodape">
      <button class="botao-acao" id="btn-cancelar-retorno">Cancelar</button>
      <button class="botao-acao botao-primario" id="btn-processar">
        Processar
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

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
  border-radius: 4px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 500px;
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
  font-size: 16px;
  font-weight: 600;
  color: #333333;
}

.modal-fechar {
  background: none;
  border: none;
  font-size: 20px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}

.modal-rodape {
  display: flex;
  justify-content: flex-end;
  padding: 16px 24px;
  border-top: 1px solid #f0f0f0;
  gap: 8px;
}

.formulario-arquivo {
  padding: 8px 0;
}

.formulario-ajuda {
  font-size: 12px;
  color: #999999;
  margin: 4px 0 0;
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .acoes-principais {
    flex-wrap: wrap;
  }

  .conteudo-vazio-container {
    padding: 0 16px;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .acoes-principais {
    justify-content: space-between;
  }

  .botao-acao {
    flex: 1;
    justify-content: center;
  }

  .filtros-rapidos,
  .abas-container {
    overflow-x: auto;
    white-space: nowrap;
    padding-bottom: 8px;
  }

  .filtro-item,
  .aba-item {
    flex-shrink: 0;
  }

  .conteudo-vazio-ilustracao img {
    max-width: 150px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .breadcrumb {
    display: none;
  }

  .acoes-principais {
    flex-direction: column;
  }

  .botao-acao {
    width: 100%;
    margin-bottom: 8px;
  }

  .conteudo-vazio-titulo {
    font-size: 16px;
  }

  .conteudo-vazio-descricao {
    font-size: 13px;
  }

  .modal-conteudo {
    width: 90%;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Verde (sucesso): #52c41a
- Verde secundário: #73d13d
- Verde claro (background): #f6ffed
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
- Amarelo (alerta): #faad14
- Amarelo claro (background): #fffbe6
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
  - Títulos: 18px
  - Subtítulos: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Semi-negrito: 600

## Fluxos de Navegação

1. **Inclusão de Remessa**:

   - O usuário acessa o módulo "Cobranças Bancárias"
   - Clica no botão "Incluir remessa" no topo da página ou no botão central na tela vazia
   - Um formulário é aberto para preenchimento dos dados da remessa
   - O usuário seleciona o banco, preenche os dados da conta e seleciona os títulos
   - O usuário salva a remessa, que é adicionada à lista

2. **Processamento de Retorno Bancário**:

   - O usuário acessa o módulo "Cobranças Bancárias"
   - Clica na aba "Retornos bancários"
   - Clica no botão "Processar retorno"
   - Um modal é aberto para seleção do banco e upload do arquivo de retorno
   - O usuário seleciona o banco e o arquivo
   - O usuário clica em "Processar"
   - O sistema processa o arquivo e exibe o resultado

3. **Filtragem de Remessas**:
   - O usuário acessa o módulo "Cobranças Bancárias"
   - Utiliza o campo de pesquisa para buscar por nome
   - Ou utiliza os filtros rápidos "por banco" ou "por período"
   - A lista de remessas é filtrada de acordo com os critérios selecionados

## Conclusão

O módulo "Cobranças Bancárias" do ERP Revo apresenta uma interface para gerenciamento de remessas e retornos bancários relacionados a cobranças. A tela inicial exibe um estado vazio quando não há itens cadastrados, com opções claras para inclusão de novas remessas.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo navegar entre abas, incluir remessas e processar retornos bancários.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento de cobranças bancárias do negócio.
