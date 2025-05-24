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
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="contato" class="formulario-label">Contato</label>
          <input type="text" id="contato" class="formulario-input" />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="email" class="formulario-label">E-mail</label>
          <input type="email" id="email" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="telefone" class="formulario-label">Telefone</label>
          <input type="tel" id="telefone" class="formulario-input" />
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Endereço de Entrega</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="cep" class="formulario-label">CEP</label>
          <input
            type="text"
            id="cep"
            class="formulario-input"
            placeholder="00000-000"
          />
        </div>

        <div class="formulario-grupo formulario-grupo-grande">
          <label for="endereco" class="formulario-label">Endereço</label>
          <input type="text" id="endereco" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="numero" class="formulario-label">Número</label>
          <input type="text" id="numero_endereco" class="formulario-input" />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="complemento" class="formulario-label">Complemento</label>
          <input type="text" id="complemento" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="bairro" class="formulario-label">Bairro</label>
          <input type="text" id="bairro" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="cidade" class="formulario-label">Cidade</label>
          <input type="text" id="cidade" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="estado" class="formulario-label">Estado</label>
          <select id="estado" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="AC">AC</option>
            <option value="AL">AL</option>
            <!-- Outros estados -->
            <option value="SP">SP</option>
            <option value="TO">TO</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Produtos</h2>

      <div class="formulario-tabela">
        <table class="tabela-produtos">
          <thead>
            <tr>
              <th class="coluna-produto">Produto</th>
              <th class="coluna-quantidade">Quantidade</th>
              <th class="coluna-unitario">Valor Unitário</th>
              <th class="coluna-desconto">Desconto</th>
              <th class="coluna-total">Total</th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <tr class="linha-adicionar">
              <td colspan="6">
                <button class="botao-adicionar-produto">
                  <span class="icone icone-adicionar"></span>
                  <span class="texto">Adicionar Produto</span>
                </button>
              </td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Subtotal:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Desconto:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Frete:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="3"></td>
              <td class="rodape-label">Total:</td>
              <td class="rodape-valor total">R$ 0,00</td>
              <td></td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Transporte</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="transportadora" class="formulario-label"
            >Transportadora</label
          >
          <div class="campo-busca">
            <input
              type="text"
              id="transportadora"
              class="formulario-input"
              placeholder="Buscar transportadora..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="frete_por_conta" class="formulario-label"
            >Frete por Conta</label
          >
          <select id="frete_por_conta" class="formulario-select">
            <option value="emitente">Emitente</option>
            <option value="destinatario">Destinatário</option>
            <option value="terceiros">Terceiros</option>
            <option value="sem_frete">Sem Frete</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="valor_frete" class="formulario-label"
            >Valor do Frete</label
          >
          <input
            type="text"
            id="valor_frete"
            class="formulario-input"
            placeholder="0,00"
          />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="volumes" class="formulario-label">Volumes</label>
          <input
            type="number"
            id="volumes"
            class="formulario-input"
            min="0"
            value="1"
          />
        </div>

        <div class="formulario-grupo">
          <label for="peso_bruto" class="formulario-label"
            >Peso Bruto (kg)</label
          >
          <input
            type="text"
            id="peso_bruto"
            class="formulario-input"
            placeholder="0,000"
          />
        </div>

        <div class="formulario-grupo">
          <label for="peso_liquido" class="formulario-label"
            >Peso Líquido (kg)</label
          >
          <input
            type="text"
            id="peso_liquido"
            class="formulario-input"
            placeholder="0,000"
          />
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Pagamento</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="forma_pagamento" class="formulario-label"
            >Forma de Pagamento</label
          >
          <select id="forma_pagamento" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="dinheiro">Dinheiro</option>
            <option value="cartao_credito">Cartão de Crédito</option>
            <option value="cartao_debito">Cartão de Débito</option>
            <option value="boleto">Boleto</option>
            <option value="pix">PIX</option>
            <option value="transferencia">Transferência Bancária</option>
            <option value="cheque">Cheque</option>
            <option value="crediario">Crediário</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="condicao_pagamento" class="formulario-label"
            >Condição de Pagamento</label
          >
          <select id="condicao_pagamento" class="formulario-select">
            <option value="">Selecione...</option>
            <option value="a_vista">À Vista</option>
            <option value="30_dias">30 Dias</option>
            <option value="30_60_dias">30/60 Dias</option>
            <option value="30_60_90_dias">30/60/90 Dias</option>
            <option value="personalizado">Personalizado</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha parcelas-container" style="display: none;">
        <div class="formulario-grupo formulario-grupo-completo">
          <label class="formulario-label">Parcelas</label>
          <div class="tabela-parcelas-container">
            <table class="tabela-parcelas">
              <thead>
                <tr>
                  <th>Número</th>
                  <th>Vencimento</th>
                  <th>Valor</th>
                  <th>Forma de Pagamento</th>
                </tr>
              </thead>
              <tbody>
                <!-- Parcelas serão adicionadas dinamicamente -->
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Observações</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <textarea
            id="observacoes"
            class="formulario-textarea"
            rows="4"
          ></textarea>
        </div>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.formulario-pedido-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-color: #f5f5f5;
}

.formulario-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.titulo-formulario {
  font-size: 24px;
  font-weight: 500;
  color: #333333;
  margin: 0;
}

.formulario-conteudo {
  flex: 1;
  padding: 24px;
  overflow: auto;
}

.formulario-secao {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
  overflow: hidden;
}

.secao-titulo {
  font-size: 16px;
  font-weight: 500;
  color: #333333;
  margin: 0;
  padding: 16px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  padding: 16px;
}

.formulario-grupo {
  flex: 1;
  min-width: 200px;
}

.formulario-grupo-grande {
  flex: 2;
  min-width: 300px;
}

.formulario-grupo-completo {
  width: 100%;
}

.formulario-label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #666666;
}

.formulario-input,
.formulario-select,
.formulario-textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.formulario-input:focus,
.formulario-select:focus,
.formulario-textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.formulario-input[readonly] {
  background-color: #f5f5f5;
  cursor: not-allowed;
}

.campo-busca {
  position: relative;
}

.botao-busca {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: #999999;
  cursor: pointer;
}

.formulario-tabela {
  padding: 0 16px 16px;
}

.tabela-produtos,
.tabela-parcelas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-produtos th,
.tabela-produtos td,
.tabela-parcelas th,
.tabela-parcelas td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-produtos th,
.tabela-parcelas th {
  font-weight: 500;
  color: #666666;
}

.coluna-quantidade,
.coluna-unitario,
.coluna-desconto,
.coluna-total {
  width: 120px;
}

.coluna-acoes {
  width: 60px;
  text-align: center;
}

.linha-adicionar td {
  padding: 16px 0;
  text-align: center;
}

.botao-adicionar-produto {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  background-color: transparent;
  border: 1px dashed #1890ff;
  border-radius: 4px;
  color: #1890ff;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-adicionar-produto:hover {
  background-color: #e6f7ff;
}

.botao-adicionar-produto .icone {
  margin-right: 8px;
}

.rodape-label {
  text-align: right;
  font-weight: 500;
  color: #666666;
}

.rodape-valor {
  text-align: right;
  font-weight: 500;
  color: #333333;
}

.rodape-valor.total {
  font-size: 16px;
  color: #1890ff;
}
```

## Interações JavaScript

### Dropdown de Mais Ações

```javascript
// Código para dropdown de mais ações
document
  .querySelector("#btn-mais-acoes")
  .addEventListener("click", function (e) {
    e.preventDefault();
    const dropdown = this.closest(".dropdown");
    dropdown.classList.toggle("ativo");

    // Fecha o dropdown ao clicar fora
    document.addEventListener("click", function fecharDropdown(e) {
      if (!dropdown.contains(e.target)) {
        dropdown.classList.remove("ativo");
        document.removeEventListener("click", fecharDropdown);
      }
    });
  });
```

### Filtros e Abas

```javascript
// Código para seleção de abas
document.querySelectorAll(".aba").forEach((aba) => {
  aba.addEventListener("click", function (e) {
    e.preventDefault();

    // Remove a classe ativa de todas as abas
    document.querySelectorAll(".aba").forEach((a) => {
      a.classList.remove("aba-ativa");
    });

    // Adiciona a classe ativa na aba clicada
    this.classList.add("aba-ativa");

    // Atualiza o filtro ativo
    const filtroAtivo = document.querySelector(".filtro-ativo");
    if (this.classList.contains("aba-mais")) {
      filtroAtivo.style.display = "none";
    } else {
      filtroAtivo.style.display = "inline-flex";
      const textoAba = this.textContent.trim().replace(/\d+/g, "").trim();
      filtroAtivo.querySelector(".texto").textContent = `Situação: ${textoAba}`;
    }

    // Carrega os pedidos com o filtro selecionado
    carregarPedidos(this.textContent.trim());
  });
});

// Código para remover filtro
document
  .querySelector(".botao-remover-filtro")
  .addEventListener("click", function () {
    // Ativa a aba "Todos"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todos")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Esconde o filtro ativo
    document.querySelector(".filtro-ativo").style.display = "none";

    // Carrega todos os pedidos
    carregarPedidos("Todos");
  });

// Código para limpar filtros
document
  .querySelector(".filtro-limpar")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Limpa os filtros de data e outros
    // ...

    // Ativa a aba "Todos"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todos")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Esconde o filtro ativo
    document.querySelector(".filtro-ativo").style.display = "none";

    // Carrega todos os pedidos
    carregarPedidos("Todos");
  });

function carregarPedidos(filtro) {
  // Simulação de carregamento de pedidos
  console.log(`Carregando pedidos com filtro: ${filtro}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/pedidos?filtro=' + encodeURIComponent(filtro))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaPedidos(data);
  //   });
}
```

### Pesquisa

```javascript
// Código para pesquisa
document
  .querySelector(".input-pesquisa")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      pesquisarPedidos(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarPedidos(termoPesquisa);
  });

function pesquisarPedidos(termo) {
  if (!termo) return;

  console.log(`Pesquisando pedidos com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/pedidos/pesquisa?termo=' + encodeURIComponent(termo))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaPedidos(data);
  //   });
}
```

### Seleção de Pedidos

```javascript
// Código para seleção de pedidos
document
  .querySelector(".checkbox-selecionar-todos")
  .addEventListener("change", function () {
    const checkboxes = document.querySelectorAll(".checkbox-selecionar");
    checkboxes.forEach((checkbox) => {
      checkbox.checked = this.checked;
    });
  });

// Atualiza o checkbox "selecionar todos" quando os checkboxes individuais são alterados
document.addEventListener("change", function (e) {
  if (e.target.classList.contains("checkbox-selecionar")) {
    const checkboxes = document.querySelectorAll(".checkbox-selecionar");
    const checkboxSelecionarTodos = document.querySelector(
      ".checkbox-selecionar-todos"
    );

    const todosSelecionados = Array.from(checkboxes).every(
      (checkbox) => checkbox.checked
    );
    const algunsSelecionados = Array.from(checkboxes).some(
      (checkbox) => checkbox.checked
    );

    checkboxSelecionarTodos.checked = todosSelecionados;
    checkboxSelecionarTodos.indeterminate =
      algunsSelecionados && !todosSelecionados;
  }
});
```

### Ordenação da Tabela

```javascript
// Código para ordenação da tabela
document.querySelectorAll(".cabecalho-ordenavel").forEach((cabecalho) => {
  cabecalho.addEventListener("click", function () {
    const coluna = this.closest("th").className.replace("coluna-", "");
    const direcaoAtual = this.getAttribute("data-direcao") || "asc";
    const novaDirecao = direcaoAtual === "asc" ? "desc" : "asc";

    // Remove a direção de todas as colunas
    document.querySelectorAll(".cabecalho-ordenavel").forEach((c) => {
      c.removeAttribute("data-direcao");
      c.querySelector(".icone").className = "icone icone-ordenar";
    });

    // Define a direção na coluna clicada
    this.setAttribute("data-direcao", novaDirecao);
    this.querySelector(
      ".icone"
    ).className = `icone icone-ordenar-${novaDirecao}`;

    // Ordena a tabela
    ordenarTabela(coluna, novaDirecao);
  });
});

function ordenarTabela(coluna, direcao) {
  console.log(`Ordenando tabela por ${coluna} em ordem ${direcao}`);

  // Aqui seria feita uma requisição para a API ou ordenação local
  // fetch(`/api/pedidos?ordenar_por=${coluna}&direcao=${direcao}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaPedidos(data);
  //   });
}
```

### Botão Voltar ao Topo

```javascript
// Código para botão voltar ao topo
document
  .querySelector(".botao-voltar-topo")
  .addEventListener("click", function () {
    window.scrollTo({
      top: 0,
      behavior: "smooth",
    });
  });
```

### Formulário de Pedido

```javascript
// Código para formulário de pedido
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioPedido = document.querySelector(
    ".formulario-pedido-container"
  );
  if (!formularioPedido) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data").value = hoje;

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação do pedido? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/vendas";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-pedido-container");

    // Verifica campos obrigatórios
    const camposObrigatorios = form.querySelectorAll("[required]");
    let valido = true;

    camposObrigatorios.forEach((campo) => {
      if (!campo.value) {
        campo.classList.add("campo-invalido");
        valido = false;
      } else {
        campo.classList.remove("campo-invalido");
      }
    });

    if (!valido) {
      alert("Preencha todos os campos obrigatórios");
      return;
    }

    // Verifica se há produtos no pedido
    const produtos = document.querySelectorAll(
      ".tabela-produtos tbody tr:not(.linha-adicionar)"
    );
    if (produtos.length === 0) {
      alert("Adicione pelo menos um produto ao pedido");
      return;
    }

    // Coleta os dados do formulário
    const pedido = {
      numero: document.querySelector("#numero").value,
      data: document.querySelector("#data").value,
      data_prevista: document.querySelector("#data_prevista").value,
      situacao: document.querySelector("#situacao").value,
      origem: document.querySelector("#origem").value,
      numero_externo: document.querySelector("#numero_externo").value,
      vendedor: document.querySelector("#vendedor").value,
      cliente: document.querySelector("#cliente").value,
      contato: document.querySelector("#contato").value,
      email: document.querySelector("#email").value,
      telefone: document.querySelector("#telefone").value,
      endereco: {
        cep: document.querySelector("#cep").value,
        endereco: document.querySelector("#endereco").value,
        numero: document.querySelector("#numero_endereco").value,
        complemento: document.querySelector("#complemento").value,
        bairro: document.querySelector("#bairro").value,
        cidade: document.querySelector("#cidade").value,
        estado: document.querySelector("#estado").value,
      },
      transporte: {
        transportadora: document.querySelector("#transportadora").value,
        frete_por_conta: document.querySelector("#frete_por_conta").value,
        valor_frete: document.querySelector("#valor_frete").value,
        volumes: document.querySelector("#volumes").value,
        peso_bruto: document.querySelector("#peso_bruto").value,
        peso_liquido: document.querySelector("#peso_liquido").value,
      },
      pagamento: {
        forma: document.querySelector("#forma_pagamento").value,
        condicao: document.querySelector("#condicao_pagamento").value,
        parcelas: [],
      },
      observacoes: document.querySelector("#observacoes").value,
      produtos: [],
    };

    // Coleta os produtos
    document
      .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
      .forEach((linha) => {
        const produto = {
          produto: linha.querySelector(".coluna-produto input").value,
          quantidade: parseFloat(
            linha.querySelector(".coluna-quantidade input").value
          ),
          valor_unitario: parseFloat(
            linha.querySelector(".coluna-unitario input").value
          ),
          desconto: parseFloat(
            linha.querySelector(".coluna-desconto input").value || 0
          ),
          total: parseFloat(
            linha.querySelector(".coluna-total").getAttribute("data-valor")
          ),
        };

        pedido.produtos.push(produto);
      });

    // Coleta as parcelas
    document.querySelectorAll(".tabela-parcelas tbody tr").forEach((linha) => {
      const parcela = {
        numero: linha.querySelector("td:nth-child(1)").textContent,
        vencimento: linha.querySelector("td:nth-child(2) input").value,
        valor: parseFloat(linha.querySelector("td:nth-child(3) input").value),
        forma_pagamento: linha.querySelector("td:nth-child(4) select").value,
      };

      pedido.pagamento.parcelas.push(parcela);
    });

    // Envia para a API
    console.log("Salvando pedido:", pedido);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Pedido salvo com sucesso!");
      window.location.href = "/vendas";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/pedidos', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(pedido)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Pedido salvo com sucesso!');
    //     window.location.href = '/vendas';
    //   } else {
    //     throw new Error('Erro ao salvar pedido');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar pedido: ${error.message}`);
    // });
  });

  // Botão de adicionar produto
  document
    .querySelector(".botao-adicionar-produto")
    .addEventListener("click", function () {
      adicionarLinhaProduto();
    });

  // Condição de pagamento
  document
    .querySelector("#condicao_pagamento")
    .addEventListener("change", function () {
      const condicao = this.value;
      const parcelasContainer = document.querySelector(".parcelas-container");

      if (condicao === "personalizado") {
        parcelasContainer.style.display = "flex";
        gerarParcelas(1);
      } else if (condicao === "30_dias") {
        parcelasContainer.style.display = "flex";
        gerarParcelas(1, 30);
      } else if (condicao === "30_60_dias") {
        parcelasContainer.style.display = "flex";
        gerarParcelas(2, 30);
      } else if (condicao === "30_60_90_dias") {
        parcelasContainer.style.display = "flex";
        gerarParcelas(3, 30);
      } else {
        parcelasContainer.style.display = "none";
      }
    });

  // CEP
  document.querySelector("#cep").addEventListener("blur", function () {
    const cep = this.value.replace(/\D/g, "");

    if (cep.length === 8) {
      // Busca o CEP
      fetch(`https://viacep.com.br/ws/${cep}/json/`)
        .then((response) => response.json())
        .then((data) => {
          if (!data.erro) {
            document.querySelector("#endereco").value = data.logradouro;
            document.querySelector("#bairro").value = data.bairro;
            document.querySelector("#cidade").value = data.localidade;
            document.querySelector("#estado").value = data.uf;
            document.querySelector("#numero_endereco").focus();
          }
        });
    }
  });
});

function adicionarLinhaProduto() {
  const tbody = document.querySelector(".tabela-produtos tbody");
  const linhaAdicionar = document.querySelector(".linha-adicionar");

  const tr = document.createElement("tr");
  tr.innerHTML = `
    <td class="coluna-produto">
      <div class="campo-busca">
        <input type="text" class="formulario-input input-produto" placeholder="Buscar produto..." required>
        <button class="botao-busca">
          <span class="icone icone-busca"></span>
        </button>
      </div>
    </td>
    <td class="coluna-quantidade">
      <input type="number" class="formulario-input input-quantidade" value="1" min="1" step="1" required>
    </td>
    <td class="coluna-unitario">
      <input type="number" class="formulario-input input-unitario" value="0.00" min="0" step="0.01" required>
    </td>
    <td class="coluna-desconto">
      <input type="number" class="formulario-input input-desconto" value="0.00" min="0" step="0.01">
    </td>
    <td class="coluna-total" data-valor="0.00">R$ 0,00</td>
    <td class="coluna-acoes">
      <button class="botao-remover">
        <span class="icone icone-remover"></span>
      </button>
    </td>
  `;

  tbody.insertBefore(tr, linhaAdicionar);

  // Adiciona eventos
  const inputProduto = tr.querySelector(".input-produto");
  inputProduto.addEventListener("focus", function () {
    // Abre modal de busca de produtos
    buscarProduto(this);
  });

  const inputQuantidade = tr.querySelector(".input-quantidade");
  const inputUnitario = tr.querySelector(".input-unitario");
  const inputDesconto = tr.querySelector(".input-desconto");

  [inputQuantidade, inputUnitario, inputDesconto].forEach((input) => {
    input.addEventListener("change", function () {
      atualizarTotalLinha(tr);
      atualizarTotais();
    });
  });

  tr.querySelector(".botao-remover").addEventListener("click", function () {
    tr.remove();
    atualizarTotais();
  });

  // Foca no campo de produto
  inputProduto.focus();
}

function buscarProduto(input) {
  // Simulação de busca de produto
  const produtos = [
    {
      id: 1,
      codigo: "P001",
      descricao: "Produto 1",
      preco: 100.0,
      estoque: 50,
    },
    {
      id: 2,
      codigo: "P002",
      descricao: "Produto 2",
      preco: 200.0,
      estoque: 30,
    },
    {
      id: 3,
      codigo: "P003",
      descricao: "Produto 3",
      preco: 150.0,
      estoque: 20,
    },
  ];

  // Cria o modal
  const modal = document.createElement("div");
  modal.classList.add("modal");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Produto</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="campo-busca">
          <input type="text" class="formulario-input input-busca-produto" placeholder="Buscar produto...">
          <button class="botao-busca">
            <span class="icone icone-busca"></span>
          </button>
        </div>
        <div class="lista-produtos">
          <table class="tabela-selecao-produtos">
            <thead>
              <tr>
                <th>Código</th>
                <th>Descrição</th>
                <th>Preço</th>
                <th>Estoque</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              ${produtos
                .map(
                  (produto) => `
                <tr data-produto-id="${produto.id}">
                  <td>${produto.codigo}</td>
                  <td>${produto.descricao}</td>
                  <td>R$ ${produto.preco.toFixed(2)}</td>
                  <td>${produto.estoque}</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
              `
                )
                .join("")}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal.querySelectorAll(".botao-selecionar").forEach((botao) => {
    botao.addEventListener("click", function () {
      const linha = this.closest("tr");
      const produtoId = linha.getAttribute("data-produto-id");
      const produto = produtos.find((p) => p.id.toString() === produtoId);

      // Preenche os campos
      const tr = input.closest("tr");
      input.value = produto.descricao;
      tr.querySelector(".input-unitario").value = produto.preco.toFixed(2);

      // Atualiza os totais
      atualizarTotalLinha(tr);
      atualizarTotais();

      // Fecha o modal
      document.body.removeChild(modal);
    });
  });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
}

function atualizarTotalLinha(linha) {
  const quantidade = parseFloat(linha.querySelector(".input-quantidade").value);
  const valorUnitario = parseFloat(
    linha.querySelector(".input-unitario").value
  );
  const desconto = parseFloat(
    linha.querySelector(".input-desconto").value || 0
  );

  const total = quantidade * valorUnitario - desconto;
  linha.querySelector(".coluna-total").textContent = `R$ ${total.toFixed(2)}`;
  linha
    .querySelector(".coluna-total")
    .setAttribute("data-valor", total.toFixed(2));
}

function atualizarTotais() {
  let subtotal = 0;
  let desconto = 0;
  let frete = parseFloat(document.querySelector("#valor_frete")?.value || 0);

  // Calcula o subtotal e desconto
  document
    .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
    .forEach((linha) => {
      const quantidade = parseFloat(
        linha.querySelector(".input-quantidade").value
      );
      const valorUnitario = parseFloat(
        linha.querySelector(".input-unitario").value
      );
      const descontoLinha = parseFloat(
        linha.querySelector(".input-desconto").value || 0
      );

      subtotal += quantidade * valorUnitario;
      desconto += descontoLinha;
    });

  // Atualiza os valores no rodapé
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(1) .rodape-valor"
  ).textContent = `R$ ${subtotal.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(2) .rodape-valor"
  ).textContent = `R$ ${desconto.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(3) .rodape-valor"
  ).textContent = `R$ ${frete.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(4) .rodape-valor"
  ).textContent = `R$ ${(subtotal - desconto + frete).toFixed(2)}`;

  // Atualiza os valores das parcelas
  atualizarParcelas(subtotal - desconto + frete);
}

function gerarParcelas(quantidade, intervalo = 30) {
  const tbody = document.querySelector(".tabela-parcelas tbody");
  tbody.innerHTML = "";

  const total = parseFloat(
    document
      .querySelector(".tabela-produtos tfoot tr:nth-child(4) .rodape-valor")
      .textContent.replace("R$ ", "")
  );
  const valorParcela = total / quantidade;

  const hoje = new Date();

  for (let i = 1; i <= quantidade; i++) {
    const tr = document.createElement("tr");

    const dataVencimento = new Date(hoje);
    dataVencimento.setDate(dataVencimento.getDate() + i * intervalo);
    const dataFormatada = dataVencimento.toISOString().split("T")[0];

    tr.innerHTML = `
      <td>${i}</td>
      <td><input type="date" class="formulario-input input-vencimento" value="${dataFormatada}"></td>
      <td><input type="text" class="formulario-input input-valor" value="${valorParcela.toFixed(
        2
      )}"></td>
      <td>
        <select class="formulario-select input-forma-pagamento">
          <option value="">Selecione...</option>
          <option value="dinheiro">Dinheiro</option>
          <option value="cartao_credito">Cartão de Crédito</option>
          <option value="cartao_debito">Cartão de Débito</option>
          <option value="boleto">Boleto</option>
          <option value="pix">PIX</option>
          <option value="transferencia">Transferência Bancária</option>
          <option value="cheque">Cheque</option>
        </select>
      </td>
    `;

    tbody.appendChild(tr);
  }

  // Adiciona eventos
  document.querySelectorAll(".input-valor").forEach((input) => {
    input.addEventListener("change", function () {
      // Verifica se o total das parcelas é igual ao total do pedido
      let totalParcelas = 0;
      document.querySelectorAll(".input-valor").forEach((input) => {
        totalParcelas += parseFloat(input.value);
      });

      const totalPedido = parseFloat(
        document
          .querySelector(".tabela-produtos tfoot tr:nth-child(4) .rodape-valor")
          .textContent.replace("R$ ", "")
      );

      if (Math.abs(totalParcelas - totalPedido) > 0.01) {
        alert(
          `O total das parcelas (R$ ${totalParcelas.toFixed(
            2
          )}) é diferente do total do pedido (R$ ${totalPedido.toFixed(2)})`
        );
      }
    });
  });
}

function atualizarParcelas(total) {
  const parcelas = document.querySelectorAll(".tabela-parcelas tbody tr");
  if (parcelas.length === 0) return;

  const valorParcela = total / parcelas.length;

  parcelas.forEach((parcela) => {
    parcela.querySelector(".input-valor").value = valorParcela.toFixed(2);
  });
}
```

## Responsividade

O módulo é responsivo e se adapta a diferentes tamanhos de tela:

```css
/* Estilos para telas médias */
@media (max-width: 1024px) {
  .formulario-linha {
    flex-direction: column;
  }

  .formulario-grupo,
  .formulario-grupo-grande {
    width: 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .modulo-cabecalho,
  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-end;
  }

  .pesquisa-filtros-container {
    flex-direction: column;
  }

  .pesquisa-container {
    width: 100%;
    max-width: none;
    margin-bottom: 16px;
  }

  .abas-container {
    flex-wrap: wrap;
  }

  .aba {
    flex-grow: 1;
    text-align: center;
  }

  .coluna-previsto,
  .coluna-documento,
  .coluna-pedido,
  .coluna-rastreamento,
  .coluna-marcadores,
  .coluna-integracao {
    display: none;
  }

  .resumo-container {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }
}

/* Estilos para telas muito pequenas */
@media (max-width: 480px) {
  .botao .texto {
    display: none;
  }

  .botao .icone {
    margin-right: 0;
  }

  .coluna-cliente {
    display: none;
  }

  .resumo-item {
    align-items: flex-start;
  }
}
```

## Paleta de Cores e Tipografia

### Cores Principais

- Azul primário: #1890ff
- Azul secundário: #40a9ff
- Azul claro (background): #e6f7ff
- Azul muito claro (background): #f0f5ff
- Verde (sucesso): #52c41a
- Verde claro (background sucesso): #f6ffed
- Vermelho (erro): #f5222d
- Vermelho claro (background erro): #fff1f0
- Amarelo (alerta): #faad14
- Amarelo claro (background alerta): #fffbe6
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
  - Títulos de seção: 16px
  - Texto normal: 14px
  - Texto pequeno: 12px
- Pesos de fonte:
  - Regular: 400
  - Médio: 500
  - Negrito: 700

## Componentes Reutilizáveis

### Botões

```css
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
```

### Campos de Formulário

```css
.formulario-input,
.formulario-select,
.formulario-textarea {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}

.formulario-input:focus,
.formulario-select:focus,
.formulario-textarea:focus {
  border-color: #1890ff;
  outline: none;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-invalido {
  border-color: #f5222d;
}

.campo-invalido:focus {
  border-color: #f5222d;
  box-shadow: 0 0 0 2px rgba(245, 34, 45, 0.2);
}
```

### Modais

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
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  width: 100%;
  max-width: 600px;
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
  font-size: 18px;
  font-weight: 500;
  color: #333333;
}

.botao-fechar {
  background: none;
  border: none;
  font-size: 20px;
  color: #999999;
  cursor: pointer;
}

.modal-corpo {
  padding: 24px;
}
```

## Fluxos de Navegação

1. **Listagem de Pedidos**:

   - O usuário acessa o módulo "Pedidos de Venda"
   - Visualiza a lista de pedidos
   - Pode filtrar por situação usando as abas
   - Pode pesquisar por cliente ou número
   - Pode aplicar filtros adicionais

2. **Criação de Pedido**:

   - O usuário clica no botão "Incluir pedido"
   - Preenche as informações gerais do pedido
   - Seleciona um cliente
   - Adiciona produtos ao pedido
   - Configura o endereço de entrega
   - Define o transporte
   - Configura o pagamento
   - Preenche observações (opcional)
   - Salva o pedido

3. **Edição de Pedido**:

   - O usuário clica em um pedido na lista
   - Visualiza os detalhes do pedido
   - Edita as informações necessárias
   - Salva as alterações

4. **Impressão de Pedido**:

   - O usuário seleciona um ou mais pedidos
   - Clica no botão "Imprimir"
   - Visualiza a prévia da impressão
   - Confirma a impressão

5. **Faturamento de Pedido**:
   - O usuário seleciona um pedido aprovado
   - Clica em "Faturar" no menu de ações
   - Confirma o faturamento
   - O sistema gera a nota fiscal

## Conclusão

O módulo "Pedidos de Venda" do ERP Revo apresenta uma interface completa e funcional para gerenciamento de pedidos. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, criar e editar pedidos de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento de pedidos de venda, como criação de pedidos, acompanhamento de status, configuração de entrega e pagamento, e faturamento, atendendo às necessidades de negócios que trabalham com vendas de produtos e serviços.
