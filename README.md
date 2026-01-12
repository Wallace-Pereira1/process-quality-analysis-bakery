# Process Quality Analysis in Bakery Production

## Descrição
Este projeto realiza uma análise do processo produtivo de uma padaria com foco na identificação de inconsistências no peso e na altura dos produtos. A partir de dados reais de produção, o estudo avalia erros de medição, desempenho dos colaboradores e padrões operacionais, propondo melhorias para padronização e eficiência.

## Contexto do Problema
A empresa analisada apresentava variações frequentes no peso e na altura dos pães produzidos, resultando em retrabalho, desperdício de insumos e impacto na qualidade do produto final. Os padrões definidos inicialmente mostraram-se difíceis de manter na prática, indicando a necessidade de uma análise mais aprofundada do processo produtivo.

## Objetivos
- Identificar falhas e irregularidades no processo de produção  
- Analisar erros de medição em relação aos valores objetivo  
- Avaliar o desempenho dos colaboradores nas medições  
- Propor melhorias para padronização e controle de qualidade  

## Metodologia
O projeto foi desenvolvido a partir das seguintes etapas:
1. Coleta de dados de produção (peso e altura dos produtos)  
2. Análise exploratória dos dados  
3. Cálculo do erro absoluto em relação ao peso objetivo  
4. Análise dos erros por colaborador  
5. Interpretação dos resultados e proposição de melhorias  

As análises foram realizadas utilizando Python e a biblioteca Pandas em ambiente Google Colab.

## Exemplo de Análise de Erro de Peso
python
# Cálculo do erro médio do peso em relação ao peso objetivo (ObjPeso)

if 'ObjPeso' in df.columns:
    df['Erro_Peso_Relativo'] = abs(df['Peso_Embalagem'] - df['ObjPeso'])
    erro_medio = df['Erro_Peso_Relativo'].mean()
    print(f"Erro médio do peso: {erro_medio}")

    erro_por_usuario = df.groupby('Nome_Usuario')['Erro_Peso_Relativo'].mean()
    print("\nErro médio por colaborador:")
    print(erro_por_usuario)
else:
    print("Coluna 'ObjPeso' não encontrada no DataFrame.")

## Principais Resultados
- O peso objetivo inicialmente definido mostrou-se inviável na prática
- Diferenças significativas de precisão foram identificadas entre os colaboradores
- Produtividade elevada esteve associada a maiores taxas de erro em alguns casos
- A ausência de padronização foi o principal fator de inconsistência

## Propostas de Melhoria
- Revisão dos padrões de peso e altura dos produtos
- Treinamento dos colaboradores focado em medição e ergonomia
- Melhor organização do processo produtivo
- Redução de retrabalho e desperdício

## Tecnologias Utilizadas
- Python
- Pandas
- Google Colab
