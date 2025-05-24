# Análise do Módulo Ferramentas - Resumo de Sincronizações - ERP Revo

## Estrutura Geral

O módulo "Ferramentas - Resumo de Sincronizações" do ERP Revo apresenta uma interface para visualização e monitoramento das sincronizações realizadas com plataformas externas. A página permite filtrar e acompanhar o status das sincronizações. Quando não há sincronizações registradas, a interface exibe uma mensagem informativa.

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
    <span class="breadcrumb-item-atual">Resumo de sincronizações</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Resumo de sincronizações</h1>
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

### Área de Filtros

A seção de filtros permite filtrar as sincronizações por período e status:

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtros-tabs">
    <a
      href="/resumo_hub_ecommerce?filtro=hoje"
      class="filtro-tab filtro-tab-ativo"
    >
      <span class="filtro-tab-icone icone-calendario"></span>
      <span class="filtro-tab-texto">Hoje</span>
    </a>
    <a href="/resumo_hub_ecommerce?filtro=pendentes" class="filtro-tab">
      <span class="filtro-tab-texto">Pendentes</span>
    </a>
    <a href="/resumo_hub_ecommerce?filtro=finalizadas" class="filtro-tab">
      <span class="filtro-tab-texto">Finalizadas</span>
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
  justify-content: flex-start;
}

.filtros-tabs {
  display: flex;
  align-items: center;
}

.filtro-tab {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  margin-right: 8px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  border: 1px solid #d9d9d9;
}

.filtro-tab:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.filtro-tab-ativo {
  background-color: #1890ff;
  color: #ffffff;
  border-color: #1890ff;
}

.filtro-tab-ativo:hover {
  background-color: #40a9ff;
  color: #ffffff;
}

.filtro-tab-icone {
  margin-right: 8px;
  font-size: 14px;
}

.icone-calendario::before {
  content: "\e902"; /* Código do ícone de calendário */
}

.filtro-tab-texto {
  font-weight: 500;
}
```

### Área de Conteúdo Principal - Estado Vazio

Quando não há sincronizações registradas, a interface exibe uma mensagem informativa:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="estado-vazio">
    <div class="estado-vazio-conteudo">
      <h2 class="estado-vazio-titulo">Nenhum registro encontrado</h2>
      <p class="estado-vazio-descricao">
        Tente alterar os filtros e pesquisar novamente
      </p>

      <div class="estado-vazio-ilustracao">
        <img
          src="/assets/images/ilustracao-vazio.svg"
          alt="Nenhum registro encontrado"
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
  border: 1px solid #ffe58f;
  border-radius: 4px;
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

### Área de Conteúdo Principal - Lista de Sincronizações

Quando há sincronizações registradas, a interface exibe uma tabela com os registros:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela">
      <thead class="tabela-cabecalho">
        <tr>
          <th class="tabela-celula tabela-celula-cabecalho">Plataforma</th>
          <th class="tabela-celula tabela-celula-cabecalho">Tipo</th>
          <th class="tabela-celula tabela-celula-cabecalho">Status</th>
          <th class="tabela-celula tabela-celula-cabecalho">Data/Hora</th>
          <th class="tabela-celula tabela-celula-cabecalho">Duração</th>
          <th class="tabela-celula tabela-celula-cabecalho">Registros</th>
          <th class="tabela-celula tabela-celula-cabecalho">Ações</th>
        </tr>
      </thead>
      <tbody class="tabela-corpo">
        <tr class="tabela-linha">
          <td class="tabela-celula">Mercado Livre</td>
          <td class="tabela-celula">Produtos</td>
          <td class="tabela-celula">
            <span class="status status-sucesso">Concluído</span>
          </td>
          <td class="tabela-celula">19/05/2025 14:30</td>
          <td class="tabela-celula">2min 30s</td>
          <td class="tabela-celula">150</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button class="botao-acao botao-acao-detalhes" title="Ver detalhes">
              <span class="icone icone-detalhes"></span>
            </button>
            <button
              class="botao-acao botao-acao-reprocessar"
              title="Reprocessar"
            >
              <span class="icone icone-reprocessar"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">Shopee</td>
          <td class="tabela-celula">Pedidos</td>
          <td class="tabela-celula">
            <span class="status status-erro">Falha</span>
          </td>
          <td class="tabela-celula">19/05/2025 13:45</td>
          <td class="tabela-celula">1min 15s</td>
          <td class="tabela-celula">45</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button class="botao-acao botao-acao-detalhes" title="Ver detalhes">
              <span class="icone icone-detalhes"></span>
            </button>
            <button
              class="botao-acao botao-acao-reprocessar"
              title="Reprocessar"
            >
              <span class="icone icone-reprocessar"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">Magento</td>
          <td class="tabela-celula">Estoque</td>
          <td class="tabela-celula">
            <span class="status status-processando">Processando</span>
          </td>
          <td class="tabela-celula">19/05/2025 12:20</td>
          <td class="tabela-celula">--</td>
          <td class="tabela-celula">--</td>
          <td class="tabela-celula tabela-celula-acoes">
            <button class="botao-acao botao-acao-detalhes" title="Ver detalhes">
              <span class="icone icone-detalhes"></span>
            </button>
            <button class="botao-acao botao-acao-cancelar" title="Cancelar">
              <span class="icone icone-cancelar"></span>
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

.status {
  display: inline-flex;
  align-items: center;
  padding: 4px 8px;
  border-radius: 2px;
  font-size: 12px;
  font-weight: 500;
}

.status-sucesso {
  background-color: #f6ffed;
  border: 1px solid #b7eb8f;
  color: #52c41a;
}

.status-erro {
  background-color: #fff1f0;
  border: 1px solid #ffa39e;
  color: #ff4d4f;
}

.status-processando {
  background-color: #e6f7ff;
  border: 1px solid #91d5ff;
  color: #1890ff;
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

.botao-acao-detalhes {
  color: #1890ff;
}

.botao-acao-detalhes:hover {
  background-color: #e6f7ff;
}

.botao-acao-reprocessar {
  color: #52c41a;
}

.botao-acao-reprocessar:hover {
  background-color: #f6ffed;
}

.botao-acao-cancelar {
  color: #ff4d4f;
}

.botao-acao-cancelar:hover {
  background-color: #fff1f0;
}

.icone-detalhes::before {
  content: "\e908"; /* Código do ícone de detalhes */
}

.icone-reprocessar::before {
  content: "\e909"; /* Código do ícone de reprocessar */
}

.icone-cancelar::before {
  content: "\e905"; /* Código do ícone de cancelar */
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

### Filtros de Sincronizações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Referências aos elementos
  const filtroTabs = document.querySelectorAll(".filtro-tab");

  // Função para aplicar filtro
  function aplicarFiltro(event) {
    // Remover classe ativa de todas as tabs
    filtroTabs.forEach(function (tab) {
      tab.classList.remove("filtro-tab-ativo");
    });

    // Adicionar classe ativa à tab clicada
    event.currentTarget.classList.add("filtro-tab-ativo");

    // Em um cenário real, aqui seria feita uma requisição AJAX
    // ou redirecionamento para a URL com o filtro aplicado
  }

  // Adicionar event listeners
  filtroTabs.forEach(function (tab) {
    tab.addEventListener("click", function (event) {
      event.preventDefault();
      aplicarFiltro(event);
    });
  });
});
```

### Ações de Sincronizações (Detalhes, Reprocessar e Cancelar)

```javascript
document.addEventListener('DOMContentLoaded', function() {
  // Referências aos elementos
  const botoesDetalhes = document.querySelectorAll('.botao-acao-detalhes');
  const botoesReprocessar = document.querySelectorAll('.botao-acao-reprocessar');
  const botoesCancelar = document.querySelectorAll('.botao-acao-cancelar');

  // Função para ver detalhes da sincronização
  function verDetalhesSincronizacao(event) {
    const botao = event.currentTarget;
    const linha = botao.closest('.tabela-linha');
    const plataforma = linha.querySelector('td:nth-child(1)').textContent;
    const tipo = linha.querySelector('td:nth-child(2)').textContent;

    // Criar elementos do modal de detalhes
    const modal = document.createElement('div');
    modal.className = 'modal';

    const modalConteudo = document.createElement('div');
    modalConteudo.className = 'modal-conteudo';

    const modalCabecalho = document.createElement('div');
    modalCabecalho.className = 'modal-cabecalho';

    const modalTitulo = document.createElement('h2');
    modalTitulo.className = 'modal-titulo';
    modalTitulo.textContent = `Detalhes da Sincronização - ${plataforma} (${tipo})`;

    const botaoFechar = document.createElement('button');
    botaoFechar.className = 'modal-botao-fechar';
    botaoFechar.innerHTML = '<span class="icone icone-fechar"></span>';

    const modalCorpo = document.createElement('div');
    modalCorpo.className = 'modal-corpo';

    // Conteúdo do modal de detalhes
    modalCorpo.innerHTML = `
      <div class="detalhes-sincronizacao">
        <div class="detalhes-grupo">
          <h3 class="detalhes-titulo">Informações Gerais</h3>
          <div class="detalhes-linha">
            <span class="detalhes-label">Plataforma:</span>
            <span class="detalhes-valor">${plataforma}</span>
          </div>
          <div class="detalhes-linha">
            <span class="detalhes-label">Tipo:</span>
            <span class="detalhes-valor">${tipo}</span>
          </div>
          <div class="detalhes-linha">
            <span class="detalhes-label">Status:</span>
            <span class="detalhes-valor">${linha.querySelector('td:nth-child(3)').textContent.trim()}</span>
          </div>
          <div class="detalhes-linha">
            <span class="detalhes-label">Data/Hora:</span>
            <span class="detalhes-valor">${linha.querySelector('td:nth-child(4)').textContent}</span>
          </div>
          <div class="detalhes-linha">
            <span class="detalhes-label">Duração:</span>
            <span class="detalhes-valor">${linha.querySelector('td:nth-child(5)').textContent}</span>
          </div>
          <div class="detalhes-linha">
            <span class="detalh
(Content truncated due to size limit. Use line ranges to read in chunks)
```
