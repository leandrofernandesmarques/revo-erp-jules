# Análise do Módulo Configuração da Nota Fiscal Eletrônica de Serviços (NFSe) - ERP Revo

## Estrutura Geral

O módulo "Configuração da Nota Fiscal Eletrônica de Serviços (NFSe)" do ERP Revo apresenta uma interface para configurar os parâmetros necessários para a emissão de notas fiscais eletrônicas de serviços. A página contém diversos campos de configuração organizados em seções lógicas, permitindo ao usuário definir as informações fiscais, tributárias e operacionais para a emissão de NFSe.

## Componentes Principais

### Cabeçalho e Menu Lateral

O cabeçalho e menu lateral seguem o mesmo padrão dos outros módulos do sistema, mantendo a consistência visual e de navegação.

### Área de Título e Navegação

A seção superior contém o título da página e links de navegação:

**Estrutura HTML:**

```html
<div class="cabecalho-container">
  <div class="breadcrumb">
    <a href="/inicio" class="breadcrumb-item">Início</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/servicos" class="breadcrumb-item">Serviços</a>
    <span class="breadcrumb-separador">/</span>
    <a href="/configuracoes" class="breadcrumb-item">Configurações</a>
    <span class="breadcrumb-separador">/</span>
    <span class="breadcrumb-item-atual"
      >Configuração da nota fiscal eletrônica de serviços (NFSe)</span
    >
  </div>

  <div class="cabecalho-titulo">
    <h1 class="titulo-pagina">
      Configuração da Nota Fiscal Eletrônica de Serviços (NFSe)
    </h1>
  </div>

  <div class="cabecalho-acoes">
    <a
      href="/configuracoes"
      class="botao-acao botao-secundario"
      id="btn-voltar"
    >
      <span class="icone icone-voltar"></span>
      <span class="texto">Voltar</span>
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
```

### Área de Alerta de Certificado Digital

A página exibe um alerta informativo sobre a necessidade de configurar um certificado digital:

**Estrutura HTML:**

```html
<div class="alerta-container">
  <div class="alerta alerta-aviso">
    <div class="alerta-icone">
      <span class="icone icone-aviso"></span>
    </div>
    <div class="alerta-conteudo">
      <h3 class="alerta-titulo">
        Para emitir NFS-e é necessário configurar um certificado digital
      </h3>
      <p class="alerta-texto">
        Não identificamos um certificado digital configurado em seu sistema.
        Configure o certificado digital para emitir NFS-e
      </p>
      <div class="alerta-acoes">
        <a
          href="/configuracoes_nfe?tipo=servico"
          class="botao-acao botao-primario"
        >
          <span class="icone icone-configurar"></span>
          <span class="texto">configurar certificado A1</span>
        </a>
      </div>
    </div>
  </div>
</div>
```

**Estilos CSS:**

```css
.alerta-container {
  margin-bottom: 24px;
}

.alerta {
  display: flex;
  padding: 16px;
  border-radius: 4px;
  background-color: #fff7e6;
  border-left: 4px solid #fa8c16;
}

.alerta-aviso {
  background-color: #fff7e6;
  border-left-color: #fa8c16;
}

.alerta-icone {
  margin-right: 12px;
  font-size: 20px;
  color: #fa8c16;
}

.alerta-conteudo {
  flex: 1;
}

.alerta-titulo {
  font-size: 16px;
  font-weight: 600;
  color: #333333;
  margin: 0;
  margin-bottom: 8px;
}

.alerta-texto {
  font-size: 14px;
  color: #666666;
  margin: 0;
  margin-bottom: 12px;
}

.alerta-acoes {
  display: flex;
  gap: 8px;
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

.icone-aviso::before {
  content: "⚠️";
}

.icone-configurar::before {
  content: "⚙️";
}
```

### Formulário de Configuração da NFSe

A área principal da página apresenta um formulário com diversos campos de configuração:

**Estrutura HTML:**

```html
<div class="formulario-container">
  <form id="form-nfse" class="formulario">
    <!-- Seção de Configurações Gerais -->
    <div class="formulario-secao">
      <div class="campo-grupo">
        <label for="modalidade" class="campo-label">Modalidade</label>
        <div class="campo-select">
          <select id="modalidade" name="modalidade" class="campo-select-input">
            <option value="nfse">
              Nota fiscal de serviço eletrônica (NFSe)
            </option>
            <option value="nfs">Nota fiscal de serviço impressa</option>
            <option value="nfe">Convênio NFe</option>
            <option value="manual">Emissão Própria (Manual)</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <!-- Seção de Configurações Tributárias -->
      <div class="campo-grupo">
        <label for="percentual-ir" class="campo-label">Percentual IR</label>
        <div class="campo-numero">
          <input
            type="text"
            id="percentual-ir"
            name="percentual_ir"
            class="campo-texto"
            value="0"
          />
          <span class="campo-numero-sufixo">%</span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="texto-ir" class="campo-label">Texto IR</label>
        <input
          type="text"
          id="texto-ir"
          name="texto_ir"
          class="campo-texto"
          value="( - ) IRenda Fonte 1,5%"
        />
      </div>

      <div class="campo-grupo">
        <label for="texto-ir-isento" class="campo-label">Texto IR Isento</label>
        <input
          type="text"
          id="texto-ir-isento"
          name="texto_ir_isento"
          class="campo-texto"
          value="IR Isento Cfe. Lei nro. 9430/96 Art."
        />
      </div>

      <div class="campo-grupo">
        <label for="percentual-iss" class="campo-label">Percentual ISS</label>
        <div class="campo-numero">
          <input
            type="text"
            id="percentual-iss"
            name="percentual_iss"
            class="campo-texto"
            value="3"
          />
          <span class="campo-numero-sufixo">%</span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="descontar-ir" class="campo-label"
          >Descontar IR automaticamente</label
        >
        <div class="campo-select">
          <select
            id="descontar-ir"
            name="descontar_ir"
            class="campo-select-input"
          >
            <option value="1">Sim</option>
            <option value="0" selected>Não</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="calcular-pis-cofins" class="campo-label"
          >Calcular PIS, COFINS e CSSL</label
        >
        <div class="campo-select">
          <select
            id="calcular-pis-cofins"
            name="calcular_pis_cofins"
            class="campo-select-input"
          >
            <option value="5000" selected>
              Notas Fiscais acima de R$ 5.000,00
            </option>
            <option value="215">Notas Fiscais acima de R$ 215,05</option>
            <option value="0">Não calcular</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="condicoes-padrao" class="campo-label"
          >Condições Padrão</label
        >
        <input
          type="text"
          id="condicoes-padrao"
          name="condicoes_padrao"
          class="campo-texto"
        />
      </div>

      <div class="campo-grupo">
        <label for="serie" class="campo-label">Série</label>
        <input
          type="text"
          id="serie"
          name="serie"
          class="campo-texto"
          value="1"
        />
        <p class="campo-descricao">Série padrão das notas fiscais</p>
      </div>

      <div class="campo-grupo">
        <label for="codigo-servico" class="campo-label"
          >Código da lista de serviço</label
        >
        <input
          type="text"
          id="codigo-servico"
          name="codigo_servico"
          class="campo-texto"
        />
        <p class="campo-descricao">Código da lista de serviço padrão</p>
      </div>

      <div class="campo-grupo">
        <label for="nomenclatura" class="campo-label"
          >Nomenclatura brasileira de serviço</label
        >
        <input
          type="text"
          id="nomenclatura"
          name="nomenclatura"
          class="campo-texto"
        />
        <p class="campo-descricao">Necessária para o IBPT</p>
      </div>

      <div class="campo-grupo">
        <label for="cnae" class="campo-label">CNAE</label>
        <input
          type="text"
          id="cnae"
          name="cnae"
          class="campo-texto"
          value="6203-1/00"
          placeholder="6203-1/00"
        />
        <p class="campo-descricao">
          CNAE específico para NFSe (deixe em branco para usar o mesmo da NFe)
        </p>
      </div>

      <div class="campo-grupo">
        <label for="iss-zerado" class="campo-label"
          >Valor do ISS zerado quando não retido</label
        >
        <div class="campo-select">
          <select id="iss-zerado" name="iss_zerado" class="campo-select-input">
            <option value="0" selected>Não</option>
            <option value="1">Sim</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
        <p class="campo-descricao">
          Em algumas empresas optantes pelo Simples Nacional, o valor de ISS
          deve ser zerado quando não retido
        </p>
      </div>

      <div class="campo-grupo">
        <label for="chave-webservice" class="campo-label"
          >Chave de autenticação do Webservice</label
        >
        <input
          type="text"
          id="chave-webservice"
          name="chave_webservice"
          class="campo-texto"
        />
        <p class="campo-descricao">Token de acesso</p>
      </div>

      <div class="campo-grupo">
        <label for="regime-especial" class="campo-label"
          >Código de identificação do regime especial de tributação</label
        >
        <div class="campo-select">
          <select
            id="regime-especial"
            name="regime_especial"
            class="campo-select-input"
          >
            <option value="">Selecione</option>
            <option value="1">Microempresa municipal</option>
            <option value="2">Estimativa</option>
            <option value="3">Sociedade de profissionais</option>
            <option value="4">Cooperativa</option>
            <option value="5">Microempresário Individual (MEI)</option>
            <option value="6">
              Microempresário e Empresa de Pequeno Porte (ME EPP)
            </option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="natureza-operacao" class="campo-label"
          >Código de natureza da operação (NFSe)</label
        >
        <div class="campo-select">
          <select
            id="natureza-operacao"
            name="natureza_operacao"
            class="campo-select-input"
          >
            <option value="">Selecione</option>
            <option value="1" selected>Tributação no município</option>
            <option value="2">Tributação fora do município</option>
            <option value="3">Isenção</option>
            <option value="4">Imune</option>
            <option value="5">
              Exigibilidade suspensa por decisão judicial
            </option>
            <option value="6">
              Exigibilidade suspensa por procedimento administrativo
            </option>
            <option value="7">Não Incidência</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="observacao-padrao" class="campo-label"
          >Observação padrão na NFS-e</label
        >
        <input
          type="text"
          id="observacao-padrao"
          name="observacao_padrao"
          class="campo-texto"
        />
      </div>

      <div class="campo-grupo">
        <label for="simples-nacional" class="campo-label"
          >Empresa optante pelo Simples nacional</label
        >
        <div class="campo-select">
          <select
            id="simples-nacional"
            name="simples_nacional"
            class="campo-select-input"
          >
            <option value="0">Não</option>
            <option value="1" selected>Sim</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="proximo-lote" class="campo-label"
          >Próximo número do lote na NFSe</label
        >
        <input
          type="text"
          id="proximo-lote"
          name="proximo_lote"
          class="campo-texto"
          value="1"
        />
      </div>

      <div class="campo-grupo">
        <label for="tipo-ambiente" class="campo-label">Tipo de ambiente</label>
        <div class="campo-select">
          <select
            id="tipo-ambiente"
            name="tipo_ambiente"
            class="campo-select-input"
          >
            <option value="1" selected>Produção</option>
            <option value="2">Homologação</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>

      <div class="campo-grupo">
        <label for="enviar-observacoes" class="campo-label"
          >Enviar observações da Ordem de Serviço para a NFSe</label
        >
        <div class="campo-select">
          <select
            id="enviar-observacoes"
            name="enviar_observacoes"
            class="campo-select-input"
          >
            <option value="1" selected>Sim</option>
            <option value="0">Não</option>
          </select>
          <span class="campo-select-seta"></span>
        </div>
      </div>
    </div>

    <div class="formulario-acoes">
      <button type="submit" class="botao-acao botao-primario" id="btn-salvar">
        <span class="texto">salvar</span>
      </button>

      <button
        type="button"
        class="botao-acao botao-secundario"
        id="btn-cancelar"
      >
        <span class="texto">cancelar</span>
      </button>
    </div>
  </form>
</div>
```

**Estilos CSS:**

```css
.formulario-container {
  padding: 0 24px 24px;
  background-color: #ffffff;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.formulario-secao {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 16px 24px;
}

.campo-grupo {
  margin-bottom: 16px;
}

.campo-label {
  display: block;
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  margin-bottom: 8px;
}

.campo-texto {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-texto:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-texto::placeholder {
  color: #bfbfbf;
}

.campo-descricao {
  font-size: 12px;
  color: #999999;
  margin: 4px 0 0 0;
}

.campo-select {
  position: relative;
}

.campo-select-input {
  width: 100%;
  padding: 8px 32px 8px 12px;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
  font-size: 14px;
  color: #333333;
  appearance: none;
  background-color: #ffffff;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.campo-select-input:focus {
  outline: none;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}

.campo-select-seta {
  position: absolute;
  top: 50%;
  right: 12px;
  transform: translateY(-50%);
  pointer-events: none;
  color: #999999;
}

.campo-select-seta::before {
  content: "▼";
  font-size: 12px;
}

.campo-numero {
  position: relative;
}

.campo-numero-sufixo {
  position: absolute;
  top: 50%;
  right: 12px;
  transform: translateY(-50%);
  color: #999999;
  font-size: 14px;
}

.formulario-acoes {
  display: flex;
  justify-content: flex-start;
  gap: 8px;
  margin-top: 16px;
  padding-top: 16px;
  border-top: 1px solid #f
(Content truncated due to size limit. Use line ranges to read in chunks)
```
