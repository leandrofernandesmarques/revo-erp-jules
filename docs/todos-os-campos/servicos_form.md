# Formulário: Serviços

## Campos Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Descrição | Input text | Sim | Descrição completa do serviço |
| Código | Input text | Não | Código ou referência (opcional) |
| Preço | Input text (numérico) | Sim | Preço de venda |
| Unidade | Input text | Sim | Ex: Pç, Kg,... |
| Situação | Select | Sim | Ativo (padrão), Inativo |
| Código do serviço conforme tabela de serviços | Input text | Não | - |
| Nomenclatura brasileira de serviço (NBS) | Input text | Não | Necessária para o IBPT |

## Descrição Complementar

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Editor de texto | Editor de texto rico | Não | Campo exibido em propostas comerciais e pedidos de venda |

## Observações

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Observações | Textarea | Não | - |

## Campos Dinâmicos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| [Campos personalizados] | Vários | Não | Campos adicionais configuráveis |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salvar o cadastro do serviço |
| Cancelar | Button | Cancelar a operação e voltar à listagem |
