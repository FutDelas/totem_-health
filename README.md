# ⚽🏃‍♀️ Projeto IoT: Monitoramento de Saúde de Atletas de Futebol Feminino de Base

<p align="center">
  <img src="https://img.shields.io/badge/Status-Concluído-4CAF50?style=for-the-badge&logo=github" alt="Status Concluído">
  <img src="https://img.shields.io/badge/Tecnologia-FIWARE%20%7C%20MQTT-0099D1?style=for-the-badge&logo=internet-explorer" alt="Tecnologias FIWARE | MQTT">
  <img src="https://img.shields.io/badge/Linguagem-C%2B%2B%20(Arduino)-00599C?style=for-the-badge&logo=c%2B%2B" alt="Linguagem C++">
</p>

> Uma solução completa de **Internet das Coisas (IoT)** para monitorar em tempo real a saúde das jogadoras, automatizar o registro de presença e disponibilizar dados cruciais para análise de desempenho e prevenção de lesões em um painel online. **Inovação no Esporte.**

---

## 🌟 Sumário (Navegável)

| Seção | Tópico | Emoji |
| :--- | :--- | :--- |
| **1.** | **[Visão Geral](#visão-geral)** | 🎯 |
| **2.** | **[Conceitos de IoT](#conceitos-de-iot)** | 💡 |
| **3.** | **[Arquitetura do Sistema](#arquitetura-do-sistema)** | 🏗️ |
| **4.** | **[Tecnologias Utilizadas](#tecnologias-utilizadas)** | 💻 |
| **5.** | **[Desenvolvimento](#desenvolvimento)** | ⚙️ |
| **6.** | **[Demonstração](#demonstração)** | 🎥 |
| **7.** | **[Benefícios](#benefícios)** | ⭐ |

---

## ➡️ Visão Geral

A solução **inovadora** foi projetada para monitorar continuamente a saúde das atletas de futebol de base, utilizando um **Dispositivo Inteligente (Pulseira)** com as seguintes funcionalidades chave:

| Funcionalidade | Descrição |
| :--- | :--- |
| **Registro Automático de Presença** | ✅ Faz o registro de presença ao aproximar do totem. |
| **Coleta de Dados Vitalícios** | 💓 Coleta dados de saúde durante treinos e partidas (**batimentos cardíacos, movimentação, tempo ativo**). |
| **Transmissão em Tempo Real** | ☁️ Envia os dados para a nuvem via protocolo **MQTT** em tempo real. |
| **Persistência de Dados** | 💾 Salva o histórico para análise futura. |
| **Análise de Desempenho** | 📈 Exibe os resultados em um **Dashboard Online**, auxiliando técnicos e profissionais de saúde na prevenção de lesões e na melhora do desempenho das atletas. |

> O principal objetivo é auxiliar na **prevenção de lesões** e otimizar o **desempenho** das atletas com base em dados concretos.

---

## 💡 Conceitos de IoT

A **Internet das Coisas (IoT)** conecta objetos do mundo físico à internet, permitindo que eles **coletem, transmitam e processem dados automaticamente**.

### Por que IoT é Crucial para este Projeto?

| Benefício | Impacto |
| :--- | :--- |
| **Automação de Processos** | 🤖 Automatiza o fluxo de informações sem intervenção manual. |
| **Coleta Contínua e Instantânea** | ⏱️ Garante coleta contínua e em tempo real. |
| **Inteligência de Dados** | 🧠 Facilita a análise inteligente de dados, permitindo **decisões baseadas em evidências**. |
| **Saúde e Performance** | 🛡️ Melhora o desempenho esportivo e atua diretamente na **redução de riscos de lesões**. |

---

## 🏗️ Arquitetura do Sistema

O sistema é construído sobre a plataforma **FIWARE**, garantindo um gerenciamento de contexto eficiente e escalável.

<p align="center">
  <img alt="Diagrama de Arquitetura do Backend do Projeto" src="https://github.com/user-attachments/assets/526fc850-e0fc-43a1-9e04-0c3e7ba139b0" />
</p>

### 🔄 Fluxo de Dados Detalhado (A Jornada do Dado)

O diagrama acima ilustra o fluxo que traduz os dados brutos da pulseira em informações de contexto acessíveis:

1.  **Início da Sessão:** A jogadora aproxima a pulseira do totem → **registro de presença** é enviado.
2.  **Transmissão de Telemetria:** Durante o jogo, a pulseira envia dados de saúde via **MQTT**.
3.  **Conversão de Protocolo:** O **IoT Agent** traduz as mensagens MQTT para o padrão **NGSIv2**.
4.  **Gerenciamento de Contexto:** O **Orion Context Broker** gerencia os dados de contexto em tempo real.
5.  **Persistência Histórica:** O **STH-Comet** armazena os dados históricos no **MongoDB**.
6.  **Visualização:** O dashboard web exibe relatórios e gráficos de desempenho.

---

## 💻 Tecnologias Utilizadas

Este projeto foi desenvolvido utilizando uma stack robusta e orientada a IoT:

| Componente | Tecnologia | Função | Badge |
| :--- | :--- | :--- | :--- |
| **Gerenciamento de Contexto** | **[FIWARE](https://www.fiware.org/)** | Plataforma open-source essencial para o coração do sistema. | <img src="https://img.shields.io/badge/FIWARE-00519E?style=flat&logo=fiware&logoColor=white" alt="FIWARE Badge"> |
| **Comunicação IoT** | **[MQTT (HiveMQ)](https://www.hivemq.com/)** | Protocolo de comunicação leve e eficiente para transmissão de dados. | <img src="https://img.shields.io/badge/MQTT-600000?style=flat&logo=mqtt&logoColor=white" alt="MQTT Badge"> |
| **Persistência de Dados** | **STH-Comet + [MongoDB](https://www.mongodb.com/)** | Armazenamento seguro e escalável de todo o histórico de telemetria. | <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white" alt="MongoDB Badge"> |
| **Orquestração** | **[Docker Compose](https://docs.docker.com/compose/)** | Facilita o deploy e a gestão de todos os microserviços (containers). | <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white" alt="Docker Badge"> |
| **Prototipagem** | **[Arduino](https://www.arduino.cc/) / [Wokwi](https://wokwi.com/)** | Simulação e prototipagem do dispositivo antes da implementação física. | <img src="https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white" alt="Arduino Badge"> |

---

## ⚙️ Desenvolvimento

O processo de implementação foi estruturado em três fases principais:

### 1. Configuração da Plataforma IoT (Backend)

| Passo | Descrição |
| :--- | :--- |
| **Deploy** | 🐳 Deploy dos containers do FIWARE (`Orion`, `IoT Agent`, `MongoDB`, `STH-Comet`) com **Docker Compose**. |
| **Broker** | 🔗 Configuração do **HiveMQ** como broker MQTT. |

### 2. Criação de Dispositivos Virtuais (Simulação)

| Passo | Descrição |
| :--- | :--- |
| **Integração** | 🔑 Configuração do **IoT Agent** com API Key e Device ID. |
| **Prototipagem** | 🧪 Simulação do envio de dados usando a plataforma **Wokwi**. |

### 3. Protocolos de Comunicação

O projeto utiliza uma combinação de protocolos otimizados:
- **MQTT (Message Queuing Telemetry Transport):** Utilização para **telemetria** (envio de dados da pulseira).
- **HTTP / NGSIv2:** Utilizado para **atualização de entidades** no Orion e comunicação entre os componentes FIWARE.

## 🎥 Demonstração

Veja o projeto em ação! O ciclo de monitoramento é simples e eficaz:

### 🔁 Ciclo de Monitoramento

| Etapa | Ação | Resultado no Sistema |
| :--- | :--- | :--- |
| **1. Início** | 🏃‍♀️ Jogadora aproxima a pulseira do totem → **login** no sistema. | ✅ Sessão iniciada. |
| **2. Monitoramento** | 🎮 Durante o jogo, dados são enviados em tempo real para o Orion. | 🚀 Dados em **tempo real** sendo processados. |
| **3. Finalização** | 🛑 Após o jogo, pulseira é aproximada novamente → **sessão é encerrada** e dados são salvos. | 💾 Histórico persistido. |
| **4. Análise** | 📊 Dashboard exibe gráficos de desempenho e indicadores de saúde. | 📈 Visualização de dados. |

### 📸 Dashboard de Análise

<p align="center">
  <img alt="Screenshot do Dashboard de Análise de Desempenho" src="https://github.com/user-attachments/assets/42aa034d-5432-4cbb-9da6-41fd527ce155" />
</p>

---

### 🔗 Links Interativos

| Recurso | Descrição | Link |
| :--- | :--- | :--- |
| **Protótipo Interativo** | Simulação do Totem e da Pulseira em funcionamento (o Wokwi utiliza botões em vez de touch). | 👉 **[Simulação no Wokwi](https://wokwi.com/projects/442099339610562561)** |
| **Vídeo Completo** | Demonstração gravada do fluxo completo, incluindo a persistência dos dados. | 🎥 **[Assista no YouTube](https://youtu.be/xJOJnZtaSCA)** |

---

## ⭐ Benefícios

Os principais ganhos com a implementação desta solução IoT são:

| Benefício | Descrição Detalhada | Emoji |
| :--- | :--- | :--- |
| **1. Automação** | Sem necessidade de digitação ou papelada, garantindo **100% de automação** no registro. | ⚙️ |
| **2. Monitoramento Contínuo** | Garante dados vitais (batimentos, tempo ativo) em **tempo real** para monitoramento imediato. | ⏱️ |
| **3. Histórico Centralizado** | Facilita a **análise de longo prazo** e identificação de padrões de desempenho. | 📈 |
| **4. Prevenção de Lesões** | Identifica riscos antes de se tornarem problemas. | 🛡️ |
| **5. Decisão Baseada em Dados** | Melhora o planejamento técnico e maximiza o desempenho. | 🧠 |

---

## 🙋‍♀️ Autoras do Projeto



| Nome | RM | Localização |
| :--- | :--- | :--- |
| Ana Luiza De Franco e Rinaldi | `RM: 564061` | 📍 São Paulo, Brasil |
| Giovana Gaspar Larocca | `RM: 564965` | 📍 São Paulo, Brasil |
| Giovanna Lins Sayama | `RM: 565901` | 📍 São Paulo, Brasil |
| Rayssa Luzia Portela Aquino | `RM: 562024` | 📍 São Paulo, Brasil |

---

