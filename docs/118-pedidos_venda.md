# Análise do Módulo Pedidos de Venda - ERP Revo

## Estrutura Geral

O módulo "Pedidos de Venda" do ERP Revo apresenta uma interface para gerenciamento de pedidos de venda. A tela principal exibe uma lista de pedidos com opções de filtragem, pesquisa e ações para criar novos pedidos.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

- Título "Pedidos de venda"
- Botão "Imprimir"
- Botão "Incluir pedido"
- Botão "Mais ações"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Pedidos de venda</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <a href="/vendas/novo" class="botao botao-primario" id="btn-incluir-pedido">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir pedido</span>
    </a>
    <div class="dropdown">
      <button class="botao botao-secundario" id="btn-mais-acoes">
        <span class="texto">Mais ações</span>
        <span class="icone icone-seta-baixo"></span>
      </button>
      <div class="dropdown-menu">
        <a href="#" class="dropdown-item">Exportar</a>
        <a href="#" class="dropdown-item">Importar</a>
        <a href="#" class="dropdown-item">Configurações</a>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.modulo-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.titulo-modulo {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.acoes-container {
  display: flex;
  gap: 8px;
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
  text-decoration: none;
}

.botao-primario {
  background-color: #1890ff;
  color: white;
  border: none;
}

.botao-primario:hover {
  background-color: #40a9ff;
}

.botao-secundario {
  background-color: white;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.botao .icone {
  margin-right: 8px;
  font-size: 16px;
}

.dropdown {
  position: relative;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  z-index: 10;
  min-width: 160px;
  padding: 8px 0;
  margin-top: 4px;
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  display: none;
}

.dropdown.ativo .dropdown-menu {
  display: block;
}

.dropdown-item {
  display: block;
  padding: 8px 16px;
  color: #333333;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.dropdown-item:hover {
  background-color: #f5f5f5;
}
```

### Área de Pesquisa e Filtros

A área de pesquisa e filtros permite buscar e filtrar pedidos:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por cliente ou número"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link">
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-filtro"></span>
      <span class="texto">filtros</span>
    </a>
    <a href="#" class="filtro-link filtro-limpar">
      <span class="icone icone-limpar"></span>
      <span class="texto">limpar filtros</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  flex: 1;
  max-width: 500px;
}

.campo-pesquisa {
  position: relative;
}

.input-pesquisa {
  width: 100%;
  padding: 8px 12px;
  padding-right: 40px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.input-pesquisa:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.botao-pesquisa {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #999999;
  cursor: pointer;
}

.filtros-container {
  display: flex;
  gap: 16px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  color: #1890ff;
  text-decoration: none;
  font-size: 14px;
}

.filtro-link:hover {
  text-decoration: underline;
}

.filtro-link .icone {
  margin-right: 4px;
}

.filtro-limpar {
  color: #f5222d;
}
```

### Abas de Situação

As abas de situação permitem filtrar pedidos por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba">Todos</a>
  <a href="#" class="aba aba-ativa">
    Em aberto
    <span class="contador">01</span>
  </a>
  <a href="#" class="aba">Aprovado</a>
  <a href="#" class="aba">Preparando envio</a>
  <a href="#" class="aba">Faturado</a>
  <a href="#" class="aba aba-mais">
    <span class="icone icone-mais"></span>
    <span class="texto">mais</span>
  </a>
  <div class="filtro-ativo">
    <span class="texto">Situação: Em aberto</span>
    <button class="botao-remover-filtro">
      <span class="icone icone-fechar"></span>
    </button>
  </div>
</div>
```

**Estilos CSS:**

```css
.abas-container {
  display: flex;
  align-items: center;
  padding: 0 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
  overflow-x: auto;
}

.aba {
  display: inline-flex;
  align-items: center;
  padding: 12px 16px;
  color: #666666;
  text-decoration: none;
  font-size: 14px;
  border-bottom: 2px solid transparent;
  transition: color 0.2s ease, border-color 0.2s ease;
  white-space: nowrap;
}

.aba:hover {
  color: #1890ff;
}

.aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.aba .contador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20px;
  height: 20px;
  padding: 0 6px;
  margin-left: 6px;
  background-color: #f5f5f5;
  border-radius: 10px;
  font-size: 12px;
  color: #666666;
}

.aba-ativa .contador {
  background-color: #e6f7ff;
  color: #1890ff;
}

.aba .icone {
  margin-right: 4px;
}

.aba-mais {
  color: #1890ff;
}

.filtro-ativo {
  display: inline-flex;
  align-items: center;
  margin-left: 16px;
  padding: 4px 8px;
  background-color: #e6f7ff;
  border-radius: 4px;
  font-size: 12px;
  color: #1890ff;
}

.filtro-ativo .texto {
  margin-right: 4px;
}

.botao-remover-filtro {
  background: none;
  border: none;
  color: #1890ff;
  cursor: pointer;
  padding: 0;
  font-size: 12px;
}
```

### Tabela de Pedidos

A tabela exibe a lista de pedidos:

**Estrutura HTML:**

```html
<div class="tabela-container">
  <table class="tabela-pedidos">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar-todos" />
        </th>
        <th class="coluna-numero">
          <div class="cabecalho-ordenavel">
            <span class="texto">Nº</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data">
          <div class="cabecalho-ordenavel">
            <span class="texto">Data</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-previsto">
          <div class="cabecalho-ordenavel">
            <span class="texto">Previsto</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-ordenavel">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-documento">
          <div class="cabecalho-ordenavel">
            <span class="texto">CNPJ / CPF</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-total">
          <div class="cabecalho-ordenavel">
            <span class="texto">Total</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-pedido">
          <div class="cabecalho-ordenavel">
            <span class="texto">Nº pedido</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-rastreamento">Rastreamento</th>
        <th class="coluna-marcadores">Marcadores</th>
        <th class="coluna-integracao">Integração</th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-pedido">
        <td class="coluna-selecao">
          <input type="checkbox" class="checkbox-selecionar" />
        </td>
        <td class="coluna-numero">
          <a href="/vendas/14" class="link-pedido">14</a>
        </td>
        <td class="coluna-data">15/05/2025</td>
        <td class="coluna-previsto"></td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-documento">50.532.118/0001-39</td>
        <td class="coluna-total">283,33</td>
        <td class="coluna-pedido"></td>
        <td class="coluna-rastreamento"></td>
        <td class="coluna-marcadores"></td>
        <td class="coluna-integracao"></td>
      </tr>
    </tbody>
  </table>
</div>
```

**Estilos CSS:**

```css
.tabela-container {
  flex: 1;
  overflow: auto;
  background-color: #ffffff;
}

.tabela-pedidos {
  width: 100%;
  border-collapse: collapse;
}

.tabela-pedidos th,
.tabela-pedidos td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-pedidos th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-pedidos tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-numero,
.coluna-data,
.coluna-previsto,
.coluna-pedido {
  width: 100px;
}

.coluna-documento {
  width: 150px;
}

.coluna-total {
  width: 100px;
  text-align: right;
}

.coluna-rastreamento,
.coluna-marcadores,
.coluna-integracao {
  width: 120px;
}

.cabecalho-ordenavel {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.cabecalho-ordenavel .icone {
  margin-left: 4px;
  font-size: 12px;
  opacity: 0.5;
}

.cabecalho-ordenavel:hover .icone {
  opacity: 1;
}

.link-pedido {
  color: #1890ff;
  text-decoration: none;
}

.link-pedido:hover {
  text-decoration: underline;
}

.checkbox-selecionar-todos,
.checkbox-selecionar {
  cursor: pointer;
}
```

### Rodapé com Resumo

O rodapé exibe um resumo dos pedidos:

**Estrutura HTML:**

```html
<div class="rodape-container">
  <div class="resumo-container">
    <div class="resumo-item">
      <span class="resumo-valor">01</span>
      <span class="resumo-label">quantidade</span>
    </div>
    <div class="resumo-item">
      <span class="resumo-valor">283,33</span>
      <span class="resumo-label">valor total (R$)</span>
    </div>
  </div>
  <button class="botao-voltar-topo" title="Voltar ao topo">
    <span class="icone icone-seta-cima"></span>
  </button>
</div>
```

**Estilos CSS:**

```css
.rodape-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 24px;
  background-color: #ffffff;
  border-top: 1px solid #f0f0f0;
}

.resumo-container {
  display: flex;
  gap: 24px;
}

.resumo-item {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.resumo-valor {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
}

.resumo-label {
  font-size: 12px;
  color: #999999;
}

.botao-voltar-topo {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #f5f5f5;
  border: none;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-voltar-topo:hover {
  background-color: #e0e0e0;
}
```

## Formulário de Criação/Edição de Pedido

O formulário para criar ou editar pedidos é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-pedido-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Novo Pedido de Venda</h1>
    </div>
    <div class="acoes-container">
      <button class="botao botao-secundario" id="btn-cancelar">
        <span class="icone icone-cancelar"></span>
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao botao-primario" id="btn-salvar">
        <span class="icone icone-salvar"></span>
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <div class="formulario-secao">
      <h2 class="secao-titulo">Informações Gerais</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="numero" class="formulario-label">Número</label>
          <input
            type="text"
            id="numero"
            class="formulario-input"
            value="15"
            readonly
          />
        </div>

        <div class="formulario-grupo">
          <label for="data" class="formulario-label">Data</label>
          <input type="date" id="data" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="data_prevista" class="formulario-label"
            >Data Prevista</label
          >
          <input type="date" id="data_prevista" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="situacao" class="formulario-label">Situação</label>
          <select id="situacao" class="formulario-select" required>
            <option value="em_aberto">Em aberto</option>
            <option value="aprovado">Aprovado</option>
            <option value="preparando_envio">Preparando envio</option>
            <option value="faturado">Faturado</option>
            <option value="cancelado">Cancelado</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="origem" class="formulario-label">Origem</label>
          <select id="origem" class="formulario-select">
            <option value="manual">Manual</option>
            <option value="proposta">Proposta Comercial</option>
            <option value="ecommerce">E-commerce</option>
            <option value="marketplace">Marketplace</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="numero_externo" class="formulario-label"
            >Número Externo</label
          >
          <input type="text" id="numero_externo" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="vendedor" class="formulario-label">Vendedor</label>
          <div class="campo-busca">
            <input
              type="text"
              id="vendedor"
              class="formulario-input"
              placeholder="Buscar vendedor..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Cliente</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="cliente" class="formulario-label">Cliente</label>
          <div class="campo-busca">
            <input
              type="text"
              id="cliente"
              class="formulario-input"
              placeholder="Buscar cliente..."
              required
            />

            (Content truncated due to size limit. Use line ranges to read in
            chunks)
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
```
