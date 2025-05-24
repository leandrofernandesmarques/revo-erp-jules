# Análise do Módulo Relatórios - ERP Revo (Serviços)

## Estrutura Geral

O módulo "Relatórios" do ERP Revo, na seção de Serviços, apresenta uma interface para acesso a diferentes tipos de relatórios relacionados aos serviços prestados. A página exibe uma lista de relatórios disponíveis, organizados por categorias, permitindo ao usuário selecionar o relatório desejado.

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
    <span class="breadcrumb-item-atual">Relatórios</span>
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">Relatórios de Serviços</h1>
  </div>

  <div class="cabecalho-acoes">
    <button class="botao-acao botao-primario" id="btn-outros-relatorios">
      <span class="icone icone-relatorio"></span>
      <span class="texto">outros relatórios</span>
    </button>
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

.botao-acao .icone {
  margin-right: 8px;
  font-size: 16px;
}
```

### Área de Categorias de Relatórios

A seção de categorias permite filtrar os relatórios por tipo:

**Estrutura HTML:**

```html
<div class="categorias-container">
  <div class="categorias-lista">
    <a
      href="#"
      class="categoria-item categoria-item-ativo"
      data-categoria="contratos"
    >
      <span class="categoria-texto">Contratos</span>
    </a>
    <a href="#" class="categoria-item" data-categoria="notas-servico">
      <span class="categoria-texto">Notas de Serviço</span>
    </a>
    <a href="#" class="categoria-item" data-categoria="ordens-servico">
      <span class="categoria-texto">Ordens de Serviço</span>
    </a>
  </div>
</div>
```

**Estilos CSS:**

```css
.categorias-container {
  padding: 0 24px 16px;
  background-color: #ffffff;
}

.categorias-lista {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
  border-bottom: 1px solid #f0f0f0;
  padding-bottom: 8px;
}

.categoria-item {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 14px;
  color: #666666;
  text-decoration: none;
  transition: background-color 0.2s ease, color 0.2s ease;
}

.categoria-item:hover {
  background-color: #f5f5f5;
  color: #333333;
}

.categoria-item-ativo {
  background-color: #e6f7ff;
  color: #1890ff;
  font-weight: 500;
}

.categoria-item-ativo:hover {
  background-color: #e6f7ff;
  color: #1890ff;
}
```

### Lista de Relatórios

A seção principal exibe a lista de relatórios disponíveis:

**Estrutura HTML:**

```html
<div class="relatorios-container">
  <div class="relatorios-lista">
    <!-- Relatório 1 -->
    <a href="/relatorios/inicio-termino-contratos" class="relatorio-item">
      <div class="relatorio-conteudo">
        <h3 class="relatorio-titulo">Início e Término de Contratos</h3>
        <p class="relatorio-descricao">
          Relação de contratos por data de início e término.
        </p>
      </div>
    </a>

    <!-- Relatório 2 -->
    <a href="/relatorios/inicio-termino-contratos-mes" class="relatorio-item">
      <div class="relatorio-conteudo">
        <h3 class="relatorio-titulo">Início e Término de Contratos por Mês</h3>
        <p class="relatorio-descricao">
          Relação dos contratos agrupados por mês.
        </p>
      </div>
    </a>

    <!-- Mais relatórios seriam listados aqui -->
  </div>
</div>
```

**Estilos CSS:**

```css
.relatorios-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
}

.relatorios-lista {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.relatorio-item {
  display: block;
  padding: 16px;
  border: 1px solid #f0f0f0;
  border-radius: 4px;
  text-decoration: none;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.relatorio-item:hover {
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.relatorio-conteudo {
  display: flex;
  flex-direction: column;
}

.relatorio-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0 0 8px;
}

.relatorio-descricao {
  font-size: 14px;
  color: #666666;
  margin: 0;
}
```

## Tela de Relatório Específico

Quando um relatório é selecionado, o sistema exibe uma tela de configuração e visualização do relatório. Abaixo está a estrutura esperada para a tela de relatório "Início e Término de Contratos":

**Estrutura HTML:**

```html
<div class="relatorio-especifico-container">
  <div class="relatorio-cabecalho">
    <div class="relatorio-titulo-container">
      <h2 class="relatorio-titulo">Relatório: Início e Término de Contratos</h2>
    </div>

    <div class="relatorio-acoes">
      <button class="botao-acao botao-secundario" id="btn-voltar">
        <span class="icone icone-voltar"></span>
        <span class="texto">Voltar</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-imprimir">
        <span class="icone icone-imprimir"></span>
        <span class="texto">Imprimir</span>
      </button>
      <button class="botao-acao botao-secundario" id="btn-exportar">
        <span class="icone icone-exportar"></span>
        <span class="texto">Exportar</span>
      </button>
    </div>
  </div>

  <div class="relatorio-filtros">
    <form class="filtros-form" id="form-filtros">
      <div class="filtros-linha">
        <div class="filtro-grupo filtro-grupo-medio">
          <label class="filtro-label" for="data_inicio">Data de Início</label>
          <input
            type="date"
            class="filtro-campo"
            id="data_inicio"
            name="data_inicio"
          />
        </div>

        <div class="filtro-grupo filtro-grupo-medio">
          <label class="filtro-label" for="data_fim">Data de Término</label>
          <input
            type="date"
            class="filtro-campo"
            id="data_fim"
            name="data_fim"
          />
        </div>
      </div>

      <div class="filtros-linha">
        <div class="filtro-grupo">
          <label class="filtro-label" for="cliente">Cliente</label>
          <select
            class="filtro-campo filtro-select"
            id="cliente"
            name="cliente"
          >
            <option value="">Todos</option>
            <option value="12345">
              MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
            </option>
            <option value="12346">EMPRESA XYZ</option>
            <option value="12347">EMPRESA ABC</option>
          </select>
        </div>
      </div>

      <div class="filtros-linha">
        <div class="filtro-grupo">
          <label class="filtro-label" for="situacao">Situação</label>
          <select
            class="filtro-campo filtro-select"
            id="situacao"
            name="situacao"
          >
            <option value="">Todas</option>
            <option value="ativo">Ativo</option>
            <option value="inativo">Inativo</option>
            <option value="suspenso">Suspenso</option>
            <option value="cancelado">Cancelado</option>
          </select>
        </div>
      </div>

      <div class="filtros-acoes">
        <button
          type="button"
          class="botao-acao botao-secundario"
          id="btn-limpar-filtros"
        >
          <span class="texto">Limpar</span>
        </button>
        <button
          type="submit"
          class="botao-acao botao-primario"
          id="btn-aplicar-filtros"
        >
          <span class="texto">Aplicar</span>
        </button>
      </div>
    </form>
  </div>

  <div class="relatorio-resultados">
    <div class="relatorio-tabela-container">
      <table class="relatorio-tabela">
        <thead>
          <tr>
            <th class="coluna-contrato">
              <div class="cabecalho-coluna">
                <span class="texto">Contrato</span>
                <span class="icone icone-ordenar"></span>
              </div>
            </th>
            <th class="coluna-cliente">
              <div class="cabecalho-coluna">
                <span class="texto">Cliente</span>
                <span class="icone icone-ordenar"></span>
              </div>
            </th>
            <th class="coluna-data-inicio">
              <div class="cabecalho-coluna">
                <span class="texto">Data de Início</span>
                <span class="icone icone-ordenar"></span>
              </div>
            </th>
            <th class="coluna-data-termino">
              <div class="cabecalho-coluna">
                <span class="texto">Data de Término</span>
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
          </tr>
        </thead>
        <tbody>
          <!-- Exemplo de linha de contrato -->
          <tr class="linha-contrato">
            <td class="coluna-contrato">
              <a href="/contratos/visualizar/12345" class="link-contrato"
                >Contrato de Manutenção #12345</a
              >
            </td>
            <td class="coluna-cliente">
              MODAS DANY - COM. DE ROUPAS E CALÇADOS LTDA
            </td>
            <td class="coluna-data-inicio">01/01/2025</td>
            <td class="coluna-data-termino">31/12/2025</td>
            <td class="coluna-valor">R$ 1.500,00</td>
            <td class="coluna-situacao">
              <span class="tag tag-ativo">Ativo</span>
            </td>
          </tr>

          <!-- Mais linhas seriam listadas aqui -->
        </tbody>
      </table>
    </div>

    <div class="relatorio-resumo">
      <div class="resumo-item">
        <span class="resumo-label">Total de contratos:</span>
        <span class="resumo-valor">1</span>
      </div>
      <div class="resumo-item">
        <span class="resumo-label">Valor total:</span>
        <span class="resumo-valor">R$ 1.500,00</span>
      </div>
    </div>

    <div class="relatorio-paginacao">
      <div class="paginacao-info">
        <span class="paginacao-texto">Exibindo 1-1 de 1 resultados</span>
      </div>
      <div class="paginacao-controles">
        <button class="paginacao-botao paginacao-botao-anterior" disabled>
          <span class="icone icone-anterior"></span>
        </button>
        <button
          class="paginacao-botao paginacao-botao-pagina paginacao-botao-ativo"
        >
          1
        </button>
        <button class="paginacao-botao paginacao-botao-proximo" disabled>
          <span class="icone icone-proximo"></span>
        </button>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.relatorio-especifico-container {
  background-color: #ffffff;
  border-radius: 4px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  margin-bottom: 24px;
}

.relatorio-cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-titulo {
  font-size: 18px;
  font-weight: 600;
  color: #333333;
  margin: 0;
}

.relatorio-acoes {
  display: flex;
  gap: 8px;
}

.botao-secundario {
  background-color: #ffffff;
  color: #666666;
  border: 1px solid #d9d9d9;
}

.botao-secundario:hover {
  background-color: #f5f5f5;
}

.relatorio-filtros {
  padding: 16px 24px;
  border-bottom: 1px solid #f0f0f0;
}

.filtros-form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.filtros-linha {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.filtro-grupo {
  flex: 1;
  min-width: 200px;
}

.filtro-grupo-medio {
  flex: 0 0 calc(50% - 8px);
}

.filtro-label {
  display: block;
  margin-bottom: 8px;
  font-size: 14px;
  color: #666666;
}

.filtro-campo {
  display: block;
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.filtro-campo:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.filtro-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.filtros-acoes {
  display: flex;
  justify-content: flex-end;
  gap: 8px;
  margin-top: 8px;
}

.relatorio-resultados {
  padding: 16px 24px;
}

.relatorio-tabela-container {
  overflow-x: auto;
  margin-bottom: 16px;
}

.relatorio-tabela {
  width: 100%;
  border-collapse: collapse;
}

.relatorio-tabela th,
.relatorio-tabela td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.relatorio-tabela th {
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

.linha-contrato {
  transition: background-color 0.2s ease;
}

.linha-contrato:hover {
  background-color: #f5f5f5;
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

.coluna-cliente {
  min-width: 200px;
}

.coluna-data-inicio,
.coluna-data-termino {
  width: 120px;
}

.coluna-valor {
  width: 120px;
  text-align: right;
}

.coluna-situacao {
  width: 120px;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 8px;
  font-size: 12px;
  border-radius: 4px;
}

.tag-ativo {
  background-color: #f6ffed;
  color: #52c41a;
}

.tag-inativo {
  background-color: #f5f5f5;
  color: #999999;
}

.tag-suspenso {
  background-color: #fff7e6;
  color: #fa8c16;
}

.tag-cancelado {
  background-color: #fff1f0;
  color: #f5222d;
}

.relatorio-resumo {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  margin-bottom: 16px;
  padding: 16px;
  background-color: #fafafa;
  border-radius: 4px;
}

.resumo-item {
  display: flex;
  align-items: center;
}

.resumo-label {
  font-size: 14px;
  color: #666666;
  margin-right: 8px;
}

.resumo-valor {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
}

.relatorio-paginacao {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 16px;
  border-top: 1px solid #f0f0f0;
}

.paginacao-info {
  font-
(Content truncated due to size limit. Use line ranges to read in chunks)
```
