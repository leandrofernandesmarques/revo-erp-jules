# Análise do Módulo Ordens de Serviço - ERP Revo

## Estrutura Geral

O módulo "Ordens de Serviço" do ERP Revo apresenta uma interface para gerenciamento de ordens de serviço. A página exibe uma lista de ordens de serviço com opções de filtragem, pesquisa e ações para gerenciamento.

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
    <span class="breadcrumb-item-atual">Ordens de Serviço</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Ordens de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <a
      href="/ordem_servicos/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-ordem"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir ordem de serviço</span>
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

A seção de pesquisa e filtros permite buscar e filtrar ordens de serviço:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente, nº da ordem ou nº de série"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-adicionais">
      <a href="#" class="filtro-adicional" id="filtro-periodo">
        <span class="icone icone-calendario"></span>
        <span class="texto">por período</span>
      </a>

      <button class="botao-filtros" id="btn-filtros">
        <span class="icone icone-filtro"></span>
        <span class="texto">filtros</span>
      </button>
    </div>
  </div>

  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="todas">
      <span class="texto">Todas</span>
      <span class="contador">26</span>
    </a>
    <a href="#" class="filtro-item filtro-ativo" data-filtro="em-aberto">
      <span class="texto">Em aberto</span>
      <span class="contador">01</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="orcadas">
      <span class="texto">Orçadas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="aprovadas">
      <span class="texto">Aprovadas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="nao-aprovadas">
      <span class="texto">Não aprovadas</span>
      <span class="contador">02</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="em-andamento">
      <span class="texto">Em andamento</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="mais">
      <span class="texto">mais</span>
    </a>
  </div>

  <div class="filtros-aplicados">
    <div class="filtro-aplicado">
      <span class="filtro-aplicado-label">Situação:</span>
      <span class="filtro-aplicado-valor">Em aberto</span>
      <span class="contador">01</span>
    </div>

    <div class="filtros-acoes">
      <button class="botao-acao botao-pequeno" id="btn-limpar-filtros">
        <span class="icone icone-limpar"></span>
      </button>
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

.botao-filtros {
  display: inline-flex;
  align-items: center;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.botao-filtros:hover {
  background-color: #f5f5f5;
}

.botao-filtros .icone {
  margin-right: 8px;
  font-size: 14px;
}

.filtros-rapidos {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  overflow-x: auto;
  padding-bottom: 4px;
}

.filtro-item {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
  white-space: nowrap;
  margin-right: 8px;
}

.filtro-item:hover {
  background-color: #f5f5f5;
}

.filtro-ativo {
  background-color: #1890ff;
  color: white;
}

.filtro-ativo:hover {
  background-color: #40a9ff;
  color: white;
}

.filtro-ativo .contador {
  background-color: white;
  color: #1890ff;
}

.contador {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 20px;
  height: 20px;
  padding: 0 6px;
  margin-left: 8px;
  background-color: #f5f5f5;
  border-radius: 10px;
  font-size: 12px;
  font-weight: 500;
}

.filtros-aplicados {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 16px;
}

.filtro-aplicado {
  display: flex;
  align-items: center;
  font-size: 14px;
}

.filtro-aplicado-label {
  color: #666666;
  margin-right: 4px;
}

.filtro-aplicado-valor {
  color: #333333;
  font-weight: 500;
  margin-right: 4px;
}

.filtros-acoes {
  display: flex;
  align-items: center;
}

.botao-pequeno {
  padding: 4px;
  width: 28px;
  height: 28px;
}

.botao-pequeno .icone {
  margin-right: 0;
}
```

### Lista de Ordens de Serviço

A tabela que exibe a lista de ordens de serviço:

**Estrutura HTML:**

```html
<div class="ordens-lista-container">
  <table class="ordens-tabela">
    <thead>
      <tr>
        <th class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-todos"
            id="selecionar-todos"
          />
        </th>
        <th class="coluna-numero">
          <div class="cabecalho-coluna">
            <span class="texto">Número</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data">
          <div class="cabecalho-coluna">
            <span class="texto">Data</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data-prevista">
          <div class="cabecalho-coluna">
            <span class="texto">Data Prevista</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-data-conclusao">
          <div class="cabecalho-coluna">
            <span class="texto">Data de conclusão</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-nome-fantasia">
          <div class="cabecalho-coluna">
            <span class="texto">Nome Fantasia</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-total">
          <div class="cabecalho-coluna">
            <span class="texto">Total</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-marcadores">
          <div class="cabecalho-coluna">
            <span class="texto">Marcadores</span>
          </div>
        </th>
        <th class="coluna-integracoes">
          <div class="cabecalho-coluna">
            <span class="texto">Integrações</span>
          </div>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr class="linha-ordem">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-ordem"
            data-id="14840"
          />
        </td>
        <td class="coluna-numero">
          <a href="/ordem_servicos/visualizar/14840" class="link-numero"
            >14840</a
          >
        </td>
        <td class="coluna-data">16/05/2025</td>
        <td class="coluna-data-prevista"></td>
        <td class="coluna-data-conclusao"></td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-nome-fantasia">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-total">0,00</td>
        <td class="coluna-marcadores"></td>
        <td class="coluna-integracoes"></td>
      </tr>
    </tbody>
  </table>

  <div class="resumo-rodape">
    <div class="resumo-item">
      <span class="resumo-valor">1</span>
      <span class="resumo-label">quantidade</span>
    </div>
    <div class="resumo-item">
      <span class="resumo-valor">0,00</span>
      <span class="resumo-label">valor total (R$)</span>
    </div>
  </div>

  <button class="botao-voltar-topo" id="btn-voltar-topo" title="Voltar ao topo">
    <span class="icone icone-seta-cima"></span>
  </button>
</div>
```

**Estilos CSS:**

```css
.ordens-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
  position: relative;
}

.ordens-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.ordens-tabela th,
.ordens-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.ordens-tabela th {
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

.linha-ordem {
  transition: background-color 0.2s ease;
}

.linha-ordem:hover {
  background-color: #f5f5f5;
}

.coluna-selecao {
  width: 40px;
  text-align: center;
}

.coluna-numero {
  width: 80px;
}

.link-numero {
  color: #1890ff;
  text-decoration: none;
}

.link-numero:hover {
  text-decoration: underline;
}

.coluna-data,
.coluna-data-prevista,
.coluna-data-conclusao {
  width: 120px;
}

.coluna-cliente,
.coluna-nome-fantasia {
  min-width: 200px;
}

.coluna-total {
  width: 100px;
  text-align: right;
}

.coluna-marcadores,
.coluna-integracoes {
  width: 120px;
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

## Formulário de Inclusão/Edição de Ordem de Serviço

Embora não esteja visível na tela atual, o formulário de inclusão/edição de ordem de serviço é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Incluir Ordem de Serviço</h2>
    <div class="formulario-acoes">
      <button class="botao-acao botao-secundario" id="btn-cancelar">
        <span class="texto">Cancelar</span>
      </button>
      <button class="botao-acao botao-primario" id="btn-salvar">
        <span class="texto">Salvar</span>
      </button>
    </div>
  </div>

  <div class="formulario-conteudo">
    <form class="formulario" id="form-ordem-servico">
      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Informações Gerais</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="numero">Número</label>
            <input
              type="text"
              class="formulario-campo"
              id="numero"
              name="numero"
              placeholder="Automático"
              readonly
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data">Data *</label>
            <input
              type="date"
              class="formulario-campo"
              id="data"
              name="data"
              required
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="situacao">Situação *</label>
            <select
              class="formulario-campo formulario-select"
              id="situacao"
              name="situacao"
              required
            >
              <option value="em-aberto">Em aberto</option>
              <option value="orcada">Orçada</option>
              <option value="aprovada">Aprovada</option>
              <option value="nao-aprovada">Não aprovada</option>
              <option value="em-andamento">Em andamento</option>
              <option value="concluida">Concluída</option>
              <option value="cancelada">Cancelada</option>
            </select>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-grande">
            <label class="formulario-label" for="cliente">Cliente *</label>
            <div class="formulario-campo-com-botao">
              <input
                type="text"
                class="formulario-campo"
                id="cliente"
                name="cliente"
                placeholder="Selecione um cliente"
                required
              />
              <button
                type="button"
                class="botao-campo"
                id="btn-selecionar-cliente"
              >
                <span class="icone icone-buscar"></span>
              </button>
            </div>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data_prevista"
              >Data Prevista</label
            >
            <input
              type="date"
              class="formulario-campo"
              id="data_prevista"
              name="data_prevista"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data_conclusao"
              >Data de Conclusão</label
            >
            <input
              type="date"
              class="formulario-campo"
              id="data_conclusao"
              name="data_conclusao"
            />
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Equipamento</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="equipamento"
              >Equipamento</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="equipamento"
              name="equipamento"
              placeholder="Descrição do equipamento"
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="marca">Marca</label>
            <input
              type="text"
              class="formulario-campo"
              id="marca"
              name="marca"
              placeholder="Marca do equipamento"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="modelo">Modelo</label>
            <input
              type="text"
              class="formulario-campo"
              id="modelo"
              name="modelo"
              placeholder="Modelo do equipamento"
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="numero_serie"
              >Número de Série</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="numero_serie"
              name="numero_serie"
              placeholder="Número de série do equipamento"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="garantia">Garantia</label>
            <select
              class="formulario-campo formulario-select"
              id="garantia"
              name="garantia"
            >
              <option value="">Selecione</option>
              <option value="sim">Sim</option>
              <option value="nao">Não</option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Defeito e Solução</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="defeito_relatado"
              >Defeito Relatado</label
            >
            <textarea
              class="formulario-campo formulario-textarea"
              id="defeito_relatado"
              name="defeito_relatado"
              placeholder="Descrição do defeito relatado pelo cliente"
            ></textarea>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="defeito_constatado"
              >Defeito Constatado</label
            >
            <textarea
              class="formulario-campo formulario-textarea"
              id="defeito_constatado"
              name="defeito_constatado"
              placeholder="Descrição do defeito constatado pelo técnico"
            ></textarea>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="solucao">Solução</label>
            <textarea
              class="formulario-campo formulario-textarea"
              id="solucao"
              name="solucao"
              placeholder="Descrição da solução aplicada"
            ></textarea>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Serviços e Peças</h3>

        <div class="formulario-abas">
          <button
            type="button"
            class="formulario-aba formulario-aba-ativa"
            data-aba="servicos"
          >
            Serviços
          </button>
          <button type="button" class="formulario-aba" data-aba="pecas">
            Peças
          </button>
        </div>

        <div class="formulario-aba-conteudo" id="aba-servicos">
          <div class="formulario-tabela-container">
            <table class="formulario-tabela" id="tabela-servicos">
              <thead>
                <tr>
                  <th class="coluna-servico">Serviço</th>
                  <th class="coluna-descricao">Descrição</th>
                  <th class="coluna-quantidade">Qtde.</th>
                  <th class="coluna-valor-unitario">Valor Unit.</th>
                  <th class="coluna-valor-total">Valor Total</th>
                  <th class="coluna-acoes">Ações</th>
                </tr>
              </thead>
              <tbody>
                <tr class="linha-servico">
                  <td class="coluna-servico">
                    <div class="formulario-campo-com-botao">
                      <input
                        type="text"
                        class="formulario-campo"
                        placeholder="Selecione um serviço"
                      />
                      <button
                        type="button"
                        class="botao-campo"
                        id="btn-selecionar-servico"
                      >
                        <span class="icone icone-buscar"></span>
                      </button>
                    </div>
                  </td>
                  <td class="coluna-descricao">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="Descrição do serviço"
                    />
                  </td>
                  <td class="coluna-quantidade">
                    <input
                      type="number"
                      class="formulario-campo"
                      value="1"
                      min="1"
                    />
                  </td>
                  <td class="coluna-valor-unitario">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="0,00"
                    />
                  </td>
                  <td class="coluna-valor-total">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="0,00"
                      readonly
                    />
                  </td>
                  <td class="coluna-acoes">
                    <button
                      type="button"
                      class="botao-acao-tabela"
                      title="Remover"
                    >
                      <span class="icone icone-excluir"></span>
                    </button>
                  </td>
                </tr>
              </tbody>
              <tfoot>
                <tr>
                  <td colspan="6">
                    <button
                      type="button"
                      class="botao-acao botao-secundario"
                      id="btn-adicionar-servico"
                    >
                      <span class="icone icone-adicionar"></span>
                      <span class="texto">Adicionar Serviço</span>
                    </button>
                  </td>
                </tr>
              </tfoot>
            </table>
          </div>
        </div>

        <div
          class="formulario-aba-conteudo"
          id="aba-pecas"
          style="display: none;"
        >
          <div class="formulario-tabela-container">
            <table class="formulario-tabela" id="tabela-pecas">
              <thead>
                <tr>
                  <th class="coluna-peca">Peça</th>
                  <th class="coluna-descricao">Descrição</th>
                  <th class="coluna-quantidade">Qtde.</th>
                  <th class="coluna-valor-unitario">Valor Unit.</th>
                  <th class="coluna-valor-total">Valor Total</th>
                  <th class="coluna-acoes">Ações</th>
                </tr>
              </thead>
              <tbody>
                <tr class="linha-peca">
                  <td class="coluna-peca">
                    <div class="formulario-campo-com-botao">
                      <input
                        type="text"
                        class="formulario-campo"
                        placeholder="Selecione uma peça"
                      />
                      <button
                        type="button"
                        class="botao-campo"
                        id="btn-selecionar-peca"
                      >
                        <span class="icone icone-buscar"></span>
                      </button>
                    </div>
                  </td>
                  <td class="coluna-descricao">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="Descrição da peça"
                    />
                  </td>
                  <td class="coluna-quantidade">
                    <input
                      type="number"
                      class="formulario-campo"
                      value="1"
                      min="1"
                    />
                  </td>
                  <td class="coluna-valor-unitario">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="0,00"
                    />
                  </td>
                  <td class="coluna-valor-total">
                    <input
                      type="text"
                      class="formulario-campo"
                      placeholder="0,00"
                      readonly
                    />
                  </td>
                  <td class="coluna-acoes">
                    <button
                      type="button"
                      class="botao-acao-tabela"
                      title="Remover"
                    >
                      <span class="icone icone-excluir"></span>
                    </button>
                  </td>
                </tr>
              </tbody>
              <tfoot>
                <tr>
                  <td colspan="6">
                    <button
                      type="button"
                      class="botao-acao botao-secundario"
                      id="btn-adicionar-peca"
                    >
                      <span class="icone icone-adicionar"></span>
                      <span class="texto">Adicionar Peça</span>
                    </button>
                  </td>
                </tr>
              </tfoot>
            </table>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Totais</h3>

        <div class="formulario-totais">
          <div class="formulario-total-item">
            <span class="formulario-total-label">Total de Serviços:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item">
            <span class="formulario-total-label">Total de Peças:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item formulario-total-geral">
            <span class="formulario-total-label">Total Geral:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Observações</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <textarea
              class="formulario-campo formulario-textarea"
              id="observacoes"
              name="observacoes"
              placeholder="Observações adicionais sobre a ordem de serviço"
            ></textarea>
          </div>
        </div>
      </div>
    </form>
  </div>
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
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.formulario-acoes {
  display: flex;
  gap: 8px;
}

.formulario-conteudo {
  padding: 24px;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.formulario-secao {
  margin-bottom: 24px;
}

.formulario-secao-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 16px;
  padding-bottom: 8px;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 16px;
}

.formulario-grupo {
  flex: 1;
  min-width: 200px;
}

.formulario-grupo-pequeno {
  flex: 0 0 120px;
}

.formulario-grupo-medio {
  flex: 0 0 calc(50% - 8px);
}

.formulario-grupo-grande {
  flex: 1;
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

.formulario-campo::placeholder {
  color: #999999;
}

.formulario-campo-com-botao {
  display: flex;
}

.formulario-campo-com-botao .formulario-campo {
  flex: 1;
  border-right: none;
  border-radius: 4px 0 0 4px;
}

.botao-campo {
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

.botao-campo:hover {
  background-color: #f5f5f5;
}

.botao-campo .icone {
  font-size: 16px;
  color: #666666;
}

.formulario-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.formulario-textarea {
  min-height: 100px;
  resize: vertical;
}

.formulario-abas {
  display: flex;
  border-bottom: 1px solid #f0f0f0;
  margin-bottom: 16px;
}

.formulario-aba {
  padding: 12px 16px;
  background-color: transparent;
  border: none;
  border-bottom: 2px solid transparent;
  font-size: 14px;
  font-weight: 500;
  color: #666666;
  cursor: pointer;
  transition: color 0.2s ease, border-color 0.2s ease;
}

.formulario-aba:hover {
  color: #1890ff;
}

.formulario-aba-ativa {
  color: #1890ff;
  border-bottom-color: #1890ff;
}

.formulario-aba-conteudo {
  margin-bottom: 16px;
}

.formulario-tabela-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.formulario-tabela {
  width: 100%;
  border-collapse: collapse;
}

.formulario-tabela th,
.formulario-tabela td {
  padding: 12px 8px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.formulario-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.formulario-tabela .coluna-servico,
.formulario-tabela .coluna-peca {
  width: 200px;
}

.formulario-tabela .coluna-descricao {
  min-width: 200px;
}

.formulario-tabela .coluna-quantidade {
  width: 80px;
}

.formulario-tabela .coluna-valor-unitario,
.formulario-tabela .coluna-valor-total {
  width: 120px;
}

.formulario-tabela .coluna-acoes {
  width: 60px;
  text-align: center;
}

.formulario-tabela tfoot td {
  padding: 16px 8px;
  border-bottom: none;
}

.botao-acao-tabela {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
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

.formulario-totais {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 8px;
  padding: 16px;
  background-color: #fafafa;
  border-radius: 4px;
}

.formulario-total-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.formulario-total-label {
  font-size: 14px;
  color: #666666;
}

.formulario-total-valor {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.formulario-total-geral {
  margin-top: 8px;
  padding-top: 8px;
  border-top: 1px solid #f0f0f0;
}

.formulario-total-geral .formulario-total-label,
.formulario-total-geral .formulario-total-valor {
  font-size: 16px;
  font-weight: 600;
}
```

## Tela de Visualização de Ordem de Serviço

Embora não esteja visível na tela atual, a visualização detalhada de uma ordem de serviço é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="visualizacao-container">
  <div class="visualizacao-cabecalho">
    <h2 class="visualizacao-titulo">Ordem de Serviço #14840</h2>
    <div class="visualizacao-acoes">
      <button class="botao-acao botao-secundario" id="btn-voltar">
        <span class="icone icone-voltar"></span>
        <span class="texto">Voltar</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-imprimir">
        <span class="icone icone-imprimir"></span>
        <span class="texto">Imprimir</span>
      </button>
      <button class="botao-acao botao-primario" id="btn-editar">
        <span class="icone icone-editar"></span>
        <span class="texto">Editar</span>
      </button>
    </div>
  </div>

  <div class="visualizacao-conteudo">
    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Informações Gerais</h3>

      <div class="visualizacao-grid">
        <div class="visualizacao-item">
          <span class="visualizacao-label">Número:</span>
          <span class="visualizacao-valor">14840</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Data:</span>
          <span class="visualizacao-valor">16/05/2025</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Situação:</span>
          <span class="visualizacao-valor">
            <span class="tag tag-em-aberto">Em aberto</span>
          </span>
        </div>
        <div class="visualizacao-item visualizacao-item-grande">
          <span class="visualizacao-label">Cliente:</span>
          <span class="visualizacao-valor"
            >MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA</span
          >
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Data Prevista:</span>
          <span class="visualizacao-valor">-</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Data de Conclusão:</span>
          <span class="visualizacao-valor">-</span>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Equipamento</h3>

      <div class="visualizacao-grid">
        <div class="visualizacao-item visualizacao-item-grande">
          <span class="visualizacao-label">Equipamento:</span>
          <span class="visualizacao-valor">-</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Marca:</span>
          <span class="visualizacao-valor">-</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Modelo:</span>
          <span class="visualizacao-valor">-</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Número de Série:</span>
          <span class="visualizacao-valor">-</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Garantia:</span>
          <span class="visualizacao-valor">-</span>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Defeito e Solução</h3>

      <div class="visualizacao-texto">
        <div class="visualizacao-texto-item">
          <span class="visualizacao-label">Defeito Relatado:</span>
          <div class="visualizacao-texto-conteudo">-</div>
        </div>
        <div class="visualizacao-texto-item">
          <span class="visualizacao-label">Defeito Constatado:</span>
          <div class="visualizacao-texto-conteudo">-</div>
        </div>
        <div class="visualizacao-texto-item">
          <span class="visualizacao-label">Solução:</span>
          <div class="visualizacao-texto-conteudo">-</div>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Serviços</h3>

      <div class="visualizacao-tabela-container">
        <table class="visualizacao-tabela">
          <thead>
            <tr>
              <th class="coluna-servico">Serviço</th>
              <th class="coluna-descricao">Descrição</th>
              <th class="coluna-quantidade">Qtde.</th>
              <th class="coluna-valor-unitario">Valor Unit.</th>
              <th class="coluna-valor-total">Valor Total</th>
            </tr>
          </thead>
          <tbody>
            <tr class="visualizacao-tabela-vazia">
              <td colspan="5">Nenhum serviço adicionado</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Peças</h3>

      <div class="visualizacao-tabela-container">
        <table class="visualizacao-tabela">
          <thead>
            <tr>
              <th class="coluna-peca">Peça</th>
              <th class="coluna-descricao">Descrição</th>
              <th class="coluna-quantidade">Qtde.</th>
              <th class="coluna-valor-unitario">Valor Unit.</th>
              <th class="coluna-valor-total">Valor Total</th>
            </tr>
          </thead>
          <tbody>
            <tr class="visualizacao-tabela-vazia">
              <td colspan="5">Nenhuma peça adicionada</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Totais</h3>

      <div class="visualizacao-totais">
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Total de Serviços:</span>
          <span class="visualizacao-total-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Total de Peças:</span>
          <span class="visualizacao-total-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-total-item visualizacao-total-geral">
          <span class="visualizacao-total-label">Total Geral:</span>
          <span class="visualizacao-total-valor">R$ 0,00</span>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Observações</h3>

      <div class="visualizacao-texto">
        <div class="visualizacao-texto-conteudo">-</div>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.visualizacao-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.visualizacao-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.visualizacao-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.visualizacao-acoes {
  display: flex;
  gap: 8px;
}

.visualizacao-conteudo {
  padding: 24px;
}

.visualizacao-secao {
  margin-bottom: 24px;
}

.visualizacao-secao-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 16px;
  padding-bottom: 8px;
  border-bottom: 1px solid #f0f0f0;
}

.visualizacao-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.visualizacao-item {
  display: flex;
  flex-direction: column;
}

.visualizacao-item-grande {
  grid-column: span 3;
}

.visualizacao-label {
  font-size: 14px;
  color: #666666;
  margin-bottom: 4px;
}

.visualizacao-valor {
  font-size: 14px;
  color: #333333;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-em-aberto {
  background-color: #e6f7ff;
  color: #1890ff;
}

.tag-orcada {
  background-color: #fff7e6;
  color: #fa8c16;
}

.tag-aprovada {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-nao-aprovada {
  background-color: #fff1f0;
  color: #f5222d;
}

.tag-em-andamento {
  background-color: #f9f0ff;
  color: #722ed1;
}

.tag-concluida {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-cancelada {
  background-color: #f5f5f5;
  color: #999999;
}

.visualizacao-texto {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.visualizacao-texto-item {
  display: flex;
  flex-direction: column;
}

.visualizacao-texto-conteudo {
  padding: 12px 16px;
  background-color: #fafafa;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  min-height: 48px;
}

.visualizacao-tabela-container {
  margin-bottom: 16px;
  overflow-x: auto;
}

.visualizacao-tabela {
  width: 100%;
  border-collapse: collapse;
}

.visualizacao-tabela th,
.visualizacao-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.visualizacao-tabela th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  font-size: 14px;
}

.visualizacao-tabela-vazia td {
  text-align: center;
  color: #999999;
  padding: 24px 16px;
}

.coluna-servico,
.coluna-peca {
  width: 200px;
}

.coluna-descricao {
  min-width: 200px;
}

.coluna-quantidade {
  width: 80px;
}

.coluna-valor-unitario,
.coluna-valor-total {
  width: 120px;
  text-align: right;
}

.visualizacao-totais {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 8px;
  padding: 16px;
  background-color: #fafafa;
  border-radius: 4px;
}

.visualizacao-total-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.visualizacao-total-label {
  font-size: 14px;
  color: #666666;
}

.visualizacao-total-valor {
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.visualizacao-total-geral {
  margin-top: 8px;
  padding-top: 8px;
  border-top: 1px solid #f0f0f0;
}

.visualizacao-total-geral .visualizacao-total-label,
.visualizacao-total-geral .visualizacao-total-valor {
  font-size: 16px;
  font-weight: 600;
}
```

## Interações JavaScript

### Dropdown de Mais Ações

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Dropdown de mais ações
  const btnMaisAcoes = document.getElementById("btn-mais-acoes");
  const menuMaisAcoes = document.getElementById("menu-mais-acoes");

  if (btnMaisAcoes && menuMaisAcoes) {
    btnMaisAcoes.addEventListener("click", function (e) {
      e.stopPropagation();
      menuMaisAcoes.classList.toggle("show");
    });

    // Fechar dropdown ao clicar fora
    document.addEventListener("click", function (e) {
      if (
        !btnMaisAcoes.contains(e.target) &&
        !menuMaisAcoes.contains(e.target)
      ) {
        menuMaisAcoes.classList.remove("show");
      }
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

      // Remove a classe ativa de todos os filtros
      filtrosRapidos.forEach((f) => f.classList.remove("filtro-ativo"));

      // Adiciona a classe ativa ao filtro clicado
      this.classList.add("filtro-ativo");

      // Atualiza o valor do filtro aplicado
      const filtroAplicadoValor = document.querySelector(
        ".filtro-aplicado-valor"
      );
      if (filtroAplicadoValor) {
        filtroAplicadoValor.textContent =
          this.querySelector(".texto").textContent;
      }

      // Atualiza o contador do filtro aplicado
      const filtroAplicadoContador = document.querySelector(
        ".filtro-aplicado .contador"
      );
      const filtroContador = this.querySelector(".contador");
      if (filtroAplicadoContador && filtroContador) {
        filtroAplicadoContador.textContent = filtroContador.textContent;
      } else if (filtroAplicadoContador) {
        filtroAplicadoContador.textContent = "";
      }

      // Aqui seria implementada a lógica para filtrar as ordens de serviço
      const filtroValor = this.getAttribute("data-filtro");
      console.log("Filtro aplicado:", filtroValor);
    });
  });
});
```

### Botão Limpar Filtros

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão limpar filtros
  const btnLimparFiltros = document.getElementById("btn-limpar-filtros");

  if (btnLimparFiltros) {
    btnLimparFiltros.addEventListener("click", function () {
      // Limpa o campo de pesquisa
      const campoPesquisa = document.getElementById("campo-pesquisa");
      if (campoPesquisa) {
        campoPesquisa.value = "";
      }

      // Ativa o filtro "Todas"
      const filtroTodas = document.querySelector(
        '.filtro-item[data-filtro="todas"]'
      );
      if (filtroTodas) {
        const event = new Event("click");
        filtroTodas.dispatchEvent(event);
      }

      // Aqui seria implementada a lógica para recarregar as ordens de serviço sem filtros
      console.log("Filtros limpos");
    });
  }
});
```

### Botão Voltar ao Topo

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão voltar ao topo
  const btnVoltarTopo = document.getElementById("btn-voltar-topo");

  if (btnVoltarTopo) {
    // Mostrar/ocultar botão ao rolar a página
    window.addEventListener("scroll", function () {
      if (window.pageYOffset > 200) {
        btnVoltarTopo.style.display = "flex";
      } else {
        btnVoltarTopo.style.display = "none";
      }
    });

    // Rolar para o topo ao clicar no botão
    btnVoltarTopo.addEventListener("click", function () {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    });
  }
});
```

### Formulário de Ordem de Serviço

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Formulário de ordem de serviço
  const formOrdemServico = document.getElementById("form-ordem-servico");

  if (formOrdemServico) {
    // Botão salvar
    const btnSalvar = document.getElementById("btn-salvar");
    if (btnSalvar) {
      btnSalvar.addEventListener("click", function () {
        if (formOrdemServico.checkValidity()) {
          // Aqui seria implementada a lógica para salvar a ordem de serviço
          console.log("Ordem de serviço salva");

          // Redireciona para a lista de ordens de serviço
          window.location.href = "/ordem_servicos";
        } else {
          // Dispara a validação nativa do navegador
          formOrdemServico.reportValidity();
        }
      });
    }

    // Botão cancelar
    const btnCancelar = document.getElementById("btn-cancelar");
    if (btnCancelar) {
      btnCancelar.addEventListener("click", function () {
        // Redireciona para a lista de ordens de serviço
        window.location.href = "/ordem_servicos";
      });
    }

    // Abas de serviços e peças
    const abas = document.querySelectorAll(".formulario-aba");
    if (abas.length > 0) {
      abas.forEach((aba) => {
        aba.addEventListener("click", function () {
          // Remove a classe ativa de todas as abas
          abas.forEach((a) => a.classList.remove("formulario-aba-ativa"));

          // Adiciona a classe ativa à aba clicada
          this.classList.add("formulario-aba-ativa");

          // Oculta todos os conteúdos de aba
          const conteudos = document.querySelectorAll(
            ".formulario-aba-conteudo"
          );
          conteudos.forEach((conteudo) => {
            conteudo.style.display = "none";
          });

          // Exibe o conteúdo da aba clicada
          const abaId = this.getAttribute("data-aba");
          const conteudo = document.getElementById(`aba-${abaId}`);
          if (conteudo) {
            conteudo.style.display = "block";
          }
        });
      });
    }

    // Botão adicionar serviço
    const btnAdicionarServico = document.getElementById(
      "btn-adicionar-servico"
    );
    if (btnAdicionarServico) {
      btnAdicionarServico.addEventListener("click", function () {
        // Aqui seria implementada a lógica para adicionar uma nova linha de serviço
        const tabelaServicos = document.getElementById("tabela-servicos");
        if (tabelaServicos) {
          const tbody = tabelaServicos.querySelector("tbody");
          const linhaServico = tbody.querySelector(".linha-servico");
          const novaLinha = linhaServico.cloneNode(true);

          // Limpa os valores dos campos
          const campos = novaLinha.querySelectorAll(".formulario-campo");
          campos.forEach((campo) => {
            if (campo.type === "number") {
              campo.value = "1";
            } else {
              campo.value = "";
            }
          });

          // Adiciona a nova linha à tabela
          tbody.appendChild(novaLinha);

          // Adiciona evento para remover a linha
          const btnRemover = novaLinha.querySelector(".botao-acao-tabela");
          if (btnRemover) {
            btnRemover.addEventListener("click", function () {
              tbody.removeChild(novaLinha);
              atualizarTotais();
            });
          }

          // Adiciona eventos para calcular o valor total
          const campoQuantidade = novaLinha.querySelector(
            ".coluna-quantidade .formulario-campo"
          );
          const campoValorUnitario = novaLinha.querySelector(
            ".coluna-valor-unitario .formulario-campo"
          );

          if (campoQuantidade && campoValorUnitario) {
            campoQuantidade.addEventListener("input", function () {
              atualizarValorTotal(novaLinha);
            });

            campoValorUnitario.addEventListener("input", function () {
              atualizarValorTotal(novaLinha);
            });
          }
        }
      });
    }

    // Botão adicionar peça
    const btnAdicionarPeca = document.getElementById("btn-adicionar-peca");
    if (btnAdicionarPeca) {
      btnAdicionarPeca.addEventListener("click", function () {
        // Aqui seria implementada a lógica para adicionar uma nova linha de peça
        const tabelaPecas = document.getElementById("tabela-pecas");
        if (tabelaPecas) {
          const tbody = tabelaPecas.querySelector("tbody");
          const linhaPeca = tbody.querySelector(".linha-peca");
          const novaLinha = linhaPeca.cloneNode(true);

          // Limpa os valores dos campos
          const campos = novaLinha.querySelectorAll(".formulario-campo");
          campos.forEach((campo) => {
            if (campo.type === "number") {
              campo.value = "1";
            } else {
              campo.value = "";
            }
          });

          // Adiciona a nova linha à tabela
          tbody.appendChild(novaLinha);

          // Adiciona evento para remover a linha
          const btnRemover = novaLinha.querySelector(".botao-acao-tabela");
          if (btnRemover) {
            btnRemover.addEventListener("click", function () {
              tbody.removeChild(novaLinha);
              atualizarTotais();
            });
          }

          // Adiciona eventos para calcular o valor total
          const campoQuantidade = novaLinha.querySelector(
            ".coluna-quantidade .formulario-campo"
          );
          const campoValorUnitario = novaLinha.querySelector(
            ".coluna-valor-unitario .formulario-campo"
          );

          if (campoQuantidade && campoValorUnitario) {
            campoQuantidade.addEventListener("input", function () {
              atualizarValorTotal(novaLinha);
            });

            campoValorUnitario.addEventListener("input", function () {
              atualizarValorTotal(novaLinha);
            });
          }
        }
      });
    }

    // Função para atualizar o valor total de uma linha
    function atualizarValorTotal(linha) {
      const quantidade =
        parseFloat(
          linha.querySelector(".coluna-quantidade .formulario-campo").value
        ) || 0;
      const valorUnitario =
        parseFloat(
          linha
            .querySelector(".coluna-valor-unitario .formulario-campo")
            .value.replace(",", ".")
        ) || 0;
      const valorTotal = quantidade * valorUnitario;

      linha.querySelector(".coluna-valor-total .formulario-campo").value =
        valorTotal.toFixed(2).replace(".", ",");

      atualizarTotais();
    }

    // Função para atualizar os totais
    function atualizarTotais() {
      let totalServicos = 0;
      let totalPecas = 0;

      // Calcula o total de serviços
      const linhasServico = document.querySelectorAll(
        "#tabela-servicos .linha-servico"
      );
      linhasServico.forEach((linha) => {
        const valorTotalTexto = linha.querySelector(
          ".coluna-valor-total .formulario-campo"
        ).value;
        const valorTotal = parseFloat(valorTotalTexto.replace(",", ".")) || 0;
        totalServicos += valorTotal;
      });

      // Calcula o total de peças
      const linhasPeca = document.querySelectorAll("#tabela-pecas .linha-peca");
      linhasPeca.forEach((linha) => {
        const valorTotalTexto = linha.querySelector(
          ".coluna-valor-total .formulario-campo"
        ).value;
        const valorTotal = parseFloat(valorTotalTexto.replace(",", ".")) || 0;
        totalPecas += valorTotal;
      });

      // Atualiza os totais na interface
      const totalGeral = totalServicos + totalPecas;

      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(1) .formulario-total-valor"
      ).textContent = `R$ ${totalServicos.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(2) .formulario-total-valor"
      ).textContent = `R$ ${totalPecas.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(3) .formulario-total-valor"
      ).textContent = `R$ ${totalGeral.toFixed(2).replace(".", ",")}`;
    }

    // Inicializa os cálculos
    atualizarTotais();
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

  .pesquisa-container {
    flex-wrap: wrap;
  }

  .filtros-adicionais {
    margin-left: 0;
    margin-top: 8px;
    width: 100%;
    justify-content: space-between;
  }

  .visualizacao-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .visualizacao-item-grande {
    grid-column: span 2;
  }

  .formulario-grupo-medio {
    flex: 1 0 100%;
  }
}

/* Estilos para telas pequenas */
@media (max-width: 768px) {
  .cabecalho-acoes {
    flex-direction: column;
    align-items: stretch;
  }

  .cabecalho-acoes .botao-acao {
    margin-bottom: 8px;
  }

  .pesquisa-container {
    flex-direction: column;
  }

  .campo-pesquisa {
    border-radius: 4px;
    border-right: 1px solid #d9d9d9;
  }

  .botao-pesquisa {
    position: absolute;
    right: 24px;
    border-radius: 0 4px 4px 0;
  }

  .filtros-adicionais {
    flex-direction: column;
    gap: 8px;
  }

  .filtro-adicional,
  .botao-filtros {
    width: 100%;
    justify-content: center;
  }

  .filtros-rapidos {
    flex-wrap: nowrap;
    overflow-x: auto;
    padding-bottom: 8px;
  }

  .filtro-item {
    flex-shrink: 0;
  }

  .filtros-aplicados {
    flex-direction: column;
    align-items: flex-start;
  }

  .filtros-acoes {
    margin-top: 8px;
    width: 100%;
  }

  .visualizacao-grid {
    grid-template-columns: 1fr;
  }

  .visualizacao-item-grande {
    grid-column: span 1;
  }

  .visualizacao-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .visualizacao-acoes {
    margin-top: 16px;
    width: 100%;
  }

  .visualizacao-acoes .botao-acao {
    flex: 1;
  }

  .formulario-cabecalho {
    flex-direction: column;
    align-items: flex-start;
  }

  .formulario-acoes {
    margin-top: 16px;
    width: 100%;
  }

  .formulario-acoes .botao-acao {
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

  .resumo-rodape {
    flex-direction: column;
    align-items: flex-start;
  }

  .resumo-item {
    margin-right: 0;
    margin-bottom: 8px;
  }

  .formulario-abas {
    flex-wrap: wrap;
  }

  .formulario-aba {
    flex: 1 0 50%;
    text-align: center;
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
- Laranja (alerta): #fa8c16
- Laranja claro (background): #fff7e6
- Vermelho (erro): #f5222d
- Vermelho claro (background): #fff1f0
- Roxo: #722ed1
- Roxo claro (background): #f9f0ff
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

1. **Listagem de Ordens de Serviço**:

   - O usuário acessa o módulo "Ordens de Serviço"
   - Visualiza a lista de ordens de serviço cadastradas
   - Pode filtrar as ordens por situação (Todas, Em aberto, Orçadas, Aprovadas, Não aprovadas, Em andamento)
   - Pode pesquisar ordens por cliente, número da ordem ou número de série
   - Pode ordenar a lista por qualquer coluna
   - Pode selecionar uma ordem para visualizar seus detalhes

2. **Inclusão de Ordem de Serviço**:

   - O usuário clica no botão "Incluir ordem de serviço"
   - Preenche os dados do formulário
   - Adiciona serviços e peças
   - Clica em "Salvar"
   - O sistema valida os dados e salva a ordem de serviço
   - O usuário é redirecionado para a lista de ordens de serviço

3. **Visualização de Ordem de Serviço**:

   - O usuário clica no número de uma ordem de serviço na lista
   - O sistema exibe os detalhes da ordem
   - O usuário pode imprimir a ordem ou editá-la

4. **Edição de Ordem de Serviço**:

   - O usuário clica no botão "Editar" na tela de visualização
   - O sistema carrega os dados da ordem no formulário
   - O usuário altera os dados necessários
   - Clica em "Salvar"
   - O sistema valida os dados e atualiza a ordem de serviço
   - O usuário é redirecionado para a lista de ordens de serviço

5. **Impressão de Ordem de Serviço**:
   - O usuário clica no botão "Imprimir" na tela de visualização
   - O sistema gera um relatório com os dados da ordem
   - O relatório é exibido em uma nova janela para impressão

## Conclusão

O módulo "Ordens de Serviço" do ERP Revo apresenta uma interface para gerenciamento de ordens de serviço. A página exibe uma lista de ordens de serviço com opções de filtragem, pesquisa e ações para gerenciamento.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, incluir, editar e visualizar ordens de serviço.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações de ordens de serviço. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento de ordens de serviço.
