#### Qual é a diferença entre um hospedeiro e um sistema final? Cite os tipos de sistemas finais. Um servidor Web é um sistema final?

Não há diferença entre os termos host e end systems, ou seja, são sinônimos. Sistemas finais podem ser subdivididos entre clients e servers. Sim, um servidor Web é um sistema final pois está na periferia da rede.

#### Questão 3 – O que é um programa cliente? O que é um programa servidor? Um programa servidor requisita e recebe serviços de um programa cliente?

Um programa cliente é um programa que funciona em um sistema final, que solicita e recebe um serviço de um programa servidor. Um programa servidor é um programa que armazena, localiza e envia arquivos e serviços para clientes. Na arquitetura cliente-servidor o servidor não requisita nem recebe serviços de clientes, e o seu papel é receber e processar requisições de clientes.

#### Questão 7 – Qual é a taxa de transmissão de LANs Ehternet? Para uma dada taxa de transmissão, cada usuário da LAN pode transmitir continuamente a essa taxa?

O acesso à Ethernet normalmente possui 100 Mbps enquanto servidores possuem um acesso de 1 Gbps a 10 Gbps.

#### Questão 8 – Cite alguns meios físicos utilizados para instalar a Ethernet.

Par de fios de cobre trançado, cabo coaxial e fibra ótica.

#### Questão 11 – Qual é a vantagem de uma rede de comutação de circuitos em relação a uma de comutação de pacotes? Quais são as vantagens da TDM sobre a FDM em uma rede de comutação de circuitos?

A vantagem é que a taxa de transmissão é garantida, uma vez que os recursos necessários para a conexão estão reservados ao longo do caminho. A vantagem da TDM sobre a FDM é que, por um período de tempo, cada circuito terá toda a largura de banda.

#### Questão 12 – Por que se afirma que a comutação de pacotes emprega multiplexação estatística? Compare a multiplexação estatística com a multiplexação que ocorre em TDM.

Pois nela a alocação ocorre por demanda, logo, a capacidade de transmissão do enlace será compartilhada pacote por pacote somente por usuarios que tenham pacotes que precisem ser transmitidos pelo enlace. Em TDM cada circuito terá ao seu dispor toda a largura de banda em um intervalo de tempo, o que acarretará desperdício de recursos quando não houverem pacotes a serem enviados. Na multiplexação estatiística o enlace é compartilhado o tempo todo por todos que necessitem do mesmo. Ou seja, a multiplexaxção estatistica oferece o mesmo que TDM para um numero muito maior de usuarios.

#### Questão 13 – Suponha que exista exatamente um comutador de pacotes entre um computador de origem e um de destino. As taxas de transmissão entre a máquina de origem e o comutador e entre este e a máquina de destino são R1 e R2, respectivamente. Admitindo que um roteador use comutação de pacotes do tipo armazena e reenvia, qual é o atraso total fim a fim para enviar um pacote de comprimento L? (Desconsidere formação de fila, atraso de propagação e atraso de processamento).

L/R1 + L/R2

#### Questão 16 – Considere o envio de um pacote de uma máquina de origem a uma de destino por uma rota fixa. Relacione os componentes do atraso que formam o atraso fim a fim. Quais deles são constantes e quais são variáveis?

Os componentes de atraso são os atrasos de processamento, atraso de propagação, atraso de transmissao e atraso de fila. Todos são variaveis, exceto o atraso de fila que varia conforme a carga da rede.

#### Questão 18 – Quanto tempo um pacote de 1.000 bytes leva para se propagar através de um enlace de 2.500 km de distância, com uma velocidade de propagação de 2,5 * 10^8 m/s e uma taxa de transmissão de 2 Mbps? Geralmente, quanto tempo um pacote de comprimento L leva para se propagar através de um enlace de distância d, velocidade de propagação s, e taxa de transmissão de R bps? Esse atraso depende do comprimento do pacote? Esse atraso depende da taxa de transmissão?

*latencia*     = Propagação + Transmissao + Fila
*Propagação*   = Distancia / Velocidade
*Transmissao*  = Tamanho / Taxa de transmissao
*Fila*         = 0 

(2500**10^3)/(2.5**10^8) = 0.01s; d/s; Não depende; Não depende.

#### Questão 19 – Suponha que o Hospedeiro A queira enviar um arquivo grande para o Hospedeiro B. O percurso do Hospedeiro A para o Hospedeiro B possui três enlaces, de taxas R1 = 500 kbps, R2 = 2Mbps, e R3 = 1 Mbps. 

##### a) Considerando que não haja nenhum outro tráfego na rede, qual é a vazão para a transferência de arquivo?

500 kbps

##### b) Suponha que o arquivo tenha 4 milhões de bytes. Dividindo o tamanho do arquivo pela vazão, quanto tempo levará a transferência para o Hospedeiro B? 

4000000 * 8 / 500000 = 64s.

##### c) Repita os itens “a” e “b”, mas agora com R2 reduzido a 100 kbps.

100 kbps; 4000000 * 8 / 100000 = 320s.

#### Questão 23 – Quais são as cincos camadas da pilha de protocolo da Internet? Quais as principais responsabilidades de cada uma dessas camadas?

- Camada de aplicação: Onde residem as aplicações e seus protocolos. Realiza tradução de nomes. Apresenta as mensagens ao usuário final e coleta dados para enviar as mensagens.
- Camada de transporte: Mensagens passam a compor os segmentos. Essa camada deve oferecer serviços de transporte às mensagens. Pode oferecer entrega garantida, controle de fluxo e controle de congestionemento.
- Camada de rede: Segmentos passam a compor os datagramas. Essa camada movimenta de uma máquina para outra os datagramas realizando entrega a camada de transporte da maquina de destino. Oferece serviço de roteamento.
- Camada de enlace: Segmentos passam a compor os quadros. Leva os datagramas de uma maquina a outra. Prove entrega garantida entre enlaces.
- Camada física: Movimenta os bit individuais de um nó a outro.

#### Questão 24 – O que é uma mensagem de camada de aplicação? Um segmento de camada de transporte? Um datagrama de camada de rede? Um quadro de camada de enlace?

São os dados a serem transmitidos de umnó ao outro. É o encapsulamento da mensagem adcionando um cabecalho de segmento. É o encapsulamento do segmento adcionando um cabecalho de datagrama. É o encapsulamento do datagrama adcionando um cabecalho de quadro.

#### Questão 25 – Que camadas da pilha do protocolo da Internet um roteador implementa? Que camadas um comutador de camada de enlace implementa? Que camadas um sistema final implementa?

O roteadores implementam as camadas física, de enlace e de rede. Os comutadores implementa as camadas física e de enlace. Os sistemas finais implementam todas as camadas.