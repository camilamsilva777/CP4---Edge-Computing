# 📘 Monitoramento de Temperatura e Luminosidade - ESP32

# 🚀Integrantes:
🔹Camila de Mendonça da Silva - RM565491
🔹Diego Zandonadi - RM561488
🔹Davi Alves - RM566279

## 🔹 Visão Geral
Este projeto é uma **prova de conceito (PoC)** que monitora **temperatura e luminosidade** utilizando um **ESP32 DOIT DEVKIT V1**.  
O protótipo foi desenvolvido em duas etapas:  
1. **Simulação no Wokwi** com sensor **DHT22** e **LDR**.  
2. **Montagem física** com sensor **DHT11** e **LDR**.  

Os dados são enviados por **ThingSpeak**.

---

## 🚀 Parte 1 – Simulação no Wokwi (DHT22 + LDR)

# Código ino
🔗 [CheckPoint1_Arduino.zip](https://github.com/user-attachments/files/22128360/CheckPoint1_Arduino.zip)

🔗 [Link Wokwi]([https://wokwi.com/](https://wokwi.com/projects/441077412366481409))  

🔗 [Thingspeak Channel]((https://thingspeak.mathworks.com/channels/3058720))  

🔗 [Vídeo do Youtube]([(https://thingspeak.mathworks.com/channels/3058720)](https://youtu.be/AKgNLOY8nAw?si=oMOQDENU1Ub3mvqR)) 

#Imagem do Protótipo no mundo real

![Imagem do protótipo no mundo real](https://github.com/user-attachments/assets/c66c153d-722f-45b1-adea-3d51915893d1)




### 🔌 Hardware virtual
- ESP32 DOIT DEVKIT V1  
- Sensor **DHT22** (temperatura e umidade)  
- Módulo **LDR com resistor** (luminosidade)
  #
### ⁉️ Como funciona:
#Após rodar o código, o sistema captará temperatura, umidade e pressão, enviando assim os dados obtidos para um Dashboard no Thingspeak. Desta forma, **os dados serão expostos em tempo real.**

# 🔌 Parte 2 – Conectando o ESP32 ao Computador e Usando com o ThingSpeak

Agora que o circuito físico já está montado (ESP32 + DHT11 + LDR com resistor embutido), vamos conectar o ESP32 no computador e visualizar os dados no **ThingSpeak**.

---

## 1️⃣ Conectando o ESP32 no computador

1. Pegue um **cabo USB** (micro-USB ou USB-C, depende do modelo do seu ESP32).  
2. Conecte o ESP32 ao computador.  
3. O sistema deve reconhecer a porta serial.  
   - No **Windows**, aparece como `COMX` (ex.: `COM3`, `COM7`).  
   - No **Linux/Mac**, aparece como `/dev/ttyUSB0` ou `/dev/tty.SLAB_USBtoUART`.  
4. No **Arduino IDE**:
   - Vá em **Ferramentas > Placa > ESP32 > DOIT ESP32 DEVKIT V1**.  
   - Vá em **Ferramentas > Porta** e selecione a porta do ESP32.  

---

## 2️⃣ Subindo o código

1. Abra o código no Arduino IDE.  
2. Confirme se os pinos estão configurados corretamente:
   ```cpp
   #define DHTPIN 5
   #define DHTTYPE DHT11
   #define LDR_PIN 34
## 📟 Acompanhando pelo Serial Monitor

1. Abra o **Serial Monitor** no Arduino IDE (atalho `Ctrl+Shift+M`).  
2. Ajuste a velocidade para **115200 baud**.  
3. Você deve ver leituras semelhantes a estas:

Conectando WiFi...
WiFi conectado!
T=25.1 °C | H=58.2 % | L=65.3 %
ThingSpeak respondeu: 1275


- O número **1275** é o **ID do registro no ThingSpeak** → significa que os dados foram enviados com sucesso.
- Após isso, acompanhe novos dados a cada **20 segundos** no Dashboard do Thingspeak 😁
