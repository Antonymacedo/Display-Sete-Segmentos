# Display Sete Segmentos

Display Sete Segmentos, que conta de 0 a 9, com Arduino Uno.

**Materiais**

•Arduino Uno

•Visor de 7 seguimentos(catódico)

•4 Resistores de 270Ω

![Opera Instantâneo_2024-12-13_204012_www tinkercad com](https://github.com/user-attachments/assets/8e5b9a5d-c2a1-407f-826c-42fa62a04b2b)

# Esquema de Conexão:
Conecte os pinos A,B,C,D,E,F,G do display aos pinos digitais do Arduino 2,3,4,5,6,7,8 respectivamente.

Ligue o pino comum do diplay ao GND

# Código

```
// Declaração das portas conectadas aos segmentos do display
const int segA = 2;
const int segB = 3;
const int segC = 4;
const int segD = 5;
const int segE = 6;
const int segF = 7;
const int segG = 8;

// Mapeamento dos números (0-9) para os segmentos do display
const int digit[10][7] = {
  {1, 1, 1, 1, 1, 1, 0}, // 0
  {0, 1, 1, 0, 0, 0, 0}, // 1
  {1, 1, 0, 1, 1, 0, 1}, // 2
  {1, 1, 1, 1, 0, 0, 1}, // 3
  {0, 1, 1, 0, 0, 1, 1}, // 4
  {1, 0, 1, 1, 0, 1, 1}, // 5
  {1, 0, 1, 1, 1, 1, 1}, // 6
  {1, 1, 1, 0, 0, 0, 0}, // 7
  {1, 1, 1, 1, 1, 1, 1}, // 8
  {1, 1, 1, 0, 0, 1, 1}  // 9
};

void setup() {
  // Configura as portas como saídas
  pinMode(segA, OUTPUT);
  pinMode(segB, OUTPUT);
  pinMode(segC, OUTPUT);
  pinMode(segD, OUTPUT);
  pinMode(segE, OUTPUT);
  pinMode(segF, OUTPUT);
  pinMode(segG, OUTPUT);
}

void loop() {
  // Loop para exibir números de 0 a 9 no display
  for (int i = 0; i < 10; i++) {
    displayDigit(i);  // Exibe o número atual
    delay(1000);      // Aguarda 1 segundo antes de mudar para o próximo número
  }
}

// Função para exibir um dígito no display
void displayDigit(int num) {
  // Escreve o estado de cada segmento de acordo com o mapeamento
  digitalWrite(segA, digit[num][0]);
  digitalWrite(segB, digit[num][1]);
  digitalWrite(segC, digit[num][2]);
  digitalWrite(segD, digit[num][3]);
  digitalWrite(segE, digit[num][4]);
  digitalWrite(segF, digit[num][5]);
  digitalWrite(segG, digit[num][6]);
}
```

# Modelo no Tinkercad

https://www.tinkercad.com/things/3xBWWTiMZLg-display-sete-segmentos
