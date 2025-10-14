# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
  <a href="https://www.fiap.com.br/">
    <img src="img/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" border="0" width="80%" height="40%">
  </a>
</p>

## 👥 Grupo 25

## 👨‍🎓 Integrantes:

- Amanda Vieira Pires (RM566330)
- Ana Gabriela Soares Santos (RM565235)
- Bianca Nascimento de Santa Cruz Oliveira (RM561390)
- Milena Pereira dos Santos Silva (RM565464)
- Nayana Mehta Miazaki (RM565045)

## 👩‍🏫 Professores:

### Tutor(a)

- Lucas Gomes Moreira

### Coordenador(a)

- André Godoi

---

# **ENTREGA 1** 🌾 FarmTech Solutions - Projeto de IA para Agricultura

## 📋 Sobre o Projeto

O **FarmTech Solutions** é um projeto de Inteligência Artificial desenvolvido para a **Fase 6 do curso de Inteligência Artificial da FIAP**. 
Com o sucesso da implementação de soluções de IA para a otimização de plantações, a FarmTech Solutions expandiu sua atuação para além do agronegócio tradicional, abrangendo agora o setor de **saúde animal** e outros serviços estratégicos. O projeto visa a implementação do **método YOLO** para detectar e segregar objetos a fim de criar um sistema de visão computacional eficaz para uma análise prática e em tempo real, fornecendo insights acionáveis para otimizar a produtividade e garantir o melhor cuidado para seu rebanho, unindo o sucesso que já obtivemos no campo com a inovação no **manejo animal**. 

### 🎯 Objetivos

- **Dataset**: seleção de imagens separadas em treinamento, validação e teste.
- **Labels**: criação de labels nas imagens para identificação dos objetos
- **Arquitetura**: YOLO

### 📊 Dataset

**Pasta**: Cap_1
**Local**: Google drive
**Link**: https://drive.google.com/drive/folders/1WLe_Iwy2RCa5MSCHE2sDJgeLfuxUh-B9?usp=drive_link

# 🏗️ Estrutura do Projeto

```
chap1-phase06-farm-tech/
├── FarmTech_Solutions_YOLO.ipynb  # Google colab notebook
└── README.md                      # Este arquivo
```

# 🔄 Fluxo do Projeto

```
🎯 Dataset → 🔀 Detecção e Segmentação 
```

# Etapas Principais

**1. 🎯 Dataset** (Make sense IA: 2 labels)

**2. 🔀 Arquitetura** (YOLO)

# 🚀 Como Executar

## 1. **Pré-requisitos**

- Google Colab Notebook
- Google Drive
- Git

## 2. **Instalação**

```bash
# Clone o repositório
git clone https://github.com/fiap-ia-2025/chap1-phase06-farm-tech.git
```

# 3. **Execução**

1. Criação do Dataset no GoogleDrive: necessário clonar as pastas do Google Drive para seu próprio Drive.
2. Executar código do Google Colab Notebook

# 🛠️ Tecnologias e Dependências

## Tecnologias Utilizadas

- **Google Colab Notebook**: Ambiente de desenvolvimento
- **Google drive**: Armazenamento dados

# 📊 Dataset

Para iniciar o desenvolvimento do sistema de visão computacional, foram selecionados dois objetos principais: `Sheep` (Ovelha) e `Cow` (Vaca). <br>
A plataforma `Make Sense IA` foi utilizada para a crucial etapa de rotulagem (labeling). Neste processo, as imagens de ovelhas e vacas foram inseridas para que os labels fossem criados e, subsequentemente, identificados com precisão em cada imagem. Isso é fundamental para treinar o modelo a reconhecer cada animal. <br>

Para garantir um treinamento robusto e uma avaliação justa do modelo, foi separado um total de 40 imagens para cada animal. O conjunto de dados foi então dividido e organizado em pastas definidas no `Google Drive`, seguindo a distribuição padrão para aprendizado de máquina: <br>

**Treino**: 32 imagens (para o treinamento do modelo). <br>

**Validação**: 4 imagens (para ajuste fino do modelo durante o treinamento). <br>

**Teste**: 4 imagens (para avaliação do desempenho final do modelo). 

# 📈 Análise e Explicação do Código

O objetivo é treinar o modelo para identificar os objetos `cow` (vaca) e `sheep` (ovelha) utilizando a arquitetura YOLOv5 (You Only Look Once, versão 5) no ambiente Google Colab.

## 1. ⚙️ Conexão com o Google Drive

Os dados de treinamento (imagens e rótulos) estão armazenados na conta do Google Drive e por isso é necessária a sua conexão.

## 2. ⬇️ Baixar o Repositório YOLOv5 e Instalar Dependências 

O **YOLOv5** é um modelo de detecção de objetos de código aberto, portanto é possível baixar os arquivos da arquitetura e instalar todas as bibliotecas Python necessárias para que o treinamento e a detecção funcionem corretamente.

## 3. 📄 Configuração do Dataset

Para informar ao **YOLOv5** onde encontrar os conjuntos de imagens e quais classes (objetos) ele deve aprender a identificar é preciso criar um arquivo de configuração: `data.yaml`.

## 4. 🧠 Treinamento do Modelo

O treinamento ocorre em duas fases, usando diferentes números de épocas, **30 épocas e 60 épocas**, para que o modelo aprenda a detectar os objetos.

| Métrica | 30 Épocas | 60 Épocas | Comparação |  
| :--- | :---: | ---: | ---: |
| mAP@0.5 | 81,7% | 86,4% | A precisão na identificação dos objetos melhorou. |
| mAP@0.5:0.95 | 46,5% | 55,1% | A precisão na localização exata das caixas delimitadoras teve um avanço. |
| Precisão | 81,7% | 87,6% | Pouca mudança na taxa de acertos, porém ambas estão altas. |
| Recall | 80% | 84% | Melhoria de 4% para encontrar os objetos reais no conjunto de validação. |
| Loss Final | 0.0247 | 0.0163 | O valor de erros diminuiu, ou seja, o modelo aprendeu a cometer menos erros. |

**Para o treinamento de 60 Épocas:**

![Histórico de Execução](img/historico.jpg)

O gráfico apresentado é o Histórico de Execução gerado durante o treinamento do modelo de Visão Computacional **YOLOv5**, que tem como objetivo detectar `Cow` (Vaca) e `Sheep `(Ovelha) e verificar a evolução e a saúde do modelo ao longo das épocas de treinamento. <br>

As `metrics/mAP_0.5`, `metrics/mAP_0.5:0.95`, `metrics/precision` e `metrics/recall` são **métricas de performance** para indicar a capacidade do modelo de acertar as detecções do conjunto de validação. A tendência clara de crescimento nessas barras aponta para um aprendizado bem-sucedido. <br>

As `train/box_loss`, `val/box_loss`, `train/cls_loss`, `val/cls_loss`, `train/obj_loss` e `val/obj_loss` são **métricas de perda** para mostrar o grau de erro do modelo. A tendência ideal é a de queda progressiva indicando que o modelo está ajustando seus pesos e diminuindo seus erros a cada época.

## 5. ✅ Validação do Teste

Ocorre a capacidade de detecção do modelo, utilizando imagens que ele nunca viu antes.

![Teste Ovelha](img/42.jpg)

![Teste Vaca](img/2.jpg)

As imagens representam o resultado e a eficácia do modelo YOLOv5 treinado. As caixas delimitam os animais e os números indicam o nível de confiança da detecção do modelo. <br>
Os resultados indicam o sucesso do treinamento com altos níveis de confiança na identificação de `cow` e `sheep` em diferentes posições, raças e ambientes.

# 🎬 Vídeo 

Link para vídeo do Youtube: https://youtu.be/ASjsuGd0Lrs

---

# **ENTREGA 2** 🔬 Comparação de Métodos de Visão Computacional

## 📋 Sobre a Entrega 2

A **Entrega 2** expande o projeto FarmTech Solutions com uma **análise comparativa** de diferentes abordagens de visão computacional. O objetivo é avaliar criticamente três métodos distintos para reconhecimento de objetos (vacas e ovelhas), comparando suas performances, facilidade de uso e aplicabilidade prática.

### 🎯 Objetivos da Entrega 2

- **Comparar 3 métodos**: YOLO Customizado vs YOLO Tradicional vs CNN do Zero
- **Avaliar métricas**: Tempo de treinamento, tempo de inferência, precisão e facilidade de uso
- **Fornecer recomendações**: Qual método usar em diferentes cenários
- **Análise crítica**: Pontos fortes e limitações de cada abordagem

### 🔬 Métodos Analisados

1. **🎯 YOLO Customizado** (da Entrega 1)
   - Modelo treinado especificamente para vacas e ovelhas
   - Transfer learning com YOLOv5

2. **⚡ YOLO Tradicional** (Ultralytics)
   - Modelo pré-treinado no dataset COCO
   - Pronto para uso, sem treinamento adicional

3. **🧠 CNN do Zero** (TensorFlow)
   - Rede neural convolucional criada from scratch
   - Classificação binária: Vaca vs Ovelha

## 🏗️ Estrutura da Entrega 2

```bash
ColabNotebooks/
├── Cap_1/ # Dataset YOLO (Entrega 1 e 2)
├── Cap_1_CNN/ # Dataset CNN organizado (Entrega 02)
│ ├── train/
│ │ ├── cow/ # Imagens de vacas para treino
│ │ └── sheep/ # Imagens de ovelhas para treino
│ ├── val/
│ │ ├── cow/ # Imagens de vacas para validação
│ │ └── sheep/ # Imagens de ovelhas para validação
│ └── test/
│ ├── cow/ # Imagens de vacas para teste
│ └── sheep/ # Imagens de ovelhas para teste
├── [Entrega02]FarmTech_Comparacao.ipynb # Notebook da Entrega 2
```

## 🚀 Como Executar a Entrega 2

### 1. **Pré-requisitos**
- Execução prévia da **Entrega 1** (YOLO Customizado)
- Google Colab Notebook
- Google Drive com as pastas organizadas

### 2. **Setup dos Dados**
```bash
# 1. Clone as pastas necessárias para seu Google Drive:
# - Cap_1 (da Entrega 1)
# - Cap_1_CNN (nova estrutura para CNN)
```
Link do Drive (Com ambas as pastas): https://drive.google.com/drive/u/0/folders/1_wOu8gbT9Kah4gCnpIoYT3CPSlozOLbK

### 3. Execução
- Conectar Google Drive no Colab
- Executar YOLO Tradicional: Análise com Ultralytics YOLOv8
- Criar e Treinar CNN: Arquitetura personalizada do zero
- Comparar Resultados: Análise comparativa dos 3 métodos

## 📊 Critérios de Avaliação e Resultados

### 🔍 Métricas de Comparação

| Critério | Descrição | YOLO Customizado | YOLO Tradicional | CNN do Zero |
|----------|-----------|------------------|------------------|-------------|
| **⏱️ Tempo de Treinamento** | Tempo necessário para treinar | [A coletar] | 0 min (pré-treinado) | [A coletar] |
| **⚡ Tempo de Inferência** | Velocidade de predição (ms/imagem) | [A coletar] | [A coletar] | [A coletar] |
| **🎯 Precisão/Accuracy** | Taxa de acertos na detecção | [A coletar] | [A coletar] | [A coletar] |
| **🔧 Facilidade de Uso** | Complexidade de implementação | Média | Alta | Baixa |
| **🔄 Flexibilidade** | Adaptação para novos objetos | Alta | Baixa | Alta |
| **📱 Aplicabilidade** | Adequação para projeto | [A avaliar] | [A avaliar] | [A avaliar] |

### 📈 Estrutura de Análise

**🔍 Análise Individual**: Cada método avaliado com métricas específicas  
**⚖️ Comparação Direta**: Tabela consolidada dos três métodos  
**🎯 Recomendações**: Por cenário (produção, pesquisa, educação)  
**📝 Conclusões**: Análise crítica e limitações identificadas  

### 📊 Resultados da Comparação

| Método | Accuracy | Tempo Inferência | Facilidade de Uso | Flexibilidade |
|--------|----------|------------------|-------------------|---------------|
| **YOLO Customizado** | **86.4%** | Não medido | Média | Alta |
| **YOLO Tradicional** | 72.9% | 520ms | **Alta** | Baixa |
| **CNN do Zero** | 62.5% | 682ms | Baixa | **Alta** |

### 🎯 Principais Descobertas

**🏆 YOLO Customizado - Melhor Performance**
- **86.4% de accuracy** - superior aos demais métodos
- Treinamento específico para vacas/ovelhas foi eficaz
- Recomendado para ambiente de produção

**⚡ YOLO Tradicional - Melhor Praticidade**  
- **Implementação imediata** sem necessidade de treinamento
- Performance adequada (72.9%) para casos de uso gerais
- Ideal para prototipagem rápida e demonstrações

**🧠 CNN do Zero - Melhor Controle**
- **Flexibilidade total** na arquitetura
- Performance limitada (62.5%) com modelo simples
- Excelente para fins educacionais e experimentação

### 💡 Conclusão

O **YOLO Customizado** demonstrou superioridade para o caso específico de detecção de vacas e ovelhas, validando a abordagem de treinamento especializado da FarmTech Solutions. A comparação revelou que modelos específicos superam soluções genéricas quando dados adequados estão disponíveis.

**Recomendação:** Implementar YOLO Customizado para casos de produção, mantendo YOLO Tradicional como alternativa para demonstrações rápidas.





