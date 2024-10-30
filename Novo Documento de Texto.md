# Modelando um Dashboard de E-commerce com Power BI Utilizando Fórmulas DAX

## Introdução
Este projeto consiste na construção de um modelo de dados em formato star schema utilizando a tabela única de *Financial Sample*. O objetivo é facilitar análises e relatórios de vendas através da criação de tabelas dimensão e uma tabela de fato.

## Estrutura do Modelo

### Tabela de Origem
- **Financials_origem**: Modo oculto, serve como backup da tabela original.

### Tabelas Dimensão
1. **D_Produtos**
   - ID_produto
   - Produto
   - Média de Unidades Vendidas
   - Média do Valor de Vendas
   - Mediana do Valor de Vendas
   - Valor Máximo de Venda
   - Valor Mínimo de Venda

2. **D_Produtos_Detalhes**
   - ID_produto
   - Discount Band
   - Sale Price
   - Units Sold
   - Manufacturing Price

3. **D_Descontos**
   - ID_produto
   - Discount
   - Discount Band

4. **D_Detalhes**
   - ID_detalhe
   - Informações adicionais sobre vendas.

5. **D_Calendário**
   - Criada utilizando a função DAX `CALENDAR()`, oferece uma visão temporal completa.

### Tabela de Fato
- **F_Vendas**
   - SK_ID
   - ID_produto
   - Produto
   - Units Sold
   - Sales Price
   - Discount Band
   - Segment
   - Country
   - Salers
   - Profit
   - Date

## Processo de Construção do Diagrama

1. **Cópia da Tabela Original**: A tabela original foi copiada e renomeada como `Financials_origem`.
2. **Criação das Tabelas Dimensão**:
   - Os dados foram filtrados e agregados utilizando funções DAX como `AVERAGE`, `MEDIAN`, `MAX` e `MIN`.
   - Cada tabela dimensão foi criada com as colunas apropriadas e as relações entre elas definidas.
3. **Criação da Tabela de Fato**: Os dados relevantes para vendas foram consolidados na tabela `F_Vendas`.
4. **Criação do Calendário**: A tabela de calendário foi gerada utilizando a função `CALENDAR()`.

## Funcionalidades e Funções DAX Utilizadas

- **`MÉDIASE()`**: Para calcular a média das unidades vendidas e dos valores de vendas em `D_Produtos`.
- **`MED()`**: Para calcular a mediana do valor de vendas.
- **`MÁXIMO()` e `MÍNIMO()`**: Para determinar os valores máximo e mínimo de vendas, respectivamente.
- **`CALENDAR()`**: Para criar a tabela de calendário, facilitando análises temporais.

## Conclusão
O modelo em star schema desenvolvido neste projeto permite análises eficientes e relatórios detalhados sobre vendas, facilitando a tomada de decisão com base em dados estruturados.

