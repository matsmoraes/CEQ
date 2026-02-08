# Controle Estatístico de Qualidade: Resistência de Peças Plásticas 📊

Este projeto implementa um sistema de monitoramento de processos industriais utilizando a **Linguagem R**. O foco principal é a análise da estabilidade da resistência à compressão de peças plásticas fabricadas via moldagem por injeção.

O trabalho aborda desde a limpeza de dados e estimativa de parâmetros (Fase 1) até a simulação de monitoramento em tempo real e análise do poder de detecção de desvios (Fase 2).

## Objetivos
* Estabelecer limites de controle estatístico para um processo industrial.
* Identificar e tratar *outliers* que possam comprometer a calibração do sistema.
* Avaliar a eficiência do gráfico de controle ($\bar{X}$) através do Número Médio de Amostras ($NMA$).
* Simular dados da Fase 2 para validar a capacidade do gráfico em detectar mudanças no processo em tempo real.

## Tecnologias e Bibliotecas
* **Linguagem:** R.
* **Biblioteca Principal:** `qcc` (Quality Control Charts).
* **Editor:** Quarto / RStudio.

## Metodologia e Resultados

### Fase 1: Estabilização e Calibração
* **Análise Inicial:** Foram utilizadas 20 amostras iniciais de 5 peças cada ($n=5$).
* **Tratamento de Dados:** Através de um Boxplot e do Gráfico de Amplitude ($R$), identificou-se a **amostra 2** como um ponto fora de controle com amplitude de $21{,}6$.
* **Estimativas Finais:** Após a exclusão do *outlier*, as novas estimativas para o processo em controle foram $\hat{\mu}_{0} = 79{,}49$ e $\hat{\sigma}_{0} = 3{,}58$.


### Fase 2: Monitoramento e Performance
* **Alarme Falso ($NMA_{0}$):** O sistema foi configurado para apresentar um alarme falso a cada $370$ amostras, em média.
* **Poder de Detecção ($NMA_{1}$):** O gráfico demonstrou alta sensibilidade; para um deslocamento na média de $\delta = 1{,}5$, o gráfico detecta a falha em apenas $1{,}69$ amostras.
* **Validação Real:** Ao simular 3 novas amostras com desvios na média e variância, o gráfico de $\bar{X}$ detectou $100\%$ das falhas imediatamente (3 de 3).

## Estrutura do Repositório
* `trabalho1_ceq.pdf`: Relatório técnico detalhado com as análises e gráficos.
* `dados4.txt`: Base de dados utilizada no estudo.
* `script.qmd`: Código fonte em Quarto/R para reprodutibilidade dos cálculos.

---
> **Nota Acadêmica:** Projeto desenvolvido por Matheus de Moraes Neves como parte integrante da graduação em Estatística na **Universidade Federal de Uberlândia (UFU)**.
