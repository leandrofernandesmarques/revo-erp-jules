# Formulário: Loja de Extensões

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Minhas extensões | Button | Não | Exibe extensões já instaladas |
| Busca | Input text | Não | Placeholder: "Busque pela funcionalidade ou dúvida" |
| E-commerce | Filter button | Não | Filtra extensões para e-commerce |
| Comércio | Filter button | Não | Filtra extensões para comércio |
| Serviço | Filter button | Não | Filtra extensões para serviços |
| Indústria | Filter button | Não | Filtra extensões para indústria |
| Conta | Filter button | Não | Filtra extensões para gestão de conta |

## Cards de Extensões

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Ícone | Image | Ícone representativo da extensão |
| Nome | Label | Nome da extensão |
| Categoria | Label | Categoria da extensão (vendas, suprimentos, etc.) |
| Preço | Label | Valor da extensão ou "GRÁTIS" |
| Instalar | Button | Inicia o processo de instalação da extensão |
| Etiqueta "Novo" | Label | Indica extensões recém-adicionadas |

## Formulário de Instalação de Extensão

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Termos de uso | Checkbox | Sim | Aceite dos termos de uso da extensão |
| Política de privacidade | Checkbox | Sim | Aceite da política de privacidade |
| Permissões solicitadas | Section | N/A | Lista de permissões requeridas pela extensão |
| Método de pagamento | Select | Condicional | Obrigatório para extensões pagas |
| Cupom de desconto | Input text | Não | Código promocional |
| Período de cobrança | Radio buttons | Condicional | Mensal, Anual |

## Detalhes da Extensão

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Descrição | Text section | Descrição detalhada da extensão |
| Funcionalidades | List | Lista de recursos e funcionalidades |
| Capturas de tela | Image gallery | Imagens demonstrativas da extensão |
| Avaliações | Rating system | Avaliações de outros usuários |
| Perguntas frequentes | Accordion | Perguntas e respostas sobre a extensão |
| Desenvolvedor | Label | Nome do desenvolvedor da extensão |
| Versão | Label | Versão atual da extensão |
| Data de atualização | Label | Data da última atualização |

## Minhas Extensões

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Status | Indicator | Status atual da extensão (Ativo, Inativo) |
| Nome | Label | Nome da extensão instalada |
| Categoria | Label | Categoria da extensão |
| Data de instalação | Label | Data em que a extensão foi instalada |
| Data de expiração | Label | Data de término da licença (se aplicável) |
| Valor | Label | Valor pago pela extensão |
| Ações | Button group | Configurar, Desativar/Ativar, Desinstalar |

## Configuração de Extensão

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome personalizado | Input text | Não | Nome personalizado para a extensão |
| Configurações específicas | Section | N/A | Campos específicos para cada extensão |
| Usuários com acesso | Multiselect | Não | Usuários que podem acessar a extensão |
| Notificações | Checkbox group | Não | Opções de notificação da extensão |
| Integração com módulos | Checkbox group | Não | Módulos que se integram com a extensão |

## Formulário de Avaliação

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Classificação | Star rating | Sim | 1 a 5 estrelas |
| Título | Input text | Sim | Título da avaliação |
| Comentário | Textarea | Sim | Texto da avaliação |
| Recomendaria | Radio buttons | Sim | Sim, Não |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Instalar | Button | Inicia instalação da extensão |
| Configurar | Button | Acessa configurações da extensão |
| Desinstalar | Button | Remove a extensão |
| Ver mais | Button | Exibe mais detalhes da extensão |
| Voltar | Button | Retorna à listagem de extensões |
