# Análise do Módulo Cobranças - ERP Revo

## Estrutura Geral

O módulo "Cobranças" do ERP Revo apresenta uma interface para gerenciamento de cobranças de contratos de serviço. A página exibe uma lista de cobranças geradas com opções de filtragem, pesquisa e ações para gerenciamento.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Ações Principais

A seção superior contém o título da página e botões de ação principais:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual">Cobranças</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Cobranças de contratos de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-enviar-boletos">
      <span class="icone icone-enviar"></span>
      <span class="texto">Enviar boletos do mês</span>
    </button>

    <a
      href="/cobrancas/gerar"
      class="botao-acao botao-primario"
      id="btn-gerar-cobrancas"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Gerar cobranças do período</span>
    </a>

    <div class="dropdown">
      <button
        class="botao-acao botao-secundario dropdown-toggle"
        id="btn-mais-acoes"
      >
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu" id="menu-mais-acoes">
        <a href="#" class="dropdown-item" id="btn-exportar">Exportar</a>
        <a href="#" class="dropdown-item" id="btn-importar">Importar</a>
        <div class="dropdown-divider"></div>
        <a href="#" class="dropdown-item" id="btn-excluir-selecionados"
          >Excluir selecionados</a
        >
      </div>
    </div>
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

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: 1px solid #1890ff;
}

.botao-primario:hover {
  background-color: #40a9ff;
  border-color: #40a9ff;
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

.dropdown {
  position: relative;
}

.dropdown-toggle {
  display: inline-flex;
  align-items: center;
}

.dropdown-toggle .icone-seta-baixo {
  margin-left: 8px;
  font-size: 12px;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 1000;
  display: none;
  min-width: 160px;
  padding: 8px 0;
  margin: 4px 0 0;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.dropdown-menu.show {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.dropdown-divider {
  height: 1px;
  margin: 8px 0;
  background-color: #f0f0f0;
}
```

### Área de Pesquisa e Filtros

A seção de pesquisa e filtros permite buscar e filtrar cobranças:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-adicionais">
      <a href="#" class="filtro-adicional" id="filtro-mes">
        <span class="icone icone-calendario"></span>
        <span class="texto">Maio</span>
      </a>

      <a href="#" class="filtro-adicional" id="filtro-filtros">
        <span class="icone icone-filtro"></span>
        <span class="texto">filtros</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  padding: 0 24px 16px;
  background-color: #ffffff;
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
  border-right: none;
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
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-pesquisa:hover {
  background-color: #f5f5f5;
}

.botao-pesquisa .icone {
  font-size: 16px;
  color: #666666;
}

.filtros-adicionais {
  display: flex;
  align-items: center;
  margin-left: 16px;
  gap: 8px;
}

.filtro-adicional {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-adicional:hover {
  background-color: #f5f5f5;
}

.filtro-adicional .icone {
  margin-right: 8px;
  font-size: 14px;
}
```

### Área de Conteúdo (Sem Cobranças)

A área de conteúdo exibe uma mensagem quando não há cobranças geradas:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="sem-cobrancas">
    <div class="sem-cobrancas-imagem">
      <img src="/assets/images/sem-cobrancas.svg" alt="Sem cobranças" />
    </div>
    <h2 class="sem-cobrancas-titulo">Sem cobranças geradas para o mês.</h2>
    <p class="sem-cobrancas-texto">
      Para gerar as cobranças você pode clicar em gerar cobranças do período.
    </p>
    <div class="sem-cobrancas-acoes">
      <button
        class="botao-acao botao-primario"
        id="btn-gerar-cobrancas-periodo"
      >
        <span class="texto">gerar cobranças do período</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  padding: 24px;
  background-color: #ffffff;
}

.sem-cobrancas {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  border: 1px solid #f0f0f0;
  border-radius: 4px;
  text-align: center;
}

.sem-cobrancas-imagem {
  margin-bottom: 24px;
}

.sem-cobrancas-imagem img {
  max-width: 200px;
}

.sem-cobrancas-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.sem-cobrancas-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px;
}

.sem-cobrancas-acoes {
  display: flex;
  gap: 8px;
}
```

### Lista de Cobranças

Embora não esteja visível na tela atual devido à ausência de cobranças geradas, a lista de cobranças é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="cobrancas-lista-container">
  <table class="cobrancas-tabela">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-contrato">
          <div class="cabecalho-coluna">
            <span class="texto">Contrato</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-valor">
          <div class="cabecalho-coluna">
            <span class="texto">Valor</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-vencimento">
          <div class="cabecalho-coluna">
            <span class="texto">Vencimento</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-situacao">
          <div class="cabecalho-coluna">
            <span class="texto">Situação</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-acoes">
          <div class="cabecalho-coluna">
            <span class="texto">Ações</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <!-- Exemplo de linha de cobrança -->
      <tr class="linha-cobranca">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-cobranca"
            data-id="12345"
          />
        </td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-contrato">
          <a href="/contratos/visualizar/12345" class="link-contrato"
            >Contrato de Manutenção #12345</a
          >
        </td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-vencimento">15/05/2025</td>
        <td class="coluna-situacao">
          <span class="tag tag-pendente">Pendente</span>
        </td>
        <td class="coluna-acoes">
          <div class="acoes-grupo">
            <button class="botao-acao-tabela" title="Visualizar">
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao-tabela" title="Enviar">
              <span class="icone icone-enviar"></span>
            </button>
            <button class="botao-acao-tabela" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
          </div>
        </td>
      </tr>
    </tbody>
  </table>

  <div class="resumo-rodape">
    <div class="resumo-item">
      <span class="resumo-valor">0</span>
      <span class="resumo-label">quantidade</span>
    </div>
    <div class="resumo-item">
      <span class="resumo-valor">R$ 0,00</span>
      <span class="resumo-label">valor total</span>
    </div>
  </div>

  <button class="botao-voltar-topo" id="btn-voltar-topo" title="Voltar ao topo">
    <span class="icone icone-seta-cima"></span>
  </button>
</div>
```

**Estilos CSS:**

```css
.cobrancas-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
  position: relative;
}

.cobrancas-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.cobrancas-tabela th,
.cobrancas-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.cobrancas-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.cabecalho-coluna {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-coluna .icone-ordenar {
  margin-left: 4px;
  font-size: 12px;
  color: #d9d9d9;
}

.cabecalho-coluna:hover .icone-ordenar {
  color: #1890ff;
}

.linha-cobranca {
  transition: background-color 0.2s ease;
}

.linha-cobranca:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-cliente {
  min-width: 200px;
}

.coluna-contrato {
  min-width: 200px;
}

.link-contrato {
  color: #1890ff;
  text-decoration: none;
}

.link-contrato:hover {
  text-decoration: underline;
}

.coluna-valor {
  width: 120px;
  text-align: right;
}

.coluna-vencimento {
  width: 120px;
}

.coluna-situacao {
  width: 120px;
}

.coluna-acoes {
  width: 120px;
}

.acoes-grupo {
  display: flex;
  gap: 4px;
}

.botao-acao-tabela {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
  border-radius: 4px;
  background-color: transparent;
  border: none;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-acao-tabela:hover {
  background-color: #f5f5f5;
}

.botao-acao-tabela .icone {
  font-size: 16px;
  color: #666666;
}

.botao-acao-tabela:hover .icone-excluir {
  color: #f5222d;
}

.botao-acao-tabela:hover .icone-visualizar {
  color: #1890ff;
}

.botao-acao-tabela:hover .icone-enviar {
  color: #52c41a;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-pendente {
  background-color: #fff7e6;
  color: #fa8c16;
}

.tag-enviado {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-pago {
  background-color: #e6f7ff;
  color: #1890ff;
}

.tag-atrasado {
  background-color: #fff1f0;
  color: #f5222d;
}

.resumo-rodape {
  display: flex;
  align-items: center;
  padding: 16px 0;
  border-top: 1px solid #f0f0f0;
}

.resumo-item {
  display: flex;
  flex-direction: column;
  margin-right: 32px;
}

.resumo-valor {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
}

.resumo-label {
  font-size: 12px;
  color: #666666;
}

.botao-voltar-topo {
  position: fixed;
  bottom: 24px;
  right: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-voltar-topo:hover {
  background-color: #f5f5f5;
}

.botao-voltar-topo .icone {
  font-size: 16px;
  color: #666666;
}
```

## Formulário de Geração de Cobranças

Embora não esteja visível na tela atual, o formulário de geração de cobranças é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Gerar Cobranças do Período</h2>
    <div class="formulario-acoes">
      <button class="botao-acao botao-secundario" id="btn-cancelar">
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao-acao botao-primario" id="btn-gerar">
        <span class="texto">Gerar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <form class="formulario" id="form-gerar-cobrancas">
      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Período</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="mes">Mês *</label>
            <select class="formulario-campo formulario-select" id="mes" name="mes" required>
              <option value="1">Janeiro</option>
              <option value="2">Fevereiro</option>
              <option value="3">Março</option>
              <option value="4">Abril</option>
              <option value="5" selected>Maio</option>
              <option value="6">Junho</option>
              <option value="7">Julho</option>
              <option value="8">Agosto</option>
              <option value="9">Setembro</option>
              <option
(Content truncated due to size limit. Use line ranges to read in chunks)
```
