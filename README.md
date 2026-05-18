# Projeto_IoT

## Alunos

- Bruno Rossi de Lima  
- Gustavo Novais Cheida
- Victor Ferraretto Novais

## Descrição do Projeto

Este projeto consiste no desenvolvimento de um sistema de cofre inteligente utilizando Arduino, com controle de acesso por senha, monitoramento de segurança por sensor de luz (LDR) e feedback visual e sonoro.

O objetivo é simular um sistema real de segurança, capaz de:
- Validar acesso por senha
- Detectar tentativas de arrombamento
- Emitir alertas
- Controlar a abertura física do cofre com servo motor

---

## Funcionalidades

- Entrada de senha utilizando 3 botões
- Validação da senha digitada
- Bloqueio do sistema após 3 tentativas incorretas
- Botão de reset para reiniciar o sistema
- Monitoramento de luz interna com sensor LDR
- Detector de arrombamento
- Alerta sonoro com buzzer
- Exibição de informações em display LCD 16x2
- Abertura física do cofre com servo motor

---

## Lógica de Funcionamento

### Estado Inicial
- O sistema inicia solicitando a senha no display LCD.

### Entrada de Senha
- O usuário utiliza os botões para inserir a senha.
- A senha digitada é exibida como `***` no LCD.

### Senha Correta
- O cofre é aberto (servo gira 90°)
- O buzzer emite um sinal sonoro
- O sistema passa a monitorar a luz interna

### Senha Incorreta
- O sistema incrementa o número de tentativas
- Após 3 erros, o sistema é bloqueado

### Arrombamento
- Se o cofre estiver fechado e o sensor detectar luz:
  - O sistema identifica como arrombamento
  - O Servo Motor representa o arrombamento do cofre
  - Um alerta sonoro é acionado

### Monitoramento de Luz
- Com o cofre aberto, o LCD exibe:
  - "Luz: LIGADA"
  - "Luz: DESLIGADA"

### Reset
- O botão de reset reinicia todo o sistema:
  - Fecha o cofre
  - Zera tentativas
  - Libera o sistema

---

## Componentes Utilizados

- Arduino Uno
- Display LCD 16x2
- Potenciômetro (para contraste do LCD)
- 4 botões (3 senha + 1 reset)
- Sensor LDR (fotoresistor)
- Resistor 10kΩ (para LDR)
- Buzzer
- Servo motor
- Protoboard

---

## Ligações Principais

### LCD
- RS → D12  
- E → D11  
- D4 → D5  
- D5 → D4  
- D6 → D3  
- D7 → D2  

### Botões
- Botão 1 → D6  
- Botão 2 → D7  
- Botão 3 → D8  
- Reset → D9  
- Todos conectados ao GND

### Buzzer
- Positivo → D10  
- Negativo → GND  

### Servo Motor
- Sinal → D13  
- VCC → 5V  
- GND → GND  

### LDR (Divisor de tensão)
- LDR → 5V  
- LDR → A0  
- Resistor 10kΩ entre A0 e GND  

---

## Conclusão

O projeto atingiu os objetivos propostos, integrando diferentes componentes de hardware em um sistema funcional de segurança.

Foi possível aplicar conceitos de:
- Entrada e saída digital
- Leitura analógica
- Controle de estados
- Interação com usuário
- Automação com Arduino

## Diagrama de conexões

<img width="1058" height="721" alt="image" src="https://github.com/user-attachments/assets/13bb9862-e126-4ebd-a90c-b8937dc25565" />

