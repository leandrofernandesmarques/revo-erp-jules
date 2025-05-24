# Formulário: Clientes e Fornecedores

## Guia: Dados Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome | Input text | Sim | Nome ou Razão Social do contato |
| Fantasia | Input text | Não | - |
| Código | Input text | Não | Opcional |
| Tipo de pessoa | Select | Sim | Pessoa Jurídica (padrão), Pessoa Física, Estrangeiro, Estrangeiro no Brasil |
| CNPJ | Input text | Sim (para PJ) | Máscara: XX.XXX.XXX/XXXX-XX |
| Contribuinte | Select | Não | 0 - Não informado (padrão), 1 - Contribuinte ICMS, 2 - Contribuinte isento de Inscrição, 9 - Não Contribuinte |
| Inscrição Estadual | Input text | Não | - |
| Inscrição Municipal | Input text | Não | - |
| Tipo de contato | Select | Sim | Cliente, Fornecedor, Transportador, Outro |
| CEP | Input text | Não | Máscara: XXXXX-XXX |
| Município | Input text | Não | Preenchido automaticamente pelo CEP |
| UF | Select | Não | Lista de estados brasileiros + EX (exterior) |
| Endereço | Input text | Não | - |
| Bairro | Input text | Não | Preenchido automaticamente pelo CEP |
| Número | Input text | Não | - |
| Complemento | Input text | Não | - |
| Possui endereço de cobrança diferente do endereço principal | Checkbox | Não | Desmarcado (padrão) |

## Guia: Dados Complementares

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Código de regime tributário | Select | Não | Não informado (padrão), Simples Nacional, Regime Normal |
| Inscrição Suframa | Input text | Não | - |
| Data de nascimento | Datepicker | Não | - |
| Status no CRM | Select | Não | Cliente (padrão), Inativo, Lead, Prospect |
| Vendedor | Input text (autocomplete) | Não | - |
| Condição de pagamento | Input text (autocomplete) | Não | Número de parcelas ou prazos padrão. Exemplos: 30 60, 3x ou 15 +2x |
| Data de criação | Datepicker | Não | Data atual (preenchido automaticamente) |

## Guia: Anexos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Procurar arquivo | Button + File upload | Não | Tamanho máximo: 2MB |

## Guia: Observações

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Observações | Textarea | Não | - |

## Campos Dinâmicos

### Campos que aparecem ao marcar "Possui endereço de cobrança diferente do endereço principal"

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| CEP de cobrança | Input text | Não | Máscara: XXXXX-XXX |
| Município de cobrança | Input text | Não | Preenchido automaticamente pelo CEP |
| UF de cobrança | Select | Não | Lista de estados brasileiros + EX (exterior) |
| Endereço de cobrança | Input text | Não | - |
| Bairro de cobrança | Input text | Não | Preenchido automaticamente pelo CEP |
| Número de cobrança | Input text | Não | - |
| Complemento de cobrança | Input text | Não | - |

### Campos que mudam conforme o Tipo de pessoa

| Tipo de Pessoa | Campo Original | Campo Alterado | Tipo de Controle | Obrigatório |
|----------------|----------------|----------------|------------------|-------------|
| Pessoa Física | CNPJ | CPF | Input text | Sim |
| Pessoa Física | - | RG | Input text | Não |
| Estrangeiro | CNPJ | Documento | Input text | Não |
| Estrangeiro no Brasil | CNPJ | Documento | Input text | Não |
