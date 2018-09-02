# Cap�tulo 1 - Redes de Computadores e a Internet
---

### 1.1 O que � a Internet? 
---
Disversas maneiras de se definir, a seguir ser�o apresentadas 2 delas.

##### 1.1.1 Uma descri��o dos componentes da rede
---
Sistemas finais s�o os dispositivos da ponta. Se comunicam atrav�s de enlaces (links) e comutadores de pacotes. Diversos meios de comunica��o. A taxa de trasmiss�o de um enlace � medida em bits por segundo. � necess�rio que o emissor segmente os dados e a cada segmento adicione bytes de cabe�alho. No destino final s�o reagregados.

Os comutadores de camada de enlace (switches) s�o tipicamente utilizados em redes de acesso, enquanto os roteadores s�o utilizados mais no n�cleo da rede. A sequencia de caminhos � chamada de rota.

Sistemas finais acessam a rede atrav�s de ISPs. Todos esses componentes da rede executam protocolos de envio e recebimento de informa��es. TCP e IP s�o os utilizados na internet. O protocolo IP especifica o formato dos pacotes que s�o enviados e recebido entre os roteadores e sistemas finais.

Padr�es s�o necessarios para que todos se entendam. Os padr�es da internet s�o feitos pela IETF, que produzem os RFCs. Definem os protocolos TCP< IP HTTP e SMTP. Tamb�m existe o IEEE que especif�ca padr�es Ethernet e Wi-Fi.


##### 1.1.2 Uma descris��o do servi�o
---
Tamb�m � poss�vel descreve-la como uma infraestrutura que prov� servi�os a aplica��es. Aplica��es distribu�das. Essas aplica��es proveem uma Interface de Programa��o de Aplica��o que especifica como o componente do sistema final solicita � infraestrutura que envie dados a um componente espec�fico de destino, executado em outro sistema final.
 

##### 1.1.3 O que � um protocolo?
---
� preciso que 2 entidades comunicantes executem o mesmo protocolo para que uma tarefa seja realizada.

"Um protocolo define o formato e a ordem das mensagens trocadas entre 2 ou mais entidades comunicantes, bem como as a��es realizadas na transmiss�ao e/ou no recebimento de um mensagem ou outro evento". 

### 1.2 A periferia da Internet
---
Como a abordagem � top-down, come�aremos analisando os sistemas finais. Tamb�m s�o conhecisdos como hosts. S�o divididos em clientes e servidores. 

##### 1.2.1 Programas clientes e servidores
---
Um programa cliente funciona em um sitema final que solicita e recebe servi�o de um servidor, que funcion em outro sistema final. Nem todas as aplica��es s�o assim. Existem os P2P.


##### 1.2.2 Redes de acesso
---
Entenderemos as redes de acesso, isto �, enlaces f�sicos que conectam um sistema final ao primeiro roteador (roteador de borda). Muitas das tecnologias empegram parcelas de infraestrutura telef�nica com fio, fornecida por uma operadora. Cada resid�ncia possui um par direto de fios de cobre tran�ado para um comutador da operador na regi�o, localizado na "central telef�nica". S�o centenas de TC's.

**Dial-up (discado)**
� o acesso por meio de linhas telef�nicas anal�gicas com um modem discado. Chama-se dial-up porque o software do usu�rio disca um n�mero de telefone do ISP e realiza uma liga��o telef�nica tradicional. O modem converte a sa�da digital do PC para o formato anal�gico para um m�ximo de 56 kbps. Bloqueia a linha telef�nica.

**DSL**
Significa linha digital de assinantes. A mesma empresa telef�nica oferece internet. A linha telef�nica conduz simult�neamente os dados e os sinais telef�nicos, codificados em diferentes frequ�ncias. Quem recebe os dados e os trata � o DSLAM (multiplexador). Milhares de resid�ncias se conectam a um �nico DSLAM. Acesso assim�trico pois as velocidades de download e upload s�o diferentes. Maior velocidade e n�o ocupa linha telef�nica. A dist�ncia deve ser entre 8 km e 15 km.

**Cabo**
Ultiliza a rede de canais de televis�o, cabo coaxial e amplificadores. As resid�ncias se conectam as Jun��es. Necessita de modens a cabo. Acesso assim�trico pois as velocidades de download e upload s�o diferentes. A velocidade varia conforme n�mero de usu�rios utilizando a rede. DSL n�o sofre desse problema. � necess�rio protocolo de acesso m�ltiplo para evitar colis�es.

**FTTH**
Fibra �tica. Maior velocidade. A fibra direta sai do CT e vai direto pra resid�ncia, mas geralmente � compartilhada, tornado-se individual ao se aproximar da resid�ncia. Redes �ticas ativas (AONs) e redes �ticas passivas (PONs). Cada resid�ncia possui um terminal de rede �tica (ONT). Na arquitetura PON, todos os pacotes enviados do terminal de linha otica (OLT) ao distribuidor s�o nele replicados.

**Ethernet**
Universidade e centros coorporativos possuem redes locais (LANs) que conectam os PCs aos roteadores de periferia.

**Wi-Fi**
Existem LANs sem fio. Onde o sistema final est� h� alguns metros do ponto de acesso. Existem tamb�m as redes maiores onde a distribui��o do sinal ocorre de forma semelhante a rede telef�nica de celular. IEEE 802.11

**Acesso sem fio em longa dist�ncia**
Utiliza a rede de celular, at� 10 Km de dist�ncia. 3G.

**WiMAX**
IEEE 802.16. Funciona independente da rede de celular.

##### 1.2.3 Meios F�sicos
---
Vis�o geral dos meios de transmiss�o mais comuns. Existem meios guiados e n�o guiados. Guiados usam cabos e n�o guiados usam a atmosfera.

**Par de fios de cobre tran�ado**
O mais barato e comum. Uma s�rie de pares � conjulgado num cabo. Um par constitui um �nico enlace. Par de fios sem blindagem (UTP) alcan�a at� 100 Mbps.

**Cabo coaxial**
Constitu�do tamb�m por 2 condutores de cobre, mas concentricos e nao paralelos. O sinal � transmitido em uma frequ�ncia diferente do sinal de TV. Pode ser usado como um meio compartilhado guiado.

**Fibras �ticas**
� um meio delgado e flex�vel que conduz pulsos de luz, representando os bits. Centenas de gigabits por segundo. Imunes a interfer�ncia eletromagn�tica e muito dif�ceis de derivar. Cabos submarinos. Alto custo.

**Canais de r�dio terrestres**
Espectro eletromagn�tico. N�o requer cabos. Sofrem atenua��o interfer�ncia.

**Canais de r�dio por sat�lite**
Um sat�lite liga 2 ou mais transmissores-receptores de microondas na Terra. Na faixa de Gbps. Sat�lites geoestacion�rios e de �rbita baixa.

### 1.3 O n�cleo da rede
---
##### 1.3.1 Comuta��o de circuitos e comuta��o de pacotes
---
S�o as duas abordagens poss�veis. Nas rede de comuta��o de circuitos os recursos necess�rios pelo caminho para a comunica��o s�o reservados pelo periodo de comunica��o e na comuta��o de pacotes n�o e as mensagens poder�o precisar entrar na fila para ter acesso. Como se fossem dois restaurante, um aceita reserva e outro n�o. Redes de telefonia s�o de circuito pois as partes precisamestabelecer uma conex�o forte. A taxa de transmiss�o �garantida. A internet � o que h� de mais apurado nas redes de comuta��o de pacotes. A internet faz o melhor esfor�o para entregar os dados prontamente, mas n�o h� garantias.

**Comuta��o de circuitos**
� importante enteder por que a internet n�o se ultiliza dessa tecnologia.

**Multiplexa��o em redes de comuta��o de circuitos**
Um circuito � implementado em um enlace por multiplexa��o por divis�o de frequ�ncia (FDM) ou por multiplexa��o por divis�o de tempo (TDM). Com FDM, cada circuito dis�e continuamente de  uma fra��o da largura de banda. Com TDM, cada circuito disp�e de toda a largura de banda periodicamente, em intervalos de tempo. � ruim pois recursos s�o desperdi�ados.

**Comuta��o de pacotes**
Em redes o emissor fragmenta mensagens longas em por��es denominadas pacotes. Os comutadores empregam a t�cnica armazena-e-reenvia, e portanto deve receber o pacote inteiro antes de come�ar os trablahos. Isso representa atraso. Atraso total � Q*L/R. Para cada enlace o comutador tem um buffer. Os pacotes tb sofrem atrasos de fila. Pode ocorrer perda de pacote pois a fila n�o � infinita.

**Comuta��o de pacotes versus comuta��o de circuitos: multiplexa��o estatp�stica**
Comparando as duas. Desvantagens da comu. pacotes: inadequada para servi�os de tempo real. Vantagens: melhor compartilhamento de banda e implementa��o mais simples, mais eficiente e mais barata. At� mesmo redes telef�nicas est�o migrando para comu. pacotes.

##### 1.3.2 Como os pacotes percorrem as redes de comutadores de pacotes?
---
Cada pacote contem em seu cabe�alho o endere�o de destino. Esse endere�o possui uma estrutura hier�rquica. Cada
roteador possui uma base de encaminhamentoque mapeia o endere�o de destino para prox. enlace. A internet possui
protocolos de roteamento para gerar as bases. Semelhante a um motorista que n�o quer usar mapa e sai pedindo
informa��es.


##### 1.3.3  ISPs e backbones da Internet
---
A internet � uma rede de redes. ISPs de acesso est�o na borda. H� tamb�m ISPs de n�vel 1: Conectam-se diretamente a
cada um dos outros ISPs de nivel 1; conectam-se a um grande numero de ISPs de nivel 2 e a outras redes de clientes;
cobertura internacional. Tamb�m s�o conhecidos como redes de backbone de Internet.
ISPs de n�vel 2 tem cobertura nacional ou regional. ISPs ligados s�o denominados pares. O pontos de conex�o s�o
conhecidos como pontos de presen�a (POP). Um ISP nivel 1 tem varios POPs.

### 1.4 Atraso, perda e vaz�o em redes de comuta��o de pacotes
---
N�o haver perdas � inalcan�avel.

##### 1.4.1 Uma vis�o geral de atraso em redes de comuta��o de pacotes
---
Em cada n� do caminho ocorrem diversos tipos de atraso, formando o atraso nodal total. A seguir vamos entender a Natureza desses atrasos.

**Tipos de atraso**
An�lise da figura 1.16. Um pacote s� pode ser transmitido se n�o houver nenhum outro pacote sendo transmitido no enlace e se n�o houver ninguem na frente dele na fila.

**Atraso de processamento**
Trata-se do tempo requerido para examinar o cabe�alho e determinar para onde direcionar o pacote. Tambem pode incluir  fatores como o tempo necessario para verifica��o de erros. Microssegundos ou menos. Depois direciona para a fila do enlace para o roteador B.

**Atraso de fila**
Tempo de espera para ser transmitido no enlace. Tempo vari�vel. � possivel prever o nro de pacotes na fila utilizando uma fun��o.Na ordem de micro ou milissegundos.

**Atraso de transmiss�o**
O pacote s� poode ser transmitido depois que os da frente forem enviados. O tamanho do pacote � L e a velocidade de transmissao de A para B � R btis/s. O atraso de transmiss�o � L/R, ou seja, a quantidade de tempo para empurrar todos os bits para o enlace. Micro a milssegundos.

**Atraso de propaga��o**
� o tempo para se propagar at� o roteador B. O tempo depende da velocidade de propaga��o do enlace. Esse atraso � calculado dividindo a dist�ncia pela velociadde. d/s.

**Compara��o entre atrasos de transmiss�o e de propaga��o**
O atraso de transmiss�o � a qtde de tempo requerida para o roteador empurrar o pacote para fora; uma fun��o do comprimento do pacote e da taxa de transmiss�o do enlace e n�o tem nada a ver com a distancia entre os roteadores.
O atraso de propaga��o � o tempo que lava para um bit se propagar at� o roteador seguinte. Uma fun��o da dist�ncia dos roteadores e nao tem nada a ver com o comprimento do pacote ou a taxa de transmiss�o do enlace.

##### 1.4.2 Atraso de fila e perda de pacote
---
O mais importante atraso nodal � o atraso de fila. Varia de pacote para pacote. A caracteriza��o deste utiliza mdedi��es estat�stica como atraso de fila medio, variancia do atraso e probabilidade. Sendo a pacotes/segundo, R taxa de transmiss�o e L o tamanho dos pacotes e a fila sendo infinita, caso L*a/R seja  > 1 o atraso � infinito. Os sistemas nao podem ter intensidade de trafego maior que 1. O processo de chegada de pacotes � aleat�rio.

**Perda de pacote**
As filas s�o finitas. Quando um pacote chega e a fila est� cheia ele � descaratado. Isso impede atraso infinito. Aumenta conforme a intenssidade do trafego. N�s podem ter seu desempenho medido tambem em probabilidade de perda de pacotes. Os pacotes s�o geralmente retransmitidos qdo se perderm.

##### 1.4.3 Atrasos fim a fim
---
Os atrasos nodais se acumulam e resultam em um atraso fim a fim.

**Traceroute**
Programa que envia pacotes especiais para medir o atraso.

**Sistema final, aplicativo e outros atrasos**
Os sistemas finais podem adicionar outros atrasos, incluisive intencionalmente. Existe tamb�m atraso de empacotamento no VoIP

##### 1.4.4 Vaz�o nas redes de computadores
---
Al�m do atraso e da perda de pacotes, a vaz�o tamb�m mede desempenho. Vaz�o � F/T bits/s sendo F o nro de bits e T o tempo. Vaz�o � muito importante na transfer�ncia de arquivos. Quando a v�rios n�s, o quhe tiver menos vazao sera um gargalo na rede. Hoje em dia o fator coercitivo para vaz�o � o acesso a rede. Dependente das taxas de transmiss�o dos enlaces. 

### 1.5 Camadas de protocolo e seus modelos de servi�o 
---

##### 1.5.1 Arquitetura de camadas
---
Como se fosse a funcionalidade de uma linha aerea. Separa��o em camadas permite modularidade, e � muito mais facil modificar a implementa��o do servi�o prestado pela camada.

**Camadas de protocolo**
Cada camada prove servi�os para a camada de cima e utiliza servi�os do camada de baixo. Podem ser implementadas em software, hardware ou ambos. A camada de rede � quase sempre uma implementa��o mista. Existe sempre uma parcela de um protocolo de camada n em cada um dos componentes da rede. Possui vantagens e desvantagens.

**Camada de aplica��o**
� onde residem aplica��es de rede e seus protocolos. HTTP, SMTP e FTP. DNS � da camada de aplica��o. Os pacotes de informa��o s�o denominados mensagens. � simples criar protocolos para esta camada.

**Camada de transporte**
Transporta mensagens da camada de aplica��o entre os lados do  cliente e servidor. H� 2 protocolos de transporte na internet: TCP e UDP. Os servi�os do TCP s�o, entrega garantida, controle de fluxo (compatibiliza��o das velocidades do remetente e receptor), fragmenta mensagens longas, controle de congestionemento. Os pacotes nessa camada chamam-se segmentos.

**Camada de rede**
Respons�vel pela movimenta��o de uma m�quina para outra de pacotes de camada de rede conhecidos como datagramas. Prove servi�o de entrega do segmento � camada de transporte na maquina de destino.  POssui dois componentes principais: o protocolo que define os campos no datagrama e o modo como os sistemas finaias e roteadores agem nesses campos. Este � o protocolo IP. Possui tambem protocolos de roteamento.

**Camada de enlace**
Para levar um pacote de um n� ao n� seguinte a camada de rede utiliza os servi�os da camada de enlace. Alguns protocolos proveem entrega garantida de um n� ao outro. Protocolos dessa camda s�o Ethernet, WIFi e PPP. Pacotes s�o denominados quadros.

**Camada f�sica**
Movimenta os bits individuais dentro do quadro. Os protocolos dependem do enlace.

**O modelo OSI**
Prove uma organiza��o em 7 camadas. As duas que n�o aparecem s�o incorporadas pela camada de aplica��o.

##### 1.5.2 Mensagens, segmentos, datagramas e quadros
---
Sistemas finais devem implementar todas as camadas, j� os n�s intermediarios (comutadores e roteadores) n�o. Cada camada adiciona um pouco de dados no cabe�alho dos dados e tamb�m bits de detec��o de erro.



# Cap�tulo 2 - Camada de aplica��o
---
Se n�o houvessem aplica��es n�o seria necess�rio redes. Terreno familiar para iniciar estudo dos protocolos. 

### 2.1 Princ�pios de aplica��es de rede
---
O cene do desenvolvimento � escrever programas que rodem em sistemas finais diferentes e se comuniquem entre si pela rede. 

##### 2.1.1 Arquiteturas de aplica��o de rede
---
� necessario elaborar um plano geral para a arquitetura. Dever� escolher entre cliente-servidor e P2P. Em cliente-servidor h� um hospedeiro sempre em funcionamento (servidor) que atende requisi��es de outros hospedeiros (clientes). O servidor tem um endere�o fixo (IP). Um conjunto de hospedeiros � denominado data center. Em P2P h� confian�a m�nima nos servidores sempre em funcionamento. Possui autoescalabilidade. Ent�o h� conex�o ocorre netre pares alternadamanete. Esses pares n�o s�o dos provedores de servi�o e sim dos pr�prios usu�rios. Muitas aplica��es s�o h�bridas.

**Desafios para P2P:**
- ISP amig�vel: Velociades de upload muito menores que download.
- Seguran�a: Natureza altamente distribu�da e exposta.
- Incentivos: Depende que os us�rios participem para oferecer largura de banda, armazenamento e recursos.

##### 2.1.2 Comunica��o entre processos
---
Entender como programas em diferentes sistemas se comunicam. Na verdade, s�o processos. Um processo pode ser imaginado como um programa que est� rodadndo dentro de um sistema final. Se comunicam pela troca de mensagens.

**Processos clientes e processos servidores**
No contexto de uma sess�o de comunica��o entre um par de processos, o processo que inicia a comunica��o � rotulado cliente. O processo que espera ser contatado � o servidor.

**A interface entre o processo e a rede de computadores**
Um processo envia mensagens para a rede e recebe mensagens dela atrav�s de uma interface de software denominada socket. Um processo � a casa e o socket a porta da casa. Um socket � a interface entre a camada de aplica��o e a de transporte dentre de uma m�quina. Pode tb ser denominado API entre a aplica��o e a rede. O desenvolvedor controla o que existe no lado de aplica��o do socket e tem pouco controle da camada de transporte. Sao eles: 
- Escolha do protocolo de transporte
- Parametros da camada
- Constroi a aplica��o usando os servi�os da camada oferecidos por esse protocolo.

##### 2.1.3 Servi�os de transporte dispon�veis para aplicacoes
---
**Transferencia confiavel de dados**
Os pacotes podem se perder. Se um protocolo fornecer um servi�o de recebimento de dados garantidos, ele fornecer� uma transfer�ncia confi�vel de dados.

**Vazao**
� a taxa � qual o processo remetente pode enviar bits ao processo destinatario. Oscila com o tempo. O servi�o � uma vaz�o disponivel garantida a uma taxa especifica. Aplica��es sens�veis a largura de banda.

**Temporiza��o**
Por exemplo cada bit do remetente chega ao socket destinatario em menos de 100 milissegundos.

**Seguran�a**
No hospedeiro remetente um protocolo pode codificar todos os dados transmitidos. 

##### 2.1.4 Servicos de transporte providos pela Internet
---
A internet disponibiliza 2 protocolos de transporte, o TCP e o UDP. 

**Servi�os do TCP**
Inclui servi�o orientado a conex�o e servi�o confi�vel de tranferencia de dados. Servico orientado a conexao significa que o cliente e o servidor troquem informa��es de controle de camada de transporte antes das mensagens da camada de aplicacao comecem a fluir. Apos essa dase de apresentacao existe uma conexao TCP entre os sockets. A conexao � full-duplex pois ambos os processos podem enviar mensagens ao mesmo tempo pela conexao. Ao termino do envio de mensagens a pliucacao deve interromper a conexao. O servico conficavel de transporte significa que os processos podem confiar em uma entrega de todos os dados e na ordem correta. TCP tb inclui mecanismo de controle de congestionamento, bom para a internet mas nao para os processos. Geralmente aplicacoes em tempo real nao usam TCP e sim UDP. SSL � um aperfeicoamento do TCP para mais seguranca.

**Servicos do UDP**
O UDP � simplificado e leve, nao orientado para conexao. Nao h� apresenta�ao entre os processos. Nao prove servico confiavel de transferencia. Muitos firewalls bloqueiam UDP pelo ausencia de controle de congestionamento.

**Servicos nao providos pelos protocolos de transporte da Internet**
Vazao e temporizacao nao sao oferecidos nem por TCP nem UDP.

**Endere�amento de processos**
� preciso especificar o nome ou endere�o da m�quina hospedeira (IP) e um identificador que especifique o processo destinatario no hospedeiro de destino (Porta).

##### 2.1.5 Protocolos de camada de aplicacao
---
Um protocolo de camada de aplicacao define como processos de uma aplicacao, que funcionam em sistemas finais diferentes, passam mensagens entre sim. Definem: os tipos de mensagens trocadas, a sintaxe dos varios tipos de mensagens, a semantica dos campos e a as regras para determinar quando e como um processo envia e responde mensagens.
Aplicacoes de rede nao sao protocolos da camada de aplicacao. Um protocolo � apenas um peda�o de aplicacao de rede. 

##### 2.1.6 Aplicacoes de rede abordadas neste livro
---
Web, transferencia de arquivos, e-mail, servico de diretorio e aplicacoes P2P. 

### 2.2 A Web e o HTTP
---
At� a d�cada de 90 a internet era usada por pesquisadores, academicos e estudantes. Em 1994 surge a World Wide Web criada por Tim Berners-Lee. 

##### 2.2.1 Descricao geral do HTTP
---
O HTTP � implementado em dois programas: um cliente e um servidor. Os programas trocam mensagens HTTP. 
Uma p�gina Web � constitu�da de objetos. Um objeto � simplesmente um arquivo - tal como um arquivo HTML ou JPEG - que se pode acessar com um unico URL. A paginas Web possuem um arquivo-base HTML e diversos objetos referenciados.
Cada URL possui 2 componentes: o nome do hospedeiro e o caminho do objeto. O HTTP utiliza TCP como transporte. � um protocolo sem estado pois o servidor HTTP nao mantem nenhuma informa��o sobre cliente.

















