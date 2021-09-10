## Projeto 1: 2019-2


### Parceiro Acadêmico
Fatec Prof. Jessen Vidal (proposta realizada pelo docente responsável pela disciplina que ordenou o projeto)


### Visão do Projeto (Equipe)

A proposta do projeto neste semestre foi aberta. A classe pôde escolher e sugerir propostas de soluções desde que na implementação do projeto, a integração com alguma placa gerenciadora de dispositivos periféricos (exemplo: Arduino) fosse realizada.
O projeto realizado pelo meu grupo teve a seguinte proposta:

Desenvolver um sistema de Vending Machine, criando a tela de interface com o cliente, onde seria realizada a seleção e compra de produtos. Após este processo, o aplicativo desenvolvido deveria enviar um sinal ao hardware da máquina de vendas, que liberaria o acesso ao produto adquirido. Fora destes momentos, o acesso aos produtos deveria permanecer restrito, trancado pelos dispositivos.


### Tecnologias adotadas na solução (Equipe)

A interface com o cliente foi realizada através de uma tela de smartphone, que simulava o display da vending machine. Um aplicativo desenvolvido através da ferramenta App Inventor provia ao usuário final as telas de seleção de produtos e finalização de compra.

Por conta da natureza da ferramenta de desenvolvimento do app, o [App Inventor](https://appinventor.mit.edu/), não há código fonte a ser disponibilizado.

Utilizamos a tecnologia Bluetooth como meio de comunicação entre o display que fica em contato com o cliente (smartphone) e o hardware da máquina de vendas que libera o acesso ao produto.

Os dispositivos internos da máquina eram compostos de uma placa Arduino e um Servo Motor. Este último era responsável por abrir a porta que liberava acesso ao produto selecionado e trancá-la novamente após isso.

A placa Arduino foi programada na linguagem de programação C.


### Contribuições pessoais

Fui responsável pela programação do software que gerenciava a placa Arduino e o Servo Motor, e que também realizava a integração com o app mobile via Bluetooth. 
Desenvolvi um simples código em C que, ao receber um comando via Bluetooth, ordenava uma rotação específica para o Servo Motor, que abria a porta para disponibilizar o produto.


A base do código criado para esta ação descrita acima pode ser vista a seguir:

```bash
#include <Servo.h> 
#include <SoftwareSerial.h>
#define servo 9 // Definindo pino do servo
Servo myservo;  // Criação do objeto de criação do Servo Motor
char comando;    // Variável de controle da angulação

void setup() {
  myservo.attach(servo);
  Serial.begin(9600); 
  myservo.write(0); // Posição trancada
}

void loop() {
  comando = Serial.read();  // Varíavel recebendo o valor do Módulo Bluetooth
  if (comando == 90){       // Verificando se houve sinal recebido
    myservo.write(comando); // Definindo o valor com base no comando recebido pelo módulo, posição aberta
    delay (5000);           // Pausa para disposição do produto
    myservo.write(0);       // Posição trancada
    }
}
```

### Aprendizados Efetivos HS (Individual)

Neste projeto obtive meu primeiro contato com documentações. Esta experiência me ensinou a buscar informações nas fontes primárias, que são as publicações técnicas geralmente realizadas pelos próprios criadores e responsáveis pelas mais diversas tecnologias. Este aprendizado é de grande valia até hoje em minha trajetória acadêmica e profissional.

Além disso, o desafio de observar um problema prático e ter como tarefa criar uma solução até então inexistente naquele contexto específico, exercitou habilidades importantes para todo analista e desenvolvedor de software.

No mais, temos os pontos específicos abaixo:

- Integração Bluetooth entre dispositivos e placa Arduino: Sei fazer com autonomia

- Integração entre placa Arduino e dispositivos periféricos: Sei fazer com autonomia

- Desenvolvimento de scripts em C: Sei fazer com autonomia
