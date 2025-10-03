# Eletrônica do Subsistema Payload - Foguete Nashira

Este repositório contém um levantamento geral do funcionamento de cada PCB embarcada no nosso foguete. O sistema foi projetado de forma modular, dividido em três placas de circuito impresso (PCBs) distintas, cada uma com uma função específica e essencial para o sucesso da missão. Todas as placas foram desenvolvidas utilizando componentes eletrônicos **SMD** devido à complexidade da missão e espaço reduzido no nosso foguete (75mm de diâmetro).

## Nossas PCB's

### 1. 🛰️ Placa de Aquisição de Dados (Data Acquisition)
![Foto da Placa de Aquisição de Dados](imagens/data_acq.jpg)

Esta placa é o **sistema sensorial** do foguete. Sua principal responsabilidade é coletar dados críticos sobre o estado e a posição do foguete durante todo o voo, desde a plataforma de lançamento até a recuperação.

* **Principais Componentes:**
    * `Módulo GNSS`: Para rastreamento (latitude, longitude), velocidade, altitude, etc.
    * `IMU (Unidade de Medição Inercial)`: Um conjunto de acelerômetros e giroscópios para determinar a orientação, atitude (roll, pitch, yaw) e acelerações sofridas pelo veículo.
    * `Barômetro`: Sensor de alta sensibilidade para medir a pressão atmosférica e contribuir com a determinação de altitude.

---

### 2. 🧠 Computador de Bordo (On-Board Computer)
![Foto da Placa de Computação de Bordo](imagens/obc.jpg)

O OBC é o **cérebro de toda a operação**. Construído em torno de um poderoso microcontrolador `STM32`, esta placa centraliza o gerenciamento de todos os subsistemas, faz a fusão e filtragem dos dados recebidos e comanda envio e armazenamento deles.

* **Principal Componente:**
    * `Microcontrolador STM32 (MCU)`: Orquestra todas as tarefas, executa os algoritmos de voo e gerencia a comunicação entre as placas.

---

### 3. 📡 Placa de Comunicação e Armazenamento (Sending & Storage)
![Foto da Placa de Computação de Bordo](imagens/send_sto.jpg)

Esta placa é o **elo de comunicação** foguete-solo e, ao mesmo tempo, a **"caixa-preta"** do foguete. Ela garante que os dados de voo sejam transmitidos para o nosso receptor e que uma cópia segura de tudo seja armazenada a bordo.

* **Principais Componentes:**
    * `Rádio LoRa E22`: Módulo de comunicação de longo alcance (Long Range).
    * `Slot para Cartão MicroSD`: Para o armazenamento local de todos os dados coletados durante o voo.


