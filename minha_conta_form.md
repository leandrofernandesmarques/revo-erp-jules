# Formulário: Minha Conta

## Abas Principais

| Aba | Descrição |
|-----|-----------|
| Dados da conta | Informações gerais da conta e uso de recursos |
| Dados de cobrança | Informações fiscais para faturamento |
| Forma de pagamento | Configuração do método de pagamento |
| Detalhes de pagamento | Histórico e detalhes de pagamentos realizados |

## Dados da Conta

### Informações Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Data de inscrição | Label informativo | N/A | Data de criação da conta |
| Plano atual | Label informativo | N/A | Nome do plano contratado |
| Valor/mês | Label informativo | N/A | Valor mensal do plano |
| Periodicidade | Label informativo | N/A | Mensal, Trimestral, Anual |
| Situação | Label informativo | N/A | Ativa, Bloqueada, Cancelada |
| Quantidade de acessos | Label informativo | N/A | Número total de acessos |
| Último acesso | Label informativo | N/A | Data e hora do último acesso |
| Último pagamento | Label informativo | N/A | Data do último pagamento |

### Indicadores de Uso

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Armazenamento de dados | Gráfico circular | Percentual de uso do espaço de dados |
| Armazenamento de arquivos | Gráfico circular | Percentual de uso do espaço de anexos |
| Usuários | Gráfico circular | Quantidade de usuários ativos vs. total |
| E-commerces | Gráfico circular | Quantidade de lojas integradas vs. total |

### Capacidade

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Espaço do plano | Label informativo | Espaço total incluído no plano |
| Espaço adicional | Label informativo | Espaço extra contratado |
| Indicações | Label informativo | Espaço ganho por indicações |
| Espaço anexos | Label informativo | Espaço para anexos no plano |
| Adicional anexos | Label informativo | Espaço adicional para anexos |
| Usuários do plano | Label informativo | Quantidade de usuários incluídos |
| Usuários adicionais | Label informativo | Quantidade de usuários extras |

## Dados de Cobrança

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Razão Social/Nome | Input text | Sim | Nome completo ou razão social |
| CNPJ/CPF | Input text | Sim | Máscara conforme tipo de pessoa |
| Email para NFe | Input text | Sim | Email para recebimento de notas fiscais |
| Endereço | Input text | Sim | Endereço completo |
| Número | Input text | Sim | Número do endereço |
| Complemento | Input text | Não | Informações adicionais do endereço |
| Bairro | Input text | Sim | Nome do bairro |
| Cidade | Input text | Sim | Nome da cidade |
| Estado | Select | Sim | Lista de estados brasileiros |
| CEP | Input text | Sim | Máscara: XXXXX-XXX |

## Forma de Pagamento

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Método de pagamento | Radio buttons | Sim | Cartão de crédito, Boleto bancário |
| Número do cartão | Input text | Sim (para cartão) | Máscara: XXXX XXXX XXXX XXXX |
| Nome no cartão | Input text | Sim (para cartão) | Nome como aparece no cartão |
| Validade | Input text | Sim (para cartão) | Máscara: MM/AAAA |
| Código de segurança | Input text | Sim (para cartão) | Máscara: XXX ou XXXX |
| Próxima cobrança | Label informativo | N/A | Data da próxima cobrança |

## Detalhes de Pagamento

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Filtro de período | Datepicker | Permite filtrar pagamentos por período |
| Tabela de pagamentos | Tabela | Lista de pagamentos com data, valor e status |
| Notas fiscais | Links | Links para download das notas fiscais |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Upgrade de plano | Button | Acessa página para alterar plano |
| Ações | Dropdown button | Opções adicionais (cancelar, alterar plano) |
| Indique e ganhe | Button | Acessa programa de indicação |
| Salvar | Button | Salva alterações nos dados |
