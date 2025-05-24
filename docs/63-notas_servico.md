# Análise do Módulo Notas de Serviço - ERP Revo

## Estrutura Geral

O módulo "Notas de Serviço" do ERP Revo apresenta uma interface para gerenciamento de notas fiscais de serviço. A página exibe uma lista de notas fiscais com opções de filtragem, pesquisa e ações para gerenciamento.

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
    <span class="breadcrumb-item-atual">Notas de Serviço</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Notas de serviço</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-secundario" id="btn-imprimir">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir</span>
    </button>

    <button class="botao-acao botao-secundario" id="btn-enviar-pendentes">
      <span class="icone icone-enviar"></span>
      <span class="texto">Enviar pendentes</span>
    </button>

    <a
      href="/notas_servico/incluir"
      class="botao-acao botao-primario"
      id="btn-incluir-nota"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
    </a>
  </div>

  <div class="cabecalho-alerta">
    <div class="alerta alerta-info">
      <span class="alerta-icone icone-info"></span>
      <span class="alerta-texto"
        >A nota de serviço ainda não foi configurada. Para configurar
        acesse</span
      >
      <a href="/configuracao_nfse" class="alerta-link"
        >Configuração da Nota Fiscal Eletrônica de Serviços (NFS-e)</a
      >
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

.cabecalho-alerta {
  margin-bottom: 16px;
}

.alerta {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-radius: 4px;
  font-size: 14px;
}

.alerta-info {
  background-color: #e6f7ff;
  border: 1px solid #91d5ff;
}

.alerta-icone {
  margin-right: 8px;
  font-size: 16px;
  color: #1890ff;
}

.alerta-texto {
  color: #333333;
}

.alerta-link {
  color: #1890ff;
  text-decoration: none;
  margin-left: 4px;
}

.alerta-link:hover {
  text-decoration: underline;
}
```

### Área de Pesquisa e Filtros

A seção de pesquisa e filtros permite buscar e filtrar notas fiscais:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <input
      type="text"
      class="campo-pesquisa"
      placeholder="Pesquise por cliente ou número"
      id="campo-pesquisa"
    />
    <button class="botao-pesquisa" id="btn-pesquisar">
      <span class="icone icone-pesquisa"></span>
    </button>

    <div class="filtros-adicionais">
      <a href="#" class="filtro-adicional" id="filtro-periodo">
        <span class="icone icone-calendario"></span>
        <span class="texto">Últimos 30 dias</span>
      </a>

      <a href="#" class="filtro-adicional" id="filtro-limpar">
        <span class="icone icone-limpar"></span>
        <span class="texto">limpar filtros</span>
      </a>
    </div>
  </div>

  <div class="filtros-rapidos">
    <a href="#" class="filtro-item" data-filtro="todas">
      <span class="texto">Todas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="pendentes">
      <span class="icone icone-status icone-status-pendente"></span>
      <span class="texto">Pendentes</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="emitidas">
      <span class="icone icone-status icone-status-emitida"></span>
      <span class="texto">Emitidas</span>
    </a>
    <a href="#" class="filtro-item" data-filtro="canceladas">
      <span class="icone icone-status icone-status-cancelada"></span>
      <span class="texto">Canceladas</span>
    </a>
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

.icone-status {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 8px;
}

.icone-status-pendente {
  background-color: #fa8c16;
}

.icone-status-emitida {
  background-color: #52c41a;
}

.icone-status-cancelada {
  background-color: #f5222d;
}
```

### Área de Conteúdo (Sem Resultados)

A área de conteúdo exibe uma mensagem quando não há resultados:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="sem-resultados">
    <div class="sem-resultados-imagem">
      <img src="/assets/images/sem-resultados.svg" alt="Sem resultados" />
    </div>
    <h2 class="sem-resultados-titulo">Sua pesquisa não retornou resultados.</h2>
    <p class="sem-resultados-texto">
      Tente outras opções de pesquisa, situações ou remova os filtros.
    </p>
    <div class="sem-resultados-acoes">
      <button class="botao-acao botao-secundario" id="btn-alterar-pesquisa">
        <span class="texto">alterar pesquisa</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-limpar-filtros">
        <span class="texto">limpar filtros</span>
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

.sem-resultados {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  border: 1px solid #f0f0f0;
  border-radius: 4px;
  text-align: center;
}

.sem-resultados-imagem {
  margin-bottom: 24px;
}

.sem-resultados-imagem img {
  max-width: 200px;
}

.sem-resultados-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.sem-resultados-texto {
  font-size: 14px;
  color: #666666;
  margin: 0 0 24px;
}

.sem-resultados-acoes {
  display: flex;
  gap: 8px;
}
```

### Lista de Notas Fiscais

Embora não esteja visível na tela atual devido à ausência de resultados, a lista de notas fiscais é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="notas-lista-container">
  <table class="notas-tabela">
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
        <th class="coluna-cliente">
          <div class="cabecalho-coluna">
            <span class="texto">Cliente</span>
            <span class="icone icone-ordenar"></span>
          </div>
        </th>
        <th class="coluna-valor">
          <div class="cabecalho-coluna">
            <span class="texto">Valor</span>
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
      <!-- Exemplo de linha de nota fiscal -->
      <tr class="linha-nota">
        <td class="coluna-selecao">
          <input
            type="checkbox"
            class="checkbox-selecionar-nota"
            data-id="12345"
          />
        </td>
        <td class="coluna-numero">
          <a href="/notas_servico/visualizar/12345" class="link-numero"
            >12345</a
          >
        </td>
        <td class="coluna-data">16/05/2025</td>
        <td class="coluna-cliente">
          MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
        </td>
        <td class="coluna-valor">R$ 1.500,00</td>
        <td class="coluna-situacao">
          <span class="tag tag-pendente">Pendente</span>
        </td>
        <td class="coluna-acoes">
          <div class="acoes-grupo">
            <button class="botao-acao-tabela" title="Visualizar">
              <span class="icone icone-visualizar"></span>
            </button>
            <button class="botao-acao-tabela" title="Editar">
              <span class="icone icone-editar"></span>
            </button>
            <button class="botao-acao-tabela" title="Excluir">
              <span class="icone icone-excluir"></span>
            </button>
            <button class="botao-acao-tabela" title="Enviar">
              <span class="icone icone-enviar"></span>
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
.notas-lista-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
  position: relative;
}

.notas-tabela {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 16px;
}

.notas-tabela th,
.notas-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.notas-tabela th {
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

.linha-nota {
  transition: background-color 0.2s ease;
}

.linha-nota:hover {
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

.coluna-data {
  width: 120px;
}

.coluna-cliente {
  min-width: 200px;
}

.coluna-valor {
  width: 120px;
  text-align: right;
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

.botao-acao-tabela:hover .icone-editar {
  color: #1890ff;
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

.tag-emitida {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-cancelada {
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

## Formulário de Inclusão/Edição de Nota Fiscal

Embora não esteja visível na tela atual, o formulário de inclusão/edição de nota fiscal é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <div class="formulario-cabecalho">
    <h2 class="formulario-titulo">Incluir Nota Fiscal de Serviço</h2>
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
    <form class="formulario" id="form-nota-fiscal">
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
            <label class="formulario-label" for="data">Data de Emissão *</label>
            <input
              type="date"
              class="formulario-campo"
              id="data"
              name="data"
              required
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="competencia"
              >Competência *</label
            >
            <input
              type="month"
              class="formulario-campo"
              id="competencia"
              name="competencia"
              required
            />
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
          <div class="formulario-grupo">
            <label class="formulario-label" for="natureza_operacao"
              >Natureza da Operação *</label
            >
            <select
              class="formulario-campo formulario-select"
              id="natureza_operacao"
              name="natureza_operacao"
              required
            >
              <option value="">Selecione</option>
              <option value="1">Tributação no município</option>
              <option value="2">Tributação fora do município</option>
              <option value="3">Isenção</option>
              <option value="4">Imune</option>
              <option value="5">
                Exigibilidade suspensa por decisão judicial
              </option>
              <option value="6">
                Exigibilidade suspensa por procedimento administrativo
              </option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Serviços</h3>

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

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Impostos</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="iss_retido">ISS Retido</label>
            <select
              class="formulario-campo formulario-select"
              id="iss_retido"
              name="iss_retido"
            >
              <option value="nao">Não</option>
              <option value="sim">Sim</option>
            </select>
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_iss"
              >Alíquota ISS (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_iss"
              name="aliquota_iss"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_iss"
              >Valor ISS (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="valor_iss"
              name="valor_iss"
              placeholder="0,00"
              readonly
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_pis"
              >Alíquota PIS (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_pis"
              name="aliquota_pis"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_pis"
              >Valor PIS (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="valor_pis"
              name="valor_pis"
              placeholder="0,00"
              readonly
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_cofins"
              >Alíquota COFINS (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_cofins"
              name="aliquota_cofins"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_cofins"
              >Valor COFINS (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="valor_cofins"
              name="valor_cofins"
              placeholder="0,00"
              readonly
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_inss"
              >Alíquota INSS (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_inss"
              name="aliquota_inss"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_inss"
              >Valor INSS (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="valor_inss"
              name="valor_inss"
              placeholder="0,00"
              readonly
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_ir"
              >Alíquota IR (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_ir"
              name="aliquota_ir"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_ir">Valor IR (R$)</label>
            <input
              type="text"
              class="formulario-campo"
              id="valor_ir"
              name="valor_ir"
              placeholder="0,00"
              readonly
            />
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="aliquota_csll"
              >Alíquota CSLL (%)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="aliquota_csll"
              name="aliquota_csll"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="valor_csll"
              >Valor CSLL (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="valor_csll"
              name="valor_csll"
              placeholder="0,00"
              readonly
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="outras_retencoes"
              >Outras Retenções (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="outras_retencoes"
              name="outras_retencoes"
              placeholder="0,00"
            />
          </div>

          <div class="formulario-grupo formulario-grupo-pequeno">
            <label class="formulario-label" for="desconto_incondicionado"
              >Desconto Incond. (R$)</label
            >
            <input
              type="text"
              class="formulario-campo"
              id="desconto_incondicionado"
              name="desconto_incondicionado"
              placeholder="0,00"
            />
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Totais</h3>

        <div class="formulario-totais">
          <div class="formulario-total-item">
            <span class="formulario-total-label">Valor dos Serviços:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item">
            <span class="formulario-total-label">Valor das Deduções:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item">
            <span class="formulario-total-label">Base de Cálculo:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item">
            <span class="formulario-total-label">Valor do ISS:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item">
            <span class="formulario-total-label">Valor das Retenções:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
          <div class="formulario-total-item formulario-total-geral">
            <span class="formulario-total-label">Valor Líquido:</span>
            <span class="formulario-total-valor">R$ 0,00</span>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Informações Complementares</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="informacoes_complementares"
              >Informações Complementares</label
            >
            <textarea
              class="formulario-campo formulario-textarea"
              id="informacoes_complementares"
              name="informacoes_complementares"
              placeholder="Informações adicionais sobre a nota fiscal"
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

.formulario-tabela .coluna-servico {
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

## Tela de Visualização de Nota Fiscal

Embora não esteja visível na tela atual, a visualização detalhada de uma nota fiscal é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="visualizacao-container">
  <div class="visualizacao-cabecalho">
    <h2 class="visualizacao-titulo">Nota Fiscal de Serviço #12345</h2>
    <div class="visualizacao-acoes">
      <button class="botao-acao botao-secundario" id="btn-voltar">
        <span class="icone icone-voltar"></span>
        <span class="texto">Voltar</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-imprimir">
        <span class="icone icone-imprimir"></span>
        <span class="texto">Imprimir</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-enviar">
        <span class="icone icone-enviar"></span>
        <span class="texto">Enviar</span>
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
          <span class="visualizacao-valor">12345</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Data de Emissão:</span>
          <span class="visualizacao-valor">16/05/2025</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Competência:</span>
          <span class="visualizacao-valor">05/2025</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Situação:</span>
          <span class="visualizacao-valor">
            <span class="tag tag-pendente">Pendente</span>
          </span>
        </div>
        <div class="visualizacao-item visualizacao-item-grande">
          <span class="visualizacao-label">Cliente:</span>
          <span class="visualizacao-valor"
            >MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA</span
          >
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Natureza da Operação:</span>
          <span class="visualizacao-valor">Tributação no município</span>
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
            <tr>
              <td class="coluna-servico">Consultoria</td>
              <td class="coluna-descricao">Serviço de consultoria em TI</td>
              <td class="coluna-quantidade">10</td>
              <td class="coluna-valor-unitario">R$ 150,00</td>
              <td class="coluna-valor-total">R$ 1.500,00</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Impostos</h3>

      <div class="visualizacao-grid">
        <div class="visualizacao-item">
          <span class="visualizacao-label">ISS Retido:</span>
          <span class="visualizacao-valor">Não</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota ISS:</span>
          <span class="visualizacao-valor">5,00%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor ISS:</span>
          <span class="visualizacao-valor">R$ 75,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota PIS:</span>
          <span class="visualizacao-valor">0,65%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor PIS:</span>
          <span class="visualizacao-valor">R$ 9,75</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota COFINS:</span>
          <span class="visualizacao-valor">3,00%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor COFINS:</span>
          <span class="visualizacao-valor">R$ 45,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota INSS:</span>
          <span class="visualizacao-valor">0,00%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor INSS:</span>
          <span class="visualizacao-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota IR:</span>
          <span class="visualizacao-valor">0,00%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor IR:</span>
          <span class="visualizacao-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Alíquota CSLL:</span>
          <span class="visualizacao-valor">0,00%</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor CSLL:</span>
          <span class="visualizacao-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Outras Retenções:</span>
          <span class="visualizacao-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Desconto Incondicionado:</span>
          <span class="visualizacao-valor">R$ 0,00</span>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Totais</h3>

      <div class="visualizacao-totais">
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Valor dos Serviços:</span>
          <span class="visualizacao-total-valor">R$ 1.500,00</span>
        </div>
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Valor das Deduções:</span>
          <span class="visualizacao-total-valor">R$ 0,00</span>
        </div>
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Base de Cálculo:</span>
          <span class="visualizacao-total-valor">R$ 1.500,00</span>
        </div>
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Valor do ISS:</span>
          <span class="visualizacao-total-valor">R$ 75,00</span>
        </div>
        <div class="visualizacao-total-item">
          <span class="visualizacao-total-label">Valor das Retenções:</span>
          <span class="visualizacao-total-valor">R$ 54,75</span>
        </div>
        <div class="visualizacao-total-item visualizacao-total-geral">
          <span class="visualizacao-total-label">Valor Líquido:</span>
          <span class="visualizacao-total-valor">R$ 1.445,25</span>
        </div>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Informações Complementares</h3>

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

.coluna-servico {
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

.visualizacao-texto {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.visualizacao-texto-conteudo {
  padding: 12px 16px;
  background-color: #fafafa;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  min-height: 48px;
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

      // Aqui seria implementada a lógica para filtrar as notas fiscais
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
  const filtroLimpar = document.getElementById("filtro-limpar");

  [btnLimparFiltros, filtroLimpar].forEach((btn) => {
    if (btn) {
      btn.addEventListener("click", function (e) {
        e.preventDefault();

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

        // Aqui seria implementada a lógica para recarregar as notas fiscais sem filtros
        console.log("Filtros limpos");
      });
    }
  });
});
```

### Botão Alterar Pesquisa

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão alterar pesquisa
  const btnAlterarPesquisa = document.getElementById("btn-alterar-pesquisa");

  if (btnAlterarPesquisa) {
    btnAlterarPesquisa.addEventListener("click", function () {
      // Foca no campo de pesquisa
      const campoPesquisa = document.getElementById("campo-pesquisa");
      if (campoPesquisa) {
        campoPesquisa.focus();
      }
    });
  }
});
```

### Botão Enviar Pendentes

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão enviar pendentes
  const btnEnviarPendentes = document.getElementById("btn-enviar-pendentes");

  if (btnEnviarPendentes) {
    btnEnviarPendentes.addEventListener("click", function () {
      // Aqui seria implementada a lógica para enviar as notas fiscais pendentes
      console.log("Enviando notas fiscais pendentes");

      // Exibe uma mensagem de confirmação
      alert(
        "As notas fiscais pendentes serão enviadas. Este processo pode levar alguns minutos."
      );
    });
  }
});
```

### Formulário de Nota Fiscal

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Formulário de nota fiscal
  const formNotaFiscal = document.getElementById("form-nota-fiscal");

  if (formNotaFiscal) {
    // Botão salvar
    const btnSalvar = document.getElementById("btn-salvar");
    if (btnSalvar) {
      btnSalvar.addEventListener("click", function () {
        if (formNotaFiscal.checkValidity()) {
          // Aqui seria implementada a lógica para salvar a nota fiscal
          console.log("Nota fiscal salva");

          // Redireciona para a lista de notas fiscais
          window.location.href = "/notas_servico";
        } else {
          // Dispara a validação nativa do navegador
          formNotaFiscal.reportValidity();
        }
      });
    }

    // Botão cancelar
    const btnCancelar = document.getElementById("btn-cancelar");
    if (btnCancelar) {
      btnCancelar.addEventListener("click", function () {
        // Redireciona para a lista de notas fiscais
        window.location.href = "/notas_servico";
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
      let valorServicos = 0;

      // Calcula o valor dos serviços
      const linhasServico = document.querySelectorAll(
        "#tabela-servicos .linha-servico"
      );
      linhasServico.forEach((linha) => {
        const valorTotalTexto = linha.querySelector(
          ".coluna-valor-total .formulario-campo"
        ).value;
        const valorTotal = parseFloat(valorTotalTexto.replace(",", ".")) || 0;
        valorServicos += valorTotal;
      });

      // Calcula os impostos
      const aliquotaIss =
        parseFloat(
          document.getElementById("aliquota_iss").value.replace(",", ".")
        ) || 0;
      const valorIss = valorServicos * (aliquotaIss / 100);
      document.getElementById("valor_iss").value = valorIss
        .toFixed(2)
        .replace(".", ",");

      const aliquotaPis =
        parseFloat(
          document.getElementById("aliquota_pis").value.replace(",", ".")
        ) || 0;
      const valorPis = valorServicos * (aliquotaPis / 100);
      document.getElementById("valor_pis").value = valorPis
        .toFixed(2)
        .replace(".", ",");

      const aliquotaCofins =
        parseFloat(
          document.getElementById("aliquota_cofins").value.replace(",", ".")
        ) || 0;
      const valorCofins = valorServicos * (aliquotaCofins / 100);
      document.getElementById("valor_cofins").value = valorCofins
        .toFixed(2)
        .replace(".", ",");

      const aliquotaInss =
        parseFloat(
          document.getElementById("aliquota_inss").value.replace(",", ".")
        ) || 0;
      const valorInss = valorServicos * (aliquotaInss / 100);
      document.getElementById("valor_inss").value = valorInss
        .toFixed(2)
        .replace(".", ",");

      const aliquotaIr =
        parseFloat(
          document.getElementById("aliquota_ir").value.replace(",", ".")
        ) || 0;
      const valorIr = valorServicos * (aliquotaIr / 100);
      document.getElementById("valor_ir").value = valorIr
        .toFixed(2)
        .replace(".", ",");

      const aliquotaCsll =
        parseFloat(
          document.getElementById("aliquota_csll").value.replace(",", ".")
        ) || 0;
      const valorCsll = valorServicos * (aliquotaCsll / 100);
      document.getElementById("valor_csll").value = valorCsll
        .toFixed(2)
        .replace(".", ",");

      const outrasRetencoes =
        parseFloat(
          document.getElementById("outras_retencoes").value.replace(",", ".")
        ) || 0;
      const descontoIncondicionado =
        parseFloat(
          document
            .getElementById("desconto_incondicionado")
            .value.replace(",", ".")
        ) || 0;

      // Calcula os totais
      const valorDeducoes = descontoIncondicionado;
      const baseCalculo = valorServicos - valorDeducoes;
      const valorRetencoes =
        valorPis +
        valorCofins +
        valorInss +
        valorIr +
        valorCsll +
        outrasRetencoes;
      const valorLiquido = baseCalculo - valorRetencoes;

      // Atualiza os totais na interface
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(1) .formulario-total-valor"
      ).textContent = `R$ ${valorServicos.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(2) .formulario-total-valor"
      ).textContent = `R$ ${valorDeducoes.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(3) .formulario-total-valor"
      ).textContent = `R$ ${baseCalculo.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(4) .formulario-total-valor"
      ).textContent = `R$ ${valorIss.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(5) .formulario-total-valor"
      ).textContent = `R$ ${valorRetencoes.toFixed(2).replace(".", ",")}`;
      document.querySelector(
        ".formulario-totais .formulario-total-item:nth-child(6) .formulario-total-valor"
      ).textContent = `R$ ${valorLiquido.toFixed(2).replace(".", ",")}`;
    }

    // Inicializa os cálculos
    atualizarTotais();

    // Adiciona eventos para atualizar os totais quando os valores dos impostos são alterados
    const camposImpostos = [
      "aliquota_iss",
      "aliquota_pis",
      "aliquota_cofins",
      "aliquota_inss",
      "aliquota_ir",
      "aliquota_csll",
      "outras_retencoes",
      "desconto_incondicionado",
    ];

    camposImpostos.forEach((campo) => {
      const elemento = document.getElementById(campo);
      if (elemento) {
        elemento.addEventListener("input", atualizarTotais);
      }
    });
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

  .filtro-adicional {
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

  .sem-resultados-acoes {
    flex-direction: column;
    width: 100%;
  }

  .sem-resultados-acoes .botao-acao {
    width: 100%;
    margin-bottom: 8px;
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

1. **Listagem de Notas Fiscais**:

   - O usuário acessa o módulo "Notas de Serviço"
   - Visualiza a lista de notas fiscais cadastradas
   - Pode filtrar as notas por situação (Todas, Pendentes, Emitidas, Canceladas)
   - Pode pesquisar notas por cliente ou número
   - Pode ordenar a lista por qualquer coluna
   - Pode selecionar uma nota para visualizar seus detalhes

2. **Inclusão de Nota Fiscal**:

   - O usuário clica no botão "Incluir nota fiscal"
   - Preenche os dados do formulário
   - Adiciona serviços
   - Preenche as informações de impostos
   - Clica em "Salvar"
   - O sistema valida os dados e salva a nota fiscal
   - O usuário é redirecionado para a lista de notas fiscais

3. **Visualização de Nota Fiscal**:

   - O usuário clica no número de uma nota fiscal na lista
   - O sistema exibe os detalhes da nota
   - O usuário pode imprimir a nota, enviá-la ou editá-la

4. **Edição de Nota Fiscal**:

   - O usuário clica no botão "Editar" na tela de visualização
   - O sistema carrega os dados da nota no formulário
   - O usuário altera os dados necessários
   - Clica em "Salvar"
   - O sistema valida os dados e atualiza a nota fiscal
   - O usuário é redirecionado para a lista de notas fiscais

5. **Envio de Nota Fiscal**:

   - O usuário clica no botão "Enviar" na tela de visualização
   - O sistema envia a nota fiscal para o sistema da prefeitura
   - O sistema atualiza o status da nota para "Emitida"
   - O usuário é redirecionado para a lista de notas fiscais

6. **Envio de Notas Pendentes**:

   - O usuário clica no botão "Enviar pendentes" na lista de notas fiscais
   - O sistema envia todas as notas fiscais pendentes para o sistema da prefeitura
   - O sistema atualiza o status das notas para "Emitida"
   - O usuário permanece na lista de notas fiscais

7. **Configuração da Nota Fiscal Eletrônica**:
   - O usuário clica no link "Configuração da Nota Fiscal Eletrônica de Serviços (NFS-e)"
   - O sistema redireciona para a página de configuração
   - O usuário preenche os dados de configuração
   - Clica em "Salvar"
   - O sistema salva as configurações
   - O usuário é redirecionado para a lista de notas fiscais

## Conclusão

O módulo "Notas de Serviço" do ERP Revo apresenta uma interface para gerenciamento de notas fiscais de serviço. A página exibe uma lista de notas fiscais com opções de filtragem, pesquisa e ações para gerenciamento.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, incluir, editar e visualizar notas fiscais.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações de notas fiscais. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento de notas fiscais de serviço.
