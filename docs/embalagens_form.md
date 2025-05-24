# Formulário: Embalagens

## Campos Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Descrição | Input text | Sim | - |
| Tipo | Select | Sim | Envelope, Pacote / Caixa, Rolo / Cilindro |
| Largura | Input text (numérico) | Sim | Em centímetros (cm) |
| Comprimento | Input text (numérico) | Sim | Em centímetros (cm) |
| Peso | Input text (numérico) | Sim | Em quilogramas (Kg) |

## Campos Dinâmicos

| Tipo de Embalagem | Campo Adicional | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-------------------|-----------------|------------------|-------------|-------------------------|
| Rolo / Cilindro | Diâmetro | Input text (numérico) | Sim | Em centímetros (cm) |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salvar o cadastro da embalagem |
| Cancelar | Button | Cancelar a operação e voltar à listagem |

## Funcionalidades Especiais

| Funcionalidade | Descrição |
|----------------|-----------|
| Criar embalagens Correios | Botão que permite criar automaticamente as embalagens padrão dos Correios |
