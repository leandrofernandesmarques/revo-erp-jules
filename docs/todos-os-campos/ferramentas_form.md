# Formulário: Ferramentas

## Navegação Principal

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Geral | Tab/Button | Acessa ferramentas gerais do sistema |
| Importações | Tab/Button | Acessa ferramentas de importação de dados |
| Backup | Tab/Button | Acessa ferramentas de backup do sistema |
| Exclusão de registros | Tab/Button | Acessa ferramentas para exclusão de dados |
| Inutilizações de NFes | Tab/Button | Acessa ferramentas para inutilizar NFes |
| Gerenciar Anexos | Tab/Button | Acessa gerenciador de anexos do sistema |
| Resumo de Sincronizações | Tab/Button | Acessa resumo de sincronizações de integrações |

## Ferramentas Gerais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Calculadora de preços | Button/Tool | N/A | Ferramenta para cálculo de preços |
| Gerador de códigos de barras | Button/Tool | N/A | Ferramenta para gerar códigos de barras |
| Verificador de CNPJ/CPF | Button/Tool | N/A | Ferramenta para validar documentos |
| Consulta de CEP | Button/Tool | N/A | Ferramenta para consultar endereços |
| Conversor de unidades | Button/Tool | N/A | Ferramenta para converter unidades de medida |

## Importações

### Importador de Contatos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Arquivo | File upload | Sim | Formatos: CSV, XLS, XLSX |
| Tipo de contato | Select | Sim | Cliente, Fornecedor, Ambos |
| Primeira linha contém cabeçalho | Checkbox | Não | Marcado por padrão |
| Delimitador | Select | Condicional | Vírgula, Ponto e vírgula, Tabulação, Outro |
| Outro delimitador | Input text | Condicional | Obrigatório se "Outro" selecionado |
| Mapeamento de campos | Mapping tool | Sim | Associação entre colunas do arquivo e campos do sistema |
| Ignorar erros | Checkbox | Não | Continua importação mesmo com erros |
| Substituir registros existentes | Checkbox | Não | Atualiza registros se já existirem |

### Importador de Produtos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Arquivo | File upload | Sim | Formatos: CSV, XLS, XLSX |
| Primeira linha contém cabeçalho | Checkbox | Não | Marcado por padrão |
| Delimitador | Select | Condicional | Vírgula, Ponto e vírgula, Tabulação, Outro |
| Outro delimitador | Input text | Condicional | Obrigatório se "Outro" selecionado |
| Mapeamento de campos | Mapping tool | Sim | Associação entre colunas do arquivo e campos do sistema |
| Importar estoque | Checkbox | Não | Importa quantidades de estoque |
| Depósito para estoque | Select | Condicional | Lista de depósitos cadastrados |
| Ignorar erros | Checkbox | Não | Continua importação mesmo com erros |
| Substituir registros existentes | Checkbox | Não | Atualiza registros se já existirem |

### Importador de Pedidos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Arquivo | File upload | Sim | Formatos: CSV, XLS, XLSX |
| Tipo de pedido | Select | Sim | Venda, Compra |
| Primeira linha contém cabeçalho | Checkbox | Não | Marcado por padrão |
| Delimitador | Select | Condicional | Vírgula, Ponto e vírgula, Tabulação, Outro |
| Outro delimitador | Input text | Condicional | Obrigatório se "Outro" selecionado |
| Mapeamento de campos | Mapping tool | Sim | Associação entre colunas do arquivo e campos do sistema |
| Status inicial | Select | Sim | Lista de status disponíveis |
| Ignorar erros | Checkbox | Não | Continua importação mesmo com erros |

## Backup

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de backup | Radio buttons | Sim | Completo, Parcial |
| Módulos a incluir | Multiselect | Condicional | Lista de módulos do sistema |
| Incluir anexos | Checkbox | Não | Inclui arquivos anexados no backup |
| Formato de saída | Select | Sim | ZIP, SQL |
| Programar backup | Checkbox | Não | Ativa agendamento de backup |
| Frequência | Select | Condicional | Diária, Semanal, Mensal |
| Dia da semana | Select | Condicional | Segunda a Domingo |
| Dia do mês | Select | Condicional | 1 a 31 |
| Hora | Timepicker | Condicional | Hora do backup agendado |
| E-mail para notificação | Input email | Não | E-mail para receber backup |

## Exclusão de Registros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de registro | Select | Sim | Produtos, Clientes, Pedidos, Notas fiscais, etc. |
| Filtros específicos | Section | N/A | Filtros específicos para cada tipo |
| Período | Datepicker (range) | Não | Período para filtrar registros |
| Status | Multiselect | Não | Status dos registros a excluir |
| Confirmação de exclusão | Checkbox | Sim | "Estou ciente que esta ação é irreversível" |
| Senha de confirmação | Input password | Sim | Senha do usuário para confirmar |

## Inutilizações de NFes

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Série | Input number | Sim | Série da NFe |
| Número inicial | Input number | Sim | Primeiro número a inutilizar |
| Número final | Input number | Sim | Último número a inutilizar |
| Justificativa | Textarea | Sim | Motivo da inutilização (mínimo 15 caracteres) |
| Ambiente | Radio buttons | Sim | Produção, Homologação |
| Certificado digital | Select | Sim | Certificado para assinatura |

## Gerenciar Anexos

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de registro | Select | Sim | Produtos, Clientes, Pedidos, Notas fiscais, etc. |
| Filtro de pesquisa | Input text | Não | Pesquisa por nome/código do registro |
| Período | Datepicker (range) | Não | Período para filtrar anexos |
| Tamanho mínimo | Input number | Não | Tamanho mínimo do arquivo em KB |
| Tamanho máximo | Input number | Não | Tamanho máximo do arquivo em KB |
| Tipo de arquivo | Multiselect | Não | PDF, Imagens, Documentos, etc. |
| Ações em massa | Button group | N/A | Selecionar todos, Excluir selecionados, etc. |

## Resumo de Sincronizações

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Período | Datepicker (range) | Sim | Período para visualizar sincronizações |
| Integração | Select | Não | Filtro por integração específica |
| Tipo de sincronização | Select | Não | Produtos, Pedidos, Estoque, Preços, etc. |
| Status | Select | Não | Sucesso, Erro, Pendente |
| Exibir detalhes | Checkbox | Não | Mostra informações detalhadas |
| Agrupar por | Select | Não | Integração, Data, Tipo, Status |

## Botões de Ação (Comuns a todas as ferramentas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Executar | Button | Executa a ferramenta selecionada |
| Cancelar | Button | Cancela a operação atual |
| Exportar resultados | Button | Exporta resultados da ferramenta |
| Ajuda | Button | Exibe documentação de ajuda |
