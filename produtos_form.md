# Formulário: Produtos

## Guia: Dados Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Descrição | Input text | Sim | Descrição completa do produto |
| Código (SKU) | Input text | Não | Código (SKU) ou referência (opcional) |
| Origem | Select | Sim | 0 - Nacional, exceto as indicadas nos códigos 3 a 5 (padrão) |
| Tipo | Select | Sim | Simples (padrão), Kit, Com variações, Fabricado, Matéria-prima |
| NCM | Input text | Sim | Exemplo: 1001.10.10 |
| GTIN/EAN | Input text | Não | Código de barras |
| Código CEST | Input text | Não | Exemplo: 01.003.00 |
| Preço de venda | Input text (numérico) | Sim | 0,00 |
| Unidade | Input text | Sim | Ex: Pç, Kg,... |
| Peso Líquido | Input text (numérico) | Não | Em Kg |
| Peso Bruto | Input text (numérico) | Não | Em Kg |
| Nº de volumes | Input text (numérico) | Não | - |

## Guia: Dados Complementares

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Marca | Input text (autocomplete) | Não | Pesquise pelo nome da marca |
| Tabela de medidas | Input text (autocomplete) | Não | Pesquise pelo nome da tabela |
| Descrição complementar | Editor de texto rico | Não | Campo exibido em propostas comerciais, pedidos de venda e descrição do produto no e-commerce |

### Seção: Imagens e anexos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Adicionar imagens ao produto | Button | Não | - |

### Seção: Campos adicionais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| [Campos personalizados] | Vários | Não | Campos adicionais configuráveis |

## Guia: Ficha técnica

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Sugerir atributos | Button | Não | - |
| Pesquise pelo nome do atributo | Input text (autocomplete) | Não | - |
| Valor | Input text | Não | - |
| Adicionar atributo | Button | Não | - |

## Guia: Anúncios

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Adicionar anúncio | Button | Não | - |

### Colunas da tabela de anúncios

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| E-commerce | Text | - | - |
| Identificador | Text | - | - |
| Descrição | Text | - | - |

## Guia: Outros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Unidade por caixa | Input text | Não | Itens por embalagem |
| Custo | Input text (numérico) | Não | Preço de custo |
| Linha de produto | Select | Não | Selecione |
| Garantia | Input text | Não | Exemplo: 3 meses |
| Markup | Input text (numérico) | Não | 0,00000 |
| Permitir inclusão nas vendas | Select | Não | Sim (padrão), Não |

### Seção: Informações tributárias adicionais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| GTIN/EAN tributável | Input text | Não | Código de barras de comercialização |
| Unidade tributável | Input text | Não | Campo usado em notas fiscais de exportação |
| Fator de conversão | Input text (numérico) | Não | Campo usado em notas fiscais de exportação |
| Código de Enquadramento IPI | Input text | Não | Código de Enquadramento Legal do IPI |
| Valor do IPI fixo | Input text (numérico) | Não | Somente para produtos com tributação específica |
| EX TIPI | Input text | Não | - |

## Campos Dinâmicos

### Campos que aparecem ao selecionar o tipo "Kit"

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Adicionar produto ao kit | Button | Sim | - |
| Produto | Input text (autocomplete) | Sim | - |
| Quantidade | Input text (numérico) | Sim | - |

### Campos que aparecem ao selecionar o tipo "Com variações"

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Adicionar variação | Button | Sim | - |
| Nome da variação | Input text | Sim | Ex: Cor, Tamanho |
| Valores | Input text (múltiplos) | Sim | Ex: Azul, Vermelho, P, M, G |

### Campos que aparecem ao selecionar o tipo "Fabricado"

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Adicionar matéria-prima | Button | Sim | - |
| Matéria-prima | Input text (autocomplete) | Sim | - |
| Quantidade | Input text (numérico) | Sim | - |

### Campos que aparecem ao clicar em "Adicionar anúncio"

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| E-commerce | Select | Sim | Lista de e-commerces integrados |
| Produto vinculado | Input text (autocomplete) | Sim | - |
| Descrição | Input text | Não | - |
