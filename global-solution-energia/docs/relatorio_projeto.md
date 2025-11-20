# Relatório do Projeto – Smart Office Verde

## 1. Introdução

A transição para modelos de trabalho mais sustentáveis exige repensar como a energia é utilizada
nos ambientes produtivos. Escritórios com estações de trabalho, iluminação artificial e sistemas
de climatização consomem uma quantidade significativa de energia, muitas vezes de forma ineficiente,
especialmente em horários em que não há pessoas presentes.

Este projeto aborda esse problema simulando o consumo energético de um escritório com várias estações
de trabalho ao longo de uma semana, identificando desperdícios e propondo uma solução baseada em
automação IoT para reduzir o consumo desnecessário.

## 2. Objetivo

- Analisar dados de consumo de energia em estações de trabalho de um escritório.
- Identificar padrões de desperdício, especialmente fora do horário de expediente.
- Simular o impacto de uma solução de automação (IoT) para desligamento inteligente de equipamentos.
- Estimar os ganhos econômicos e ambientais dessa solução.
- Conectar a proposta ao contexto de futuro do trabalho, com escritórios mais inteligentes e sustentáveis.

## 3. Descrição da Solução

A solução proposta é composta por dois elementos principais:

1. **Análise de Dados (Opção A)**  
   Utiliza um conjunto de dados simulados de consumo horário por estação de trabalho. A análise
   permite separar o consumo em:
   - horário de expediente (por exemplo, 8h às 18h)
   - horário fora de expediente (antes das 8h e após as 18h)
   - instantes em que não há pessoas presentes, mas ainda há equipamentos ligados

   A partir disso, é possível estimar o desperdício de energia e os possíveis ganhos ao reduzir esse consumo.

2. **Automação IoT Simulada (Opção B)**  
   Considera a existência (real ou hipotética) de um sistema de sensores de presença e tomadas inteligentes.
   A lógica é simples:
   - Se uma estação de trabalho permanecer sem pessoas por um período acima de um limite (por exemplo, 15 minutos),
     determinados equipamentos podem ser desligados automaticamente (monitor, iluminação local e, em certas
     condições, o ar-condicionado da área).
   - A simulação aplica essa lógica sobre os dados de consumo para calcular um novo cenário com automação,
     comparando com o cenário original.

## 4. Metodologia

### 4.1. Dados Simulados

O arquivo `dados/consumo_simulado_escritorio.csv` contém dados simulados para 7 dias, com:

- 8 estações de trabalho (`Estacao_01` a `Estacao_08`)
- Registros horários de 7h às 22h
- Para cada registro:
  - data e hora
  - estação de trabalho
  - flag de presença (`pessoas_presentes`)
  - flags de equipamentos ligados (computador, monitor, iluminação, ar-condicionado)
  - consumo total daquela estação na hora (`consumo_wh`)

As probabilidades de presença e de uso de ar-condicionado foram definidas de forma a refletir:

- Maior presença em horário de trabalho (8h–18h).
- Maior uso do ar-condicionado em horários de maior calor (por exemplo, 11h–17h).
- Possibilidade de equipamentos permanecerem ligados mesmo sem pessoas presentes (desperdício).

### 4.2. Análise no Notebook

O notebook `codigo/analise_consumo.ipynb` executa as seguintes etapas:

1. Carrega os dados simulados.
2. Converte os campos de data e hora para um índice temporal.
3. Calcula o consumo total por dia e por estação.
4. Separa o consumo em:
   - horário de expediente (8h–18h)
   - fora do expediente
5. Identifica o consumo em horas em que `pessoas_presentes == 0`, caracterizando potencial desperdício.
6. Constrói gráficos para visualizar:
   - consumo médio por hora do dia
   - comparação entre consumo total e consumo potencialmente desperdiçado
7. Aplica uma simulação de automação IoT, onde:

   - Se `pessoas_presentes == 0`, assume-se que determinados equipamentos seriam desligados.
   - O novo consumo “pós-automação” é recalculado.
   - Calcula-se a economia absoluta (Wh, kWh) e relativa (%).

8. Estima-se o impacto econômico e ambiental usando:
   - uma tarifa de exemplo (por ex.: R$ 0,80 / kWh)
   - um fator médio de emissão (por ex.: 0,084 kg CO₂ / kWh)

> Observação: os valores de tarifa e fator de emissão são assumidos e podem ser ajustados para
> refletir melhor a realidade local ou fontes oficiais.

### 4.3. Interpretação dos Resultados

A partir das métricas calculadas, é possível responder questões como:

- Qual porcentagem do consumo total ocorre fora do expediente?
- Quanto do consumo está associado a estações sem presença registrada?
- Qual seria a economia de energia se a automação IoT fosse aplicada?
- Em termos financeiros, qual seria a economia mensal aproximada?
- Quantos kg de CO₂ poderiam ser evitados em um mês ou em um ano?

Essas respostas são essenciais para justificar a adoção de políticas de eficiência energética e de
soluções tecnológicas em ambientes de trabalho.

## 5. Conexão com o Futuro do Trabalho

O futuro do trabalho é marcado por modelos híbridos, home office parcial, horários flexíveis e
uso intensivo de tecnologia nos escritórios. Isso traz novos desafios:

- Mais variação de presença ao longo do dia.
- Maior risco de esquecer equipamentos ligados em salas pouco utilizadas.
- Dificuldade de controle manual do consumo em ambientes grandes.

A solução proposta se conecta a esse contexto ao sugerir:

- Escritórios inteligentes (*smart offices*) que usam sensores e automação para reduzir desperdício.
- Tomadas e luminárias inteligentes que desligam automaticamente quando não há pessoas.
- Painéis de monitoramento que mostram consumo em tempo real e relatórios de eficiência.

Dessa forma, a tecnologia não só reduz custos operacionais, mas também contribui para metas ESG
(ambientais, sociais e de governança) e para uma imagem institucional mais sustentável.

## 6. Resultados Esperados (Exemplo Conceitual)

Embora os valores exatos dependam da simulação executada, a expectativa em um cenário típico é:

- Redução perceptível (por exemplo, 15% a 30%) do consumo fora de expediente.
- Economia mensal em R$ ao considerar a tarifa local de energia.
- Redução de emissões de CO₂ proporcional à economia de kWh.
- Evidência de que a maior parte do desperdício ocorre em horários previsíveis (noite, fim de semana),
  o que facilita a implementação de políticas e automações específicas.

Esses resultados podem ser apresentados em gráficos e tabelas no notebook e utilizados no vídeo.

## 7. Roteiro Sugerido para o Vídeo (até 3 minutos)

**Duração total:** aprox. 3 minutos  
**Formato sugerido:** gravação de tela + narração dos integrantes

1. **Abertura (0:00 – 0:20)**  
   - Apresentar o grupo, o curso e o tema da Global Solution.  
   - Frase de impacto: “Muitos escritórios desperdiçam energia todos os dias sem perceber.”

2. **Problema (0:20 – 0:50)**  
   - Mostrar um slide ou imagem de escritório com luzes e computadores ligados.  
   - Explicar que o consumo desnecessário (fora de expediente e sem pessoas) gera custo e impacto ambiental.

3. **Solução Proposta (0:50 – 1:40)**  
   - Mostrar rapidamente o arquivo de dados e o notebook.  
   - Explicar que foram simulados vários dias de consumo por estação de trabalho.  
   - Destacar que o projeto:  
     - analisa dados para identificar desperdício  
     - simula uma automação IoT que desliga equipamentos quando não há presença

4. **Resultados (1:40 – 2:30)**  
   - Mostrar gráficos do notebook (por exemplo, consumo por hora e economia simulada).  
   - Falar de exemplos numéricos:  
     - “No nosso cenário, X% do consumo acontecia sem presença.”  
     - “Com a automação, poderíamos reduzir Y kWh por semana, o que significa aproximadamente R$ Z por mês e W kg de CO₂ evitados.”

5. **Conexão com o Futuro do Trabalho (2:30 – 2:50)**  
   - Destacar que ambientes híbridos e flexíveis exigem soluções inteligentes.  
   - Explicar que a mesma lógica pode ser aplicada em coworkings, escritórios corporativos, etc.

6. **Fechamento (2:50 – 3:00)**  
   - Reforçar a mensagem de que **dados + automação = escritórios mais sustentáveis**.  
   - Agradecer e encerrar.

## 8. Conclusão

Este projeto demonstra, de forma simples e prática, como o uso de dados e de conceitos de IoT pode
contribuir para a redução do consumo de energia em ambientes de trabalho. Embora os dados sejam simulados,
a lógica e a abordagem se aplicam diretamente a cenários reais, reforçando a importância da tecnologia
para um futuro do trabalho mais sustentável, eficiente e inteligente.
