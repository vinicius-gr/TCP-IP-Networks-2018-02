# Capítulo 1 - Redes de Computadores e a Internet
---

## 1.1 O que é a Internet? 
---
Disversas maneiras de se definir, a seguir serão apresentadas 2 delas.

### 1.1.1 Uma descrição dos componentes da rede
---
Sistemas finais são os dispositivos da ponta. Se comunicam através de enlaces (links) e comutadores de pacotes. Diversos meios de comunicação. A taxa de trasmissão de um enlace é medida em bits por segundo. É necessário que o emissor segmente os dados e a cada segmento adicione bytes de cabeçalho. No destino final são reagregados.

Os comutadores de camada de enlace (switches) são tipicamente utilizados em redes de acesso, enquanto os roteadores são utilizados mais no núcleo da rede. A sequencia de caminhos é chamada de rota.

Sistemas finais acessam a rede através de ISPs. Todos esses componentes da rede executam protocolos de envio e recebimento de informações. TCP e IP são os utilizados na internet. O protocolo IP especifica o formato dos pacotes que são enviados e recebido entre os roteadores e sistemas finais.

Padrões são necessarios para que todos se entendam. Os padrões da internet são feitos pela IETF, que produzem os RFCs. Definem os protocolos TCP< IP HTTP e SMTP. Também existe o IEEE que especifíca padrões Ethernet e Wi-Fi.


### 1.1.2 Uma descrisção do serviço
---
Também é possível descreve-la como uma infraestrutura que provê serviços a aplicações. Aplicações distribuídas. Essas aplicações proveem uma Interface de Programação de Aplicação que especifica como o componente do sistema final solicita à infraestrutura que envie dados a um componente específico de destino, executado em outro sistema final.
 

### 1.1.3 O que é um protocolo?
---
É preciso que 2 entidades comunicantes executem o mesmo protocolo para que uma tarefa seja realizada.

"Um protocolo define o formato e a ordem das mensagens trocadas entre 2 ou mais entidades comunicantes, bem como as ações realizadas na transmissçao e/ou no recebimento de um mensagem ou outro evento". 

## 1.2 A periferia da Internet
---
Como a abordagem é top-down, começaremos analisando os sistemas finais. Também são conhecisdos como hosts. São divididos em clientes e servidores. 

### 1.2.1 Programas clientes e servidores
---
Um programa cliente funciona em um sitema final que solicita e recebe serviço de um servidor, que funcion em outro sistema final. Nem todas as aplicações são assim. Existem os P2P.


### 1.2.2 Redes de acesso
---
Entenderemos as redes de acesso, isto é, enlaces físicos que conectam um sistema final ao primeiro roteador (roteador de borda). Muitas das tecnologias empegram parcelas de infraestrutura telefônica com fio, fornecida por uma operadora. Cada residência possui um par direto de fios de cobre trançado para um comutador da operador na região, localizado na "central telefônica". São centenas de TC's.

**Dial-up (discado)**
É o acesso por meio de linhas telefônicas analógicas com um modem discado. Chama-se dial-up porque o software do usuário disca um número de telefone do ISP e realiza uma ligação telefônica tradicional. O modem converte a saída digital do PC para o formato analógico para um máximo de 56 kbps. Bloqueia a linha telefônica.

**DSL**
Significa linha digital de assinantes. A mesma empresa telefônica oferece internet. A linha telefônica conduz simultâneamente os dados e os sinais telefônicos, codificados em diferentes frequências. Quem recebe os dados e os trata é o DSLAM (multiplexador). Milhares de residências se conectam a um único DSLAM. Acesso assimétrico pois as velocidades de download e upload são diferentes. Maior velocidade e não ocupa linha telefônica. A distância deve ser entre 8 km e 15 km.

**Cabo**
Ultiliza a rede de canais de televisão, cabo coaxial e amplificadores. As residências se conectam as Junções. Necessita de modens a cabo. Acesso assimétrico pois as velocidades de download e upload são diferentes. A velocidade varia conforme número de usuários utilizando a rede. DSL não sofre desse problema. É necessário protocolo de acesso múltiplo para evitar colisões.

**FTTH**
Fibra ótica. Maior velocidade. A fibra direta sai do CT e vai direto pra residência, mas geralmente é compartilhada, tornado-se individual ao se aproximar da residência. Redes óticas ativas (AONs) e redes óticas passivas (PONs). Cada residência possui um terminal de rede ótica (ONT). Na arquitetura PON, todos os pacotes enviados do terminal de linha otica (OLT) ao distribuidor são nele replicados.

**Ethernet**
Universidade e centros coorporativos possuem redes locais (LANs) que conectam os PCs aos roteadores de periferia.

**Wi-Fi**
Existem LANs sem fio. Onde o sistema final está há alguns metros do ponto de acesso. Existem também as redes maiores onde a distribuição do sinal ocorre de forma semelhante a rede telefônica de celular. IEEE 802.11

**Acesso sem fio em longa distância**
Utiliza a rede de celular, até 10 Km de distância. 3G.

**WiMAX**
IEEE 802.16. Funciona independente da rede de celular.

### 1.2.3 Meios Físicos
---
Visão geral dos meios de transmissão mais comuns. Existem meios guiados e não guiados. Guiados usam cabos e não guiados usam a atmosfera.

**Par de fios de cobre trançado**
O mais barato e comum. Uma série de pares é conjulgado num cabo. Um par constitui um único enlace. Par de fios sem blindagem (UTP) alcança até 100 Mbps.

**Cabo coaxial**
Constituído também por 2 condutores de cobre, mas concentricos e nao paralelos. O sinal é transmitido em uma frequência diferente do sinal de TV. Pode ser usado como um meio compartilhado guiado.

**Fibras óticas**
É um meio delgado e flexível que conduz pulsos de luz, representando os bits. Centenas de gigabits por segundo. Imunes a interferência eletromagnética e muito difíceis de derivar. Cabos submarinos. Alto custo.

**Canais de rádio terrestres**
Espectro eletromagnético. Não requer cabos. Sofrem atenuação interferência.

**Canais de rádio por satélite**
Um satélite liga 2 ou mais transmissores-receptores de microondas na Terra. Na faixa de Gbps. Satélites geoestacionários e de órbita baixa.

## 1.3 O núcleo da rede
---
### 1.3.1 Comutação de circuitos e comutação de pacotes
---
São as duas abordagens possíveis. Nas rede de comutação de circuitos os recursos necessários pelo caminho para a comunicação são reservados pelo periodo de comunicação e na comutação de pacotes não e as mensagens poderão precisar entrar na fila para ter acesso. Como se fossem dois restaurante, um aceita reserva e outro não. Redes de telefonia são de circuito pois as partes precisamestabelecer uma conexão forte. A taxa de transmissão égarantida. A internet é o que há de mais apurado nas redes de comutação de pacotes. A internet faz o melhor esforço para entregar os dados prontamente, mas não há garantias.

**Comutação de circuitos**
É importante enteder por que a internet não se ultiliza dessa tecnologia.

**Multiplexação em redes de comutação de circuitos**
Um circuito é implementado em um enlace por multiplexação por divisão de frequência (FDM) ou por multiplexação por divisão de tempo (TDM). Com FDM, cada circuito disõe continuamente de  uma fração da largura de banda. Com TDM, cada circuito dispõe de toda a largura de banda periodicamente, em intervalos de tempo. É ruim pois recursos são desperdiçados.
Podemos dizer que, para o TDM, cada sinal usa toda a largura de banda por algum tempo, enquanto que para o FDM, cada sinal usa uma pequena parte da largura de banda o tempo todo.
O TDM oferece maior flexibilidade e eficiência, alocando dinamicamente mais períodos para os sinais que precisam de mais largura de banda, enquanto reduz os períodos de tempo para os sinais que não precisam dele. O FDM não possui este tipo de flexibilidade, uma vez que não pode alterar dinamicamente a largura da frequência alocada.
A vantagem do FDM sobre o TDM está em latência. Latência é o tempo que leva para os dados chegarem ao seu destino. Como o TDM aloca períodos de tempo, somente um canal pode transmitir em um determinado momento, e alguns dados costumam ser atrasados, embora muitas vezes seja apenas em milissegundos. Como os canais no FDM podem transmitir a qualquer momento, suas latências seriam muito menores em comparação com o TDM. O FDM é frequentemente usado em aplicativos nos quais a latência é de extrema prioridade, como aqueles que exigem informações em tempo real.

**Comutação de pacotes**
Em redes o emissor fragmenta mensagens longas em porções denominadas pacotes. Os comutadores empregam a técnica armazena-e-reenvia, e portanto deve receber o pacote inteiro antes de começar os trablahos. Isso representa atraso. Atraso total é Q*L/R. Para cada enlace o comutador tem um buffer. Os pacotes tb sofrem atrasos de fila. Pode ocorrer perda de pacote pois a fila não é infinita.

**Comutação de pacotes versus comutação de circuitos: multiplexação estatística**
Comparando as duas. Desvantagens da comu. pacotes: inadequada para serviços de tempo real. Vantagens: melhor compartilhamento de banda e implementação mais simples, mais eficiente e mais barata. Até mesmo redes telefônicas estão migrando para comu. pacotes.

### 1.3.2 Como os pacotes percorrem as redes de comutadores de pacotes?
---
Cada pacote contem em seu cabeçalho o endereço de destino. Esse endereço possui uma estrutura hierárquica. Cada
roteador possui uma base de encaminhamentoque mapeia o endereço de destino para prox. enlace. A internet possui
protocolos de roteamento para gerar as bases. Semelhante a um motorista que não quer usar mapa e sai pedindo
informações.


### 1.3.3  ISPs e backbones da Internet
---
A internet é uma rede de redes. ISPs de acesso estão na borda. Há também ISPs de nível 1: Conectam-se diretamente a
cada um dos outros ISPs de nivel 1; conectam-se a um grande numero de ISPs de nivel 2 e a outras redes de clientes;
cobertura internacional. Também são conhecidos como redes de backbone de Internet.
ISPs de nível 2 tem cobertura nacional ou regional. ISPs ligados são denominados pares. O pontos de conexão são
conhecidos como pontos de presença (POP). Um ISP nivel 1 tem varios POPs.

## 1.4 Atraso, perda e vazão em redes de comutação de pacotes
---
Não haver perdas é inalcançavel.

### 1.4.1 Uma visão geral de atraso em redes de comutação de pacotes
---
Em cada nó do caminho ocorrem diversos tipos de atraso, formando o atraso nodal total. A seguir vamos entender a Natureza desses atrasos.

#### Tipos de atraso
Análise da figura 1.16. Um pacote só pode ser transmitido se não houver nenhum outro pacote sendo transmitido no enlace e se não houver ninguem na frente dele na fila.

##### Atraso de processamento
Trata-se do tempo requerido para examinar o cabeçalho e determinar para onde direcionar o pacote. Tambem pode incluir  fatores como o tempo necessario para verificação de erros. Microssegundos ou menos. Depois direciona para a fila do enlace para o roteador B. Não há formula.

##### Atraso de fila
Tempo de espera para ser transmitido no enlace. Tempo variável. É possivel prever o nro de pacotes na fila utilizando uma função.Na ordem de micro ou milissegundos. Não há fórmula.

##### Atraso de transmissão
O pacote só poode ser transmitido depois que os da frente forem enviados. O tamanho do pacote é L e a velocidade de transmissao de A para B é R btis/s. O atraso de transmissão é L/R, ou seja, a quantidade de tempo para empurrar todos os bits para o enlace. Micro a milssegundos. Fórmula: L/R

##### Atraso de propagação
É o tempo para se propagar até o roteador B. O tempo depende da velocidade de propagação do enlace. Esse atraso é calculado dividindo a distância pela velociadde. Fórmula: d/s.

##### Comparação entre atrasos de transmissão e de propagação
O atraso de transmissão é a qtde de tempo requerida para o roteador empurrar o pacote para fora; uma função do comprimento do pacote e da taxa de transmissão do enlace e não tem nada a ver com a distancia entre os roteadores.
O atraso de propagação é o tempo que lava para um bit se propagar até o roteador seguinte. Uma função da distância dos roteadores e nao tem nada a ver com o comprimento do pacote ou a taxa de transmissão do enlace.

### 1.4.2 Atraso de fila e perda de pacote
---
O mais importante atraso nodal é o atraso de fila. Varia de pacote para pacote. A caracterização deste utiliza mdedições estatística como atraso de fila medio, variancia do atraso e probabilidade. Sendo a pacotes/segundo, R taxa de transmissão e L o tamanho dos pacotes e a fila sendo infinita, caso L*a/R seja  > 1 o atraso é infinito. Os sistemas nao podem ter intensidade de trafego maior que 1. O processo de chegada de pacotes é aleatório.

**Perda de pacote**
As filas são finitas. Quando um pacote chega e a fila está cheia ele é descaratado. Isso impede atraso infinito. Aumenta conforme a intenssidade do trafego. Nós podem ter seu desempenho medido tambem em probabilidade de perda de pacotes. Os pacotes são geralmente retransmitidos qdo se perderm.

### 1.4.3 Atrasos fim a fim
---
Os atrasos nodais se acumulam e resultam em um atraso fim a fim.

**Traceroute**
Programa que envia pacotes especiais para medir o atraso.

**Sistema final, aplicativo e outros atrasos**
Os sistemas finais podem adicionar outros atrasos, incluisive intencionalmente. Existe também atraso de empacotamento no VoIP

### 1.4.4 Vazão nas redes de computadores
---
Além do atraso e da perda de pacotes, a vazão também mede desempenho. Vazão é F/T bits/s sendo F o nro de bits e T o tempo. Vazão é muito importante na transferência de arquivos. Quando a vários nós, o quhe tiver menos vazao sera um gargalo na rede. Hoje em dia o fator coercitivo para vazão é o acesso a rede. Dependente das taxas de transmissão dos enlaces. 

## 1.5 Camadas de protocolo e seus modelos de serviço 
---

### 1.5.1 Arquitetura de camadas
---
Como se fosse a funcionalidade de uma linha aerea. Separação em camadas permite modularidade, e é muito mais facil modificar a implementação do serviço prestado pela camada.

**Camadas de protocolo**
Cada camada prove serviços para a camada de cima e utiliza serviços do camada de baixo. Podem ser implementadas em software, hardware ou ambos. A camada de rede é quase sempre uma implementação mista. Existe sempre uma parcela de um protocolo de camada n em cada um dos componentes da rede. Possui vantagens e desvantagens.

**Camada de aplicação**
É onde residem aplicações de rede e seus protocolos. HTTP, SMTP e FTP. DNS é da camada de aplicação. Os pacotes de informação são denominados mensagens. É simples criar protocolos para esta camada.

**Camada de transporte**
Transporta mensagens da camada de aplicação entre os lados do  cliente e servidor. Há 2 protocolos de transporte na internet: TCP e UDP. Os serviços do TCP são, entrega garantida, controle de fluxo (compatibilização das velocidades do remetente e receptor), fragmenta mensagens longas, controle de congestionemento. Os pacotes nessa camada chamam-se segmentos.

**Camada de rede**
Responsável pela movimentação de uma máquina para outra de pacotes de camada de rede conhecidos como datagramas. Prove serviço de entrega do segmento à camada de transporte na maquina de destino.  POssui dois componentes principais: o protocolo que define os campos no datagrama e o modo como os sistemas finaias e roteadores agem nesses campos. Este é o protocolo IP. Possui tambem protocolos de roteamento.

**Camada de enlace**
Para levar um pacote de um nó ao nó seguinte a camada de rede utiliza os serviços da camada de enlace. Alguns protocolos proveem entrega garantida de um nó ao outro. Protocolos dessa camda são Ethernet, WIFi e PPP. Pacotes são denominados quadros.

**Camada física**
Movimenta os bits individuais dentro do quadro. Os protocolos dependem do enlace.

**O modelo OSI**
Prove uma organização em 7 camadas. As duas que não aparecem são incorporadas pela camada de aplicação.

### 1.5.2 Mensagens, segmentos, datagramas e quadros
---
Sistemas finais devem implementar todas as camadas, já os nós intermediarios (comutadores e roteadores) não. Cada camada adiciona um pouco de dados no cabeçalho dos dados e também bits de detecção de erro.



# Capítulo 2 - Camada de aplicação
---
Se não houvessem aplicações não seria necessário redes. Terreno familiar para iniciar estudo dos protocolos. 

## 2.1 Princípios de aplicações de rede
---
O cene do desenvolvimento é escrever programas que rodem em sistemas finais diferentes e se comuniquem entre si pela rede. 

### 2.1.1 Arquiteturas de aplicação de rede
---
É necessario elaborar um plano geral para a arquitetura. Deverá escolher entre cliente-servidor e P2P. Em cliente-servidor há um hospedeiro sempre em funcionamento (servidor) que atende requisições de outros hospedeiros (clientes). O servidor tem um endereço fixo (IP). Um conjunto de hospedeiros é denominado data center. Em P2P há confiança mínima nos servidores sempre em funcionamento. Possui autoescalabilidade. Então há conexão ocorre netre pares alternadamanete. Esses pares não são dos provedores de serviço e sim dos próprios usuários. Muitas aplicações são híbridas.

**Desafios para P2P:**
- ISP amigável: Velociades de upload muito menores que download.
- Segurança: Natureza altamente distribuída e exposta.
- Incentivos: Depende que os usários participem para oferecer largura de banda, armazenamento e recursos.

### 2.1.2 Comunicação entre processos
---
Entender como programas em diferentes sistemas se comunicam. Na verdade, são processos. Um processo pode ser imaginado como um programa que está rodadndo dentro de um sistema final. Se comunicam pela troca de mensagens.

**Processos clientes e processos servidores**
No contexto de uma sessão de comunicação entre um par de processos, o processo que inicia a comunicação é rotulado cliente. O processo que espera ser contatado é o servidor.

**A interface entre o processo e a rede de computadores**
Um processo envia mensagens para a rede e recebe mensagens dela através de uma interface de software denominada socket. Um processo é a casa e o socket a porta da casa. Um socket é a interface entre a camada de aplicação e a de transporte dentre de uma máquina. Pode tb ser denominado API entre a aplicação e a rede. O desenvolvedor controla o que existe no lado de aplicação do socket e tem pouco controle da camada de transporte. Sao eles: 
- Escolha do protocolo de transporte
- Parametros da camada
- Constroi a aplicação usando os serviços da camada oferecidos por esse protocolo.

### 2.1.3 Serviços de transporte disponíveis para aplicacoes
---
**Transferencia confiavel de dados**
Os pacotes podem se perder. Se um protocolo fornecer um serviço de recebimento de dados garantidos, ele fornecerá uma transferência confiável de dados.

**Vazao**
É a taxa à qual o processo remetente pode enviar bits ao processo destinatario. Oscila com o tempo. O serviço é uma vazão disponivel garantida a uma taxa especifica. Aplicações sensíveis a largura de banda.

**Temporização**
Por exemplo cada bit do remetente chega ao socket destinatario em menos de 100 milissegundos.

**Segurança**
No hospedeiro remetente um protocolo pode codificar todos os dados transmitidos. 

### 2.1.4 Servicos de transporte providos pela Internet
---
A internet disponibiliza 2 protocolos de transporte, o TCP e o UDP. 

**Serviços do TCP**
Inclui serviço orientado a conexão e serviço confiável de tranferencia de dados. Servico orientado a conexao significa que o cliente e o servidor troquem informações de controle de camada de transporte antes das mensagens da camada de aplicacao comecem a fluir. Apos essa dase de apresentacao existe uma conexao TCP entre os sockets. A conexao é full-duplex pois ambos os processos podem enviar mensagens ao mesmo tempo pela conexao. Ao termino do envio de mensagens a pliucacao deve interromper a conexao. O servico conficavel de transporte significa que os processos podem confiar em uma entrega de todos os dados e na ordem correta. TCP tb inclui mecanismo de controle de congestionamento, bom para a internet mas nao para os processos. Geralmente aplicacoes em tempo real nao usam TCP e sim UDP. SSL é um aperfeicoamento do TCP para mais seguranca.

**Servicos do UDP**
O UDP é simplificado e leve, nao orientado para conexao. Nao há apresentaçao entre os processos. Nao prove servico confiavel de transferencia. Muitos firewalls bloqueiam UDP pelo ausencia de controle de congestionamento.

**Servicos nao providos pelos protocolos de transporte da Internet**
Vazao e temporizacao nao sao oferecidos nem por TCP nem UDP.

**Endereçamento de processos**
É preciso especificar o nome ou endereço da máquina hospedeira (IP) e um identificador que especifique o processo destinatario no hospedeiro de destino (Porta).

### 2.1.5 Protocolos de camada de aplicacao
---
Um protocolo de camada de aplicacao define como processos de uma aplicacao, que funcionam em sistemas finais diferentes, passam mensagens entre sim. Definem: os tipos de mensagens trocadas, a sintaxe dos varios tipos de mensagens, a semantica dos campos e a as regras para determinar quando e como um processo envia e responde mensagens.
Aplicacoes de rede nao sao protocolos da camada de aplicacao. Um protocolo é apenas um pedaço de aplicacao de rede. 

### 2.1.6 Aplicacoes de rede abordadas neste livro
---
Web, transferencia de arquivos, e-mail, servico de diretorio e aplicacoes P2P. 

## 2.2 A Web e o HTTP
---
Até a década de 90 a internet era usada por pesquisadores, academicos e estudantes. Em 1994 surge a World Wide Web criada por Tim Berners-Lee. 

### 2.2.1 Descricao geral do HTTP
---
O HTTP é implementado em dois programas: um cliente e um servidor. Os programas trocam mensagens HTTP. 
Uma página Web é constituída de objetos. Um objeto é simplesmente um arquivo - tal como um arquivo HTML ou JPEG - que se pode acessar com um unico URL. A paginas Web possuem um arquivo-base HTML e diversos objetos referenciados.
Cada URL possui 2 componentes: o nome do hospedeiro e o caminho do objeto. O HTTP utiliza TCP como transporte. É um protocolo sem estado pois o servidor HTTP nao mantem nenhuma informação sobre cliente.

### 2.2.2 Conexoes persistentes e nao persistentes

Em varias aplicacoes, cliente e servidor se comunicam por um periodo prolongado, onde o cliente faz diversas requisicoes. Essas requisicoes podem ser consecutivas, periodicas ou aleatorias. Quando se usa TCP a aplicacao precisa decidir se cada par de mensagens sera enviado por conexoes distintas ou uma mesma conexao. O HTTP utiliza conexoes persistentes por padrao.

#### O HTTP com conexoes nao persistentes

Por padrao, os browsers abrem em media de cinco a dez conexoes TCP paralelas e cada uma manipula um par de mensagens. A utilizaocao de conexoes paralelas reduz o tempo de resposta.
O browsers fazem apresentacao de 3 vias. O browser envia um reconhecimento para o servidor, este responde o reconhecimento e o browser envia um terceiro reconhecimento mas este junto com a requisição HTTP, em seguida o browser responde. Ao todo sao 4 RTTs.

#### O HTTP com conexoes persistentes

Cada objeto requer uma conexao a ser criada e mantida no HTTP nao persistente. Isso tb envolve alocacao de buffers TCP e conservação de variáveis TCP tanto no cliente quanto no servidor. Isso pode causar sobrecarga. Outra desvantagem é que cada objeto necessitará de dois RTTs.
No HTTP persistente uma pagina inteira e seus objetos podem ser enviados por uma mesma conexao. As requisicoes podem ser feitas em paralelo. 
Geralemente o servidor fecha a conexao quando nao é usada por um certo periodo de tempo.

### 2.2.3 Formato da mensagem HTTP
 
 As especificacoes do HTTP [RFC 2616] definem os formatos das mensagens HTTP. Ha dois tipos de mensagens HTTP: de requisicao e de resposta.

#### Mensagem de requisicao HTTP

A primeira linha de requisicao HTTP é denominada linha de requisição.  as demais, linhas de cabeçalho. Cada linha termina com um carriage  return (cr) e line feed (lf); A linha de requisição tem 3 campos separados por esoaco (sp): campo do metodo, URL e versao do HTTP. A linha do Host é necessária para os armazenadores intermediarios da Web. A linha de connection indica que o cliente deseja encerrar a conexao a pos a meresposta. A linha de User-Agent mostra qual o navegador realizou a requisicao. A linha Accept-language mostra que o usuario prefere uma versao em frances do objeto se disponivel. 
Se o metodo for POST o corpo de entidade cointera o que o usuario digitou nos campos do formulario. Formularios tambem podem usar GET mas os dados terao de ser passado atraves da URL. Outros metodos sao HEAD, utilizado para depuracao, pois a resposta nao vem com o objeto requisitado. Existem também os métodos PUT, para atualizacoes e DELETE para delecoes.

#### Mensagem de resposta HTTP

A linha inicial e chamada linha de estado, a demais linhas de cabeçalho e em seguida corpo de entidade, onde se encontra o objeto solicitado. A linha de estado tambem possui tres campos: a versao do protocolo, o status code e a mensagem de estado.
A linha Connection indica que o servidor fechará a conexao apos enviar a mensagem. A linha Date indica o momento em que a resposta foi criada. A linha Server mostra qual o tipo de servidor (analogo a linha User-Agent da requisiscao). A linha Last-Modified indica o momento que o objeto sofreu a ultima modificacao e e fundamental para cache de objeto. A linha Content-length indica o nro de bytes do objeto. A linha content type indica o tipo do objeto.
Tipos de resposta:

- 200 OK: requisicao bem-sucedida;
- 301 - Moved Permanently: objeto movio para outra URL e o software cliente faz requisicao para nova URL.
- 400 - Bad Request: requisicao nao entendida pelo servidor.
- 404 - Not Found: documento requisitado nao existe.
- 505 - HTTP Version Not Supported: a versao do HTTP nao é suportada pelo servidor.

### 2.2.4 Interacao usuario-servidor: cookies

Cookies servempara que os sites identifiquem mantenham registros dos usuários. 
Possui 4 componentes:
- Uma linha de cabecalho de cookie na resposta HTTP;
- Uma linha de cabecalho de cookie na requisicao HTTP;
- Um arquivo de cookie mantido no cliente e gerenciado pelo browser;
- Um banco de dados de apoio mantido no servidor;
Simplificam experiencia de compras na internet. O cookie mantido no cliente o identifica no banco de apoio no servidor. Muita controversia.
Podem ser usados para manter sessoes.

### 2.2.5 Caches Web

Conhecidos tambem como servidores proxy. Atendem requisicoes HTTP em nome de um servidor Web de origem. Possui seu proprio disco de armazenagem e mantem copias de objetos requisitados recentemente. Ao mesmo etmpo servidor e cliente. ISPs instalam proxys. Usado para reduzir tempos de resposta e reduzir o trafego no enlace de acesso da instituicao à internet.

### 2.2.6 GET condicional

As copias nos proxys podem estar desatualizadas. GET codicional serve para verificar mudancas. É GET condicional se (1) usar metodo GET e (2) possuir linha de cabecalaho If-Modified-Since. Servidores retornam 304 - Not Modified se nao houve mudanca. Economiza largura de banda.

## 2.3 Transferencia de arquivo: FTP

E necessario autorizar-se diante do servidor para fazer a copia dos arquivos. Tanto HTTP quanto FTP utilizam TCP, mas o FTP utiliza duas conexoes TCPs paralelas:uma conexao de controle e uma conexao de dados. Portanto envia as informacoes de controle fora da banda. O FTP envia exatamente um arquivo pela conexao de dados e em seguida fecha-a. A conexao de controle e mantida durante a sessao. Sao mantidas informacoes de estado sobre o usuario. Isso limita o numero de sessoe que o FTP pode manter simultaneamente. O HTTP é sem estado.

### 2.3.1 Comandos e respostas FTP

Os comandos e respostas sao enviadas no formato ASCII 7 bits. Os comandos sao encerrados assim como no HTTP carriage return e line feed. Os mais comuns são USER, PASS, LIST, RETR e STOR.

## 2.4 Correio eletronico na Internet

Meio de comunicação assincrono. Tres componentes: agentes de usuario, servidores de correio e o SMTP, que é o principal protocolo de email.

### 2.4.1 SMTP

Mais antigo que o HTTP. Bastante antigo e arcaico. Limita o corpo das mensagens ao formato ASCII 7 bits. Isso exige codificaçao e decodificacao. SMTP noramalmente nao usa servidores de correio intermediarios para enviar correspondencias.

### 2.4.2 Comparacao com o HTTP

O HTTP transfere arquivos (objetos) de um servidor Web para um cliente Web (normalmente um browser). O SMTP transfere arquivos (mensagens de email) de um servidor de correio para outro. O HTTP persistente e o SMTP utilizam conexoes persitentes. Entretanto as diferenças sao q o HTTP é um protocolo principalmente de recuperacao de informacoes (pull protocol), e em contrapartida o STMP é um protocolo de envio de informacoes (push protocol). HTTP nao restringe dados a ASCII 7 bits, enquanto o SMTP o faz. O HTTP separa cada objeto em sua propria mensagem, enquanto o STMP envia tudo em uma mensagem só.

### 2.4.3 Formatos de mensagem de correio e MIME

Quando uma mensagem de email e enviada, um cabecalho contendo informacoes perifericas antecede o corpo da mensagem em si. As linhas de cabecalho sao separadas por uma linha em branco (CRLF). Cada cada linha consiste de uma palavra chave seguida de dois pontos e um valor. Algumas sao obrigatorias e outras opcionais. Deve conter pelo menos FROM e TO. Sao diferente de comandos SMTP. Os comandos fazem parte do protocolo de apresentacao do SMTP, enquantos as linhas de cabecalho sao parte da mensagem em si.

### 2.4.4 Protocolos de acesso ao correio

O acesso ao correio atualmente utiliza uma arquitetura cliente servidor. Nao é possivel manter um servidor STMP em casa, pois isso significaria a necessidade de manter o servidor sempre ativo. Geralmente os servidores de correio sao compartilhados. O problema é que o STMP serve para enviar mensagens (protocolo de push). Enviar portanto é simples, mas como os usuarios acessam suas caixas postais? Ai que entram POP3, IMAP e HTTP que sao de pull.

#### POP3

Protocolo de acesso extremamente simples. Funcionalidades limitadas. O clente abre uma conexao TCP com o servidor na porta 110. Apos ativar a conexao TCP sao tres fases: Autorizacao, transacao e atualizacao. Em uma transacao POP3 o agente emite varios comandos para o servidor e este uma resposta para cada um, que pode ser OK ou ERR. O POP3 mantem informacoes de estado, mas nao sobre a sessao.

#### IMAP

Nao é possivel manter hierarquia de pastas com o POP3, por isso surgiu o IMAP. Significativamente mais complexo. Mantem informacoes entre sessoe. Possui comandos para criar, modificaar e apagar pastas e associar mensagens a elas. Por default as mensagens vao para a pasta INBOX. Permite baixar partes de mensagens, bom para conexoes com pouca largura.

#### E-mail para Web

Hoje em dia o que ocorre é que os emails estao no browser e portanto as comunicacoes dos cliente para os servidores de correio sao feitas por HTTP, e os servidores de correio continuam dialogando por SMTP.

## 2.5 DNS: o serviço de diretório da Internet

Um identificador é o nome de hospedeiro. Além disso, possuem o endereço IP. Endereços IP são hierárquicos da esquerda para direita.

### 2.5.1 Serviços fornecidos pelo DNS

É necessário um serviço de diretório para a conversão. Trata-se de (1) um banco de dados distribuído implementado em uma hierarquia de servidores de nome e (2) um protocolo de camada de aplicação que permite que hospedeiros consultem o banco. Os servidores geralmente são UNIS que executam o software BIND. O protocolo DSN utiliza UDP e usa a porta 53.
Somente depois de obter o endereço DNS o browser pode abrir uma conexão TCP com o processo servidor.
DNS adiciona mais um atraso às aplicações.
Outros serviços:
- Apelidos de hospedeiro;
- Apelidos de servidor de correio;
- Distribuição de carga;

### 2.5.2 Visão geral do modo de funcionamento do DNS

A aplicação chama o lado clente do DNS. Apartir daí o DNS do usuário assume o controle, enviando uma mensagemde consulta para a rede em um datagrama UDP à porta 53. O DNS não é centralizado pois isso acarretaria em: 
- Um único ponto de falha;
- Volume de tráfego alto;
- Banco de dados distante;
- Difícil manutenção;

#### Um banco de dados distribuído, hierárquico

Existem 3 classes: raiz, alto-nível e com autoridade.
- Servidores de nomes raiz: Existem 13 na internet. Maior parte na américa do norte. Cada um é um conglomerado replicado para segurança e confiabilidade.
- Servidores de nomes de Domínio de Alto Nivel (TLD): Sao responsáveis por domínios como com, org, net, edu e gov e países como uk.fr e br.
- Servidores de nomes com autoridade: São montados pelas organizações ou contratar um serviço.
Os ISPs possuem servidores DNS locais que agem como proxys.

#### Cache DNS

Explorado para reduzir o tráfego e melhorar desempenho. Geralmente informações são descartadas após 2 dias.

### 2.5.3 Registros e mensagens DNS

Um registro de recurso (RR) é uma tupla de quatro elementos: (Name, Value, Type, TTL).
Podem ser:
- tipo A: name é o hostname e value é o IP.
- tipo NS: name é o domínio e o value é o nome do servidor de nomes com autoridade que sabem onde estão os IPs do domínio.
- tipo CNAME: name é o apelido e o value é nome canônico.
- tipo MX: name é o hospedeiro e o value é o nome canônico de um servidor.


#### Mensagens DNS

Usar nslookup para enviar mensagens DNS.

#### Para inserir registros no banco de dados do DNS

Entidades registradora é uma entidade comercial que verifica se é exclusivo o nome, registra-o no banco de dados do DNS e cobra uma taxa. Informar também nomes e endereços dos servidores DNS com autoridade primarios e secundarios.

## 2.6 Aplicacoes P2P

Em P2P os pares (usuarios) comunicam diretamente entre si. As tres aplicacoes estudadas serao bitTorrent (compartlhamento de arquivos), banco de dados distribuidos (DHT) e o Skype (telefonia).

### 2.6.1 Distribuição de arquivos P2P

O protocolo mais popular atualmente é o bitTorrent. Desenvolvido por Bram Cohen.

#### Escalabilidade de arquiteturas P2P

Para a distribuição de um arquivo na arquitetura cliente servidor, têm-se: 
Dcs = máx{NF / us, F / dmin}.

Com isso podemos dizer que o tempo de distribuição aumenta linear mente com N.

Para a distribuição de um arquivo na arquiterua P2P têm-se: 
Dp2p = máx{F / us, F / dmin, NF / us + Σ ui}


Aplicações P2P apresentam autoescalabilidade, pois pares passam a ser redistribuidores.

#### BitTorrent

A coleção de todos os pares que participam da distribuição de um arquivo é chamada de torrent. Os downloads são feitos em blocos de geralmente 256Kb. Enquanto um par vai fazendo download de blocos faz também o upload para outros pares.
Cada torrent tem um nó de infraestrutura chamado rastreador. Quando um par chega em um torrent, ele se registra no rastreador e se mantém informando que ainda está no torrent. Assim, o rastreador possui registro de todos que estão participando.
Os pares estabelecem conexoes TCP simultaneas. Os pares fazem solicitações de blocos que ainda não possuem. Os blocos a serem solicitados seguem a plítica de rarest first. Isso serve para que os blocos mais raros nao sejam perdidos. Para determinar a quais pedidos atender, o protocolo usa a troca inteligente, ou seja, os pares que possuem a maior taxa. Sao quatro pares revisados periodicamente, e sao chamados de unchoked. Tambem é escolhido um vizinho aleatorio chamado de optimistically unchoked. Pares com taxas de upload parecidas tendem a se encontrar. Isso se chama tit-fot-tat, essencial para a sobrevivencia do bitTorrent.

### 2.6.2 Distributed Hash Tables (DHTs)

Descrevendo uma abordagem elegante para um projeto de banco de dados P2P. O identificador de cada par é um número entre [0, 2^n-1]. Para transformar chaves não inteiras em inteiros utiliza-se uma função Hash, pública a todos os pares.

#### DHT circular

Nesta disposição, cada par rastreia apenas seu sucessor imediato (% 2^n). É um caso especial de rede sobreposta. Esta acima da rede onde se encontram os enlaces fisicos, roteadores e hospedeiros. Os enlaces sao virtuais. Para manter o numero de mensagens enviadas e o numero de pares rastreados controlado, é usada a rede sobreposta circular como fundação, mas utilizar "atalhos".

#### Peer Churn

Pares vem e vão. Cada par deve verificar periodicamente se seus vizinhos estão vivos.

### 2.6.3 Estudo de caso: telefonia por Internet P2P com Skype

Trata-se de uma aplicação P2P pois no núcleo, duplas de usuário (pares) comunicam-se entre si em tempo real. O Skype emprega P2P para localização de usuário e NAT traversal.


Descrevendo uma abordagem elegante para um projeto de banco de dados P2P. O identificador de cada par é um número entre [0, 2^n-1]. Para transformar chaves não inteiras em inteiros utiliza-se uma função Hash, pública a todos os pares.

#### DHT circular

Nesta disposição, cada par rastreia apenas seu sucessor imediato (% 2^n). É um caso especial de rede sobreposta. Esta acima da rede onde se encontram os enlaces fisicos, roteadores e hospedeiros. Os enlaces sao virtuais. Para manter o numero de mensagens enviadas e o numero de pares rastreados controlado, é usada a rede sobreposta circular como fundação, mas utilizar "atalhos".

#### Peer Churn

Pares vem e vão. Cada par deve verificar periodicamente se seus vizinhos estão vivos.

### 2.6.3 Estudo de caso: telefonia por Internet P2P com Skype

Trata-se de uma aplicação P2P pois no núcleo, duplas de usuário (pares) comunicam-se entre si em tempo real. O Skype emprega P2P para localização de usuário e NAT traversal.

# Capiítulo 3 - Camda de transporte

A principal função é ampliar o serviço de entrega da camada de rede entre dois sistemas finais para um serviço de entrega entre dois processos de camada de aplicaçao que rodam nos sistemas finais.

## 3.1 Introdução e serviços de camada de transporte

Um protocolo de camada de transporte fornece comunicação lõgica entre processos de aplicação em hospedeiros diferentes. Essa communicacao logica abstrai para a aplicacao como se os dois hospedeiros estivessem conectados diretamente. Na verdade existem diversos roteadores e tipos de enlaces conectando eles. 
Está implementada em sistemas finais. Os pacotes são denominados segmentos.

### 3.3.1 Relação entre as camadas de transporte e de rede

A camada de rede oferece a comunicação lógica entre hospedeiros, ao contrario da de transporte que é entre processos. Oferece vários tipos de serviços de transporte. Dependente do funcionamento da camada de rede. Oferece criptografia mesmo que a camada de rede nao oferecça.

### 3.1.2 Visão geral da camada de transporte da Internet

Disponibiliza UDP e TCP, no caso da Internet. Ao criar os sockets escolhe um dos 2. O pacote aqui se chama segmento. Na camada de rede existe o IP que não é confiável. Cada hosperdeiro possui um endereço IP. A apmpliação da entrega hospedeiro a hospedeiro para processo a processo chama-se multiplexaocao/demultiplexacao da camada de transporte. Oferecem verificação de integridade. Esses dois são os únicos oferecidos pelo UDP. Jao o TCP oferece entrega confiável e controle de congestionamento. 

## 3.2 Multiplexação e demultiplexação

Um processo pode ter um ou mais sockets. Cada segmento possui um conjunto de campos para direcionamento à porta correta. Os segmentos contem nro de porta fonte e nro de porta destino. Cada nro é de 16 bit na faixa 0 a 65535. os nros entre 0 a 1023 são ditos bem conhecidos e sao restritos. HTTP usa o 80.

#### Multiplexação e demultiplexação não orientados para conexão

O socket UDP é identificado apenas pela porta fonte e IP da fonte.

#### Multiplexacao e demultiplexacao orientadoas a conexao

O socket UDP é identificado pela porta fonte e IP fonte e pela porta destino e IP destino.

#### Servidores Web e TCP

Servidores modernos utilizam threads. Um subprocesso leve.

## 3.3 Transporte não orientado para conexão: UDP

UDP adciona na mensagem os campos de porta fonte e do destino e dois outros campos.O UDP tem as seguintes vantagens:
- Melhor controle no nível da aplicação sobre quais dados são enviados e quando.
- Não há estabelecimento de conexao
- Nao ha estafos de conexao
- Pequena sobrecarga de cabeçalho de pacote.

### 3.3.1 Etrutura do segmento UDP

O cabeçalho possui 4 campos de 2 bytes cada. Os numeros das portas, o comprimento e a soma de verificação.

### 3.3.2 Soma de verificação UDP

Oferece verificação pois nem todos os campos de enlace oferecem verificação como o Ethernet. Pode haver erro tb no armazenamento no roteadors. A dele é fim a fim. Não faz nada para recuperar o erro. Pode descartar o segmento ou passalo para a camada de cima com um aviso.

## 3.4 Princípios da transferência confiável de dados

Os dados são entregues sem corrompimento e na ordem certa. A transferência bidirecional é chamada de full duplex.

### 3.4.1 Construindo um protocolo de transferência confiável de dados

#### Transferência confiável de dados sobre um canal perfeitamente confiável: rdt 1.0

Implementação trivial, já que a camada subjacente oferece transferência confiável.

#### Transferência confiável de dados por um canal com erros de bits: rdt 2.0

O pacotes podem sofrer corrompimentos na vida real. Apos detectar o erro, pede a reenvio do pacote. São necessárias tres capacitacoes: Detecção de erros, Realimentação do destinatário e Retransmissao. O remetente não enviará novos dados até ter ctz que o destinatario recebeu o pacote em questao.  O problema é se o pacote com o ack e nack estiver corrompido. A solucao adotada é adicionar um campo com um numero de sequencia.

#### Transferencia confiavel de dados por um canal com perda e com erros de bits: rdt 3.0

Para perdas de pacotes é introduzido um mecanismo de contagem do tempo. Um valor de tempo provavel que a perda tenha acontecido e reenvia o pacote. Por isso pacotes duplicados sao introduzidos na rede. Chamado de protocolo bit alternante. A soma de tudo resulta em somas de verificação, numeros de sequencia, temporizadores e pacotes de reconhecimento.

### 3.4.2 Protocolos de transferencia confiavel de dados com paralelismo

Pare e espere apresenta desempenho ruim. A solução chama-se pipelining.

### 3.4.3 Go-Back-N

### 3.4.4 Repetição seletiva (SR)

## 3.5 Transporte orientado para conexão: TCP

O TCP é orientado a conexao pois os processos devem estabelecer um handshake antes de trocar dados. O estado da conexao reside inteiramente nos dois sistemas finais. Os roteadores enxergam datagrams e não conexões. O serviço oferecido é full-duplex. O TCP é sempre ponto a ponto, unico remetente e unico destinatario.

### 3.5.1 A conexão TCP

O establecimento ocorre pelo 3-way handshake. A camada de aplicação passa para a camada de transporte os dados a serem enviados e a camada de transporte armazena em um buffer de envio. Quando vai realizar o envio tira um pedaço dos dados que tem o tamanho maximo de segmento. Este ultimo é calculado usando a unidade maxima de transmissao. Valores comuns são 1460, 536 e 512 bytes. Quando chega ao destinos os dados sao colocados no buffer de recepção.

### 3.5.2 Estrutura do segmento TCP

Os campos de cabeçalho do TCP são: 
- Nro de porta fonte
- Nro de porta destinnho
- Nro de sequencia
- Nro de reconhecimento
- Comprimento do cabeçalho
- Janela de recepção
- Campo de opções
- Campo de flag

#### Numeros de sequencia e numeros de reconhecimento

O nro de sequencia para um segmento é o nro do primeiro byte do segmento. O numero de reconhecimento que o hospedeiro A atribui a seu segmento é o número de sequencia do proximo byte que ele estiver aguardando do hospedeiro B. TCP promove reconhecimentos cumulativos. Caso receba um pacote fora de ordem a tendencia é armazenar o pacote e aguardar os faltantes.

#### Telnet: um estudo de caso para numeros de sequencia e numeros de reconhecimento.