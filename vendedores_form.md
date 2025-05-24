# Formulário: Vendedores

## Campos Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome | Input text | Sim | Nome completo do vendedor |
| Fantasia | Input text | Não | Nome de fantasia ou apelido |
| Código | Input text | Não | Opcional |
| Tipo de Pessoa | Select | Sim | Jurídica (padrão), Física, Estrangeiro, Estrangeiro no Brasil |
| CNPJ | Input text | Sim (para PJ) | Máscara: XX.XXX.XXX/XXXX-XX |
| Contribuinte | Select | Não | Não informado (padrão), Contribuinte ICMS, Contribuinte isento de Inscrição, Não Contribuinte |
| Inscrição Estadual | Input text | Não | - |
| CEP | Input text | Não | Máscara: XXXXX-XXX |
| Cidade | Input text | Não | Preenchido automaticamente pelo CEP |
| UF | Select | Não | Lista de estados brasileiros + EX (exterior) |
| Endereço | Input text | Não | - |
| Bairro | Input text | Não | Preenchido automaticamente pelo CEP |
| Número | Input text | Não | - |
| Complemento | Input text | Não | - |
| Telefone | Input text | Não | - |
| Celular | Input text | Não | - |
| Email | Input text | Não | - |
| Situação | Select | Sim | Ativo com acesso ao sistema (padrão), Ativo, Inativo, Sem Movimento, Excluído |
| Depósito | Select | Não | Padrão, Geral |
| E-mail para comunicações | Input text | Não | - |

## Dados de acesso

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Usuário do Sistema | Input text | Não | Necessário apenas para vendedores com acesso ao sistema |

## Campos Dinâmicos

### Campos que mudam conforme o Tipo de pessoa

| Tipo de Pessoa | Campo Original | Campo Alterado | Tipo de Controle | Obrigatório |
|----------------|----------------|----------------|------------------|-------------|
| Pessoa Física | CNPJ | CPF | Input text | Sim |
| Pessoa Física | - | RG | Input text | Não |
| Estrangeiro | CNPJ | Documento | Input text | Não |
| Estrangeiro no Brasil | CNPJ | Documento | Input text | Não |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salvar o cadastro do vendedor |
| Cancelar | Button | Cancelar a operação e voltar à listagem |
