# Global Solution – Soluções em Energias Renováveis e Sustentáveis

Repositório da Global Solution de **Ciência da Computação – 2º semestre de 2025**.

## 🎯 Tema do Projeto

**Smart Office Verde – Monitoramento inteligente de energia em estações de trabalho**

A proposta deste projeto é analisar o consumo de energia em um ambiente de trabalho
(estações de trabalho de escritório) e simular o impacto de uma automação IoT que
reduz desperdícios, conectando tecnologia, eficiência energética e futuro do trabalho.

O projeto foi desenvolvido para atender aos seguintes requisitos do enunciado:

1. **Coleta e Análise de Dados**  
   Uso de dados simulados de consumo de energia por estação de trabalho, ao longo de vários dias,
   com informações de presença, equipamentos ligados e consumo horário.

2. **Conexão com o Futuro do Trabalho**  
   Demonstra como escritórios inteligentes (smart offices) podem utilizar dados e automação para
   reduzir custos, emissões de CO₂ e desperdícios, especialmente em cenários híbridos de trabalho.

3. **Desenvolvimento da Solução – Opções A e B**  
   - **Opção A – Análise de Dados**: identificação de desperdícios, estimativa de ganhos econômicos
     e ambientais quando o consumo fora de horário de trabalho é reduzido.
   - **Opção B – Dispositivo IoT (simulado)**: simulação de lógica de automação baseada em sensor
     de presença, desligamento automático de equipamentos e comparação de cenários antes vs. depois.

4. **Repositório Organizado no GitHub**  
   Contém dados, código, documentação e instruções de execução.

5. **Vídeo Explicativo (até 3 min)**  
   O roteiro sugerido para o vídeo está no documento `docs/relatorio_projeto.md` na seção
   **“Roteiro sugerido para o vídeo (até 3 min)”**.

---

## 🗂 Estrutura do Repositório

```text
global-solution-energia/
├─ dados/
│  └─ consumo_simulado_escritorio.csv
├─ codigo/
│  └─ analise_consumo.ipynb
├─ docs/
│  └─ relatorio_projeto.md
├─ requirements.txt
└─ README.md
```

### 📁 `dados/consumo_simulado_escritorio.csv`

Arquivo de dados simulados contendo:

- `data` – data da medição (YYYY-MM-DD)  
- `hora` – hora (HH:MM)  
- `estacao` – identificador da estação de trabalho (por exemplo, `Estacao_01`)  
- `pessoas_presentes` – 1 se há alguém na estação, 0 se não  
- `computador` – 1 se o computador está ligado, 0 se não  
- `monitor` – 1 se o monitor está ligado, 0 se não  
- `iluminacao` – 1 se a iluminação local está ligada, 0 se não  
- `ar_condicionado` – 1 se o ar-condicionado da área está ligado, 0 se não  
- `consumo_wh` – consumo estimado daquela estação naquela hora (em Wh)

Os valores foram simulados considerando maior presença de pessoas e maior probabilidade
de ar-condicionado ligado em horário comercial (8h às 18h).

### 📁 `codigo/analise_consumo.ipynb`

Notebook Jupyter com:

- Carregamento e inspeção dos dados
- Cálculo de consumo total por dia
- Separação entre consumo em **horário de trabalho** e **fora do expediente**
- Identificação de desperdício (energia consumida quando não há pessoas presentes)
- Simulação de um cenário **com automação IoT**, que desliga equipamentos quando não há presença
- Estimativas de economia em:
  - kWh
  - R$ (considerando uma tarifa assumida em documentação)
  - kg de CO₂ evitados (fator médio de emissão por kWh)
- Geração de gráficos (sem formatação específica de cor, para compatibilidade geral)

### 📁 `docs/relatorio_projeto.md`

Documento de apoio contendo:

- Introdução e contexto
- Objetivo geral do projeto
- Descrição da solução proposta
- Metodologia de simulação de dados e análise
- Resultados esperados e interpretação
- Conexão com o futuro do trabalho
- Roteiro sugerido para o vídeo de até 3 minutos

---

## ▶️ Como Executar o Projeto Localmente

### 1. Pré-requisitos

- Python 3.10+ (recomendado)
- `pip` atualizado
- Jupyter Notebook ou JupyterLab

### 2. Clonar o repositório

```bash
git clone https://github.com/SEU_USUARIO/global-solution-energia.git
cd global-solution-energia
```

> Substitua `SEU_USUARIO` pelo seu usuário do GitHub ao criar o repositório.

### 3. Criar ambiente virtual (opcional, mas recomendado)

```bash
python -m venv venv
source venv/bin/activate  # Linux/macOS
# ou
venv\Scripts\activate   # Windows
```

### 4. Instalar dependências

```bash
pip install -r requirements.txt
```

### 5. Abrir o notebook

```bash
jupyter notebook codigo/analise_consumo.ipynb
```

Em seguida, execute as células na ordem para reproduzir as análises e gráficos.

---

## 📹 Vídeo (até 3 minutos)

O vídeo deve:

1. Apresentar **o problema** (desperdício de energia em ambientes de trabalho).  
2. Mostrar **a solução** (análise de dados + automação IoT simulada).  
3. Destacar **os resultados esperados** (economia de energia, redução de CO₂, conexão com futuro do trabalho).  

O link do vídeo (YouTube como “Não listado”) deve ser incluído:

- Na área de entrega oficial da disciplina.  
- Opcionalmente, pode ser adicionado também neste `README` após a gravação.

---

## 🧠 Critérios de Avaliação (como este projeto atende)

- **Técnica (60 pts)**:  
  - Análise clara e estruturada dos dados.  
  - Metodologia explícita para cálculo de desperdício e economia.  
  - Simulação coerente de automação IoT.

- **Inovação (30 pts)**:  
  - Uso de conceito de *smart office* com presença e automação.  
  - Conexão direta com novos modelos de trabalho (híbrido, flexível).  

- **Usabilidade (10 pts)**:  
  - Repositório organizado.  
  - Notebook comentado e legível.  
  - Roteiro de vídeo e documentação explicando a aplicação prática.

---

## ✉️ Contato / Créditos

- Curso: Ciência da Computação – 2º semestre de 2025  
- Disciplina: Global Solution – Soluções em Energias Renováveis e Sustentáveis  
- Projeto desenvolvido como estudo acadêmico.
