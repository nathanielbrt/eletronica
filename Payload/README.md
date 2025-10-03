Aviônica Modular para [Nome do Projeto/Foguete]
Este repositório contém todo o design, documentação e arquivos de desenvolvimento para o sistema de aviônica embarcada do projeto [Nome do Projeto]. O sistema foi projetado de forma modular, dividido em três placas de circuito impresso (PCBs) distintas, cada uma com uma função crítica para o sucesso da missão.

Todas as placas foram desenvolvidas utilizando a tecnologia SMD (Surface-Mount Device) para garantir um design compacto, leve e com alta resistência a vibrações, ideal para aplicações aeroespaciais.

As Placas do Sistema
O sistema de aviônica é composto pelas seguintes placas:

1. 🛰️ Placa de Aquisição de Dados (Data Acquisition)
Esta placa funciona como o sistema sensorial do veículo. Sua principal responsabilidade é coletar dados críticos sobre o estado e a posição do foguete durante todo o voo, desde a plataforma de lançamento até a recuperação.

Principais Componentes:

Módulo GNSS: Para rastreamento de posição global (latitude, longitude) e velocidade com alta precisão.

IMU (Unidade de Medição Inercial): Um conjunto de acelerômetros e giroscópios de 9 eixos para determinar a orientação, atitude (roll, pitch, yaw) e acelerações sofridas pelo veículo.

Barômetro: Sensor de alta sensibilidade para medir a pressão atmosférica, permitindo um cálculo preciso da altitude.

Principais Responsabilidades:

Coletar dados brutos de todos os sensores de bordo.

Fornecer um fluxo constante de informações para o computador de bordo.

Garantir a integridade dos dados na fonte de coleta.

2. 🧠 Computador de Bordo (On-Board Computer - OBC)
O OBC é o cérebro de toda a operação. Construído em torno de um poderoso microcontrolador STM32, esta placa centraliza o gerenciamento de todos os subsistemas. Ela não apenas processa os dados, mas também toma decisões críticas em tempo real.

Principal Componente:

Microcontrolador STM32 (MCU): Orquestra todas as tarefas, executa os algoritmos de voo e gerencia a comunicação entre as placas.

Principais Responsabilidades:

Administrar e alimentar os demais subsistemas.

Receber os dados brutos da placa de Aquisição de Dados.

Executar algoritmos de fusão de sensores (ex: Filtro de Kalman) para combinar os dados da IMU, GNSS e barômetro, gerando uma estimativa de estado muito mais precisa e confiável.

Gerenciar o envio de dados para a placa de comunicação e o salvamento local no SD Card.

3. 📡 Placa de Comunicação e Armazenamento (Telemetry & Storage)
Esta placa é o elo de comunicação com o mundo exterior e, ao mesmo tempo, a "caixa-preta" do foguete. Ela garante que os dados de voo sejam transmitidos para a equipe em solo e que uma cópia segura de tudo seja armazenada a bordo.

Principais Componentes:

Rádio LoRa E22: Módulo de comunicação de longo alcance (Long Range) para enviar pacotes de dados (telemetria) para uma estação em solo, mesmo a quilômetros de distância.

Slot para Cartão MicroSD: Para o armazenamento local de todos os dados coletados durante o voo, servindo como um backup essencial para análise pós-voo.

Principais Responsabilidades:

Enviar telemetria em tempo real para a estação de solo.

Gravar logs de alta frequência de todos os dados dos sensores e do estado do veículo no cartão de memória.

Garantir a redundância dos dados, protegendo-os contra falhas de comunicação.
