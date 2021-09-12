## Projeto 1: 2019-2


### Parceiro Acadêmico
Fatec Prof. Jessen Vidal (proposta realizada pelo docente responsável pela disciplina que ordenou o projeto)


### Visão do Projeto

A proposta do projeto neste semestre foi aberta. A classe pôde escolher e sugerir propostas de soluções desde que na implementação do projeto, a integração com alguma placa gerenciadora de dispositivos periféricos (exemplo: Arduino) fosse realizada.
O projeto realizado pelo meu grupo teve a seguinte proposta:

Desenvolver um sistema de Vending Machine, criando a tela de interface com o cliente, onde seria realizada a seleção e compra de produtos. Após este processo, o aplicativo desenvolvido deveria enviar um sinal ao hardware da máquina de vendas, que liberaria o acesso ao produto adquirido. Fora destes momentos, o acesso aos produtos deveria permanecer restrito, trancado pelos dispositivos.


### Tecnologias adotadas na solução

#### Interface com o usuário - App Inventor

A interface com o cliente foi realizada através de uma tela de smartphone, que simulava o display da vending machine. Um aplicativo desenvolvido através da ferramenta App Inventor, para o sistema operacional Android, provia ao usuário final as telas de seleção de produtos e finalização de compra.

A programação nesta plataforma se dá em blocos. Diversos recursos de linguagens de programação tradicionais (condições, loops e operações) em blocos ilustrativos, que tornam a construção de rotinas e lógicas visuais e, desta forma, mais intuitivas.

Por conta desta natureza da ferramenta - [App Inventor](https://appinventor.mit.edu/) - não há código fonte a ser disponibilizado.

#### Arduino 

O funcionamento da vending machine foi construído utilizando o Arduino, com a placa central e dois periféricos. Um servo motor e um módulo Bluetooth HC-05.

O Arduino é uma plataforma de prototipagem. Usualmente, ao falar em "Arduino", nos remetemos a placa central que liga diversos dispositivos que são interligados por ela. Entretanto, o Arduino como plataforma fornece diversos recursos (comunicação Serial, alimentação elétrica, periféricos da propria plataforma, etc) que facilitam a prototipagem de sistemas embarcados, que podem servir às mais diversas finalidades específicas.

O Servo Motor ou o módulo HC-05, dentre outros, fazem parte desta plataforma. Estes dispositivos em conjunto possibilitam a prototipagem de sistemas embarcados. E, neste exemplo, de um que seria responsável apenas por receber instruções para abrir e trancar uma porta.


##### Módulo Bluetooth HC-05

A conexão entre o app Android criado e o sistema da máquina de vendas foi realizada via Bluetooth. Para isso, utilizamos o módulo Bluetooth HC-05.

O módulo HC-05 é um dispositivo serial de comunicação Bluetooth. [ver mais](https://www.gme.cz/data/attachments/dsh.772-148.1.pdf)

Este módulo possui 4 pinos principais de conexão com a placa Arduino. Dois pinos são responsáveis pela comunicação serial (RXD e TXD), e dois pinos de alimentação (VCC) e o que fecha o curto para garantir a corrente elétrica, o GND. 

Na prática, a conexão destes pinos fica da seguinte forma:

![image](https://user-images.githubusercontent.com/45850297/132968177-13fa8c56-ff56-4bd2-9ccc-b75e205529e5.png)

O módulo possui versões 5V e 3.3V. Como a alimentação padrão mais próxima no Arduino é de 5V, caso o módulo seja de 3.3V, é necessário utilizar resistências para evitar danos elétricos ao módulo. No caso atual, este preparo não foi necessário, pois utilizamos uma versão 5V.

Abaixo, temos a código utilizado na placa Arduino para realizar a conexão com o módulo Bluetooth. Definimos o módulo com o nome de "Serial", aplicando os pinos 10 e 11 para conexão serial, nos pinos RX e TX, respectivamente.

O comando de 90 bytes foi definido como padrão para a instrução de abrir a porta para liberação de produtos. Na função "void loop()", podemos ver que a variável "comando" recebe o retorno da leitura do que foi recebido da porta Serial.

```code
#include <Servo.h> 
#include <SoftwareSerial.h>
#define servo 6 // Definindo pino do servo
Servo myservo;  // Criação do objeto de criação do Servo Motor
char comando;    // Variável de controle da angulação
SoftwareSerial Serial(10, 11) // Módulo bluetooth

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

Os dispositivos internos da máquina eram compostos de uma placa Arduino e um Servo Motor. Este último era responsável por abrir a porta que liberava acesso ao produto selecionado e trancá-lo novamente após isso.

##### Servo Motor

O servo motor é um periférico que pode ser utilizado no Arduino. Ele possibilita a geração de movimentos rotacionais controlados.
Por exemplo: com um servo motor, podemos realizar rotações limitadas, porém com maior precisão. Suas versões mais comuns não permitem uma rotação contínua, como uma roda de carro, por exemplo.

Entretanto, caso seja necessário realizar rotações específicas, determinando até mesmo a quantidade de graus que o movimento deve ter, o servo motor é o ideal para esta demanda. Como necessitávamos de uma tranca automática, ele atendeu à necessidade do projeto.

A montagem deste dispositivo é similar a do módulo HC-05. Temos uma demonstração de como ela ficaria na prática:

![image](https://user-images.githubusercontent.com/45850297/132969607-4f0f0591-94f9-4d43-9529-ef4265b4aa02.png)

Como pode ser visto, a alimentação ainda é realizada conectando as saídas de 5V e GND, que fecham o circuito de alimentação, e um pino é escolhido para recebimento das instruções de rotação. Neste exemplo, o 6.

No código exibido no item anterior, podemos observar que o servo com seu respectivo pino, e durante a rotina ele recebe o valor de bytes recebidos pelo módulo bluetooth (90). 90º é a posição em que a tranca da vending machine estaria liberada.

### Contribuições pessoais

Fui responsável pela programação do script que gerenciava a placa Arduino, Servo Motor, e o módulo Bluetooth, que já foi citado em um item anterior.


### Aprendizados Efetivos HS

Neste projeto obtive meu primeiro contato com documentações. Esta experiência me ensinou a buscar informações nas fontes primárias, que são as publicações técnicas geralmente realizadas pelos próprios criadores e responsáveis pelas mais diversas tecnologias. Este aprendizado é de grande valia até hoje em minha trajetória acadêmica e profissional.

Além disso, o desafio de observar um problema prático e ter como tarefa criar uma solução até então inexistente naquele contexto específico, exercitou habilidades importantes para todo analista e desenvolvedor de software.

No mais, temos os pontos específicos abaixo:

- Integração Bluetooth entre dispositivos e placa Arduino: Sei fazer com autonomia

- Integração entre placa Arduino e dispositivos periféricos: Sei fazer com autonomia

- Desenvolvimento de scripts em C: Sei fazer com autonomia
