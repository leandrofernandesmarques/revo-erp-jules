# Formulário: Agenda

## Abas Principais

| Aba | Descrição |
|-----|-----------|
| Meus compromissos | Exibe compromissos agendados para o usuário atual |
| Agendados para outros usuários | Exibe compromissos agendados para outros usuários do sistema |

## Controles de Visualização

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Navegação de mês | Botões (anterior/próximo) | N/A | Permite navegar entre meses |
| Hoje | Button | N/A | Retorna para o dia atual |
| Visualização | Toggle buttons | Sim | Mensal (padrão), Semanal, Diário |

## Calendário

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Dias do mês | Grid interativo | Exibe os dias do mês com compromissos marcados |
| Compromissos | Cards informativos | Exibe detalhes dos compromissos agendados |

## Formulário de Novo Compromisso

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Título | Input text | Sim | Descrição breve do compromisso |
| Data | Datepicker | Sim | Data do compromisso |
| Hora inicial | Timepicker | Sim | Horário de início |
| Hora final | Timepicker | Não | Horário de término |
| Descrição | Textarea | Não | Detalhes do compromisso |
| Responsável | Select | Sim | Usuário atual (padrão), outros usuários do sistema |
| Tipo | Select | Não | Reunião, Ligação, Visita, Outro |
| Notificação | Select | Não | Sem notificação, 15 min antes, 30 min antes, 1 hora antes, 1 dia antes |
| Repetição | Select | Não | Não repetir (padrão), Diariamente, Semanalmente, Mensalmente, Anualmente |

## Campos de Compromissos Financeiros

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Cliente/Fornecedor | Select | Não | Lista de clientes/fornecedores cadastrados |
| Valor | Input text (numérico) | Não | Valor monetário |
| Categoria | Select | Não | Lista de categorias financeiras |
| Situação | Select | Não | Pendente, Confirmado, Cancelado |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Novo Compromisso | Button | Abre formulário para criar novo compromisso |
| Editar | Button | Edita compromisso existente |
| Excluir | Button | Remove compromisso |
| Salvar | Button | Salva novo compromisso ou alterações |
| Cancelar | Button | Cancela criação ou edição de compromisso |
