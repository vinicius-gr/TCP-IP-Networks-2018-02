#### Questão 3 – Qual é a diferença entre rotear e repassar (transmitir)?

Repassar é mover o pacote da porta de entrada para a porta de saída correta. Rotear determinar as rotas que o pacote fará entre a fonte e o destino.

#### Questão 7 – Discuta por que cada porta de entrada em um roteador de alta velocidade armazena uma cópia-sombra da tabela de repasse.

Com a cópia sombra a busca de rota é feita localmente, na porta de entrada, sem precisar buscar o processador de roteamento central, com isso não é criado um gargalo.

#### Questão 8 – Três tipos de elementos de comutação são discutidos na Seção 4.3. Cite e descreva brevemente cada tipo.

Comutação via memória; Comutação via bus; Comutação via rede de interconexão. Esta ultima pode repassar pacotes em paralelo desde que para diferentes portas.

#### Questão 9 – Descreva como pode ocorrer perda de pacotes em portas de entrada. Descreva como a perda de pacotes pode ser eliminada em portas de entrada (sem usar buffers infinitos).

Se a taxa de chagada de pacotes exceder a taxa comutação entao filas serão formadas nas portas de entrada. Se essa diferença persistir as filas escederão a capacidade e pacotes serão perdidos. A perda pode ser eliminada se a velocidade de comutação for pelo menos N vezes a taxa de chagada, onde N é o nro de portas de entrada.

#### Questão 10 – Descreva como pode ocorrer perda de pacotes em portas de saída.

Mesmo que as velocidades das linhas de entrada e saída sejam iguais, a perda pode ocorrer caso muitos pacotes sejam enviados para uma mesma porta de saída. Caso isso ocorra será formada uma fila e se a diferença persistir ocorrerá perda.

#### Questão 12 – Roteadores têm endereços IP? Em caso positivo, quantos endereços eles têm?

Sim, possuem um endereço para cada interface.

#### Questão 15 – Suponha que haja três roteadores entre os hospedeiros da fonte e do destino. Ignorando a fragmentação, um datagrama IP enviado do hospedeiro da fonte até o hospedeiro do destino transitará por quantas interfaces? Quantas tabelas de repasse serão indexadas para deslocar o datagrama desde a fonte até o destino?

8 interfaces e 3 tabelas de repasse.

#### Questão 16 – Suponha que uma aplicação gere blocos de 40 bytes de dados a cada 20 milissegundos e que cada bloco seja encapsulado em um segmento TCP e, em seguida, em um datagrama IP. Que porcentagem de cada datagrama será sobrecarga e que porcentagem será dados de aplicação?

50% cada.

#### Questão 17 – Suponha que o Hospedeiro A envie ao Hospedeiro B um segmento TCP encapsulado em um datagrama IP. Quando o Hospedeiro B recebe o datagrama, como a camada de rede no Hospedeiro B sabe que deve passar o segmento (isto é, a carga útil do datagrama) para TCP e não para UDP ou qualquer outra coisa?

O campo de protocolo de 8 bits do datagrama contém essa informação de qual protocolo de transporte deve ser passado.

#### Questão 19 – Compare os campos de cabeçalho do IPv4 e do IPv6 e aponte suas diferenças. Eles têm algum campo em comum?

O cabecçalho do IPv6 tem comprimento fizo e não inclui a maioria das opções que um cabeçalho IPv4 pode incluir. Os endereços são de 128 bits no IPv6 e o comprimento total é de 40 bytes apenas. Os campos são similares: Traffic class, payload length, next header e hop limit são similares a type of service, total length, upper layer protocol e time to live no IPv4.

#### Questão 21 – Compare e aponte as diferenças entre os algoritmos de estado de enlace e de vetor de distâncias.

Estado de enlace: computa o caminho de menor custo entre a fonte e o destino usando conhecimento global sobre a rede. Vetor de distâncias: computa o caminho de menor custo de forma iterativa e distribuida. Um nó so conhece o vizinho que deve repassar o pacote para chegar ao destino com o menor custo, e o custo do caminho dele até o destino.

#### Questão 22 – Discuta como uma organização hierárquica da Internet possibilitou estender sua escala para milhões de usuários.

Roteadores sao organizados em sistemas autonomos. Dentro de um SA, todos os roteadores executam o mesmo protocole de roteamento intra-SA. O problema de escalabilidade é resolvido com o fato de um roteador em um SA precisar conhecer apenas sobre os roteadores neste SA e as subredes ligadas ao SA. Para roteamento entre SAs o protocolo inter-SA é baseado no grafo e nã leva roteadores individuis em conta.

#### Questão 28 – Por que considerações políticas não são tão importantes para protocolos intra-AS como o OSPF e o RIP, quanto para um protocolo de roteamento inter-AS como BGP?



#### Problema 9 – Considere uma rede de datagramas que usa endereços de hospedeiros de 32 bits. Suponha que um roteador tenha quatro enlaces, numerados de 0 a 3, e que os pacotes têm de ser repassados para as interfaces de enlaces como segue:

#### a) Elabore uma tabela de repasse que tenha quatro registros, use compatibilização com o prefixo mais longo e repasse pacotes para as interfaces de enlaces corretas.

#### b) Descreva como sua tabela de repasse determina a interface de enlace apropriada para datagramas com os seguintes endereços:
11001000 10010001 01010001 01010101
11100001 01000000 11000011 00111100
11100001 10000000 00010001 01110111



#### Problema 14 – No Problema 9, solicitamos que você elaborasse uma tabela de repasse (usando compatibilização de prefixo mais longo). Reescreva a tabela usando a notação a.b.c.d/x em vez da notação de cadeia binária.



#### Problema 17 – Considere enviar um datagrama de 2.400 bytes por um enlace que tem uma MTU de 700 bytes. Suponha que o datagrama original esteja marcado com o número de identificação 422. Quantos fragmentos são gerados? Quais são os valores em vários campos dos datagramas IP gerados em relação `a fragmentação?



#### Problema 24 – Considere a seguinte rede. Com os custos de enlace indicados, use o algoritmo do caminho mais curto de Dijkstra para calcular o caminho mais curto de x até todos os nós da rede. Mostre como o algoritmo funciona calculando uma tabela semelhante à tabela 4.3.



#### Problema 26 – Considere a rede mostrada a seguir e admita que cada nó inicialmente conheça os custos até cada um de seus vizinhos. Considere o algoritmo de vetor de distâncias e mostre os registros na tabela de distâncias para o nó z.nsíveis ao atraso, mas não tão sensíveis a perda de dados, logo o menor delay do UDP é mais atraente que a entrega garantida do TCP.