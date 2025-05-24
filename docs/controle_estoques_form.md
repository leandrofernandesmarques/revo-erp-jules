# Formulário: Controle de Estoques

## Filtros e Controles Principais

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Pesquisa | Input text | Não | Placeholder: "Pesquise por nome, código (SKU) ou GTIN/EAN" |
| Filtros | Button/Modal | Não | Abre modal com filtros adicionais |
| Limpar filtros | Button | Não | Remove todos os filtros aplicados |
| Tipo de produto | Toggle buttons | Não | Todos (padrão), Simples, Kits, Matéria-prima |
| Alterar pesquisa | Button | Não | Modifica parâmetros de pesquisa |

## Botões de Ação

| Rótulo do Campo | Tipo de Controle | Função |
|-----------------|------------------|--------|
| Inventário de estoque | Button | Inicia processo de inventário |
| Gerenciar produtos | Button | Acessa gerenciamento de produtos |
| Mais ações | Dropdown button | Opções adicionais (importar, exportar, etc.) |

## Tabela de Produtos em Estoque

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Código | Column | Código/SKU do produto |
| Nome | Column | Nome/descrição do produto |
| Tipo | Column | Tipo do produto (simples, kit, matéria-prima) |
| Estoque atual | Column | Quantidade disponível em estoque |
| Estoque mínimo | Column | Quantidade mínima configurada |
| Estoque máximo | Column | Quantidade máxima configurada |
| Localização | Column | Posição física do produto no estoque |
| Valor unitário | Column | Preço unitário do produto |
| Valor em estoque | Column | Valor total do estoque deste produto |
| Ações | Column | Botões de edição, movimentação e histórico |

## Formulário de Movimentação de Estoque

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Tipo de movimentação | Select | Sim | Entrada, Saída, Transferência, Ajuste |
| Produto | Select/Search | Sim | Lista de produtos cadastrados |
| Quantidade | Input number | Sim | Quantidade a ser movimentada |
| Depósito origem | Select | Condicional | Lista de depósitos (obrigatório para transferências) |
| Depósito destino | Select | Condicional | Lista de depósitos (obrigatório para transferências) |
| Motivo | Select | Sim | Venda, Compra, Devolução, Perda, Consumo, Outros |
| Observações | Textarea | Não | Detalhes adicionais sobre a movimentação |
| Data | Datepicker | Sim | Data da movimentação (padrão: data atual) |

## Formulário de Inventário

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Nome do inventário | Input text | Sim | Nome para identificação do inventário |
| Data de início | Datepicker | Sim | Data de início do inventário |
| Data de término | Datepicker | Não | Data prevista para conclusão |
| Depósito | Select | Sim | Depósito a ser inventariado |
| Produtos | Multiselect | Não | Produtos específicos a serem inventariados |
| Tipo de contagem | Radio buttons | Sim | Total, Por categoria, Por localização |
| Bloquear movimentações | Checkbox | Não | Impede movimentações durante o inventário |

## Detalhes do Produto

| Rótulo do Campo | Tipo de Controle | Descrição |
|-----------------|------------------|-----------|
| Histórico de movimentações | Tabela | Lista de entradas e saídas do produto |
| Gráfico de evolução | Gráfico | Evolução do estoque ao longo do tempo |
| Depósitos | Tabela | Quantidade disponível em cada depósito |
| Alertas | Indicadores | Avisos de estoque mínimo ou máximo atingidos |

## Configurações de Estoque

| Rótulo do Campo | Tipo de Controle | Obrigatório | Valores Padrão/Máscaras |
|-----------------|------------------|-------------|-------------------------|
| Método de avaliação | Select | Sim | Custo médio, PEPS (FIFO), UEPS (LIFO) |
| Permitir estoque negativo | Checkbox | Não | Permite ou bloqueia estoque negativo |
| Alerta de estoque mínimo | Checkbox | Não | Ativa alertas de estoque mínimo |
| Alerta de estoque máximo | Checkbox | Não | Ativa alertas de estoque máximo |
| Depósito padrão | Select | Sim | Depósito principal para movimentações |
