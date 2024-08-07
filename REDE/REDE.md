# Evolução dos protocolos de internet e da pilha TCP/IP e IOT

# História do `TCP/IP`

A tecnologia TCP/IP foi criada para ser roteável e interligar diversos hosts. 

O conjunto de protocolos de comunicação foi desenvolvido em 1969, no Departamento de Defesa dos Estados Unidos. Ele fez parte do projeto conhecido como ARPANET que ao longo dos anos se transformou em Internet.

Um dos primeiros testes do protocolo TCP/IP ocorreu em 1975, entre a Universidade de Stanford, nos Estados Unidos, e a University College London, na Inglaterra.
Ao longo das décadas seguintes, o desenvolvimento da tecnologia se juntaria a outros avanços, como a criação do HTTP, para a formação da Internet tal qual ela é conhecida hoje: uma rede mundial de computadores trocando dados e informações de maneira incessante.

## Modelo `OSI` (Open Systems Interconnection)  e `TCP/IP` (Transmission Control Protocol/Internet Protocol)

O Modelo TCP/IP tem o mesmo objetivo do Modelo OSI, que é a de definir um modelo padrão de camadas para a implementação de camadas na arquitetura da rede. 

![alt text](image.png)

![alt text](image-1.png)

### `A Camada de Aplicação`

A camada de aplicação refere-se aos programas e protocolos que o TCP/IP deve utilizar para iniciar a transmissão de dados.

Fazendo um paralelo com um serviço postal, a camada de aplicação seria o momento de escolher qual serviço você quer utilizar dependendo do elemento que deseja enviar. Por exemplo, você pode contratar os serviços dos Correios para enviar um telegrama ou uma transportadora para enviar uma caixa.

No universo digital não é diferente: um navegador de Internet pode utilizar protocolos como o HTTP e o HTTPS para realizar a comunicação a partir das URLs. Enquanto isso, um cliente de transferência de arquivos, como o FileZilla, utiliza o protocolo FTP. Já um serviço de email geralmente utiliza o protocolo SMTP.

Em outras palavras, a camada de aplicação existe para que o TCP/IP defina qual o tipo ou finalidade daquela transmissão de dados específica, seja ela o carregamento de um site, o upload de arquivo ou o envio de um email, por exemplo. A partir desta definição, o processo é encaminhado para as camadas seguintes.

### `Camada de transporte`

A camada de transporte refere-se ao Protocolo de Controle de Transmissão (TCP) da sigla TCP/IP. Ela é que define como os dados serão transmitidos entre as duas partes do processo cliente/servidor.

A camada de transporte seria a preparação do seu pacote para envio: o serviço define qual meio de transporte será utilizado e como o pacote será embalado para que chegue no seu destino intacto, entre outras medidas.

Para isso ela estabelece os canais de comunicação de transferência de dados, todos eles independentes dos hosts e responsáveis por garantir que cada byte que compõe os dados em questão serão transmitidos de forma íntegra, os dados são divididos em pacotes e numerados, criando uma sequência lógica que será verificada nas camadas seguintes para garantir que o processo seja concluído, definindo para onde os dados devem ser enviados e a que taxa essa transferência deve ser realizada.

##### `Portas TCP`

Para realizar esse processo, o TCP usa as chamadas portas, elementos numéricos que identificam os pontos de uma transferência de dados. As portas são sempre utilizadas em conjunto com um endereço de rede (como o endereço IP, sobre o qual falaremos mais abaixo).

Por serem identificadas numericamente num padrão de 16 bits, as portas vão do 0 até o 65535. Alguns números de portas são universalmente utilizados para determinados processos. Por exemplo:

Porta 20: transferência de dados via FTP
Porta 21: controle de comando FTP
Porta 22: login SSH (Secure Shell)
Porta 25: recebimento de emails via SMTP
Porta 53: serviço de DNS (Sistema de Nomes de Domínio)
Porta 80: transferências HTTP
Porta 443: transferências HTTPS (via TLS/SSL)
Vale notar que, embora o TCP seja o protocolo mais utilizado na camada de transporte, outros protocolos também podem ser utilizados. Podem ser citados como exemplo o SCTP (Stream Control Transmission Protocol) e o UDP (User Datagram Protocol).

### `A Camada de Rede (IP)`

No paralelo com o serviço postal, a camada de rede — também conhecida como camada de Internet — é responsável por dar o sinal verde final para o envio do seu pacote. 

Em linguagem mais técnica, essa camada lida com as interfaces dos hosts e transforma os pacotes de dados em datagramas. Cada datagrama possui dois componentes principais: um cabeçalho (header), contendo o endereço IP da origem e do destino e outros dados relevantes, e a carga útil (payload), que contém os dados em si que estão sendo enviados.

Aqui, vale fazer a distinção entre IP e endereço IP. IP, ou Protocolo de Internet, é o conjunto de regras e definições que permite que os dados sejam enviados entre computadores e servidores conectados ao redor do mundo. 

O endereço IP, por outro lado, é um elemento específico, utilizado para identificar numericamente cada host envolvido no processo de transferência — garantindo, desta forma, que os dados saiam do lugar certo e cheguem ao lugar certo, da mesma forma que um endereço doméstico para uma transportadora.

Além do protocolo IP, a camada de rede também utiliza o protocolo ICMP (Protocolo de Mensagens de Controle da Internet), responsável por fornecer relatórios de erros às fontes de envio de dados. Desta forma, caso haja algum problema na comunicação entre os hosts, a mensagem definirá qual foi o erro ocorrido e ajustes poderão ser realizados para completar o processo de maneira bem-sucedida.

### `A Camada de Interface`

Por fim, a camada de interface — também chamada de camada de enlace de dados ou ligação de dados — lida com a transferência em si dos dados entre os hosts. Ou seja, finalizando o paralelo com o serviço postal, trata-se do envio de fato do seu pacote ao destinatário.
A camada de interface é responsável, entre outros aspectos, por definir como os dados serão transmitidos, seja por uma conexão cabeada (como Ethernet, por exemplo) ou sem fios (como uma rede Wi-Fi).

" Leituras Sugeridas
Como Configurar um Firewall no Ubuntu com UFW
Como Configurar Port Forwarding em um Servidor Minecraft no Windows, macOS e Linux
O que é SSL / TLS e HTTPS? "

### Datagrama IP

A RFC 1594 define o termo datagrama da seguinte forma: “Uma entidade independente e autocontida de dados que transporta informações suficientes para serem roteadas da origem ao computador de destino sem depender de trocas anteriores entre este computador de origem e de destino e a rede de transporte”.

Um datagrama é uma unidade de transferência básica associada a uma rede de comutação de pacotes. Os datagramas são normalmente estruturados em seções de cabeçalho e carga útil. Os datagramas fornecem um serviço de comunicação sem conexão em uma rede comutada por pacotes. A entrega, a hora de chegada e a ordem de chegada dos datagramas não precisam ser garantidas pela rede. Cada datagrama possui dois componentes, um cabeçalho e uma carga útil de dados. O cabeçalho contém todas as informações suficientes para o roteamento do equipamento de origem ao destino e a carga útil são os dados a serem transportados. O datagrama IP não é orientada a conexão, sem confirmação de entrega ou recebimento, não trata erros. São 6 linhas cada com 32 bits.

![alt text](image-2.png)

![alt text](image-3.png)

`Primeira linha do datagrama`

`Version`

Caso seja IPV4 ficaria quatro em binário (0100) .Utilizndo o código BCD 8421 (de Binary-coded decimal 8421). Os valores 8421 são respectivamente os valores de 2 elevado ao valor de sua posição (3,2,1,0)

![alt text](image-4.png)

`IHL (Internet Header language)`

É o tamanho dp cabeçalho e possui tamanho variável. Options nem é utilizado.

![alt text](image-5.png)

`Type of service (TOS)`

Trata a qualidade do serviço (QoS - Quality of service) D - delay, T - trucut, R - reliability 
É possível fazer mais não funciona a contento.

![alt text](image-6.png)

![alt text](image-7.png)

![alt text](image-8.png)

`Total Length`

É possível descobrir o tamanho do cabeçalho e começa a área de dados.

![alt text](image-9.png)

`Segunda linha do datagrama`

`Identification`

O campo Identification num datagrama IP é um inteiro que identifica o datagrama. Este campo é muito importante porque, quando um gateway fragmenta um datagrama, ele copia a maioria dos campos do cabeçalho do datagrama.
Quando um datagrama é criado o emissor o identifica com um número de identificação (Identification), assim como um endereço IP de origem e destino. Para cada novo datagrama criado o emissor gera uma nova identificação incrementando o valor deste campo.

![alt text](image-10.png)

`Flags`

`DF` - Don't fragment (não fragmentar) - Não permite que um datagrama seja fragmentado (ex.: o destino é incapaz de remontar o datagrama. MF - More fragments (mais fragmentos) - indica que mais fragmentos estão sendo esperados para a remontagem do pacote. O valor 0 não posso fragmentar o datagrama se for 1 sim.

![alt text](image-11.png)
`Fragment ofset`

`MF` - More Fragment (mais fragmento)

![alt text](image-12.png)

![alt text](image-13.png)

`Time to Live (TTL)`
Tempo de vida do pacote, seu campo de 8 bits. Evitar que pacotes fiquem vagando em loops, ele possui 255, número máximo de máquinas para chegar ao destino, quase esse valor de 255 chegue a 0, o pacote é descartado.

![alt text](image-14.png)

![alt text](image-15.png)

Fragmentação e remontagem de IPv4
Embora o comprimento máximo de um datagrama IPv4 seja 65535, a maioria dos links de transmissão impõe um limite menor de comprimento máximo do pacote, chamado MTU. O valor de MTU depende do link de transmissão.

`Protocol`

Para quem será entregue os dados, os mais utilizados são TCP, UDP e ICMP

![alt text](image-16.png)

`Header Checksum`

Soma de verificação do cabeçalho, através dessa verificação o roteador sabe se é para ele a informação. O TTL faz um decremento e atualiza o Checkum.

`Source Address`

É o endereço do IP de origem 32 bits IPV4.

![alt text](image-17.png)

`Destination Address`

É o endereço do IP de destino 32 bits IPV4.

![alt text](image-18.png)

`Optios`

É opcional

![alt text](image-19.png)

![alt text](image-20.png)

![alt text](image-21.png)

Não é muito fácil nem usual traçar a rota.

![alt text](image-22.png)

![alt text](image-23.png)

Na prática a maquina A quer se comunicar com o máquinna D.

![alt text](image-24.png)

![alt text](image-25.png)

![alt text](image-26.png)

`ARP (Address Resolution Protocol)`

É um protocolo que permite que os dispositivos numa rede determinem o endereço físico de outro dispositivo com base no seu endereço IP. O endereço físico, também conhecido como endereço de controlo de acesso à mídia (MAC), é um endereço fixo da máquina, enquanto o endereço IP é um endereço de protocolo de Internet (IP) que está constantemente a mudar. Como estes dois endereços diferem em comprimento e formato, o ARP é essencial para permitir que computadores e outros dispositivos se comuniquem através de uma rede. O ARP é utilizado somente em redes internas.

![alt text](image-27.png)

![alt text](image-28.png)

## Bibliografia

https://www.hostinger.com.br/tutoriais/tcp-ip#Historia_do_TCPIP

https://www.uniaogeek.com.br/arquitetura-de-redes-tcpip/

https://pt.wikipedia.org/wiki/Datagrama#:~:text=de%20itens%20identificados.-,Defini%C3%A7%C3%A3o,e%20a%20rede%20de%20transporte%E2%80%9D.

https://www.youtube.com/watch?v=2O-zMcYe-RE