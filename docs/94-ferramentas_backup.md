# Análise do Módulo Ferramentas - Backup - ERP Revo

## Estrutura Geral

O módulo "Ferramentas - Backup" do ERP Revo apresenta uma interface para gerenciamento de backups do sistema. A página permite visualizar backups existentes, criar novos backups e aplicar filtros de pesquisa. Quando não há backups cadastrados, a interface exibe uma mensagem informativa e um botão para incluir um novo backup.

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
    <span class="breadcrumb-item-atual">Backup</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Backup</h1>
  </div>

  <div class="cabecalho-acoes">
    <a href="/incluir_backup" class="botao botao-primario">
      <span class="botao-icone icone-adicionar"></span>
      <span class="botao-texto">Incluir Backup</span>
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

.cabecalho-acoes {
  display: flex;
  align-items: center;
  justify-content: flex-end;
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
  transition: background-color 0.2s ease, color 0.2s ease,
    border-color 0.2s ease;
  text-decoration: none;
}

.botao-primario {
  background-color: #1890ff;
  color: #ffffff;
  border: 1px solid #1890ff;
}

.botao-primario:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
}

.botao-icone {
  margin-right: 8px;
  font-size: 14px;
}

.icone-adicionar::before {
  content: "\e900"; /* Código do ícone de adicionar */
}
```

### Área de Filtros e Pesquisa

A seção de filtros permite pesquisar e filtrar os backups:

**Estrutura HTML:**

```html
<div class="filtros-container">
  <div class="filtro-pesquisa">
    <input type="text" class="campo-pesquisa" placeholder="Pesquisa..." />
    <button class="botao-pesquisa">
      <span class="icone icone-pesquisa"></span>
    </button>
  </div>

  <div class="filtros-acoes">
    <a href="/backup?filtro=em_aberto" class="filtro-link">
      <span class="filtro-texto">Em aberto</span>
    </a>

    <a href="/backup?filtro=por_periodo" class="filtro-link">
      <span class="filtro-icone icone-calendario"></span>
      <span class="filtro-texto">por período</span>
    </a>

    <a href="/backup" class="filtro-link filtro-limpar">
      <span class="filtro-icone icone-limpar"></span>
      <span class="filtro-texto">limpar filtros</span>
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
  width: 300px;
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

.filtro-icone {
  margin-right: 6px;
  font-size: 14px;
}

.filtro-texto {
  font-weight: 500;
}

.filtro-limpar {
  color: #ff4d4f;
}

.filtro-limpar:hover {
  background-color: #fff1f0;
  color: #ff4d4f;
}

.icone-calendario::before {
  content: "\e902"; /* Código do ícone de calendário */
}

.icone-limpar::before {
  content: "\e903"; /* Código do ícone de limpar */
}
```

### Área de Conteúdo Principal - Estado Vazio

Quando não há backups cadastrados, a interface exibe uma mensagem informativa:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="estado-vazio">
    <div class="estado-vazio-conteudo">
      <h2 class="estado-vazio-titulo">
        Você não possui nenhum item cadastrado.
      </h2>
      <p class="estado-vazio-descricao">
        Para inserir novos registros você pode clicar em Incluir Backup.
      </p>

      <a href="/incluir_backup" class="botao botao-primario estado-vazio-acao">
        <span class="botao-texto">Incluir Backup</span>
      </a>

      <div class="estado-vazio-ilustracao">
        <img
          src="/assets/images/ilustracao-vazio.svg"
          alt="Nenhum item encontrado"
          class="ilustracao-img"
        />
      </div>
    </div>
  </div>

  <div class="ajuda-container">
    <p class="ajuda-texto">Ficou com alguma dúvida?</p>
    <a href="/ajuda/backup" class="ajuda-link">Acesse a ajuda do Revo.</a>
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

.estado-vazio-acao {
  margin-bottom: 24px;
}

.estado-vazio-ilustracao {
  margin-top: 16px;
}

.ilustracao-img {
  max-width: 200px;
  height: auto;
}

.ajuda-container {
  margin-top: 24px;
  text-align: center;
}

.ajuda-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 8px 0;
}

.ajuda-link {
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
}

.ajuda-link:hover {
  text-decoration: underline;
}
```

### Área de Conteúdo Principal - Lista de Backups

Quando há backups cadastrados, a interface exibe uma tabela com os registros:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="tabela-container">
    <table class="tabela">
      <thead class="tabela-cabecalho">
        <tr>
          <th class="tabela-celula tabela-celula-cabecalho">Data</th>
          <th class="tabela-celula tabela-celula-cabecalho">Hora</th>
          <th class="tabela-celula tabela-celula-cabecalho">Tipo</th>
          <th class="tabela-celula tabela-celula-cabecalho">Status</th>
          <th class="tabela-celula tabela-celula-cabecalho">Ações</th>
        </tr>
      </thead>
      <tbody class="tabela-corpo">
        <tr class="tabela-linha">
          <td class="tabela-celula">19/05/2025</td>
          <td class="tabela-celula">10:30</td>
          <td class="tabela-celula">Completo</td>
          <td class="tabela-celula">
            <span class="badge badge-sucesso">Concluído</span>
          </td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-download"
              title="Baixar backup"
            >
              <span class="icone icone-download"></span>
            </button>
            <button
              class="botao-acao botao-acao-excluir"
              title="Excluir backup"
            >
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">18/05/2025</td>
          <td class="tabela-celula">15:45</td>
          <td class="tabela-celula">Parcial</td>
          <td class="tabela-celula">
            <span class="badge badge-sucesso">Concluído</span>
          </td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-download"
              title="Baixar backup"
            >
              <span class="icone icone-download"></span>
            </button>
            <button
              class="botao-acao botao-acao-excluir"
              title="Excluir backup"
            >
              <span class="icone icone-excluir"></span>
            </button>
          </td>
        </tr>
        <tr class="tabela-linha">
          <td class="tabela-celula">17/05/2025</td>
          <td class="tabela-celula">08:15</td>
          <td class="tabela-celula">Completo</td>
          <td class="tabela-celula">
            <span class="badge badge-erro">Falha</span>
          </td>
          <td class="tabela-celula tabela-celula-acoes">
            <button
              class="botao-acao botao-acao-excluir"
              title="Excluir backup"
            >
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

.botao-acao-download {
  color: #1890ff;
}

.botao-acao-download:hover {
  background-color: #e6f7ff;
}

.botao-acao-excluir {
  color: #ff4d4f;
}

.botao-acao-excluir:hover {
  background-color: #fff1f0;
}

.icone-download::before {
  content: "\e904"; /* Código do ícone de download */
}

.icone-excluir::before {
  content: "\e905"; /* Código do ícone de excluir */
}

.badge {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.badge-sucesso {
  background-color: #f6ffed;
  border: 1px solid #b7eb8f;
  color: #52c41a;
}

.badge-erro {
  background-color: #fff1f0;
  border: 1px solid #ffa39e;
  color: #ff4d4f;
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

### Modal de Inclusão de Backup

```javascript
document.addEventListener('DOMContentLoaded', function() {
  // Referências aos elementos
  const botaoIncluirBackup = document.querySelector('a[href="/incluir_backup"]');

  // Função para abrir modal de inclusão de backup
  function abrirModalIncluirBackup(event) {
    event.preventDefault();

    // Criar elementos do modal
    const modal = document.createElement('div');
    modal.className = 'modal';

    const modalConteudo = document.createElement('div');
    modalConteudo.className = 'modal-conteudo';

    const modalCabecalho = document.createElement('div');
    modalCabecalho.className = 'modal-cabecalho';

    const modalTitulo = document.createElement('h2');
    modalTitulo.className = 'modal-titulo';
    modalTitulo.textContent = 'Incluir Backup';

    const botaoFechar = document.createElement('button');
    botaoFechar.className = 'modal-botao-fechar';
    botaoFechar.innerHTML = '<span class="icone icone-fechar"></span>';

    const modalCorpo = document.createElement('div');
    modalCorpo.className = 'modal-corpo';

    // Formulário de backup
    modalCorpo.innerHTML = `
      <form class="formulario">
        <div class="formulario-grupo">
          <label class="formulario-label">Tipo de Backup</label>
          <div class="formulario-opcoes">
            <label class="formulario-opcao">
              <input type="radio" name="tipo_backup" value="completo" checked />
              <span class="formulario-opcao-texto">Completo</span>
            </label>
            <label class="formulario-opcao">
              <input type="radio" name="tipo_backup" value="parcial" />
              <span class="formulario-opcao-texto">Parcial</span>
            </label>
          </div>
        </div>

        <div class="formulario-grupo">
          <label class="formulario-label" for="data_backup">Data</label>
          <input type="date" id="data_backup" class="formulario-campo" value="${new Date().toISOString().split('T')[0]}" />
        </div>

        <div class="
(Content truncated due to size limit. Use line ranges to read in chunks)
```
