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
            <select
              class="formulario-campo formulario-select"
              id="mes"
              name="mes"
              required
            >
              <option value="1">Janeiro</option>
              <option value="2">Fevereiro</option>
              <option value="3">Março</option>
              <option value="4">Abril</option>
              <option value="5" selected>Maio</option>
              <option value="6">Junho</option>
              <option value="7">Julho</option>
              <option value="8">Agosto</option>
              <option value="9">Setembro</option>
              <option value="10">Outubro</option>
              <option value="11">Novembro</option>
              <option value="12">Dezembro</option>
            </select>
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="ano">Ano *</label>
            <select
              class="formulario-campo formulario-select"
              id="ano"
              name="ano"
              required
            >
              <option value="2023">2023</option>
              <option value="2024">2024</option>
              <option value="2025" selected>2025</option>
              <option value="2026">2026</option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Contratos</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <div class="formulario-opcoes">
              <label class="formulario-opcao">
                <input
                  type="radio"
                  name="tipo_contratos"
                  value="todos"
                  checked
                />
                <span class="formulario-opcao-texto">Todos os contratos</span>
              </label>
              <label class="formulario-opcao">
                <input
                  type="radio"
                  name="tipo_contratos"
                  value="selecionados"
                />
                <span class="formulario-opcao-texto"
                  >Contratos selecionados</span
                >
              </label>
            </div>
          </div>
        </div>

        <div
          class="formulario-linha"
          id="contratos-selecionados"
          style="display: none;"
        >
          <div class="formulario-grupo">
            <label class="formulario-label" for="contratos"
              >Selecione os contratos</label
            >
            <select
              class="formulario-campo formulario-select"
              id="contratos"
              name="contratos[]"
              multiple
            >
              <option value="12345">
                Contrato de Manutenção #12345 - MODAS DANY
              </option>
              <option value="12346">
                Contrato de Suporte #12346 - EMPRESA XYZ
              </option>
              <option value="12347">
                Contrato de Consultoria #12347 - EMPRESA ABC
              </option>
            </select>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Configurações de Cobrança</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="data_vencimento"
              >Data de Vencimento *</label
            >
            <input
              type="date"
              class="formulario-campo"
              id="data_vencimento"
              name="data_vencimento"
              required
            />
          </div>

          <div class="formulario-grupo formulario-grupo-medio">
            <label class="formulario-label" for="forma_pagamento"
              >Forma de Pagamento *</label
            >
            <select
              class="formulario-campo formulario-select"
              id="forma_pagamento"
              name="forma_pagamento"
              required
            >
              <option value="">Selecione</option>
              <option value="boleto">Boleto Bancário</option>
              <option value="pix">PIX</option>
              <option value="cartao">Cartão de Crédito</option>
              <option value="transferencia">Transferência Bancária</option>
            </select>
          </div>
        </div>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <label class="formulario-label" for="observacoes"
              >Observações</label
            >
            <textarea
              class="formulario-campo formulario-textarea"
              id="observacoes"
              name="observacoes"
              placeholder="Observações adicionais sobre as cobranças"
            ></textarea>
          </div>
        </div>
      </div>

      <div class="formulario-secao">
        <h3 class="formulario-secao-titulo">Envio Automático</h3>

        <div class="formulario-linha">
          <div class="formulario-grupo">
            <div class="formulario-opcoes">
              <label class="formulario-opcao">
                <input
                  type="checkbox"
                  name="enviar_automaticamente"
                  id="enviar_automaticamente"
                />
                <span class="formulario-opcao-texto"
                  >Enviar cobranças automaticamente após geração</span
                >
              </label>
            </div>
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

.formulario-select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23666' d='M6 8.5L1.5 4h9z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 32px;
}

.formulario-select[multiple] {
  height: 120px;
  background-image: none;
}

.formulario-textarea {
  min-height: 100px;
  resize: vertical;
}

.formulario-opcoes {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.formulario-opcao {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.formulario-opcao input[type="radio"],
.formulario-opcao input[type="checkbox"] {
  margin-right: 8px;
}

.formulario-opcao-texto {
  font-size: 14px;
  color: #333333;
}
```

## Tela de Visualização de Cobrança

Embora não esteja visível na tela atual, a visualização detalhada de uma cobrança é um componente importante deste módulo. Abaixo está a estrutura esperada:

**Estrutura HTML:**

```html
<div class="visualizacao-container">
  <div class="visualizacao-cabecalho">
    <h2 class="visualizacao-titulo">Cobrança #12345</h2>
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
          <span class="visualizacao-valor">01/05/2025</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Data de Vencimento:</span>
          <span class="visualizacao-valor">15/05/2025</span>
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
        <div class="visualizacao-item visualizacao-item-grande">
          <span class="visualizacao-label">Contrato:</span>
          <span class="visualizacao-valor">
            <a href="/contratos/visualizar/12345" class="link-contrato"
              >Contrato de Manutenção #12345</a
            >
          </span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Forma de Pagamento:</span>
          <span class="visualizacao-valor">Boleto Bancário</span>
        </div>
        <div class="visualizacao-item">
          <span class="visualizacao-label">Valor:</span>
          <span class="visualizacao-valor">R$ 1.500,00</span>
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
              <td class="coluna-servico">Manutenção</td>
              <td class="coluna-descricao">Serviço de manutenção mensal</td>
              <td class="coluna-quantidade">1</td>
              <td class="coluna-valor-unitario">R$ 1.500,00</td>
              <td class="coluna-valor-total">R$ 1.500,00</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="visualizacao-secao">
      <h3 class="visualizacao-secao-titulo">Histórico de Envios</h3>

      <div class="visualizacao-tabela-container">
        <table class="visualizacao-tabela">
          <thead>
            <tr>
              <th class="coluna-data">Data</th>
              <th class="coluna-hora">Hora</th>
              <th class="coluna-email">E-mail</th>
              <th class="coluna-situacao">Situação</th>
            </tr>
          </thead>
          <tbody>
            <tr class="visualizacao-tabela-vazia">
              <td colspan="4">Nenhum envio realizado</td>
            </tr>
          </tbody>
        </table>
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

.coluna-data,
.coluna-hora {
  width: 120px;
}

.coluna-email {
  min-width: 200px;
}

.coluna-situacao {
  width: 120px;
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

### Botão Gerar Cobranças do Período

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão gerar cobranças do período
  const btnGerarCobrancasPeriodo = document.getElementById(
    "btn-gerar-cobrancas-periodo"
  );
  const btnGerarCobrancas = document.getElementById("btn-gerar-cobrancas");

  [btnGerarCobrancasPeriodo, btnGerarCobrancas].forEach((btn) => {
    if (btn) {
      btn.addEventListener("click", function () {
        // Redireciona para a página de geração de cobranças
        window.location.href = "/cobrancas/gerar";
      });
    }
  });
});
```

### Botão Enviar Boletos do Mês

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Botão enviar boletos do mês
  const btnEnviarBoletos = document.getElementById("btn-enviar-boletos");

  if (btnEnviarBoletos) {
    btnEnviarBoletos.addEventListener("click", function () {
      // Aqui seria implementada a lógica para enviar os boletos do mês
      console.log("Enviando boletos do mês");

      // Exibe uma mensagem de confirmação
      alert(
        "Os boletos do mês serão enviados. Este processo pode levar alguns minutos."
      );
    });
  }
});
```

### Formulário de Geração de Cobranças

```javascript
document.addEventListener("DOMContentLoaded", function () {
  // Formulário de geração de cobranças
  const formGerarCobrancas = document.getElementById("form-gerar-cobrancas");

  if (formGerarCobrancas) {
    // Botão gerar
    const btnGerar = document.getElementById("btn-gerar");
    if (btnGerar) {
      btnGerar.addEventListener("click", function () {
        if (formGerarCobrancas.checkValidity()) {
          // Aqui seria implementada a lógica para gerar as cobranças
          console.log("Cobranças geradas");

          // Redireciona para a lista de cobranças
          window.location.href = "/cobrancas";
        } else {
          // Dispara a validação nativa do navegador
          formGerarCobrancas.reportValidity();
        }
      });
    }

    // Botão cancelar
    const btnCancelar = document.getElementById("btn-cancelar");
    if (btnCancelar) {
      btnCancelar.addEventListener("click", function () {
        // Redireciona para a lista de cobranças
        window.location.href = "/cobrancas";
      });
    }

    // Opções de tipo de contratos
    const radioTipoContratos = document.querySelectorAll(
      'input[name="tipo_contratos"]'
    );
    const contratosSelecionados = document.getElementById(
      "contratos-selecionados"
    );

    radioTipoContratos.forEach((radio) => {
      radio.addEventListener("change", function () {
        if (this.value === "selecionados") {
          contratosSelecionados.style.display = "block";
        } else {
          contratosSelecionados.style.display = "none";
        }
      });
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

  .sem-cobrancas-acoes {
    flex-direction: column;
    width: 100%;
  }

  .sem-cobrancas-acoes .botao-acao {
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

1. **Listagem de Cobranças**:

   - O usuário acessa o módulo "Cobranças"
   - Visualiza a lista de cobranças geradas
   - Pode filtrar as cobranças por mês
   - Pode pesquisar cobranças por cliente
   - Pode selecionar uma cobrança para visualizar seus detalhes

2. **Geração de Cobranças**:

   - O usuário clica no botão "Gerar cobranças do período"
   - Preenche os dados do formulário (mês, ano, contratos, configurações)
   - Clica em "Gerar"
   - O sistema gera as cobranças para o período selecionado
   - O usuário é redirecionado para a lista de cobranças

3. **Visualização de Cobrança**:

   - O usuário clica em uma cobrança na lista
   - O sistema exibe os detalhes da cobrança
   - O usuário pode imprimir a cobrança, enviá-la ou editá-la

4. **Envio de Cobrança**:

   - O usuário clica no botão "Enviar" na tela de visualização
   - O sistema envia a cobrança para o cliente
   - O sistema atualiza o status da cobrança para "Enviado"
   - O usuário é redirecionado para a lista de cobranças

5. **Envio de Boletos do Mês**:
   - O usuário clica no botão "Enviar boletos do mês" na lista de cobranças
   - O sistema envia todos os boletos do mês para os clientes
   - O sistema atualiza o status das cobranças para "Enviado"
   - O usuário permanece na lista de cobranças

## Conclusão

O módulo "Cobranças" do ERP Revo apresenta uma interface para gerenciamento de cobranças de contratos de serviço. A página exibe uma lista de cobranças geradas com opções de filtragem, pesquisa e ações para gerenciamento.

A interface é responsiva e se adapta a diferentes tamanhos de tela, garantindo uma boa experiência em dispositivos móveis e desktop. As interações JavaScript são bem implementadas, permitindo filtrar, pesquisar, gerar e enviar cobranças.

A paleta de cores é consistente com o restante do sistema, utilizando o azul como cor primária e cores específicas para diferentes situações de cobranças. Os componentes são reutilizáveis e seguem um padrão visual coerente, facilitando a implementação no Figma.

O módulo oferece uma experiência de usuário eficiente, com ações bem posicionadas e informações organizadas de forma a facilitar o gerenciamento de cobranças de contratos de serviço.
