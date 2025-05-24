# Análise do Módulo Expedição - ERP Revo

## Estrutura Geral

O módulo "Expedição" do ERP Revo apresenta uma interface para gerenciamento de envios e expedição de mercadorias. A tela principal exibe uma área de pesquisa, filtros, abas de situação e uma lista de expedições quando disponíveis.

## Componentes Principais

### Alerta de Configuração

O módulo exibe um alerta quando os serviços dos correios não estão configurados:

**Estrutura HTML:**

```html
<div class="alerta-configuracao">
  <div class="alerta-mensagem">
    Os serviços dos correios ainda não foram configurados. Para configurar
    acesse as configurações das
    <a href="/configuracoes/formas-envio" class="link-configuracao"
      >Formas de Envio</a
    >.
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-configuracao {
  display: flex;
  align-items: center;
  padding: 12px 24px;
  background-color: #fffbe6;
  border-bottom: 1px solid #faad14;
}

.alerta-mensagem {
  font-size: 14px;
  color: #666666;
}

.link-configuracao {
  color: #1890ff;
  text-decoration: none;
  font-weight: 500;
}

.link-configuracao:hover {
  text-decoration: underline;
}
```

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção e botões de ação principais:

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Expedição</h1>
  </div>
  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-integrar-intelipost">
      <span class="icone icone-integrar"></span>
      <span class="texto">Integrar com a Intelipost</span>
    </button>
    <button class="botao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>
    <button class="botao botao-primario" id="btn-incluir-expedicao">
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir expedição</span>
    </button>
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

A área de pesquisa e filtros permite buscar e filtrar expedições:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise por nº, pedido, nota fiscal ou destinatário"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <div class="filtro-grupo">
      <a href="#" class="filtro-link filtro-agrupamento">
        <span class="icone icone-agrupamento"></span>
        <span class="texto">Agrupamentos</span>
      </a>
      <a href="#" class="filtro-link filtro-forma-envio">
        <span class="texto">por forma de envio</span>
      </a>
    </div>
    <div class="filtro-grupo">
      <a href="#" class="filtro-link filtro-mes-atual">
        <span class="icone icone-calendario"></span>
        <span class="texto">Maio</span>
      </a>
      <a href="#" class="filtro-link filtro-limpar">
        <span class="icone icone-limpar"></span>
        <span class="texto">limpar filtros</span>
      </a>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.pesquisa-filtros-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
  padding: 16px 24px;
  background-color: #ffffff;
  border-bottom: 1px solid #f0f0f0;
}

.pesquisa-container {
  display: flex;
  align-items: center;
  gap: 8px;
  width: 100%;
}

.campo-pesquisa {
  position: relative;
  flex: 1;
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
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
}

.filtro-grupo {
  display: flex;
  align-items: center;
  gap: 8px;
}

.filtro-link {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 14px;
  color: #1890ff;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.filtro-link:hover {
  background-color: #f0f5ff;
}

.filtro-agrupamento,
.filtro-forma-envio,
.filtro-mes-atual {
  background-color: #f0f5ff;
  border: 1px solid #d6e4ff;
}

.filtro-limpar {
  color: #f5222d;
}

.filtro-link .icone {
  margin-right: 8px;
}
```

### Abas de Situação

As abas de situação permitem filtrar expedições por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">
    <span class="indicador indicador-pendente"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-concluida"></span>
    <span class="texto">Concluídas</span>
  </a>
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

.indicador {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-pendente {
  background-color: #faad14;
}

.indicador-concluida {
  background-color: #52c41a;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há expedições ou quando a pesquisa não retorna resultados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-vazio">
    <div class="mensagem-vazio">
      <h2 class="titulo-vazio">Sua pesquisa não retornou resultados.</h2>
      <p class="texto-vazio">
        Tente outras opções de pesquisa, situações ou remova os filtros.
      </p>
    </div>

    <div class="ilustracao-vazio">
      <img
        src="/assets/images/ilustracao-sem-resultados.svg"
        alt="Sem resultados"
      />
    </div>

    <div class="acoes-vazio">
      <button class="botao botao-primario" id="btn-alterar-pesquisa">
        <span class="texto">alterar pesquisa</span>
      </button>
      <button class="botao botao-secundario" id="btn-limpar-filtros">
        <span class="texto">limpar filtros</span>
      </button>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-container {
  flex: 1;
  padding: 24px;
  background-color: #f5f5f5;
  overflow: auto;
}

.conteudo-vazio {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 600px;
  margin: 0 auto;
  padding: 32px;
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
}

.mensagem-vazio {
  text-align: center;
  margin-bottom: 24px;
}

.titulo-vazio {
  font-size: 18px;
  font-weight: 500;
  color: #333333;
  margin: 0 0 8px 0;
}

.texto-vazio {
  font-size: 14px;
  color: #666666;
  margin: 0;
}

.ilustracao-vazio {
  margin-bottom: 24px;
}

.ilustracao-vazio img {
  max-width: 100%;
  height: auto;
  max-height: 200px;
}

.acoes-vazio {
  display: flex;
  gap: 12px;
}
```

### Tabela de Expedições

Quando houver expedições, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-expedicoes">
      <thead>
        <tr>
          <th class="coluna-selecao">
            <input type="checkbox" class="checkbox-selecionar-todos" />
          </th>
          <th class="coluna-situacao"></th>
          <th class="coluna-numero">
            <div class="cabecalho-ordenavel">
              <span class="texto">Número</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data">
            <div class="cabecalho-ordenavel">
              <span class="texto">Data</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-pedido">
            <div class="cabecalho-ordenavel">
              <span class="texto">Pedido</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-nota">
            <div class="cabecalho-ordenavel">
              <span class="texto">Nota Fiscal</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-destinatario">
            <div class="cabecalho-ordenavel">
              <span class="texto">Destinatário</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-forma-envio">
            <div class="cabecalho-ordenavel">
              <span class="texto">Forma de Envio</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-rastreamento">
            <div class="cabecalho-ordenavel">
              <span class="texto">Rastreamento</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Expedições serão adicionadas dinamicamente -->
      </tbody>
    </table>

    <div class="paginacao">
      <div class="paginacao-info">
        <span class="texto">Exibindo 0 de 0 registros</span>
      </div>
      <div class="paginacao-controles">
        <button class="botao-paginacao" disabled>
          <span class="icone icone-primeira-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-pagina-anterior"></span>
        </button>
        <span class="paginacao-pagina">Página 1 de 1</span>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-proxima-pagina"></span>
        </button>
        <button class="botao-paginacao" disabled>
          <span class="icone icone-ultima-pagina"></span>
        </button>
      </div>
      <div class="paginacao-por-pagina">
        <span class="texto">Itens por página:</span>
        <select class="select-por-pagina">
          <option value="10">10</option>
          <option value="25">25</option>
          <option value="50">50</option>
          <option value="100">100</option>
        </select>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.conteudo-tabela {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.tabela-expedicoes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-expedicoes th,
.tabela-expedicoes td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-expedicoes th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-expedicoes tbody tr:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-situacao {
  width: 40px;
  text-align: center;
}

.coluna-numero,
.coluna-data,
.coluna-pedido,
.coluna-nota {
  width: 100px;
}

.coluna-rastreamento {
  width: 150px;
}

.coluna-acoes {
  width: 80px;
  text-align: center;
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

.paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  border-top: 1px solid #f0f0f0;
}

.paginacao-info,
.paginacao-pagina {
  font-size: 14px;
  color: #666666;
}

.paginacao-controles {
  display: flex;
  align-items: center;
  gap: 8px;
}

.botao-paginacao {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: white;
  color: #666666;
  cursor: pointer;
}

.botao-paginacao:hover:not(:disabled) {
  background-color: #f5f5f5;
}

.botao-paginacao:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.paginacao-por-pagina {
  display: flex;
  align-items: center;
  gap: 8px;
}

.paginacao-por-pagina .texto {
  font-size: 14px;
  color: #666666;
}

.select-por-pagina {
  padding: 4px 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
}
```

## Formulário de Criação/Edição de Expedição

O formulário para criar ou editar expedições é exibido em uma nova página ou modal:

**Estrutura HTML:**

```html
<div class="formulario-expedicao-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Expedição</h1>
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
          <label for="data_expedicao" class="formulario-label"
            >Data de Expedição</label
          >
          <input
            type="date"
            id="data_expedicao"
            class="formulario-input"
            required
          />
        </div>

        <div class="formulario-grupo">
          <label for="pedido" class="formulario-label">Pedido</label>
          <div class="campo-busca">
            <input
              type="text"
              id="pedido"
              class="formulario-input"
              placeholder="Buscar pedido..."
              required
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="nota_fiscal" class="formulario-label">Nota Fiscal</label>
          <div class="campo-busca">
            <input
              type="text"
              id="nota_fiscal"
              class="formulario-input"
              placeholder="Buscar nota fiscal..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-grande">
          <label for="destinatario" class="formulario-label"
            >Destinatário</label
          >
          <input
            type="text"
            id="destinatario"
            class="formulario-input"
            readonly
          />
        </div>

        <div class="formulario-grupo">
          <label for="situacao" class="formulario-label">Situação</label>
          <select id="situacao" class="formulario-select" required>
            <option value="pendente">Pendente</option>
            <option value="concluida">Concluída</option>
          </select>
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Endereço de Entrega</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="cep" class="formulario-label">CEP</label>
          <input type="text" id="cep" class="formulario-input" readonly />
        </div>

        <div class="formulario-grupo formulario-grupo-grande">
          <label for="endereco" class="formulario-label">Endereço</label>
          <input type="text" id="endereco" class="formulario-input" readonly />
        </div>

        <div class="formulario-grupo">
          <label for="numero" class="formulario-label">Número</label>
          <input type="text" id="numero" class="formulario-input" readonly />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="complemento" class="formulario-label">Complemento</label>
          <input
            type="text"
            id="complemento"
            class="formulario-input"
            readonly
          />
        </div>

        <div class="formulario-grupo">
          <label for="bairro" class="formulario-label">Bairro</label>
          <input type="text" id="bairro" class="formulario-input" readonly />
        </div>

        <div class="formulario-grupo">
          <label for="cidade" class="formulario-label">Cidade</label>
          <input type="text" id="cidade" class="formulario-input" readonly />
        </div>

        <div class="formulario-grupo">
          <label for="estado" class="formulario-label">Estado</label>
          <input type="text" id="estado" class="formulario-input" readonly />
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Informações de Envio</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="forma_envio" class="formulario-label"
            >Forma de Envio</label
          >
          <select id="forma_envio" class="formulario-select" required>
            <option value="">Selecione...</option>
            <option value="correios_sedex">Correios - SEDEX</option>
            <option value="correios_pac">Correios - PAC</option>
            <option value="transportadora">Transportadora</option>
            <option value="retirada">Retirada na Loja</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="transportadora" class="formulario-label"
            >Transportadora</label
          >
          <select id="transportadora" class="formulario-select" disabled>
            <option value="">Selecione...</option>
            <option value="transportadora_1">Transportadora 1</option>
            <option value="transportadora_2">Transportadora 2</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="codigo_rastreamento" class="formulario-label"
            >Código de Rastreamento</label
          >
          <input
            type="text"
            id="codigo_rastreamento"
            class="formulario-input"
          />
        </div>
      </div>

      <div class="formulario-linha">
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

        <div class="formulario-grupo">
          <label for="prazo_entrega" class="formulario-label"
            >Prazo de Entrega (dias)</label
          >
          <input
            type="number"
            id="prazo_entrega"
            class="formulario-input"
            min="1"
            value="1"
          />
        </div>

        <div class="formulario-grupo">
          <label for="data_entrega" class="formulario-label"
            >Data Prevista de Entrega</label
          >
          <input type="date" id="data_entrega" class="formulario-input" />
        </div>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Volumes</h2>

      <div class="formulario-tabela">
        <table class="tabela-volumes">
          <thead>
            <tr>
              <th class="coluna-numero">Número</th>
              <th class="coluna-peso">Peso (kg)</th>
              <th class="coluna-altura">Altura (cm)</th>
              <th class="coluna-largura">Largura (cm)</th>
              <th class="coluna-comprimento">Comprimento (cm)</th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="coluna-numero">1</td>
              <td class="coluna-peso">
                <input
                  type="number"
                  class="formulario-input input-peso"
                  value="1.000"
                  min="0.001"
                  step="0.001"
                />
              </td>
              <td class="coluna-altura">
                <input
                  type="number"
                  class="formulario-input input-altura"
                  value="10"
                  min="1"
                  step="1"
                />
              </td>
              <td class="coluna-largura">
                <input
                  type="number"
                  class="formulario-input input-largura"
                  value="10"
                  min="1"
                  step="1"
                />
              </td>
              <td class="coluna-comprimento">
                <input
                  type="number"
                  class="formulario-input input-comprimento"
                  value="10"
                  min="1"
                  step="1"
                />
              </td>
              <td class="coluna-acoes">
                <button class="botao-remover">
                  <span class="icone icone-remover"></span>
                </button>
              </td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="6">
                <button class="botao-adicionar-volume">
                  <span class="icone icone-adicionar"></span>
                  <span class="texto">Adicionar Volume</span>
                </button>
              </td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>

    <div class="formulario-secao">
      <h2 class="secao-titulo">Observações</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <label for="observacoes" class="formulario-label">Observações</label>
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
.formulario-expedicao-container {
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

.tabela-volumes {
  width: 100%;
  border-collapse: collapse;
}

.tabela-volumes th,
.tabela-volumes td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-volumes th {
  font-weight: 500;
  color: #666666;
}

.coluna-numero {
  width: 80px;
}

.coluna-peso,
.coluna-altura,
.coluna-largura,
.coluna-comprimento {
  width: 120px;
}

.coluna-acoes {
  width: 60px;
  text-align: center;
}

.botao-remover {
  background: none;
  border: none;
  color: #f5222d;
  cursor: pointer;
}

.botao-adicionar-volume {
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

.botao-adicionar-volume:hover {
  background-color: #e6f7ff;
}

.botao-adicionar-volume .icone {
  margin-right: 8px;
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

    // Carrega as expedições com o filtro selecionado
    const situacao =
      this.querySelector(".texto")?.textContent.trim() ||
      this.textContent.trim();
    carregarExpedicoes(situacao);
  });
});

// Código para filtro de período
document
  .querySelector(".filtro-mes-atual")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o seletor de mês
    const meses = [
      "Janeiro",
      "Fevereiro",
      "Março",
      "Abril",
      "Maio",
      "Junho",
      "Julho",
      "Agosto",
      "Setembro",
      "Outubro",
      "Novembro",
      "Dezembro",
    ];

    const anos = [2023, 2024, 2025];

    // Cria o modal de seleção
    const modal = document.createElement("div");
    modal.classList.add("modal-selecao-periodo");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Período</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="selecao-ano">
          <label class="selecao-label">Ano:</label>
          <div class="selecao-opcoes">
            ${anos
              .map(
                (ano) => `
              <button class="botao-opcao ${
                ano === 2025 ? "ativo" : ""
              }" data-ano="${ano}">${ano}</button>
            `
              )
              .join("")}
          </div>
        </div>
        <div class="selecao-mes">
          <label class="selecao-label">Mês:</label>
          <div class="selecao-opcoes">
            ${meses
              .map(
                (mes, index) => `
              <button class="botao-opcao ${
                index === 4 ? "ativo" : ""
              }" data-mes="${index + 1}">${mes}</button>
            `
              )
              .join("")}
          </div>
        </div>
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-aplicar-periodo">
            <span class="texto">Aplicar</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-periodo">
            <span class="texto">Cancelar</span>
          </button>
        </div>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-cancelar-periodo")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    // Seleção de ano
    modal.querySelectorAll(".selecao-ano .botao-opcao").forEach((botao) => {
      botao.addEventListener("click", function () {
        modal.querySelectorAll(".selecao-ano .botao-opcao").forEach((b) => {
          b.classList.remove("ativo");
        });
        this.classList.add("ativo");
      });
    });

    // Seleção de mês
    modal.querySelectorAll(".selecao-mes .botao-opcao").forEach((botao) => {
      botao.addEventListener("click", function () {
        modal.querySelectorAll(".selecao-mes .botao-opcao").forEach((b) => {
          b.classList.remove("ativo");
        });
        this.classList.add("ativo");
      });
    });

    // Aplicar filtro
    modal
      .querySelector("#btn-aplicar-periodo")
      .addEventListener("click", function () {
        const anoSelecionado = modal
          .querySelector(".selecao-ano .botao-opcao.ativo")
          .getAttribute("data-ano");
        const mesSelecionado = modal
          .querySelector(".selecao-mes .botao-opcao.ativo")
          .getAttribute("data-mes");
        const mesNome = meses[parseInt(mesSelecionado) - 1];

        // Atualiza o texto do filtro
        document.querySelector(".filtro-mes-atual .texto").textContent =
          mesNome;

        // Carrega as expedições do período
        carregarExpedicoes(null, anoSelecionado, mesSelecionado);

        // Fecha o modal
        document.body.removeChild(modal);
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

// Código para filtro de agrupamento
document
  .querySelector(".filtro-forma-envio")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Abre o seletor de forma de envio
    const formasEnvio = [
      { id: "todas", nome: "Todas" },
      { id: "correios_sedex", nome: "Correios - SEDEX" },
      { id: "correios_pac", nome: "Correios - PAC" },
      { id: "transportadora", nome: "Transportadora" },
      { id: "retirada", nome: "Retirada na Loja" },
    ];

    // Cria o modal de seleção
    const modal = document.createElement("div");
    modal.classList.add("modal-selecao-forma-envio");
    modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Selecionar Forma de Envio</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="selecao-forma-envio">
          ${formasEnvio
            .map(
              (forma) => `
            <div class="opcao-forma-envio">
              <input type="radio" name="forma_envio" id="forma_${
                forma.id
              }" value="${forma.id}" ${forma.id === "todas" ? "checked" : ""}>
              <label for="forma_${forma.id}">${forma.nome}</label>
            </div>
          `
            )
            .join("")}
        </div>
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-aplicar-forma-envio">
            <span class="texto">Aplicar</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-forma-envio">
            <span class="texto">Cancelar</span>
          </button>
        </div>
      </div>
    </div>
  `;

    document.body.appendChild(modal);

    // Adiciona eventos
    modal.querySelector(".botao-fechar").addEventListener("click", function () {
      document.body.removeChild(modal);
    });

    modal
      .querySelector("#btn-cancelar-forma-envio")
      .addEventListener("click", function () {
        document.body.removeChild(modal);
      });

    // Aplicar filtro
    modal
      .querySelector("#btn-aplicar-forma-envio")
      .addEventListener("click", function () {
        const formaSelecionada = modal.querySelector(
          'input[name="forma_envio"]:checked'
        ).value;
        const formaNome = formasEnvio.find(
          (f) => f.id === formaSelecionada
        ).nome;

        // Atualiza o texto do filtro
        if (formaSelecionada === "todas") {
          document.querySelector(".filtro-forma-envio .texto").textContent =
            "por forma de envio";
        } else {
          document.querySelector(".filtro-forma-envio .texto").textContent =
            formaNome;
        }

        // Carrega as expedições com o filtro selecionado
        carregarExpedicoes(null, null, null, formaSelecionada);

        // Fecha o modal
        document.body.removeChild(modal);
      });

    // Fecha o modal ao clicar fora
    modal.addEventListener("click", function (e) {
      if (e.target === modal) {
        document.body.removeChild(modal);
      }
    });
  });

// Código para limpar filtros
document
  .querySelector(".filtro-limpar")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Reseta os filtros
    document.querySelector(".filtro-mes-atual .texto").textContent = "Maio";
    document.querySelector(".filtro-forma-envio .texto").textContent =
      "por forma de envio";

    // Ativa a aba "Todas"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todas")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Carrega todas as expedições
    carregarExpedicoes("Todas");
  });

// Código para botões de limpar filtros na área vazia
document
  .querySelector("#btn-limpar-filtros")
  .addEventListener("click", function () {
    // Reseta os filtros
    document.querySelector(".filtro-mes-atual .texto").textContent = "Maio";
    document.querySelector(".filtro-forma-envio .texto").textContent =
      "por forma de envio";

    // Ativa a aba "Todas"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todas")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Carrega todas as expedições
    carregarExpedicoes("Todas");
  });

function carregarExpedicoes(situacao, ano, mes, formaEnvio) {
  // Simulação de carregamento de expedições
  console.log(
    `Carregando expedições com situação: ${situacao}, período: ${mes}/${ano}, forma de envio: ${formaEnvio}`
  );

  // Aqui seria feita uma requisição para a API
  // fetch('/api/expedicoes', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({
  //     situacao,
  //     ano,
  //     mes,
  //     forma_envio: formaEnvio
  //   })
  // })
  // .then(response => response.json())
  // .then(data => {
  //   atualizarTabelaExpedicoes(data);
  // });
}
```

### Pesquisa

```javascript
// Código para pesquisa
document
  .querySelector(".input-pesquisa")
  .addEventListener("keydown", function (e) {
    if (e.key === "Enter") {
      pesquisarExpedicoes(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarExpedicoes(termoPesquisa);
  });

// Código para botão de alterar pesquisa na área vazia
document
  .querySelector("#btn-alterar-pesquisa")
  .addEventListener("click", function () {
    document.querySelector(".input-pesquisa").focus();
  });

function pesquisarExpedicoes(termo) {
  if (!termo) return;

  console.log(`Pesquisando expedições com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch(`/api/expedicoes/pesquisa?termo=${encodeURIComponent(termo)}`)
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaExpedicoes(data);
  //   });
}
```

### Formulário de Expedição

```javascript
// Código para formulário de expedição
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioExpedicao = document.querySelector(
    ".formulario-expedicao-container"
  );
  if (!formularioExpedicao) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data_expedicao").value = hoje;

  // Calcula a data prevista de entrega (hoje + prazo)
  const calcularDataEntrega = () => {
    const dataExpedicao = new Date(
      document.querySelector("#data_expedicao").value
    );
    const prazoEntrega = parseInt(
      document.querySelector("#prazo_entrega").value
    );

    if (isNaN(dataExpedicao.getTime()) || isNaN(prazoEntrega)) return;

    const dataEntrega = new Date(dataExpedicao);
    dataEntrega.setDate(dataEntrega.getDate() + prazoEntrega);

    document.querySelector("#data_entrega").value = dataEntrega
      .toISOString()
      .split("T")[0];
  };

  // Atualiza a data de entrega quando o prazo ou a data de expedição mudar
  document
    .querySelector("#prazo_entrega")
    .addEventListener("change", calcularDataEntrega);
  document
    .querySelector("#data_expedicao")
    .addEventListener("change", calcularDataEntrega);

  // Calcula a data inicial
  calcularDataEntrega();

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação da expedição? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/expedicao";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-expedicao-container");

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

    // Coleta os dados do formulário
    const expedicao = {
      data_expedicao: document.querySelector("#data_expedicao").value,
      pedido: document.querySelector("#pedido").value,
      nota_fiscal: document.querySelector("#nota_fiscal").value,
      destinatario: document.querySelector("#destinatario").value,
      situacao: document.querySelector("#situacao").value,
      endereco: {
        cep: document.querySelector("#cep").value,
        logradouro: document.querySelector("#endereco").value,
        numero: document.querySelector("#numero").value,
        complemento: document.querySelector("#complemento").value,
        bairro: document.querySelector("#bairro").value,
        cidade: document.querySelector("#cidade").value,
        estado: document.querySelector("#estado").value,
      },
      envio: {
        forma_envio: document.querySelector("#forma_envio").value,
        transportadora: document.querySelector("#transportadora").value,
        codigo_rastreamento: document.querySelector("#codigo_rastreamento")
          .value,
        valor_frete: document.querySelector("#valor_frete").value,
        prazo_entrega: document.querySelector("#prazo_entrega").value,
        data_entrega: document.querySelector("#data_entrega").value,
      },
      volumes: [],
      observacoes: document.querySelector("#observacoes").value,
    };

    // Coleta os volumes
    document
      .querySelectorAll(".tabela-volumes tbody tr")
      .forEach((linha, index) => {
        const volume = {
          numero: index + 1,
          peso: parseFloat(linha.querySelector(".input-peso").value),
          altura: parseInt(linha.querySelector(".input-altura").value),
          largura: parseInt(linha.querySelector(".input-largura").value),
          comprimento: parseInt(
            linha.querySelector(".input-comprimento").value
          ),
        };

        expedicao.volumes.push(volume);
      });

    // Envia para a API
    console.log("Salvando expedição:", expedicao);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Expedição salva com sucesso!");
      window.location.href = "/expedicao";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/expedicoes', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(expedicao)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Expedição salva com sucesso!');
    //     window.location.href = '/expedicao';
    //   } else {
    //     throw new Error('Erro ao salvar expedição');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar expedição: ${error.message}`);
    // });
  });

  // Busca de pedido
  document.querySelector("#pedido").addEventListener("focus", function () {
    // Abre modal de busca de pedidos
    const modal = document.createElement("div");
    modal.classList.add("modal-busca-pedido");
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Selecionar Pedido</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="campo-busca">
            <input type="text" class="formulario-input input-busca-pedido" placeholder="Buscar pedido...">
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
          <div class="lista-pedidos">
            <table class="tabela-selecao-pedidos">
              <thead>
                <tr>
                  <th>Número</th>
                  <th>Data</th>
                  <th>Cliente</th>
                  <th>Valor</th>
                  <th></th>
                </tr>
              </thead>
              <tbody>
                <tr data-pedido-id="1001">
                  <td>1001</td>
                  <td>15/05/2025</td>
                  <td>Cliente A</td>
                  <td>R$ 1.500,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-pedido-id="1002">
                  <td>1002</td>
                  <td>16/05/2025</td>
                  <td>Cliente B</td>
                  <td>R$ 2.000,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-pedido-id="1003">
                  <td>1003</td>
                  <td>17/05/2025</td>
                  <td>Cliente C</td>
                  <td>R$ 1.000,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
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
        const pedidoId = linha.getAttribute("data-pedido-id");
        const pedidoNumero = linha.querySelector("td:first-child").textContent;
        const clienteNome = linha.querySelector("td:nth-child(3)").textContent;

        // Preenche os campos
        document.querySelector("#pedido").value = pedidoNumero;
        document.querySelector("#destinatario").value = clienteNome;

        // Simula busca de dados do pedido
        setTimeout(() => {
          // Preenche os campos de endereço
          document.querySelector("#cep").value = "01234-567";
          document.querySelector("#endereco").value = "Rua Exemplo";
          document.querySelector("#numero").value = "123";
          document.querySelector("#complemento").value = "Apto 45";
          document.querySelector("#bairro").value = "Centro";
          document.querySelector("#cidade").value = "São Paulo";
          document.querySelector("#estado").value = "SP";
        }, 500);

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
  });

  // Busca de nota fiscal
  document.querySelector("#nota_fiscal").addEventListener("focus", function () {
    // Abre modal de busca de notas fiscais
    const modal = document.createElement("div");
    modal.classList.add("modal-busca-nota");
    modal.innerHTML = `
      <div class="modal-conteudo">
        <div class="modal-cabecalho">
          <h2 class="modal-titulo">Selecionar Nota Fiscal</h2>
          <button class="botao-fechar">&times;</button>
        </div>
        <div class="modal-corpo">
          <div class="campo-busca">
            <input type="text" class="formulario-input input-busca-nota" placeholder="Buscar nota fiscal...">
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
          <div class="lista-notas">
            <table class="tabela-selecao-notas">
              <thead>
                <tr>
                  <th>Número</th>
                  <th>Série</th>
                  <th>Data</th>
                  <th>Cliente</th>
                  <th>Valor</th>
                  <th></th>
                </tr>
              </thead>
              <tbody>
                <tr data-nota-id="5001">
                  <td>5001</td>
                  <td>1</td>
                  <td>15/05/2025</td>
                  <td>Cliente A</td>
                  <td>R$ 1.500,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-nota-id="5002">
                  <td>5002</td>
                  <td>1</td>
                  <td>16/05/2025</td>
                  <td>Cliente B</td>
                  <td>R$ 2.000,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
                <tr data-nota-id="5003">
                  <td>5003</td>
                  <td>1</td>
                  <td>17/05/2025</td>
                  <td>Cliente C</td>
                  <td>R$ 1.000,00</td>
                  <td>
                    <button class="botao botao-primario botao-selecionar">Selecionar</button>
                  </td>
                </tr>
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
        const notaId = linha.getAttribute("data-nota-id");
        const notaNumero = linha.querySelector("td:first-child").textContent;
        const notaSerie = linha.querySelector("td:nth-child(2)").textContent;

        // Preenche o campo
        document.querySelector(
          "#nota_fiscal"
        ).value = `${notaNumero}/${notaSerie}`;

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
  });

  // Controle de forma de envio
  document
    .querySelector("#forma_envio")
    .addEventListener("change", function () {
      const formaEnvio = this.value;
      const transportadoraSelect = document.querySelector("#transportadora");

      if (formaEnvio === "transportadora") {
        transportadoraSelect.disabled = false;
        transportadoraSelect.required = true;
      } else {
        transportadoraSelect.disabled = true;
        transportadoraSelect.required = false;
        transportadoraSelect.value = "";
      }
    });

  // Botão de adicionar volume
  document
    .querySelector(".botao-adicionar-volume")
    .addEventListener("click", function () {
      const tbody = document.querySelector(".tabela-volumes tbody");
      const numeroVolume = tbody.querySelectorAll("tr").length + 1;

      const tr = document.createElement("tr");
      tr.innerHTML = `
      <td class="coluna-numero">${numeroVolume}</td>
      <td class="coluna-peso">
        <input type="number" class="formulario-input input-peso" value="1.000" min="0.001" step="0.001">
      </td>
      <td class="coluna-altura">
        <input type="number" class="formulario-input input-altura" value="10" min="1" step="1">
      </td>
      <td class="coluna-largura">
        <input type="number" class="formulario-input input-largura" value="10" min="1" step="1">
      </td>
      <td class="coluna-comprimento">
        <input type="number" class="formulario-input input-comprimento" value="10" min="1" step="1">
      </td>
      <td class="coluna-acoes">
        <button class="botao-remover">
          <span class="icone icone-remover"></span>
        </button>
      </td>
    `;

      tbody.appendChild(tr);

      // Adiciona evento de remover
      tr.querySelector(".botao-remover").addEventListener("click", function () {
        tbody.removeChild(tr);

        // Atualiza os números dos volumes
        tbody.querySelectorAll("tr").forEach((linha, index) => {
          linha.querySelector(".coluna-numero").textContent = index + 1;
        });
      });
    });
});
```

### Impressão

```javascript
// Código para impressão
document.querySelector("#btn-imprimir").addEventListener("click", function () {
  // Verifica se há expedições selecionadas
  const checkboxes = document.querySelectorAll(".checkbox-selecionar:checked");

  if (checkboxes.length === 0) {
    alert("Selecione pelo menos uma expedição para imprimir");
    return;
  }

  // Coleta os IDs das expedições selecionadas
  const expedicoesIds = Array.from(checkboxes).map((checkbox) => {
    return checkbox.closest("tr").getAttribute("data-id");
  });

  // Abre o modal de opções de impressão
  const modal = document.createElement("div");
  modal.classList.add("modal-opcoes-impressao");
  modal.innerHTML = `
    <div class="modal-conteudo">
      <div class="modal-cabecalho">
        <h2 class="modal-titulo">Opções de Impressão</h2>
        <button class="botao-fechar">&times;</button>
      </div>
      <div class="modal-corpo">
        <div class="opcoes-impressao">
          <div class="opcao-impressao">
            <input type="checkbox" id="imprimir_etiqueta" checked>
            <label for="imprimir_etiqueta">Etiqueta de Endereçamento</label>
          </div>
          <div class="opcao-impressao">
            <input type="checkbox" id="imprimir_declaracao">
            <label for="imprimir_declaracao">Declaração de Conteúdo</label>
          </div>
          <div class="opcao-impressao">
            <input type="checkbox" id="imprimir_comprovante">
            <label for="imprimir_comprovante">Comprovante de Postagem</label>
          </div>
        </div>
        <div class="acoes-modal">
          <button class="botao botao-primario" id="btn-confirmar-impressao">
            <span class="icone icone-imprimir"></span>
            <span class="texto">Imprimir</span>
          </button>
          <button class="botao botao-secundario" id="btn-cancelar-impressao">
            <span class="texto">Cancelar</span>
          </button>
        </div>
      </div>
    </div>
  `;

  document.body.appendChild(modal);

  // Adiciona eventos
  modal.querySelector(".botao-fechar").addEventListener("click", function () {
    document.body.removeChild(modal);
  });

  modal
    .querySelector("#btn-cancelar-impressao")
    .addEventListener("click", function () {
      document.body.removeChild(modal);
    });

  modal
    .querySelector("#btn-confirmar-impressao")
    .addEventListener("click", function () {
      const opcoes = {
        etiqueta: modal.querySelector("#imprimir_etiqueta").checked,
        declaracao: modal.querySelector("#imprimir_declaracao").checked,
        comprovante: modal.querySelector("#imprimir_comprovante").checked,
      };

      imprimirExpedicoes(expedicoesIds, opcoes);

      // Fecha o modal
      document.body.removeChild(modal);
    });

  // Fecha o modal ao clicar fora
  modal.addEventListener("click", function (e) {
    if (e.target === modal) {
      document.body.removeChild(modal);
    }
  });
});

function imprimirExpedicoes(ids, opcoes) {
  console.log("Imprimindo expedições:", ids, "com opções:", opcoes);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/expedicoes/imprimir', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({
  //     ids,
  //     opcoes
  //   })
  // })
  // .then(response => response.blob())
  // .then(blob => {
  //   const url = URL.createObjectURL(blob);
  //   window.open(url, '_blank');
  // });

  // Simulação de impressão
  alert("Documentos enviados para impressão!");
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
  .modulo-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-start;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pesquisa-filtros-container {
    gap: 12px;
  }

  .filtros-container {
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
  }

  .abas-container {
    flex-wrap: wrap;
  }

  .aba {
    flex-grow: 1;
    text-align: center;
  }

  .coluna-nota,
  .coluna-forma-envio,
  .coluna-rastreamento {
    display: none;
  }

  .paginacao {
    flex-direction: column;
    gap: 12px;
    align-items: flex-start;
  }

  .paginacao-controles {
    order: -1;
    align-self: center;
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

  .coluna-data,
  .coluna-destinatario {
    display: none;
  }

  .paginacao-pagina {
    display: none;
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

### Indicadores de Status

```css
.indicador {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-right: 8px;
}

.indicador-pendente {
  background-color: #faad14;
}

.indicador-concluida {
  background-color: #52c41a;
}
```

## Fluxos de Navegação

1. **Listagem de Expedições**:

   - O usuário acessa o módulo "Expedição"
   - Visualiza a lista de expedições
   - Pode filtrar por situação usando as abas
   - Pode pesquisar por número, pedido, nota fiscal ou destinatário
   - Pode aplicar filtros adicionais por período ou forma de envio

2. **Criação de Expedição**:

   - O usuário clica no botão "Incluir expedição"
   - Seleciona um pedido
   - Os dados do destinatário e endereço são preenchidos automaticamente
   - Seleciona a forma de envio
   - Adiciona informações de volumes
   - Salva a expedição

3. **Impressão de Documentos**:

   - O usuário seleciona uma ou mais expedições
   - Clica no botão "Imprimir"
   - Seleciona os documentos a serem impressos (etiquetas, declarações, comprovantes)
   - Confirma a impressão

4. **Rastreamento de Envio**:

   - O usuário acessa os detalhes de uma expedição
   - Visualiza o código de rastreamento
   - Pode clicar em um link para rastrear o envio no site da transportadora

5. **Conclusão de Expedição**:
   - O usuário acessa os detalhes de uma expedição pendente
   - Atualiza o status para "Concluída"
   - Salva as alterações

## Conclusão

O módulo "Expedição" do ERP Revo apresenta uma interface completa e funcional para gerenciamento de envios e expedição de mercadorias. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, criar e imprimir expedições de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento de expedições, como criação, impressão de documentos e rastreamento de envios, atendendo às necessidades logísticas das empresas.
