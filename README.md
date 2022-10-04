# Dashboard-RetornoInvestimento-DR
Dashboard com informações de retorno de investimentps com diversos indicadores financeiros (AINDA EM DESENVOLVIMENTO)

Nesse projeto eu realizei etapas como:

## Conexão com fontes de dados

A base de dados utilizada estava em um único arquivo .xlsx porém com várias abas com os dados dos indicadores.

## ETL - Extrair, Transformar e Carregar dados

Após carregar os dados para o Power BI eu realizei a modelagem e transformação dos mesmos conforme a necessidade dos requisitos que eu teria que informar no Dashboard.

Por fim o modelo ficou assim:

![Modelo](https://github.com/MatheusFCBarros/Dashboard-RetornoInvestimento-DR/blob/main/Modelo.png)

## Requisitos a serem respondidos

Oferecer um levantamento histórico sobre 8 indicadores econômicos dentro do cenário brasileiro entre os anos de 2011 e primeiro semestre de 2021

Os indicadores foram classificados em:

MACRO ECONÔMICOS - IPCA / SELIC

RENDA FIXA - DI

RENDA VARIÁVEL - BOVA11 / SMAL11

CAMBIAL - DÓLAR

CRYPTOMOEDAS - BITCOIN / EUTHEREUM

## Criação de calculos com funções DAX

Algumas medidas que foram criadas:

Bitcoin Acum = 
            SUMX(DB_Bitcoin,DB_Bitcoin[Retorno mensal (%)])
    
Bitcoin Acum 2021 = 
    CALCULATE( 
    
        SUMX(
        
            DB_Bitcoin,DB_Bitcoin[Retorno Mensal (%)]),
        
                DATESBETWEEN(dCalendario[Data],
                
                DATE(2021,1,1),
                
                DATE(2021,6,1)
            )
    )
    
Bitcoin Media Anual = 
            AVERAGEX(
                        VALUES(
                                    dCalendario[AnoNum]), [Bitcoin Acum])

## Personalização do layout do relatório

![Dashboard](https://github.com/MatheusFCBarros/Dashboard-RetornoInvestimento-DR/blob/main/Dashboard.png)


Link para visualizar o Dashboard: https://bit.ly/3SJ5z4K
