# Análise do Módulo Notas Fiscais - ERP Revo

## Estrutura Geral

O módulo "Notas Fiscais" do ERP Revo apresenta uma interface para gerenciamento de notas fiscais eletrônicas. A tela principal exibe uma lista de notas fiscais com opções de filtragem, pesquisa e ações para criar, autorizar e imprimir notas fiscais.

## Componentes Principais

### Cabeçalho do Módulo

O cabeçalho do módulo apresenta o título da seção, informações sobre o ambiente e botões de ação principais:

- Título "Notas Fiscais"
- Alerta de ambiente de testes
- Botão "Imprimir DANFEs"
- Botão "Autorizar pendentes"
- Botão "Incluir nota fiscal"
- Botão "Mais ações"

**Estrutura HTML:**

```html
<div class="modulo-cabecalho">
  <div class="titulo-container">
    <h1 class="titulo-modulo">Notas Fiscais</h1>
  </div>

  <div class="alerta-ambiente">
    <div class="alerta-icone">
      <span class="icone icone-alerta"></span>
    </div>
    <div class="alerta-mensagem">
      Você está no ambiente para testes de notas fiscais.
      <a href="#" class="link-alterar-ambiente">alterar ambiente</a>
      para gerar notas com valor fiscal.
    </div>
  </div>

  <div class="acoes-container">
    <button class="botao botao-secundario" id="btn-imprimir-danfes">
      <span class="icone icone-imprimir"></span>
      <span class="texto">Imprimir DANFEs</span>
    </button>
    <button class="botao botao-secundario" id="btn-autorizar-pendentes">
      <span class="icone icone-autorizar"></span>
      <span class="texto">Autorizar pendentes</span>
    </button>
    <a
      href="/notas_fiscais/novo"
      class="botao botao-primario"
      id="btn-incluir-nota"
    >
      <span class="icone icone-adicionar"></span>
      <span class="texto">Incluir nota fiscal</span>
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
  flex-direction: column;
  gap: 16px;
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

.alerta-ambiente {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  background-color: #fffbe6;
  border-radius: 4px;
  border: 1px solid #faad14;
}

.alerta-icone {
  margin-right: 12px;
  color: #faad14;
  font-size: 18px;
}

.alerta-mensagem {
  font-size: 14px;
  color: #666666;
}

.link-alterar-ambiente {
  color: #1890ff;
  text-decoration: none;
  margin: 0 4px;
}

.link-alterar-ambiente:hover {
  text-decoration: underline;
}

.acoes-container {
  display: flex;
  gap: 8px;
  align-self: flex-end;
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

A área de pesquisa e filtros permite buscar e filtrar notas fiscais:

**Estrutura HTML:**

```html
<div class="pesquisa-filtros-container">
  <div class="pesquisa-container">
    <div class="campo-pesquisa">
      <input
        type="text"
        placeholder="Pesquise pelo nome do cliente"
        class="input-pesquisa"
      />
      <button class="botao-pesquisa">
        <span class="icone icone-pesquisa"></span>
      </button>
    </div>
    <div class="dropdown-filtro-cliente">
      <button class="botao-filtro-cliente">
        Cliente
        <span class="icone icone-seta-baixo"></span>
      </button>
    </div>
  </div>
  <div class="filtros-container">
    <a href="#" class="filtro-link">
      <span class="texto">Últimos 30 dias</span>
    </a>
    <a href="#" class="filtro-link">
      <span class="icone icone-calendario"></span>
      <span class="texto">data de emissão</span>
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
  display: flex;
  align-items: center;
  gap: 8px;
  flex: 1;
  max-width: 500px;
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

.dropdown-filtro-cliente {
  position: relative;
}

.botao-filtro-cliente {
  display: flex;
  align-items: center;
  gap: 4px;
  padding: 8px 12px;
  background-color: #ffffff;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  cursor: pointer;
}

.botao-filtro-cliente:hover {
  background-color: #f5f5f5;
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

As abas de situação permitem filtrar notas fiscais por status:

**Estrutura HTML:**

```html
<div class="abas-container">
  <a href="#" class="aba aba-ativa">Todas</a>
  <a href="#" class="aba">
    <span class="indicador indicador-pendente"></span>
    <span class="texto">Pendentes</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-emitida"></span>
    <span class="texto">Emitidas</span>
  </a>
  <a href="#" class="aba">
    <span class="indicador indicador-cancelada"></span>
    <span class="texto">Canceladas</span>
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

.indicador-emitida {
  background-color: #52c41a;
}

.indicador-cancelada {
  background-color: #f5222d;
}
```

### Área de Conteúdo Vazio

A área de conteúdo exibe uma mensagem quando não há notas fiscais ou quando a pesquisa não retorna resultados:

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

### Tabela de Notas Fiscais

Quando houver notas fiscais, a área de conteúdo exibirá uma tabela:

**Estrutura HTML:**

```html
<div class="conteudo-container">
  <div class="conteudo-tabela">
    <table class="tabela-notas">
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
          <th class="coluna-serie">
            <div class="cabecalho-ordenavel">
              <span class="texto">Série</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-data">
            <div class="cabecalho-ordenavel">
              <span class="texto">Data</span>
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
          <th class="coluna-valor">
            <div class="cabecalho-ordenavel">
              <span class="texto">Valor</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-chave">
            <div class="cabecalho-ordenavel">
              <span class="texto">Chave</span>
              <span class="icone icone-ordenar"></span>
            </div>
          </th>
          <th class="coluna-acoes"></th>
        </tr>
      </thead>
      <tbody>
        <!-- Notas fiscais serão adicionadas dinamicamente -->
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

.tabela-notas {
  width: 100%;
  border-collapse: collapse;
}

.tabela-notas th,
.tabela-notas td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #f0f0f0;
}

.tabela-notas th {
  background-color: #fafafa;
  font-weight: 500;
  color: #666666;
  white-space: nowrap;
}

.tabela-notas tbody tr:hover {
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
.coluna-serie {
  width: 80px;
}

.coluna-data {
  width: 100px;
}

.coluna-documento {
  width: 150px;
}

.coluna-valor {
  width: 100px;
  text-align: right;
}

.coluna-chave {
  width: 200px;
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

## Formulário de Criação/Edição de Nota Fiscal

O formulário para criar ou editar notas fiscais é exibido em uma nova página:

**Estrutura HTML:**

```html
<div class="formulario-nota-container">
  <div class="formulario-cabecalho">
    <div class="titulo-container">
      <h1 class="titulo-formulario">Nova Nota Fiscal</h1>
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
          <label for="tipo_documento" class="formulario-label"
            >Tipo de Documento</label
          >
          <select id="tipo_documento" class="formulario-select" required>
            <option value="nfe">NF-e (Nota Fiscal Eletrônica)</option>
            <option value="nfce">
              NFC-e (Nota Fiscal de Consumidor Eletrônica)
            </option>
            <option value="nfse">
              NFS-e (Nota Fiscal de Serviço Eletrônica)
            </option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="natureza_operacao" class="formulario-label"
            >Natureza da Operação</label
          >
          <select id="natureza_operacao" class="formulario-select" required>
            <option value="venda">Venda</option>
            <option value="venda_servico">Venda de Serviço</option>
            <option value="devolucao">Devolução</option>
            <option value="remessa">Remessa</option>
            <option value="transferencia">Transferência</option>
            <option value="outras">Outras</option>
          </select>
        </div>

        <div class="formulario-grupo">
          <label for="finalidade" class="formulario-label">Finalidade</label>
          <select id="finalidade" class="formulario-select" required>
            <option value="normal">Normal</option>
            <option value="complementar">Complementar</option>
            <option value="ajuste">Ajuste</option>
            <option value="devolucao">Devolução</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="serie" class="formulario-label">Série</label>
          <input
            type="text"
            id="serie"
            class="formulario-input"
            value="1"
            required
          />
        </div>

        <div class="formulario-grupo">
          <label for="numero" class="formulario-label">Número</label>
          <input
            type="text"
            id="numero"
            class="formulario-input"
            value="1"
            readonly
          />
        </div>

        <div class="formulario-grupo">
          <label for="data_emissao" class="formulario-label"
            >Data de Emissão</label
          >
          <input
            type="date"
            id="data_emissao"
            class="formulario-input"
            required
          />
        </div>

        <div class="formulario-grupo">
          <label for="data_saida" class="formulario-label"
            >Data de Saída/Entrada</label
          >
          <input type="date" id="data_saida" class="formulario-input" />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="pedido" class="formulario-label">Pedido</label>
          <div class="campo-busca">
            <input
              type="text"
              id="pedido"
              class="formulario-input"
              placeholder="Buscar pedido..."
            />
            <button class="botao-busca">
              <span class="icone icone-busca"></span>
            </button>
          </div>
        </div>

        <div class="formulario-grupo">
          <label for="situacao" class="formulario-label">Situação</label>
          <select id="situacao" class="formulario-select" required>
            <option value="pendente">Pendente</option>
            <option value="autorizada">Autorizada</option>
            <option value="cancelada">Cancelada</option>
          </select>
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
          <label for="tipo_cliente" class="formulario-label">Tipo</label>
          <select id="tipo_cliente" class="formulario-select" required>
            <option value="pf">Pessoa Física</option>
            <option value="pj">Pessoa Jurídica</option>
          </select>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="documento" class="formulario-label">CNPJ/CPF</label>
          <input type="text" id="documento" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="ie" class="formulario-label">Inscrição Estadual</label>
          <input type="text" id="ie" class="formulario-input" />
        </div>

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
      <h2 class="secao-titulo">Endereço</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="cep" class="formulario-label">CEP</label>
          <input
            type="text"
            id="cep"
            class="formulario-input"
            placeholder="00000-000"
            required
          />
        </div>

        <div class="formulario-grupo formulario-grupo-grande">
          <label for="endereco" class="formulario-label">Endereço</label>
          <input type="text" id="endereco" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="numero_endereco" class="formulario-label">Número</label>
          <input
            type="text"
            id="numero_endereco"
            class="formulario-input"
            required
          />
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo">
          <label for="complemento" class="formulario-label">Complemento</label>
          <input type="text" id="complemento" class="formulario-input" />
        </div>

        <div class="formulario-grupo">
          <label for="bairro" class="formulario-label">Bairro</label>
          <input type="text" id="bairro" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="cidade" class="formulario-label">Cidade</label>
          <input type="text" id="cidade" class="formulario-input" required />
        </div>

        <div class="formulario-grupo">
          <label for="estado" class="formulario-label">Estado</label>
          <select id="estado" class="formulario-select" required>
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
              <th class="coluna-ncm">NCM</th>
              <th class="coluna-cfop">CFOP</th>
              <th class="coluna-quantidade">Quantidade</th>
              <th class="coluna-unitario">Valor Unitário</th>
              <th class="coluna-desconto">Desconto</th>
              <th class="coluna-total">Total</th>
              <th class="coluna-acoes"></th>
            </tr>
          </thead>
          <tbody>
            <tr class="linha-adicionar">
              <td colspan="8">
                <button class="botao-adicionar-produto">
                  <span class="icone icone-adicionar"></span>
                  <span class="texto">Adicionar Produto</span>
                </button>
              </td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="5"></td>
              <td class="rodape-label">Subtotal:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="5"></td>
              <td class="rodape-label">Desconto:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="5"></td>
              <td class="rodape-label">Frete:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="5"></td>
              <td class="rodape-label">Impostos:</td>
              <td class="rodape-valor">R$ 0,00</td>
              <td></td>
            </tr>
            <tr>
              <td colspan="5"></td>
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
          <label for="modalidade_frete" class="formulario-label"
            >Modalidade do Frete</label
          >
          <select id="modalidade_frete" class="formulario-select">
            <option value="0">
              0 - Contratação por conta do Remetente (CIF)
            </option>
            <option value="1">
              1 - Contratação por conta do Destinatário (FOB)
            </option>
            <option value="2">2 - Contratação por conta de Terceiros</option>
            <option value="3">
              3 - Transporte Próprio por conta do Remetente
            </option>
            <option value="4">
              4 - Transporte Próprio por conta do Destinatário
            </option>
            <option value="9">9 - Sem Frete</option>
          </select>
        </div>

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
            <option value="01">01 - Dinheiro</option>
            <option value="02">02 - Cheque</option>
            <option value="03">03 - Cartão de Crédito</option>
            <option value="04">04 - Cartão de Débito</option>
            <option value="05">05 - Crédito Loja</option>
            <option value="10">10 - Vale Alimentação</option>
            <option value="11">11 - Vale Refeição</option>
            <option value="12">12 - Vale Presente</option>
            <option value="13">13 - Vale Combustível</option>
            <option value="15">15 - Boleto Bancário</option>
            <option value="16">16 - Depósito Bancário</option>
            <option value="17">17 - PIX</option>
            <option value="99">99 - Outros</option>
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
      <h2 class="secao-titulo">Informações Adicionais</h2>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <label for="informacoes_complementares" class="formulario-label"
            >Informações Complementares</label
          >
          <textarea
            id="informacoes_complementares"
            class="formulario-textarea"
            rows="4"
          ></textarea>
        </div>
      </div>

      <div class="formulario-linha">
        <div class="formulario-grupo formulario-grupo-completo">
          <label for="informacoes_fisco" class="formulario-label"
            >Informações para o Fisco</label
          >
          <textarea
            id="informacoes_fisco"
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
.formulario-nota-container {
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

.coluna-ncm,
.coluna-cfop,
.coluna-quantidade,
.coluna-unitario,
.coluna-desconto,
.coluna-total {
  width: 100px;
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

    // Carrega as notas fiscais com o filtro selecionado
    const situacao =
      this.querySelector(".texto")?.textContent.trim() ||
      this.textContent.trim();
    carregarNotasFiscais(situacao);
  });
});

// Código para limpar filtros
document
  .querySelector(".filtro-limpar")
  .addEventListener("click", function (e) {
    e.preventDefault();

    // Limpa os filtros de data e outros
    // ...

    // Ativa a aba "Todas"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todas")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Carrega todas as notas fiscais
    carregarNotasFiscais("Todas");
  });

// Código para botões de limpar filtros na área vazia
document
  .querySelector("#btn-limpar-filtros")
  .addEventListener("click", function () {
    // Limpa os filtros de data e outros
    // ...

    // Ativa a aba "Todas"
    document.querySelectorAll(".aba").forEach((aba) => {
      aba.classList.remove("aba-ativa");
      if (aba.textContent.trim().includes("Todas")) {
        aba.classList.add("aba-ativa");
      }
    });

    // Carrega todas as notas fiscais
    carregarNotasFiscais("Todas");
  });

function carregarNotasFiscais(situacao) {
  // Simulação de carregamento de notas fiscais
  console.log(`Carregando notas fiscais com situação: ${situacao}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/notas_fiscais?situacao=' + encodeURIComponent(situacao))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaNotasFiscais(data);
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
      pesquisarNotasFiscais(this.value);
    }
  });

document
  .querySelector(".botao-pesquisa")
  .addEventListener("click", function () {
    const termoPesquisa = document.querySelector(".input-pesquisa").value;
    pesquisarNotasFiscais(termoPesquisa);
  });

// Código para botão de alterar pesquisa na área vazia
document
  .querySelector("#btn-alterar-pesquisa")
  .addEventListener("click", function () {
    document.querySelector(".input-pesquisa").focus();
  });

function pesquisarNotasFiscais(termo) {
  if (!termo) return;

  console.log(`Pesquisando notas fiscais com termo: ${termo}`);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/notas_fiscais/pesquisa?termo=' + encodeURIComponent(termo))
  //   .then(response => response.json())
  //   .then(data => {
  //     atualizarTabelaNotasFiscais(data);
  //   });
}
```

### Botões de Ação

```javascript
// Código para botão de imprimir DANFEs
document
  .querySelector("#btn-imprimir-danfes")
  .addEventListener("click", function () {
    const notasSelecionadas = obterNotasSelecionadas();

    if (notasSelecionadas.length === 0) {
      alert("Selecione pelo menos uma nota fiscal para imprimir");
      return;
    }

    imprimirDANFEs(notasSelecionadas);
  });

// Código para botão de autorizar pendentes
document
  .querySelector("#btn-autorizar-pendentes")
  .addEventListener("click", function () {
    const notasSelecionadas = obterNotasSelecionadas();

    if (notasSelecionadas.length === 0) {
      alert("Selecione pelo menos uma nota fiscal pendente para autorizar");
      return;
    }

    autorizarNotasFiscais(notasSelecionadas);
  });

function obterNotasSelecionadas() {
  const checkboxes = document.querySelectorAll(".checkbox-selecionar:checked");
  return Array.from(checkboxes).map((checkbox) => {
    const linha = checkbox.closest("tr");
    return {
      id: linha.getAttribute("data-id"),
      numero: linha.querySelector(".coluna-numero").textContent,
      serie: linha.querySelector(".coluna-serie").textContent,
    };
  });
}

function imprimirDANFEs(notas) {
  console.log("Imprimindo DANFEs:", notas);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/notas_fiscais/imprimir', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({ notas })
  // })
  // .then(response => response.blob())
  // .then(blob => {
  //   const url = URL.createObjectURL(blob);
  //   window.open(url, '_blank');
  // });
}

function autorizarNotasFiscais(notas) {
  console.log("Autorizando notas fiscais:", notas);

  // Aqui seria feita uma requisição para a API
  // fetch('/api/notas_fiscais/autorizar', {
  //   method: 'POST',
  //   headers: {
  //     'Content-Type': 'application/json'
  //   },
  //   body: JSON.stringify({ notas })
  // })
  // .then(response => response.json())
  // .then(data => {
  //   alert(`${data.autorizadas} notas fiscais autorizadas com sucesso`);
  //   carregarNotasFiscais('Todas');
  // });
}
```

### Formulário de Nota Fiscal

```javascript
// Código para formulário de nota fiscal
document.addEventListener("DOMContentLoaded", function () {
  // Verifica se estamos na página de formulário
  const formularioNota = document.querySelector(".formulario-nota-container");
  if (!formularioNota) return;

  // Define a data atual como padrão
  const hoje = new Date().toISOString().split("T")[0];
  document.querySelector("#data_emissao").value = hoje;
  document.querySelector("#data_saida").value = hoje;

  // Botão de cancelar
  document
    .querySelector("#btn-cancelar")
    .addEventListener("click", function () {
      if (
        confirm(
          "Deseja cancelar a criação da nota fiscal? As alterações não salvas serão perdidas."
        )
      ) {
        window.location.href = "/notas_fiscais";
      }
    });

  // Botão de salvar
  document.querySelector("#btn-salvar").addEventListener("click", function () {
    const form = document.querySelector(".formulario-nota-container");

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

    // Verifica se há produtos na nota
    const produtos = document.querySelectorAll(
      ".tabela-produtos tbody tr:not(.linha-adicionar)"
    );
    if (produtos.length === 0) {
      alert("Adicione pelo menos um produto à nota fiscal");
      return;
    }

    // Coleta os dados do formulário
    const notaFiscal = {
      tipo_documento: document.querySelector("#tipo_documento").value,
      natureza_operacao: document.querySelector("#natureza_operacao").value,
      finalidade: document.querySelector("#finalidade").value,
      serie: document.querySelector("#serie").value,
      numero: document.querySelector("#numero").value,
      data_emissao: document.querySelector("#data_emissao").value,
      data_saida: document.querySelector("#data_saida").value,
      pedido: document.querySelector("#pedido").value,
      situacao: document.querySelector("#situacao").value,
      cliente: {
        nome: document.querySelector("#cliente").value,
        tipo: document.querySelector("#tipo_cliente").value,
        documento: document.querySelector("#documento").value,
        ie: document.querySelector("#ie").value,
        email: document.querySelector("#email").value,
        telefone: document.querySelector("#telefone").value,
        endereco: {
          cep: document.querySelector("#cep").value,
          logradouro: document.querySelector("#endereco").value,
          numero: document.querySelector("#numero_endereco").value,
          complemento: document.querySelector("#complemento").value,
          bairro: document.querySelector("#bairro").value,
          cidade: document.querySelector("#cidade").value,
          estado: document.querySelector("#estado").value,
        },
      },
      transporte: {
        modalidade_frete: document.querySelector("#modalidade_frete").value,
        transportadora: document.querySelector("#transportadora").value,
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
      informacoes_complementares: document.querySelector(
        "#informacoes_complementares"
      ).value,
      informacoes_fisco: document.querySelector("#informacoes_fisco").value,
      produtos: [],
    };

    // Coleta os produtos
    document
      .querySelectorAll(".tabela-produtos tbody tr:not(.linha-adicionar)")
      .forEach((linha) => {
        const produto = {
          produto: linha.querySelector(".coluna-produto input").value,
          ncm: linha.querySelector(".coluna-ncm input").value,
          cfop: linha.querySelector(".coluna-cfop input").value,
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

        notaFiscal.produtos.push(produto);
      });

    // Coleta as parcelas
    document.querySelectorAll(".tabela-parcelas tbody tr").forEach((linha) => {
      const parcela = {
        numero: linha.querySelector("td:nth-child(1)").textContent,
        vencimento: linha.querySelector("td:nth-child(2) input").value,
        valor: parseFloat(linha.querySelector("td:nth-child(3) input").value),
        forma_pagamento: linha.querySelector("td:nth-child(4) select").value,
      };

      notaFiscal.pagamento.parcelas.push(parcela);
    });

    // Envia para a API
    console.log("Salvando nota fiscal:", notaFiscal);

    // Simulação de salvamento
    setTimeout(() => {
      alert("Nota fiscal salva com sucesso!");
      window.location.href = "/notas_fiscais";
    }, 1000);

    // Aqui seria feita uma requisição para a API
    // fetch('/api/notas_fiscais', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json'
    //   },
    //   body: JSON.stringify(notaFiscal)
    // })
    // .then(response => {
    //   if (response.ok) {
    //     alert('Nota fiscal salva com sucesso!');
    //     window.location.href = '/notas_fiscais';
    //   } else {
    //     throw new Error('Erro ao salvar nota fiscal');
    //   }
    // })
    // .catch(error => {
    //   alert(`Erro ao salvar nota fiscal: ${error.message}`);
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
    <td class="coluna-ncm">
      <input type="text" class="formulario-input input-ncm" placeholder="0000.00.00" required>
    </td>
    <td class="coluna-cfop">
      <input type="text" class="formulario-input input-cfop" placeholder="0000" required>
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
      ncm: "8471.30.19",
      cfop: "5102",
    },
    {
      id: 2,
      codigo: "P002",
      descricao: "Produto 2",
      preco: 200.0,
      ncm: "8471.60.52",
      cfop: "5102",
    },
    {
      id: 3,
      codigo: "P003",
      descricao: "Produto 3",
      preco: 150.0,
      ncm: "8471.90.14",
      cfop: "5102",
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
                <th>NCM</th>
                <th>CFOP</th>
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
                  <td>${produto.ncm}</td>
                  <td>${produto.cfop}</td>
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
      tr.querySelector(".input-ncm").value = produto.ncm;
      tr.querySelector(".input-cfop").value = produto.cfop;
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
  let impostos = 0; // Cálculo de impostos seria mais complexo na vida real

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

  // Calcula impostos (simplificado)
  impostos = (subtotal - desconto) * 0.18; // 18% de ICMS, por exemplo

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
  ).textContent = `R$ ${impostos.toFixed(2)}`;
  document.querySelector(
    ".tabela-produtos tfoot tr:nth-child(5) .rodape-valor"
  ).textContent = `R$ ${(subtotal - desconto + frete + impostos).toFixed(2)}`;

  // Atualiza os valores das parcelas
  atualizarParcelas(subtotal - desconto + frete + impostos);
}

function gerarParcelas(quantidade, intervalo = 30) {
  const tbody = document.querySelector(".tabela-parcelas tbody");
  tbody.innerHTML = "";

  const total = parseFloat(
    document
      .querySelector(".tabela-produtos tfoot tr:nth-child(5) .rodape-valor")
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
          <option value="01">01 - Dinheiro</option>
          <option value="03">03 - Cartão de Crédito</option>
          <option value="15">15 - Boleto Bancário</option>
          <option value="17">17 - PIX</option>
        </select>
      </td>
    `;

    tbody.appendChild(tr);
  }

  // Adiciona eventos
  document.querySelectorAll(".input-valor").forEach((input) => {
    input.addEventListener("change", function () {
      // Verifica se o total das parcelas é igual ao total da nota
      let totalParcelas = 0;
      document.querySelectorAll(".input-valor").forEach((input) => {
        totalParcelas += parseFloat(input.value);
      });

      const totalNota = parseFloat(
        document
          .querySelector(".tabela-produtos tfoot tr:nth-child(5) .rodape-valor")
          .textContent.replace("R$ ", "")
      );

      if (Math.abs(totalParcelas - totalNota) > 0.01) {
        alert(
          `O total das parcelas (R$ ${totalParcelas.toFixed(
            2
          )}) é diferente do total da nota (R$ ${totalNota.toFixed(2)})`
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
  .modulo-cabecalho {
    align-items: flex-start;
  }

  .acoes-container {
    margin-top: 16px;
    align-self: flex-start;
    flex-wrap: wrap;
  }

  .pesquisa-filtros-container {
    flex-direction: column;
  }

  .pesquisa-container {
    width: 100%;
    max-width: none;
    margin-bottom: 16px;
  }

  .filtros-container {
    width: 100%;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  .abas-container {
    flex-wrap: wrap;
  }

  .aba {
    flex-grow: 1;
    text-align: center;
  }

  .coluna-serie,
  .coluna-data,
  .coluna-documento,
  .coluna-chave {
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

  .coluna-cliente {
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

.indicador-emitida {
  background-color: #52c41a;
}

.indicador-cancelada {
  background-color: #f5222d;
}
```

## Fluxos de Navegação

1. **Listagem de Notas Fiscais**:

   - O usuário acessa o módulo "Notas Fiscais"
   - Visualiza a lista de notas fiscais
   - Pode filtrar por situação usando as abas
   - Pode pesquisar por cliente
   - Pode aplicar filtros adicionais

2. **Criação de Nota Fiscal**:

   - O usuário clica no botão "Incluir nota fiscal"
   - Preenche as informações gerais da nota
   - Seleciona um cliente
   - Adiciona produtos à nota
   - Configura o transporte
   - Configura o pagamento
   - Preenche informações adicionais
   - Salva a nota fiscal

3. **Autorização de Notas Fiscais**:

   - O usuário seleciona uma ou mais notas pendentes
   - Clica no botão "Autorizar pendentes"
   - Confirma a autorização
   - O sistema envia as notas para a SEFAZ

4. **Impressão de DANFEs**:

   - O usuário seleciona uma ou mais notas autorizadas
   - Clica no botão "Imprimir DANFEs"
   - Visualiza a prévia da impressão
   - Confirma a impressão

5. **Cancelamento de Nota Fiscal**:
   - O usuário acessa os detalhes de uma nota fiscal
   - Clica em "Cancelar" no menu de ações
   - Informa o motivo do cancelamento
   - Confirma o cancelamento
   - O sistema envia o cancelamento para a SEFAZ

## Conclusão

O módulo "Notas Fiscais" do ERP Revo apresenta uma interface completa e funcional para gerenciamento de notas fiscais eletrônicas. A organização visual é clara, com componentes bem definidos e uma hierarquia de informações que facilita o uso.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, criar e autorizar notas fiscais de forma intuitiva.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes estados e situações. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece funcionalidades específicas para gerenciamento de notas fiscais, como criação, autorização, impressão e cancelamento, atendendo às necessidades fiscais e tributárias das empresas brasileiras.
