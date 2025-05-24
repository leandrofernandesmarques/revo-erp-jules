# Fluxos de Navegação e Interações do Módulo Integrações

## Visão Geral dos Fluxos

O módulo de Integrações do ERP Revo apresenta diversos fluxos de navegação e interações que permitem ao usuário instalar, configurar, gerenciar e monitorar integrações com plataformas externas. Este documento detalha os principais fluxos de navegação e interações do módulo, incluindo comportamentos esperados, validações e mensagens exibidas ao usuário.

## 1. Fluxo de Acesso ao Módulo Integrações

### Caminho de Navegação

1. Usuário acessa o ERP Revo através do login
2. No menu lateral, usuário clica no item "Integrações"
3. Sistema carrega a página principal do módulo Integrações

### Comportamento Esperado

- Ao acessar o módulo, o sistema exibe a tela principal com a lista de integrações disponíveis para instalação
- Se o usuário já possui integrações configuradas, o sistema exibe a tela de integrações configuradas
- O menu lateral destaca o item "Integrações" como ativo

### Interações

- Hover sobre o item "Integrações" no menu lateral: aplica efeito visual de hover
- Clique no item "Integrações": carrega a página principal do módulo

## 2. Fluxo de Navegação entre Categorias de Integrações

### Caminho de Navegação

1. Na tela principal do módulo Integrações, usuário visualiza os filtros de categorias
2. Usuário clica em um dos filtros: "todas as integrações", "marketplaces e hubs", "plataformas de e-commerce" ou "outras integrações"
3. Sistema filtra as integrações exibidas de acordo com a categoria selecionada

### Comportamento Esperado

- Ao clicar em um filtro, o sistema destaca visualmente o filtro selecionado
- O sistema exibe apenas as integrações da categoria selecionada
- A descrição da categoria é atualizada de acordo com o filtro selecionado

### Interações

- Hover sobre os filtros: aplica efeito visual de hover
- Clique em um filtro: destaca o filtro selecionado e atualiza a lista de integrações
- Filtro ativo: apresenta estilo visual diferenciado (cor de fundo, cor de texto)

### Validações

- Se não houver integrações na categoria selecionada, o sistema exibe uma mensagem informando que não há integrações disponíveis

## 3. Fluxo de Pesquisa de Integrações

### Caminho de Navegação

1. Na tela principal do módulo Integrações, usuário visualiza o campo de pesquisa
2. Usuário digita um termo de pesquisa no campo
3. Usuário pressiona Enter ou clica no botão de pesquisa
4. Sistema filtra as integrações exibidas de acordo com o termo pesquisado

### Comportamento Esperado

- Ao digitar no campo de pesquisa, o sistema não realiza a filtragem automaticamente
- Ao pressionar Enter ou clicar no botão de pesquisa, o sistema filtra as integrações
- O sistema considera o nome e o tipo da integração na pesquisa
- A pesquisa é case-insensitive (não diferencia maiúsculas de minúsculas)

### Interações

- Foco no campo de pesquisa: aplica efeito visual de foco
- Digitação no campo: não realiza filtragem automática
- Pressionar Enter ou clicar no botão de pesquisa: realiza a filtragem

### Validações

- Se não houver resultados para o termo pesquisado, o sistema exibe uma mensagem informando que não foram encontradas integrações
- Se o campo de pesquisa estiver vazio, o sistema exibe todas as integrações da categoria atual

## 4. Fluxo de Instalação de Integração com Marketplace

### Caminho de Navegação

1. Usuário localiza a integração desejada na lista de marketplaces
2. Usuário clica no botão "instalar" da integração
3. Sistema redireciona para a tela de configuração da integração
4. Usuário preenche o nome da integração no ERP
5. Usuário clica no botão "conectar com [nome do marketplace]"
6. Sistema redireciona para a página de autenticação do marketplace
7. Usuário realiza a autenticação na plataforma do marketplace
8. Marketplace redireciona de volta para o ERP com o código de autorização
9. Sistema finaliza a configuração e exibe mensagem de sucesso
10. Sistema redireciona para a lista de integrações configuradas

### Comportamento Esperado

- Ao clicar em "instalar", o sistema redireciona para a tela de configuração
- O campo de nome da integração é pré-preenchido com o nome do marketplace
- O botão "conectar" permanece desabilitado até que o campo de nome seja preenchido
- Após a autenticação bem-sucedida, o sistema exibe uma mensagem de sucesso
- O sistema redireciona automaticamente para a lista de integrações configuradas após alguns segundos

### Interações

- Hover sobre o botão "instalar": aplica efeito visual de hover
- Clique no botão "instalar": redireciona para a tela de configuração
- Digitação no campo de nome: habilita o botão "conectar" se o campo não estiver vazio
- Clique no botão "conectar": redireciona para a página de autenticação do marketplace
- Autenticação na plataforma externa: processo específico de cada marketplace

### Validações

- Campo de nome da integração: obrigatório
- Se a autenticação falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema
- Se o usuário cancelar a autenticação, o sistema retorna à tela de configuração sem realizar a integração

## 5. Fluxo de Instalação de Integração com Plataforma de E-commerce

### Caminho de Navegação

1. Usuário localiza a integração desejada na lista de plataformas de e-commerce
2. Usuário clica no botão "instalar" da integração
3. Sistema redireciona para a tela de configuração da integração
4. Usuário preenche o nome da integração no ERP
5. Usuário preenche as informações específicas da plataforma (URL da loja, credenciais)
6. Usuário clica no botão "Conectar"
7. Sistema realiza a conexão com a plataforma
8. Se necessário, sistema redireciona para autenticação externa
9. Sistema finaliza a configuração e exibe mensagem de sucesso
10. Sistema redireciona para a lista de integrações configuradas

### Comportamento Esperado

- Ao clicar em "instalar", o sistema redireciona para a tela de configuração
- O campo de nome da integração é pré-preenchido com o nome da plataforma
- O botão "Conectar" permanece desabilitado até que todos os campos obrigatórios sejam preenchidos
- Após a conexão bem-sucedida, o sistema exibe uma mensagem de sucesso
- O sistema redireciona automaticamente para a lista de integrações configuradas após alguns segundos

### Interações

- Hover sobre o botão "instalar": aplica efeito visual de hover
- Clique no botão "instalar": redireciona para a tela de configuração
- Digitação nos campos: habilita o botão "Conectar" se todos os campos obrigatórios estiverem preenchidos
- Clique no botão "Conectar": inicia o processo de conexão com a plataforma

### Validações

- Campo de nome da integração: obrigatório
- Campos específicos da plataforma: validações específicas para cada plataforma
- URL da loja: deve ser uma URL válida
- Credenciais: devem estar no formato correto
- Se a conexão falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema

## 6. Fluxo de Instalação de Outra Integração

### Caminho de Navegação

1. Usuário localiza a integração desejada na lista de outras integrações
2. Usuário clica no botão "instalar" da integração
3. Sistema redireciona para a tela de configuração da integração
4. Usuário preenche o nome da integração no ERP
5. Usuário preenche as informações específicas da integração (chave de API, etc.)
6. Usuário clica no botão "Conectar"
7. Sistema realiza a conexão com a integração
8. Sistema finaliza a configuração e exibe mensagem de sucesso
9. Sistema redireciona para a lista de integrações configuradas

### Comportamento Esperado

- Ao clicar em "instalar", o sistema redireciona para a tela de configuração
- O campo de nome da integração é pré-preenchido com o nome da integração
- O botão "Conectar" permanece desabilitado até que todos os campos obrigatórios sejam preenchidos
- Após a conexão bem-sucedida, o sistema exibe uma mensagem de sucesso
- O sistema redireciona automaticamente para a lista de integrações configuradas após alguns segundos

### Interações

- Hover sobre o botão "instalar": aplica efeito visual de hover
- Clique no botão "instalar": redireciona para a tela de configuração
- Digitação nos campos: habilita o botão "Conectar" se todos os campos obrigatórios estiverem preenchidos
- Clique no botão "Conectar": inicia o processo de conexão com a integração

### Validações

- Campo de nome da integração: obrigatório
- Campos específicos da integração: validações específicas para cada integração
- Se a conexão falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema

## 7. Fluxo de Visualização de Integrações Configuradas

### Caminho de Navegação

1. Usuário acessa o módulo Integrações
2. Sistema exibe a lista de integrações configuradas
3. Usuário visualiza os detalhes das integrações, como nome, tipo, status e última sincronização

### Comportamento Esperado

- O sistema exibe a lista de integrações configuradas pelo usuário
- Cada integração exibe informações como nome, tipo, status e última sincronização
- As integrações são ordenadas por data de configuração, da mais recente para a mais antiga
- O status da integração é representado visualmente por cores e ícones

### Interações

- Hover sobre os itens da lista: aplica efeito visual de hover
- Scroll na lista: permite visualizar todas as integrações configuradas

## 8. Fluxo de Filtragem de Integrações Configuradas

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário visualiza os filtros disponíveis
2. Usuário seleciona um filtro de status (Todos, Ativo, Inativo, Com erro)
3. Usuário seleciona um filtro de tipo (Todos, Marketplaces, E-commerce, Outros)
4. Sistema filtra as integrações exibidas de acordo com os filtros selecionados

### Comportamento Esperado

- Ao selecionar um filtro, o sistema atualiza imediatamente a lista de integrações
- Os filtros podem ser combinados (status + tipo)
- Se não houver integrações que atendam aos critérios de filtro, o sistema exibe uma mensagem informando que não foram encontradas integrações

### Interações

- Clique nos filtros de status: atualiza a lista de integrações
- Clique nos filtros de tipo: atualiza a lista de integrações
- Combinação de filtros: aplica ambos os filtros simultaneamente

## 9. Fluxo de Pesquisa de Integrações Configuradas

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário visualiza o campo de pesquisa
2. Usuário digita um termo de pesquisa no campo
3. Usuário pressiona Enter ou clica no botão de pesquisa
4. Sistema filtra as integrações exibidas de acordo com o termo pesquisado

### Comportamento Esperado

- Ao digitar no campo de pesquisa, o sistema não realiza a filtragem automaticamente
- Ao pressionar Enter ou clicar no botão de pesquisa, o sistema filtra as integrações
- O sistema considera o nome da integração na pesquisa
- A pesquisa é case-insensitive (não diferencia maiúsculas de minúsculas)
- A pesquisa pode ser combinada com os filtros de status e tipo

### Interações

- Foco no campo de pesquisa: aplica efeito visual de foco
- Digitação no campo: não realiza filtragem automática
- Pressionar Enter ou clicar no botão de pesquisa: realiza a filtragem

### Validações

- Se não houver resultados para o termo pesquisado, o sistema exibe uma mensagem informando que não foram encontradas integrações
- Se o campo de pesquisa estiver vazio, o sistema exibe todas as integrações que atendem aos filtros de status e tipo

## 10. Fluxo de Sincronização de Integração

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário localiza a integração desejada
2. Usuário clica no botão de sincronização da integração
3. Sistema inicia o processo de sincronização
4. Sistema exibe indicador de progresso
5. Sistema finaliza a sincronização e atualiza a hora da última sincronização
6. Sistema exibe mensagem de sucesso

### Comportamento Esperado

- Ao clicar no botão de sincronização, o sistema inicia imediatamente o processo
- O botão de sincronização é substituído por um indicador de progresso durante o processo
- Após a sincronização bem-sucedida, o sistema atualiza a hora da última sincronização
- O sistema exibe uma notificação informando que a sincronização foi concluída com sucesso

### Interações

- Hover sobre o botão de sincronização: aplica efeito visual de hover
- Clique no botão de sincronização: inicia o processo de sincronização
- Durante a sincronização: botão é desabilitado e exibe indicador de progresso

### Validações

- Se a sincronização falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema
- Se a integração estiver inativa, o botão de sincronização é substituído por um botão de ativação

## 11. Fluxo de Edição de Configurações de Integração

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário localiza a integração desejada
2. Usuário clica no botão de configurações ou seleciona "Editar" no menu de opções
3. Sistema exibe modal com as configurações atuais
4. Usuário edita as configurações desejadas
5. Usuário clica em "Salvar alterações"
6. Sistema salva as configurações e atualiza a interface
7. Sistema exibe mensagem de sucesso

### Comportamento Esperado

- Ao clicar no botão de configurações, o sistema exibe um modal com as configurações atuais
- Os campos são pré-preenchidos com os valores atuais
- O botão "Salvar alterações" permanece habilitado mesmo sem alterações
- Após salvar as alterações, o sistema atualiza a interface com os novos valores
- O sistema exibe uma notificação informando que as configurações foram salvas com sucesso

### Interações

- Hover sobre o botão de configurações: aplica efeito visual de hover
- Clique no botão de configurações: exibe o modal de configurações
- Digitação nos campos: atualiza os valores
- Clique no botão "Salvar alterações": salva as configurações e fecha o modal
- Clique no botão "Cancelar" ou no botão de fechar: fecha o modal sem salvar as alterações

### Validações

- Campo de nome da integração: obrigatório
- Outros campos: validações específicas para cada tipo de integração
- Se houver erros de validação, o sistema exibe mensagens de erro próximas aos campos com problemas
- Se o salvamento falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema

## 12. Fluxo de Remoção de Integração

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário localiza a integração desejada
2. Usuário clica no botão de mais opções
3. Usuário seleciona "Remover integração" no menu
4. Sistema exibe modal de confirmação
5. Usuário confirma a remoção
6. Sistema remove a integração e atualiza a interface
7. Sistema exibe mensagem de sucesso

### Comportamento Esperado

- Ao clicar em "Remover integração", o sistema exibe um modal de confirmação
- O modal exibe o nome da integração a ser removida
- O modal informa que a ação não poderá ser desfeita
- Após confirmar a remoção, o sistema remove a integração da lista
- O sistema exibe uma notificação informando que a integração foi removida com sucesso

### Interações

- Hover sobre o botão de mais opções: aplica efeito visual de hover
- Clique no botão de mais opções: exibe o menu de opções
- Hover sobre a opção "Remover integração": aplica efeito visual de hover
- Clique na opção "Remover integração": exibe o modal de confirmação
- Clique no botão "Remover": remove a integração e fecha o modal
- Clique no botão "Cancelar" ou no botão de fechar: fecha o modal sem remover a integração

### Validações

- A remoção de uma integração é irreversível
- O sistema solicita confirmação do usuário antes de remover a integração
- Se a remoção falhar, o sistema exibe uma mensagem de erro com detalhes sobre o problema

## 13. Fluxo de Adição de Nova Integração

### Caminho de Navegação

1. Na tela de integrações configuradas, usuário clica no botão "Adicionar integração"
2. Sistema redireciona para a tela principal do módulo Integrações
3. Usuário segue o fluxo de instalação da integração desejada

### Comportamento Esperado

- Ao clicar em "Adicionar integração", o sistema redireciona para a tela principal do módulo
- O usu
  (Content truncated due to size limit. Use line ranges to read in chunks)
