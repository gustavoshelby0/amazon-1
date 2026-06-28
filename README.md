# Análise de "No Driver Found" da Uber

# Problema de Negócio

A Amazon é o maior marketplace do mundo, com milhões de produtos em seu catálogo. No entanto, manter um portfólio extenso gera custos significativos de armazenagem, logística e gestão de fornecedores

# Premissas da análise

Dados de 100.000 vendas feitas pela Amazon.

Vendas realizadas nos Estados Unidos, Canadá, Índia, Reino Unido e Austrália.

Os dados analisados correspondem ao período de 2020 a 2024.


# Estratégia da solução

O método Fato-Dimensão foi usado para desenvolver a análise de dados.

# Passo 1: Resumir o contexto em uma pergunta aberta

As perguntas abertas são um tipo de demanda muito comum em análise de dados nas quais a demanda possui N possíveis soluções e cabe ao analista de dados avaliar as possibilidades e escolher a alternativa com o maior retorno e o menor esforço possível. Para essa análise, foi definida a seguinte pergunta aberta:

Como estão as vendas da Amazon? A empresa tem muitos produtos bons ou é simplesmente um armazém de brechó?

# Passo 2: Transformar pergunta aberta em fechada

As perguntas fechadas são um tipo de demanda muito comum na área de análise de dados. Essa demanda contém todos os detalhes da análise de dados e direciona o analista exatamente para o que precisa ser feito. Geralmente, a pergunta fechada é a escolha de uma solução entre todas as alternativas possíveis, feita por um profissional mais sênior da área.

Para essa análise, foi definida a seguinte pergunta fechada:

Pergunta Fechada: Faça um gráfico de Pareto mostrando todas as categorias da Amazon. Veja quais categorias pagam as contas da empresa e quais são simplesmente peso morto no estoque.

# Passo 3: Definição da Coluna Fato

O Fato é a coluna de interesse que representa o ponto focal da análise. Nesse caso, a coluna "OrderID" mostra quantas vendas foram feitas, quando e feito uma contagem e segmentacao por categoria...

# Passo 4: Identificação das Dimensões

As colunas foram agrupadas em dimensões comuns que fornecem mais detalhes sobre o Fato que será analisado. Foram organizadas as seguintes dimensões:

Tempo: OrderDate. (Base cronológica para análises de sazonalidade e tendências).

Produto e Marca: ProductID, ProductName, Category, Brand. (Detalhamento do item vendido para análise de portfólio e desempenho por categoria).

Cliente e Vendedor: CustomerID, CustomerName, SellerID. (Identificação das partes envolvidas na transação).

Valores e Custos: Quantity, UnitPrice, Discount, Tax, ShippingCost, TotalAmount. (Métricas financeiras da venda; TotalAmount é a métrica central de faturamento).

Pagamento e Status: PaymentMethod, OrderStatus. (OrderStatus é a variável alvo para classificação do resultado do pedido).

Localização: City, State, Country. (Base geográfica para análises regionais de desempenho).

Controle: OrderID. (Identificador único para rastreabilidade do registro).


# Passo 5: Hipóteses Analíticas

H1: A taxa de corridas perdidas pela Uber é de 2% quando olhado para o "No Driver Found".

H2: O "No Driver Found" só acontece quando o passageiro está no ponto de partida na cidade grande.

H3: O "No Driver Found" é alto quando o ponto de desembarque é na cidade grande.

H4: O "No Driver Found" tem a maior taxa quando é no Uber XL, porque esse veículo tem pouca disponibilidade.

H5: O "No Driver Found" acontece com maior frequência à noite, no período noturno (6 às 12pm).

Fiz no início apenas 4 Hipóteses para quebrar o gelo. Isso é uma análise exploratória do dataframe com base na pergunta fechada que o Analista de Dados Sr (Gustavo Shelby) me sugeriu.

**Hipótese Inicial → Rodar Excel/Análise → Obter Insight → Questionar o Insight → Gerar Nova Hipótese → Rodar Nova Análise.**

# Passo 6: Critérios de Priorização

- **Critério 1:** Dados disponíveis.
- **Critério 2:** Insights acionáveis.

# Passo 7: Priorização das Hipóteses Analíticas

H1: A taxa de corridas perdidas pela Uber é de 2% quando olhado para o "No Driver Found".

H2: O "No Driver Found" só acontece quando o passageiro está no ponto de partida na cidade grande.

H3: O "No Driver Found" é alto quando o ponto de desembarque é na cidade grande.

H4: O "No Driver Found" tem a maior taxa quando é no Uber XL, porque esse veículo tem pouca disponibilidade.

H5: O "No Driver Found" acontece com maior frequência à noite, no período noturno (6 às 12pm).

# Insights da análise

# Resultados

**📥 Baixe a apresentação em PowerPoint (clique no link e, em seguida, em "Download" ou "View raw"):**  
  [https://docs.google.com/presentation/d/1jrQ17n-un9UXdU5uls8ValpbZDV1kk1F/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true](https://docs.google.com/presentation/d/1jrQ17n-un9UXdU5uls8ValpbZDV1kk1F/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true)

# Próximos passos

Fazer o acompanhamento das futuras mudanças que a diretoria poderá implementar na cidade de Delhi (Índia).

Este é o retrato do sintoma. Na próxima fase, precisamos responder: isso acontece porque as corridas têm baixo valor monetário para o motorista? Ou porque a distância até o embarque é muito grande?

Para isso, será necessário cruzar os 7% de perdas por "No Driver Found" com o tempo médio de espera dos motoristas por região, e com o valor médio recebido por corrida, a fim de identificar a principal causa do problema.
