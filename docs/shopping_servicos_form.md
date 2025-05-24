# Formulário: Shopping de Serviços

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Busca | Input text | Não | Placeholder: "Busque por empresas" |
| Todos os parceiros | Toggle button | Não | Exibe todos os parceiros disponíveis |
| Agência | Toggle button | Não | Filtra parceiros do tipo Agência |
| Consultoria de Ecommerce | Toggle button | Não | Filtra parceiros de consultoria |
| Cursos digitais | Toggle button | Não | Filtra parceiros de cursos |
| Implementador | Toggle button | Não | Filtra parceiros implementadores |
| Certificado Digital | Toggle button | Não | Filtra parceiros de certificado digital |

## Cards de Parceiros

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Logo | Image | Logotipo da empresa parceira |
| Nome | Label | Nome da empresa parceira |
| Tipo | Label | Categoria do parceiro (Implementador, Agência, etc.) |
| Localização | Label | Cidade/Estado do parceiro |
| Nível de parceria | Badge | Classificação do parceiro (Diamante, Ouro, etc.) |
| Detalhes | Link/Button | Acessa página detalhada do parceiro |

## Detalhes do Parceiro

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Logo | Image | Logotipo da empresa parceira |
| Nome | Label | Nome da empresa parceira |
| Tipo | Label | Categoria do parceiro |
| Descrição | Text section | Descrição detalhada do parceiro |
| Serviços oferecidos | List | Lista de serviços disponíveis |
| Contato | Section | Informações de contato |
| Website | Link | Site do parceiro |
| E-mail | Link | E-mail de contato |
| Telefone | Label | Número de telefone |
| Redes sociais | Icon links | Links para redes sociais |
| Portfólio | Gallery | Exemplos de trabalhos realizados |
| Avaliações | Rating system | Avaliações de outros usuários |

## Formulário de Contato com Parceiro

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome | Input text | Sim | Nome completo |
| E-mail | Input email | Sim | E-mail válido |
| Telefone | Input text | Sim | Máscara: (99) 99999-9999 |
| Empresa | Input text | Não | Nome da empresa |
| Assunto | Select | Sim | Orçamento, Dúvida, Parceria |
| Mensagem | Textarea | Sim | Texto da mensagem |
| Autorizo contato | Checkbox | Sim | Consentimento para contato |
| Política de privacidade | Checkbox | Sim | Aceite da política de privacidade |

## Formulário de Avaliação de Parceiro

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Classificação | Star rating | Sim | 1 a 5 estrelas |
| Título | Input text | Sim | Título da avaliação |
| Comentário | Textarea | Sim | Texto da avaliação |
| Serviço contratado | Select | Sim | Lista de serviços do parceiro |
| Recomendaria | Radio buttons | Sim | Sim, Não |
| Nome | Input text | Sim | Nome do avaliador |
| E-mail | Input email | Sim | E-mail válido |

## Formulário de Solicitação de Parceria

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome da empresa | Input text | Sim | Nome da empresa |
| CNPJ | Input text | Sim | Máscara: 99.999.999/9999-99 |
| Tipo de parceria | Select | Sim | Implementador, Agência, Consultoria, etc. |
| Website | Input text | Sim | URL válida |
| Nome do responsável | Input text | Sim | Nome completo |
| E-mail | Input email | Sim | E-mail válido |
| Telefone | Input text | Sim | Máscara: (99) 99999-9999 |
| Descrição da empresa | Textarea | Sim | Texto descritivo |
| Serviços oferecidos | Checkbox group | Sim | Lista de serviços disponíveis |
| Experiência com ERP | Select | Sim | Nenhuma, Básica, Intermediária, Avançada |
| Como conheceu | Select | Sim | Internet, Indicação, Evento, Outros |
| Documentos | File upload | Sim | Portfólio, certificações, etc. |
| Termos de parceria | Checkbox | Sim | Aceite dos termos de parceria |

## Botões de Ação (Comuns a todas as telas)

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Ver detalhes | Button | Acessa página detalhada do parceiro |
| Entrar em contato | Button | Abre formulário de contato |
| Solicitar orçamento | Button | Solicita orçamento ao parceiro |
| Avaliar | Button | Abre formulário de avaliação |
| Compartilhar | Button | Compartilha perfil do parceiro |
| Voltar | Button | Retorna à listagem de parceiros |
