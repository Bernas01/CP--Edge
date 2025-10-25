# 🌡️ Projeto ESP32 com MQTT, DHT11 e LDR

Este projeto tem como objetivo demonstrar a coleta e transmissão de dados de sensores utilizando a placa **ESP32**.  
São utilizados o sensor **DHT11** (para temperatura e umidade) e um **LDR** (para luminosidade).  
Os dados são enviados via **MQTT** para um broker, permitindo monitoramento remoto e integração com sistemas IoT.

---

## 🎯 Objetivos

- Ler temperatura e umidade através do **DHT11**.  
- Medir a luminosidade ambiente com um **LDR**.  
- Enviar as informações para um **servidor MQTT**.  
- Demonstrar um fluxo completo de coleta e publicação de dados em rede IoT.

---

## ⚙️ Componentes Utilizados

| Componente | Descrição | Quantidade |
|-------------|------------|-------------|
| ESP32 | Microcontrolador Wi-Fi e Bluetooth | 1 |
| DHT11 | Sensor de Temperatura e Umidade | 1 |
| LDR | Sensor de Luminosidade | 1 |
| Resistor de 10kΩ | Para divisor de tensão do LDR | 1 |
| Jumpers | Fios de conexão | Vários |
| Protoboard | Montagem dos componentes | 1 |

---

## 🔌 Conexões do Circuito

| Componente | Pino ESP32 | Observações |
|-------------|------------|-------------|
| DHT11 (DATA) | GPIO 4 | Conecte também ao VCC (3.3V) e GND |
| LDR | GPIO 34 | Conectado em divisor de tensão com resistor de 10kΩ |
| MQTT | Wi-Fi | Comunicação sem fio com broker MQTT |

---

## 🧩 Bibliotecas Necessárias

As seguintes bibliotecas devem ser instaladas na **IDE do Arduino**:

1. **WiFi.h** – já incluída no pacote ESP32  
2. **PubSubClient** – para comunicação MQTT  
3. **DHT sensor library** – para leitura do sensor DHT11  

📦 Instalação via IDE Arduino:  
> `Sketch > Incluir Biblioteca > Gerenciar Bibliotecas...`

Busque e instale:
- “**PubSubClient**” (Nick O'Leary)  
- “**DHT sensor library**” (Adafruit)

---

## ⚙️ Configurações do Código

Edite as variáveis abaixo de acordo com a sua rede e broker MQTT:

```cpp
const char* ssid = "FIAP-IOT";         
const char* password = "F!@p25.IOT";   

const char* mqttServer = "54.221.163.3"; 
const int mqttPort = 1883;
const char* mqttUser = "nicolas";
const char* mqttPassword = "banana";
