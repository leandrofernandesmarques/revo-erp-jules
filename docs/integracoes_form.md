# Formulário: Integrações

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por integrações ou canais de venda" |
| Todas as integrações | Toggle button | Não | Exibe todas as integrações disponíveis |
| Marketplaces e hubs | Toggle button | Não | Filtra apenas marketplaces e hubs |
| Plataformas de e-commerce | Toggle button | Não | Filtra apenas plataformas de e-commerce |
| Outras integrações | Toggle button | Não | Filtra apenas outras integrações |

## Cartões de Integração (Comuns a todas as categorias)

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Logo | Image | Logotipo da plataforma/marketplace |
| Nome | Label | Nome da plataforma/marketplace |
| Categoria | Label | Tipo de integração (Marketplace, E-commerce, etc.) |
| Instalar | Button | Inicia o processo de instalação da integração |

## Formulário de Configuração de Marketplace

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome da integração | Input text | Sim | Nome personalizado para a integração |
| Credenciais de acesso | Section | N/A | Seção para credenciais específicas |
| Chave de API | Input text | Condicional | Chave de API do marketplace |
| Token de acesso | Input text | Condicional | Token de acesso do marketplace |
| Usuário | Input text | Condicional | Nome de usuário na plataforma |
| Senha | Input password | Condicional | Senha de acesso à plataforma |
| ID da loja | Input text | Condicional | Identificador da loja no marketplace |
| Ambiente | Radio buttons | Sim | Produção, Homologação/Sandbox |

## Configurações de Sincronização (Marketplaces)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Sincronizar estoque | Checkbox | Não | Ativa sincronização de estoque |
| Sincronizar preços | Checkbox | Não | Ativa sincronização de preços |
| Sincronizar pedidos | Checkbox | Não | Ativa sincronização de pedidos |
| Intervalo de sincronização | Select | Sim | 5 min, 15 min, 30 min, 1 hora, 2 horas |
| Depósito para estoque | Select | Condicional | Lista de depósitos cadastrados |
| Tabela de preço | Select | Condicional | Lista de tabelas de preço cadastradas |
| Status para novos pedidos | Select | Condicional | Status inicial para pedidos importados |

## Mapeamento de Categorias (Marketplaces)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Categoria no ERP | Select | Sim | Lista de categorias do ERP |
| Categoria no marketplace | Select | Sim | Lista de categorias do marketplace |
| Adicionar mapeamento | Button | Não | Adiciona novo mapeamento de categoria |

## Formulário de Configuração de E-commerce

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome da integração | Input text | Sim | Nome personalizado para a integração |
| URL da loja | Input text | Sim | Endereço completo da loja virtual |
| Chave de API | Input text | Sim | Chave de API da plataforma |
| Token de acesso | Input text | Sim | Token de acesso da plataforma |
| Versão da API | Select | Sim | Versões disponíveis da API |
| Ambiente | Radio buttons | Sim | Produção, Homologação/Sandbox |

## Configurações de Sincronização (E-commerce)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Sincronizar produtos | Checkbox | Não | Ativa sincronização de produtos |
| Sincronizar estoque | Checkbox | Não | Ativa sincronização de estoque |
| Sincronizar preços | Checkbox | Não | Ativa sincronização de preços |
| Sincronizar pedidos | Checkbox | Não | Ativa sincronização de pedidos |
| Sincronizar clientes | Checkbox | Não | Ativa sincronização de clientes |
| Intervalo de sincronização | Select | Sim | 5 min, 15 min, 30 min, 1 hora, 2 horas |
| Depósito para estoque | Select | Condicional | Lista de depósitos cadastrados |
| Tabela de preço | Select | Condicional | Lista de tabelas de preço cadastradas |
| Status para novos pedidos | Select | Condicional | Status inicial para pedidos importados |

## Formulário de Configuração de Outras Integrações

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome da integração | Input text | Sim | Nome personalizado para a integração |
| Tipo de integração | Select | Sim | CRM, ERP, Financeiro, Logística, Outros |
| Credenciais de acesso | Section | N/A | Seção para credenciais específicas |
| Chave de API | Input text | Condicional | Chave de API do sistema |
| Token de acesso | Input text | Condicional | Token de acesso do sistema |
| Usuário | Input text | Condicional | Nome de usuário no sistema |
| Senha | Input password | Condicional | Senha de acesso ao sistema |
| URL do serviço | Input text | Condicional | Endereço do serviço de integração |
| Ambiente | Radio buttons | Sim | Produção, Homologação/Sandbox |

## Configurações de Sincronização (Outras Integrações)

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Dados a sincronizar | Multiselect | Sim | Produtos, Clientes, Pedidos, Financeiro, etc. |
| Direção da sincronização | Radio buttons | Sim | Importar, Exportar, Bidirecional |
| Intervalo de sincronização | Select | Sim | 5 min, 15 min, 30 min, 1 hora, 2 horas |
| Executar sincronização manual | Button | Não | Inicia sincronização imediata |

## Painel de Integrações Configuradas

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Status | Indicator | Status atual da integração (Ativo, Inativo, Erro) |
| Nome | Label | Nome personalizado da integração |
| Tipo | Label | Categoria da integração |
| Última sincronização | Label | Data e hora da última sincronização |
| Próxima sincronização | Label | Data e hora da próxima sincronização programada |
| Ações | Button group | Editar, Pausar/Ativar, Sincronizar agora, Excluir |

## Logs de Sincronização

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Data/Hora | Column | Momento da ocorrência |
| Tipo | Column | Tipo de evento (Informação, Alerta, Erro) |
| Descrição | Column | Detalhes do evento de sincronização |
| Dados | Button | Exibe dados detalhados do evento |

## Botões de Ação (Comuns a todos os formulários)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Salvar | Button | Salva a configuração da integração |
| Cancelar | Button | Cancela a configuração da integração |
| Testar conexão | Button | Verifica se as credenciais estão corretas |
| Sincronizar agora | Button | Inicia sincronização imediata |
