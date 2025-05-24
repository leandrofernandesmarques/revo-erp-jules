# Análise do Módulo Ferramentas - Gerenciar Anexos - ERP Revo

## Estrutura Geral

O módulo "Ferramentas - Gerenciar Anexos" do ERP Revo apresenta uma interface para visualização e gerenciamento de arquivos anexados no sistema. A página permite pesquisar, filtrar e gerenciar os anexos existentes. Quando não há anexos cadastrados, a interface exibe uma mensagem informativa.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação, conforme documentado no módulo "Ferramentas - Geral".

### Área de Título e Navegação

A seção superior contém o título da página e links de navegação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/ferramentas_geral" class="breadcrumb-item">Ferramentas</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Gerenciar anexos</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Gerenciar anexos</h1>
  </div>
</div>
```

**Estilos CSS:**

```css
.cabecalho-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  margin-left: 240px; /* Espaço para o menu lateral */
  display: flex;
  flex-direction: column;
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
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.titulo-pagina {
  font-size: 24px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}
```

### Área de Filtros e Pesquisa

A seção de filtros permite pesquisar e filtrar os anexos:

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtro-pesquisa">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por nome ou extensão"
    />
    <button class="botao-pesquisa">
      <span class="icone icone-pesquisa"></span>
    </button>
  </div>

  <div class="filtros-acoes">
    <a href="/gerenciar_anexos?filtro=por_origem" class="filtro-link">
      <span class="filtro-texto">por origem</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.filtros-container {
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  margin-left: 240px; /* Espaço para o menu lateral */
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.filtro-pesquisa {
  position: relative;
  width: 400px;
}

.campo-pesquisa {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease;
}

.campo-pesquisa:focus {
  outline: none;
  border-color: #40a9ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-pesquisa::placeholder {
  color: #999999;
}

.botao-pesquisa {
  position: absolute;
  right: 0;
  top: 0;
  height: 100%;
  width: 40px;
  background: transparent;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999999;
}

.botao-pesquisa:hover {
  color: #666666;
}

.icone-pesquisa::before {
  content: "\e901"; /* Código do ícone de pesquisa */
}

.filtros-acoes {
  display: flex;
  align-items: center;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  margin-left: 8px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.filtro-link:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.filtro-texto {
  font-weight: 500;
}
```

### Área de Conteúdo Principal - Estado Vazio

Quando não há anexos cadastrados, a interface exibe uma mensagem informativa:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="estado-vazio">
    <div class="estado-vazio-conteudo">
      <h2 class="estado-vazio-titulo">
        Você não possui nenhum item cadastrado.
      </h2>
      <p class="estado-vazio-descricao">
        Ainda não existem anexos no seu sistema.
      </p>

      <div class="estado-vazio-ilustracao">
        <img
          src="/assets/images/ilustracao-vazio.svg"
          alt="Nenhum item encontrado"
          class="ilustracao-img"
        />
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  margin-left: 240px; /* Espaço para o menu lateral */
  background-color: #f5f5f5;
  min-height: calc(100vh - 180px); /* Altura total menos cabeçalho e filtros */
  display: flex;
  flex-direction: column;
}

.estado-vazio {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 48px 0;
}

.estado-vazio-conteudo {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  padding: 32px;
  max-width: 600px;
  width: 100%;
  text-align: center;
  position: relative;
}

.estado-vazio-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 16px 0;
}

.estado-vazio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px 0;
}

.estado-vazio-ilustracao {
  margin-top: 16px;
}

.ilustracao-img {
  max-width: 200px;
  height: auto;
}
```

### Área de Conteúdo Principal - Lista de Anexos

Quando há anexos cadastrados, a interface exibe uma tabela com os registros:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela">
      <thead class="tabela-cabecalho">
        <tr>
          <th class="tabela-celula tabela-celula-cabecalho">Nome</th>
          <th class="tabela-celula tabela-celula-cabecalho">Extensão</th>
          <th class="tabela-celula tabela-celula-cabecalho">Tamanho</th>
          <th class="tabela-celula tabela-celula-cabecalho">Data</th>
          <th class="tabela-celula tabela-celula-cabecalho">Origem</th>
          <th class="tabela-celula tabela-celula-cabecalho">Ações</th>
        </tr>
      </thead>
      <tbody class="tabela-corpo">
        <tr class="tabela-linha">
          <td class="tabela-celula">Contrato_123</td>
          <td class="tabela-celula">PDF</td>
          <td class="tabela-celula">1.2 MB</td>
          <td class="tabela-celula">19/05/2025</td>
          <td class="tabela-celula">Pedido #12345</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-visualizar"
              title="Visualizar anexo"
            >
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao botao-acao-baixar" title="Baixar anexo">
              <span class="icone icone-baixar"></span>
            </button>
            <button class="botao-acao botao-acao-excluir" title="Excluir anexo">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">Nota_Fiscal_456</td>
          <td class="tabela-celula">PDF</td>
          <td class="tabela-celula">0.8 MB</td>
          <td class="tabela-celula">18/05/2025</td>
          <td class="tabela-celula">Nota Fiscal #456</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-visualizar"
              title="Visualizar anexo"
            >
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao botao-acao-baixar" title="Baixar anexo">
              <span class="icone icone-baixar"></span>
            </button>
            <button class="botao-acao botao-acao-excluir" title="Excluir anexo">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">Imagem_Produto</td>
          <td class="tabela-celula">JPG</td>
          <td class="tabela-celula">2.5 MB</td>
          <td class="tabela-celula">17/05/2025</td>
          <td class="tabela-celula">Produto #789</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-visualizar"
              title="Visualizar anexo"
            >
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao botao-acao-baixar" title="Baixar anexo">
              <span class="icone icone-baixar"></span>
            </button>
            <button class="botao-acao botao-acao-excluir" title="Excluir anexo">
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="paginacao">
    <span class="paginacao-info">Exibindo 1-3 de 3 itens</span>
    <div class="paginacao-controles">
      <button
        class="paginacao-botao paginacao-botao-anterior paginacao-botao-desabilitado"
      >
        <span class="icone icone-anterior"></span>
      </button>
      <button
        class="paginacao-botao paginacao-botao-pagina paginacao-botao-ativo"
      >
        1
      </button>
      <button
        class="paginacao-botao paginacao-botao-proximo paginacao-botao-desabilitado"
      >
        <span class="icone icone-proximo"></span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
  margin-bottom: 16px;
}

.tabela {
  width: 100%;
  border-collapse: collapse;
}

.tabela-cabecalho {
  background-color: #fafafa;
}

.tabela-celula {
  padding: 12px 16px;
  font-size: 14px;
  border-bottom: 1px solid #f0f0f0;
  color: #333333;
}

.tabela-celula-cabecalho {
  font-weight: 600;
  color: #666666;
  text-align: left;
}

.tabela-linha:hover {
  background-color: #f5f5f5;
}

.tabela-celula-acoes {
  text-align: right;
  white-space: nowrap;
}

.botao-acao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 4px;
  background-color: transparent;
  border: none;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
  margin-left: 4px;
}

.botao-acao:hover {
  background-color: #f0f0f0;
}

.botao-acao-visualizar {
  color: #1890ff;
}

.botao-acao-visualizar:hover {
  background-color: #e6f7ff;
}

.botao-acao-baixar {
  color: #52c41a;
}

.botao-acao-baixar:hover {
  background-color: #f6ffed;
}

.botao-acao-excluir {
  color: #ff4d4f;
}

.botao-acao-excluir:hover {
  background-color: #fff1f0;
}

.icone-visualizar::before {
  content: "\e908"; /* Código do ícone de visualizar */
}

.icone-baixar::before {
  content: "\e909"; /* Código do ícone de baixar */
}

.icone-excluir::before {
  content: "\e905"; /* Código do ícone de excluir */
}

.paginacao {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 0;
}

.paginacao-info {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
}

.paginacao-botao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 32px;
  height: 32px;
  padding: 0 8px;
  margin: 0 4px;
  border-radius: 4px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease,
    border-color 0.2s ease;
}

.paginacao-botao:hover:not(.paginacao-botao-desabilitado) {
  border-color: #1890ff;
  color: #1890ff;
}

.paginacao-botao-ativo {
  background-color: #1890ff;
  border-color: #1890ff;
  color: #ffffff;
}

.paginacao-botao-desabilitado {
  cursor: not-allowed;
  color: #d9d9d9;
}

.icone-anterior::before {
  content: "\e906"; /* Código do ícone de anterior */
}

.icone-proximo::before {
  content: "\e907"; /* Código do ícone de próximo */
}
```

## Interações JavaScript

### Filtro por Origem

```javascript
document.addEventListener('DOMContentLoaded', function() {
  // Referências aos elementos
  const filtroPorOrigem = document.querySelector('a[href="/gerenciar_anexos?filtro=por_origem"]');

  // Função para abrir modal de filtro por origem
  function abrirModalFiltroPorOrigem(event) {
    event.preventDefault();

    // Criar elementos do modal
    const modal = document.createElement('div');
    modal.className = 'modal';

    const modalConteudo = document.createElement('div');
    modalConteudo.className = 'modal-conteudo modal-conteudo-pequeno';

    const modalCabecalho = document.createElement('div');
    modalCabecalho.className = 'modal-cabecalho';

    const modalTitulo = document.createElement('h2');
    modalTitulo.className = 'modal-titulo';
    modalTitulo.textContent = 'Filtrar por Origem';

    const botaoFechar = document.createElement('button');
    botaoFechar.className = 'modal-botao-fechar';
    botaoFechar.innerHTML = '<span class="icone icone-fechar"></span>';

    const modalCorpo = document.createElement('div');
    modalCorpo.className = 'modal-corpo';

    // Formulário de filtro por origem
    modalCorpo.innerHTML = `
      <form class="formulario">
        <div class="formulario-grupo">
          <label class="formulario-label">Tipo de Origem</label>
          <div class="formulario-opcoes">
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_pedido" value="1" checked />
              <span class="formulario-opcao-texto">Pedidos</span>
            </label>
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_nota" value="1" checked />
              <span class="formulario-opcao-texto">Notas Fiscais</span>
            </label>
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_produto" value="1" checked />
              <span class="formulario-opcao-texto">Produtos</span>
            </label>
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_cliente" value="1" checked />
              <span class="formulario-opcao-texto">Clientes</span>
            </label>
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_fornecedor" value="1" checked />
              <span class="formulario-opcao-texto">Fornecedores</span>
            </label>
            <label class="formulario-opcao">
              <input type="checkbox" name="origem_outros" value="1" checked />
              <span class="formulario-opcao-texto">Outros</span>
            </label>
          </div>
        </div>
      </form>
    `;

    const modalRodape = document.createElement('div');
    modalRodape.className = 'modal-rodape';

    const botaoCancelar = document.createElement('button');
    botaoCancelar.className = 'botao botao-secundario';
    botaoCancelar.textContent = 'Cancelar';

    const botaoAplicar = document.createElement('button');
    botaoAplicar.className = 'botao botao-primario';
    botaoAplicar.textContent = 'Aplicar';

    // Montar estrutura do modal
    modalCabecalho.appendChild(modalTitulo);
    modalCabecalho.appendChild(botaoFechar);

    modalRodape.appendChild(botaoCancelar);
    modalRodape.appendChild(botaoAplicar);

    modalConteudo.appendChild(modalCabecalho);
    modalConteudo.appendChild(modalCorpo);
    modalConteudo.appendChild(modalRodape);

    modal.appendChild(modalConteudo);

    document.body.appendChild(modal);

    // Adicionar event listeners
    botaoFechar.addEventListener('click', fecharModal);
    botaoCancelar.addEventListener('click', fecharModal);
    modal.addEventListener('c
(Content truncated due to size limit. Use line ranges to read in chunks)
```
