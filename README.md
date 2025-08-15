# Challenge_Telecom_X_Parte_2
Challenge Telecom X: análise de evasão de clientes - Parte 2, da formação Modelagem de Dados com Python G8 - ONE
# Relatório
1. Introdução

O objetivo desta análise foi identificar os fatores que mais influenciam a evasão de clientes (churn) e avaliar modelos preditivos capazes de antecipar quais clientes estão em risco de deixar a empresa. Foram utilizados dois modelos principais: Regressão Logística e Random Forest.

2. Metodologia

Pré-processamento dos dados:

Variáveis categóricas binárias foram codificadas como 0/1.

Valores ausentes (NaN) foram preenchidos: médias para variáveis numéricas e moda para variáveis binárias.

As colunas numéricas foram normalizadas para a Regressão Logística.

Divisão do dataset:

70% para treino e 30% para teste, mantendo a proporção de clientes que evadiram e não evadiram.

Modelos utilizados:

Regressão Logística: modelo linear, coeficientes interpretáveis, boa base para entender influência direta das variáveis.

Random Forest: modelo de árvores de decisão, capaz de capturar relações não lineares e interações entre variáveis. Foi utilizado class_weight='balanced' para compensar o desbalanceamento de classes.

Avaliação dos modelos:

Métricas: acurácia, precisão, recall, F1-score e matriz de confusão.

Comparação do desempenho entre classes majoritária (não evadiram) e minoritária (evadiram).

3. Desempenho dos Modelos
Regressão Logística Corrigida

Acurácia: 80%

Recall da classe Churn=1: 54%

Precisão da classe Churn=1: 66%

F1-score: 60%

Observações:

Identifica bem clientes que não evadiram.

Detecta parcialmente clientes que evadiram, mas ainda há margem de melhoria.

Coeficientes indicam quais variáveis aumentam ou diminuem a probabilidade de evasão.

Random Forest (balanceada)

Acurácia: 78%

Recall da classe Churn=1: 48%

Precisão da classe Churn=1: 60%

F1-score: 53%

Observações:

Capta relações não lineares e interações entre variáveis.

Menor desempenho que a Regressão Logística na detecção de churn, mesmo com balanceamento.

4. Fatores que mais influenciam a evasão

Com base na Regressão Logística (coeficientes) e Random Forest (importância das variáveis), os principais fatores que afetam a evasão foram:

Duração do contrato (tenure)

Clientes com tempo de contrato mais curto apresentam maior risco de churn.

Estratégia: programas de fidelização para clientes recém-contratados, descontos progressivos ou benefícios exclusivos nos primeiros meses.

Tipo de contrato (um ou dois anos)

Contratos curtos ou mensais aumentam a chance de evasão, enquanto contratos anuais reduzem o risco.

Estratégia: incentivar contratos mais longos oferecendo vantagens e bônus de renovação.

Gastos totais e mensais (account.Charges.Monthly e account.Charges.Total)

Clientes com gastos mais baixos tendem a evadir mais.

Estratégia: monitorar clientes com menor gasto e oferecer pacotes adicionais ou promoções para aumentar engajamento.

Serviços contratados (Internet, TV, Backup, TechSupport)

Clientes sem serviços adicionais ou sem suporte online têm maior risco de evasão.

Estratégia: promover upgrade de serviços, pacotes combinados e comunicação ativa sobre benefícios.

Características pessoais

Idade/SeniorCitizen e parceiros/dependentes impactam marginalmente, mas podem influenciar o consumo de serviços e decisões de retenção.

Cobrança e método de pagamento

Clientes com pagamentos eletrônicos ou cheques apresentam comportamentos de churn diferentes.

Estratégia: flexibilizar métodos de pagamento e alertas automáticos para reduzir fricção no processo de cobrança.

5. Estratégias de retenção baseadas nos resultados

Segmentação de clientes de risco:

Usar o modelo preditivo para identificar clientes com alta probabilidade de churn.

Focar esforços de retenção nesses clientes.

Programas de fidelidade e incentivos:

Descontos progressivos, bônus de renovação e ofertas exclusivas nos primeiros meses de contrato.

Promoção de serviços adicionais:

Incentivar contratação de serviços complementares (Internet, TV, TechSupport) que aumentam engajamento e reduzem evasão.

Comunicação personalizada:

Alertas proativos, e-mails ou mensagens sobre benefícios, upgrades ou pagamentos, com base no perfil de consumo.

Monitoramento contínuo:

Revisar regularmente o desempenho do modelo e atualizar com novos dados.

Ajustar estratégias conforme mudanças de comportamento dos clientes.

6. Conclusão

A Regressão Logística mostrou melhor desempenho geral na detecção de churn, além de fornecer interpretabilidade direta dos coeficientes.

A Random Forest identifica interações complexas, mas precisa de ajustes (oversampling, tuning de hiperparâmetros) para melhorar o recall da classe minoritária.

Os principais fatores de evasão incluem tempo de contrato, tipo de contrato, gastos e serviços contratados.

Estratégias de retenção devem ser focadas nos clientes recém-contratados, com contratos curtos, baixo gasto ou poucos serviços, usando programas de fidelização, comunicação personalizada e incentivos.
