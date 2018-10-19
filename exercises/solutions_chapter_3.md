#### Questão 3 – Considere uma conexão TCP entre o hospedeiro A e o hospedeiro B. Suponha que os segmentos TCP que trafegam do hospedeiro A para o hospedeiro B tenham número de porta da fonte x e número de porta do destino y. Quais são os números de porta da fonte e do destino para os segmentos que trafegam do hospedeiro B para o hospedeiro A? 

Porta fonte será y e porta destino será x.

#### Questão 4 – Descreva por que um desenvolvedor de aplicação pode escolher rodar uma aplicação sobre UDP em vez de sobre TCP. 

UDP oferece muito menos delay, uma vez que nao retransmite pacotes e não há necessidade de estabelecimento de uma conexão. Outra vantagem é que requer menos processamento dos sistemas finais e também é um protocolo muito mais simples.

#### Questão 5 – Por que o tráfego de voz e de vídeo é frequentemente enviado por meio do UDP e não do TCP na Internet de hoje? (Dica: A resposta que procuramos não tem nenhuma relação com o mecanismo de controle de congestionamento no TCP.) 

Pois estas são aplicações sensíveis ao atraso, mas não tão sensíveis a perda de dados, logo o menor delay do UDP é mais atraente que a entrega garantida do TCP.

#### Questão 6 – É possível que uma aplicação desfrute de transferência confiável de dados mesmo quando roda sobre UDP? Caso a resposta seja afirmativa, como isso acontece? 

Sim, é possível. Entretanto a entrega garantida passa a ser controlada pela camada de aplicação.

#### Questão 7 – Suponha que um processo no Computador C possua um socket UDP com número de porta 6789 e que o Computador A e o Computador B, individualmente, enviem um segmento UDP ao Computador C com número de porta de destino 6789. Esses dois segmentos serão encaminhados para o mesmo socket no Computador C? Se sim, como o processo no Computador C saberá que esses dois segmentos vieram de dois computadores diferentes? 

Sim. O host C terá essa informação através dos endereços IPs dos segmentos fornecidos pelo datagrama IP.

#### Questão 8 – Suponha que um servidor da Web seja executado no Computador C na porta 80. Esse servidor utiliza conexões continuas e, no momento, está recebendo solicitações de dois Computadores diferentes, A e B. Todas as solicitações estão sendo enviadas através do mesmo socket no Computador C? Se eles estão passando por diferentes sockets, dois desses sockets possuem porta 80? Discuta e explique. 

Não, no caso de conexões persistentes as conexões são enviadas para sockets diferentes. Sim, possuem a porta 80, mas seus identificadores são formados por 4 elementos: IP da fonte, porta fonte, IP destino e porta destino. Ao passar para a aplicação, fica implícito no id do socket o IP de origem.

#### Questão 9 – Nos nossos protocolos rdt, por que precisamos introduzir números de sequência?

Os numeros de sequencia foram introduzidos para que o receptor saiba se um pacote é uma retransmissao ou novos dados.

#### Questão 10 – Nos nossos protocolos rdt, por que precisamos introduzir temporizadores? 

Temporizadores foram introduzidos para que o remetente pudesse identificar a perda ou de um pacote ou de um ACK.

#### Questão 11 – Suponha que o atraso de viagem de ida e volta entre o emissor e o receptor seja constante e conhecido para o emissor. Ainda seria necessário um temporizador no protocolo rdt 3.0, supondo que os pacotes podem ser perdidos? Explique. 

Sim, pois para saber se um pacote foi perdido o emissor precisa ter contabilizado quanto tempo se passou desde o envio. A unica difereça é que saberiamos com certeza se o pacote foi perdido, pois no mundo real quando o timer acaba ainda existe a possibilidade de o RTT estar sendo maior devido o congestionemento da rede.

#### Questão 12 – Visite o applet Go-Back-N Java no Companion siteWeb. a) A fonte enviou cinco pacotes e depois interrompeu a animação antes que qualquer um dos cinco pacotes chegassem ao destino. Então, elimine o primeiro pacote e reinicie a animação. Descreva o que acontece. b) Repita o experimento, mas agora deixe o primeiro pacote chegar ao destino e elimine o primeiro reconhecimento. Descreva novamente o que acontece. c) Por fim, tente enviar seis pacotes. O que acontece? 

a) O receptor reconhece apenas o ultimo pacote recebido corretamente, o que faz com que o emissor retransmita todos os 5 pacotes.
b) O emissor retransmite os 5 pacotes.
c) São enviados normalmente.

#### Questão 13 – Repita a questão 12, mas agora com o applet Selective Repeat Java. O que difere o Selective Repeat do Go-Back-N? 

a) Apenas o primeiro pacote foi retransmitido.
b) O emissor retransmite o pacote com ACK perdido.
c) São enviados normalmente.

#### Questão 14 – Verdadeiro ou falso: 
- a) O hospedeiro A está enviando ao hospedeiro B um arquivo grande por uma conexão TCP. Suponha que o hospedeiro B não tenha dados para enviar para o hospedeiro A. O hospedeiro B não enviará reconhecimentos para o hospedeiro A porque ele não pode dar carona aos reconhecimentos dos dados. Falso
- b) O tamanho de rwnd do TCP nunca muda enquanto dura a conexão. Falso
- c) Suponha que o hospedeiro A esteja enviando ao hospedeiro B um arquivo grande por uma conexão TCP. O número de bytes não reconhecidos que o hospedeiro A envia não pode exceder o tamanho do buffer de recepção. Verdadeiro
- d) Imagine que o hospedeiro A esteja enviando ao hospedeiro B um arquivo grande por uma conexão TCP. Se o número de sequência por um segmento dessa conexão for m, então o número de sequência para o segmento subsequente será necessariamente m+1. Falso
- e) O segmento TCP tem um campo em seu cabeçalho para Rwnd. Verdadeiro
- f) Suponha que o último SampleRTT de uma conexão TCP seja igual a 1 segundo. Então, o valor corrente de Timeout Interval para a conexão será necessariamente ajustado para um valor >= 1 segundo. Falso
- g) Imagine que a hospedeiro A envie ao hospedeiro B, por uma conexão TCP, um segmento com o número de sequência 38 e 4 bytes de dados. Nesse segmento, o número de reconhecimento será necessariamente 42. Falso

#### Questão 15 – Suponha que o hospedeiro A envie dois segmentos TCP um atrás do outro ao hospedeiro B sobre uma conexão TCP. O primeiro segmento tem número de sequência 90 e o segundo, número de sequência 110. a) Quantos dados tem o primeiro segmento? b) Suponha que o primeiro segmento seja perdido, mas o segundo chegue a B. No reconhecimento que B envia a A, qual será o número de reconhecimento? 

a) 20 bytes
b) ACK = 90.

#### Questão 16 – Considere o exemplo do Telnet discutido na Sessão 3.5. Alguns segundos após o usuário digitar a letra `C`, ele digitará a letra `R`. Depois disso, quantos segmentos serão enviados e o que será colocado nos campos de número de sequência e de reconhecimento dos segmentos? 

3 segmentos; Seq = 43, Ack = 80, dados = 'R' -> Seq = 80, Ack = 44, dados = 'R' -> Seq = 44, Ack = 81;

#### Questão 17 – Suponha que duas conexões TCP estejam presentes em algum enlace congestionado de velocidade R bps. Ambas as conexões têm um arquivo imenso para enviar (na mesma direção, pelo enlace congestionado). As transmissões dos arquivos começam exatamente ao mesmo tempo. Qual é a velocidade de transmissão que o TCP gostaria de dar a cada uma das conexões? 

R/2 bps

#### Questão 18 – Verdadeiro ou falso: considere o controle de congestionamento no TCP. Quando um temporizador expira no remente, o “valor de ssthresh” é ajustado para a metade de seu valor anterior. 

Falso.

#### Problema 3 – O UDP e o TCP usam complementos de 1 para suas somas de verificação. Suponha que você tenha as seguintes três palavras de 8 bits: 01010011, 01010100 e 01110100. Qual é o complemento de 1 para as somas dessas palavras? (Note que, embora o UDP e o TCP usem palavras de 16 bits no cálculo da soma de verificação, nesse problema solicitamos que você considere somas de 8 bits). Mostre todo o trabalho. Por que o UDP toma o complemento de 1 da soma, isto é, por que não toma apenas a soma? Com o esquema de complemento de 1, como o destinatário detecta erros? É possível que um erro de 1 bit passe despercebido? E um erro de 2 bits? 

  01010011
+ 01010100
----------
  10100111

  10100111
+ 01110100
----------
  00011011
+        1
----------
  00011100

~ 00011100
----------
  11100011

Deve somar as palavras e o checksum e o resultado deve ser 11111111. Caso seja diferente, há erro.
1 bit nao será despercebido.
2 bits pode ser despercebido.

#### Problema 4 – a) Suponha que você tenha os seguintes bytes: 01011100 e 01010110. Qual é o complemento da soma desses 2 bytes? b) Suponha que você tenha os seguintes bytes: 11011010 e 00110110. Qual é o complemento de 1 da soma desses 2 bytes? c) Para os bytes do item (a), dê um exemplo em que um bit é invertido em cada um dos 2 bytes e, mesmo assim, o complemento de um não muda. 

- a)

  01011100
+ 01010110
----------
  10110010

- b)

  11011010
+ 00110110
----------
  00010000  
+        1 
----------
  00010001

- c) 01011110 e 01010100

#### Problema 5 – Suponha que o receptor UDP calcule a soma de verificação da Internet para o segmento UDP recebido e encontro que essa soma coincide com o valor transportado no campo da soma de verificação. O receptor pode estar absolutamente certo de que não ocorreu nenhum erro de bit? Explique.

Não, o receptor não pode ter certeza absoluta de que nenhum erro tenha ocorrido. Isso ocorre devido à maneira como a soma de verificação do pacote é calculada. Se o bits correspondentes (que seriam adicionados juntos) de duas palavras de 16 bits no pacote foram 0 e 1, em seguida, mesmo que estes sejam invertidos para 1 e 0, respectivamente, a soma ainda permanece como mesmo. Iste significa que a soma de verificação será verificada mesmo se houver erro de transmissão.

#### Problema 7 – No protocolo rdt3.0, os pacotes ACK que fluem do destinatário ao remetente não têm números de sequência (embora tenham um campo de ACK que contém o número de sequência do pacote que estão reconhecendo). Por que nossos pacotes ACK não requerem números de sequência? 

Nós vimos que o remetente precisa de números de seqüência para que o receptor possa dizer se um pacote de dados é um duplicata de um pacote de dados já recebido. No caso de ACKs, o remetente não precisa dessa informação (ou seja, um número de seqüência em um ACK) para informar a detecção de um ACK duplicado. Um ACK duplicado é óbvio para o receptor rdt3.0, desde quando ele recebeu o ACK original, ele fez a transição para o próximo estado. O ACK duplicado não é o ACK que o remetente precisa e, portanto, é ignorado pelo remetente rdt3.0.

####  Problema 21 – Considere os protocolos GBN e SR. Suponha que o espaço de números de sequência seja de tamanho k. Qual será o maior tamanho de janela permissível que evitará que ocorram problemas como os da Figura 3.27 para cada um desses protocolos? 

GBN: k - 1
SR: (k + 1)/2

####  Problema 22 – Responda verdadeiro ou falso `as seguintes perguntas e justifique resumidamente sua resposta: a) Com o protocolo SR, é possível o remetente receber um ACK para um pacote que caia fora de sua janela corrente. b) Com o GBN, é possível o remetente receber um ACK para um pacote que caia fora de sua janela corrente. c) O protocolo bit alternante é o mesmo que o protocolo SR com janela do remetente e do destinatário de tamanho 1. d) O protocolo bit alternante é o mesmo que o protocolo GBN com janela do remetente e do destinatário de tamanho 1. 

a) V
b) V
c) V
d) V

####  Problema 23 – Dissemos que uma aplicação pode escolher o UDP para um protocolo de transporte pois ele oferece um controle de aplicação melhor (do que o TCP) de quais dados são enviados em um segmento e quando isso ocorre. a) Por que uma aplicação possui mais controle de quais dados são enviados em um segmento? b) Por que uma aplicação possui mais controle de quando o segmento é enviado? 

a) Pois UDP não quebra as mensagens como o TCP faz. Não há MSS para o UDP.
b) Pois não haverá controle de fluxo nem congestionamento.

####  Problema 25 – Os hospedeiros A e B estão se comunicando por meio de uma conexão TCP, e o hospedeiro B já recebeu de A todos os bytes até o byte 126. Suponha que o Hospedeiro A envie, então, dois segmentos para o Hospedeiro B sucessivamente. O primeiro e o segundo segmentos contêm 70 e 50 bytes de dados, respectivamente. No primeiro segmento, o número de sequência é 127, o número de porta de partida é 302, e o número de porta de destino é 80. O hospedeiro B envia um reconhecimento ao receber um segmento do hospedeiro A. a) No segundo segmento enviado do Hospedeiro A para N, quais são o número de sequência, a porta de partida e a porta de destino? b) Se o primeiro segmento chegar antes do segundo, no reconhecimento do primeiro segmento que chegar, qual é o número do reconhecimento, da porta de partida e da porta de destino? c) Se o segundo segmento chegar antes do primeiro, no reconhecimento do primeiro segmento que chegar, qual é o número do reconhecimento? d) Suponha que dois segmentos enviados por A cheguem em ordem a B. O primeiro reconhecimento é perdido e o segundo chega após o primeiro intervalo do esgotamento de temporização. Elabore um diagrama de temporização, mostrando esses segmentos, e todos os outros, e os reconhecimentos enviados. (Admita que não haja nenhuma perda de pacote adicional.) Para cada segmento de seu desenho, apresente o número de sequência e o número de bytes de dados; para cada reconhecimento adicionado por você, apresente o número do reconhecimento. 


####  Problema 33 – Na Seção 3.5.4 vimos que o TCP espera até receber três ACKs duplicados antes de realizar uma retransmissão rápida. Na sua opinião, por que os projetistas do TCP preferiram não realizar uma retransmissão rápida após ser recebido o primeiro ACK duplicado para um segmento? 

A resposta está no RFC 2001: Como o TCP nao sabe se um ACK duplicado é causado por um pacote perdido ou desordenação é melhor esperar por um numero maior de bytes duplicados. Três ou mais é um forte indicativo de perda de pacote.

####  Problema 37 – Considere a Figura 3.58 Admitindo-se que TCP Reno é o protocolo que experimenta o comportamento mostrado no gráfico, responda `as seguintes perguntas. Em todos os casos você deverá apresentar uma justificativa resumida para sua resposta. a) Quais os intervalos de tempo em que a partida lenta do TCP está em execução? b) Quais os intervalos de tempo em que a prevenção de congestionamento do TCP está em execução? c) Após a 16ª rodada de transmissão, a perda de segmento será detectada por três ACKs duplicados ou por um esgotamento de temporização? d) Após a 22ª rodada de transmissão, a perda de segmento será detectada por três ACKs duplicados ou por um esgotamento de temporização? e) Qual é o valor inicial de ssthresh na primeira rodada de transmissão? f) Qual é o valor inicial de ssthresh na 18ª rodada de transmissão? g) Qual é o valor de ssthresh na 4ª rodada de transmissão? h) Durante qual rodada de transmissão é enviado o 70º segmento? i) Admitindo-se que uma perda de pacote será detectada após 26ª rodada pelo reconhecimento de três ACKs duplicados, quais serão os valores do tamanho da janela de congestionamento e de ssthresh? j) Suponha que o TCP Tahoe seja usado (em vez do TCP Reno) e que ACKs duplicados triplos sejam recebidos na 16ª sessão. Quais são o ssthresh e o tamanho da janela de congestionamento na 19ª sessão? k) Suponha novamente que o TCP Tahoe seja usado, e que exista um evento de esgotamento de temporização na 22ª sessão. Quantos pacotes foram enviados da 17ª sessão até a 22ª.

- a) [1,6] e [23,26]
- b) [6,16] e [17,22]
- c) 3 ACKs duplicados
- d) Esgotamento
- e) 32
- f) 21
- g) 13
- h) 7ª rodada
- i) 4
- j) 
- k) 