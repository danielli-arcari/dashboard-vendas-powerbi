# Dashboard de Vendas em Power BI

## Sobre o projeto

Este projeto foi desenvolvido durante minha participação em uma formação em Engenharia e Análise de Dados promovida pela [MCIO Brasil](https://mciobrasil.org.br/) em parceria com a [Leega Academy](https://leega.com.br/).

A formação faz parte da minha jornada de desenvolvimento profissional na área de dados. No Módulo 3, voltado a Engenharia e Arquitetura de Dados, foram apresentados conceitos de modelagem, transformação e visualização de dados utilizando o Microsoft Power BI.

Durante as aulas, reproduzi os exercícios propostos com a base disponibilizada pela Leega e, a partir deles, ampliei o trabalho por iniciativa própria, transformando o exercício em um pequeno projeto de análise de dados.

Além das atividades realizadas durante o treinamento, desenvolvi:

- dashboard de visão geral das vendas;
- indicadores de receita, lucro, quantidade vendida e margem;
- filtros por ano, trimestre, produto, estado e canal de venda;
- dimensão calendário para análise temporal;
- medidas adicionais utilizando DAX;
- análise de Receita Realizada x Receita Estimada;
- indicadores de diferença e percentual de atingimento das metas;
- comparação dos resultados por produto;
- página de resumo executivo com interpretação dos resultados e recomendações.

---

## Resumo da base apresentada pela Leega

A base original disponibilizada para o treinamento é composta por três tabelas principais:

### Vendas

Tabela com os registros das vendas realizadas pela empresa.

Entre os campos utilizados estão:

- Data da Venda
- Produto
- Cliente
- Estado
- Localidade
- Canal de Venda
- Quantidade
- Preço Unitário
- Receita
- Custo
- Lucro
- Margem

Essa tabela foi utilizada como principal fonte para o cálculo dos indicadores comerciais e financeiros.

### Produto

Tabela dimensional contendo informações de classificação dos produtos:

- Linha
- Tipo
- Produto
- Código Produto

O campo `Produto` foi utilizado para estabelecer o relacionamento com as tabelas de vendas e estimativas.

### Estimativa

Tabela contendo os valores planejados pela empresa para cada produto e ano:

- Ano
- Produto
- Receita
- Lucro

Ela foi utilizada para comparar os resultados efetivamente realizados com os valores estimados.

Durante o treinamento também foram criadas consultas derivadas, como:

- Venda Sumarizada;
- Receita Estimada por Produto;
- Venda Projetada;
- Vendas e Produtos.

Essas consultas fizeram parte dos exercícios de transformação e modelagem realizados no Power Query.

Para a construção do dashboard final, utilizei principalmente as tabelas `Vendas`, `Produto` e `Estimativa`, além de dimensões auxiliares criadas para análise temporal.

---

## Modelagem dos dados

O modelo foi estruturado utilizando a tabela `Produto` como dimensão comum entre os dados de vendas e estimativas.

Também foram criadas duas dimensões auxiliares:

- `DimAno`, utilizada na comparação entre receita realizada e estimada;
- `DimCalendario`, utilizada para permitir análises temporais por ano e trimestre.

A criação dessas dimensões permitiu controlar corretamente os filtros e evitar comparações entre períodos diferentes.

---

## Como construí os relatórios

O relatório final foi dividido em três páginas, cada uma com um objetivo específico.

### 1. Visão Geral das Vendas

A primeira página foi criada para fornecer uma visão geral do desempenho comercial.

Foram utilizados quatro indicadores principais:

- Receita Total;
- Lucro Total;
- Quantidade Vendida;
- Margem.

Também foram criadas as seguintes visualizações:

- Receita Total por Produto;
- evolução da Receita ao longo do tempo;
- Lucro Total por Linha de Produto;
- Receita Total por Canal de Venda.

Foram adicionadas segmentações para permitir a exploração dos dados por:

- Ano;
- Trimestre;
- Produto;
- Estado;
- Canal de Venda.

Essa página permite analisar tanto o resultado consolidado quanto segmentos específicos da operação.

### 2. Realizado x Estimado

A segunda página foi criada para avaliar o desempenho da empresa em relação às previsões.

Foram criados indicadores para:

- Receita Realizada;
- Receita Estimada;
- Diferença entre realizado e estimado;
- Percentual de atingimento da meta.

Também foi criado um gráfico comparando Receita Realizada x Receita Estimada por Produto.

Como a tabela de estimativas fornecida possui metas anuais, a comparação foi mantida no nível de ano, evitando comparar valores trimestrais realizados com metas anuais.

Resultados observados:

| Ano | Receita realizada | Receita estimada | Diferença | Atingimento |
|---|---:|---:|---:|---:|
| 2017 | R$ 3,25 bi | R$ 3,23 bi | R$ 20,56 mi | 100,64% |
| 2018 | R$ 5,45 bi | R$ 5,29 bi | R$ 161,02 mi | 103,04% |

### 3. Resumo Executivo

A terceira página foi criada com foco na interpretação dos dados.

Em vez de repetir os gráficos e indicadores das páginas anteriores, essa página apresenta:

- resumo dos resultados de 2017;
- resumo dos resultados de 2018;
- principais achados da análise;
- pontos de atenção;
- recomendações de negócio.

O objetivo foi transformar os números apresentados no dashboard em informações que poderiam apoiar uma tomada de decisão gerencial.

---

## Medidas DAX utilizadas

### Receita Total

```DAX
Receita Total =
SUM(Vendas[Receita])
```

## Sobre as instituições

### Leega Academy

A Leega é uma empresa especializada em tecnologia, Dados, Analytics, Cloud e Inteligência Artificial, atuando também na formação e desenvolvimento de profissionais da área.
Conheça a Leega: https://leega.com.br/

### MCIO Brasil

A MCIO Brasil é uma associação sem fins lucrativos que trabalha para ampliar a inclusão, o desenvolvimento e a ascensão de mulheres no mercado de tecnologia, promovendo iniciativas como capacitações, mentorias e conexão com oportunidades profissionais.
Conheça a MCIO Brasil: https://mciobrasil.org.br/

A formação da qual este projeto faz parte é uma iniciativa realizada em parceria entre a MCIO Brasil e a Leega Academy.
