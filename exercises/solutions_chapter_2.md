#### Questão 5 – Que informação é usada por um processo que está rodando em um hospedeiro para identifcar um processo que está rodando em outro hospedeiro?

O endereço IP do outro hospedeiro e o número da porta do socket.

#### Questão 6 – Suponha que você queira fazer uma transação de um cliente remoto para um servidor da maneira mais rápida possível. Você usaria o UDP ou o TCP? Por quê?

O UDP pois esse faz uso do melhor esforço, não oferecendo garantias de entrega. O UDP pode fazer a entrega em um RTT: O cliente envia a requisição de transação e o servidor responde. Já no TCP primeiro seria necessário abrir uma conexão e depois ocorrer a transação ( 2 RTTs ).

#### Questão 7 – Com referência a Figura 2.4, vemos que nenhuma das aplicações relacionadas nela requer “sem perda de dados” e “temporização”. Você consegue imaginar uma aplicação que requeira “sem perda de dados” e seja também altamente sensível ao atraso?

Aplicação                                   | Perda de dados    | Largura de banda                                      | Sensibilidade ao atraso
---                                         | ---               | ---                                                   | ---
Transferência de arquivos                   | Sem perda         | Elástica                                              | Não
E-mail                                      | Sem perda         | Elástica                                              | Não
Documentos Web                              | Sem perda         | Elástica (alguns kbps)                                | Não
Telefonia via Internet /  Videoconferência  | Tolerante à perda | Áudio: alguns kbps – 1 Mbps Vídeo: 10 kbps – 5 Mbps   | Sim: décimos de segundo
Áudio / vídeo armazenado                    | Tolerante à perda | Áudio: alguns kbps – 1 Mbps Vídeo: 10 kbps – 5 Mbps   | Sim: alguns segundos
Jogos interativos                           | Tolerante à perda | Alguns kbps – 10 Mbps                                 | Sim: décimos de segundo         
Mensagem instantânea                        | Sem perda         | Elástica                                              | Sim e não

#### Questão 11 – Por que HTTP, FTP, SMTP, POP3 rodam sobre TCP e não sobre UDP?

Esse protocolos necessitam de entregas garantidas e na ordem correta, pois não são tolerantes a perdas, e o TCP oferece isso.

#### Questão 13 – Descreva como o cache Web pode reduzir o atraso na recepção de um objeto desejado. O cache Web reduzirá o atraso para todos os objetos requisitados por um usuário ou somente para alguns objetos? Por quê?

O cache reduz o atraso pois o dado solicitado pode estar cacheado em algum lugar antes do servidor Web, seja na própria máquina do usuário, em um proxy, ou alguma parte do ISP; É possivel que o cache reduza o atraso para todos os objetos solicitados, caso a rede seja congestionada, pois mesmos para objetos não cacheaveis, estes serão recuperados mais rapidamente pois a rede esta mais livre.

#### Questão 15 – Por que se diz que o FTP envia informações de controle “fora da banda”?

Pois as informações de controle são enviadas em uma conexão separada da conexao que está realmente tranferindo os dados.

#### Questão 16 – Suponha que Alice envie uma mensagem a Bob por meio de uma conta de e-mail da Web (como o Hotmail), e que Bob acesse seu e-mail por seu servidor de correio usando POP3. Descreva como a mensagem vai do hospedeiro de Alice até o hospedeiro de Bob. Não se esqueça de relacionar a séria de protocolos de camada de aplicação usados para movimentar a mensagem entre os dois hospedeiros.

A mensagem sairá da conta de e-mail Web de Alice para o servidor de correio utilizando HTTP. O servidor de correio de Alice enviara a mensagem para o servidor de correio de Bob utilizando SMTP e Bob recuperará a mensagem de seu servidor de correio para seu hospedeiro usando POP3.

#### Questão 18 – Da perspectiva de um usuário, qual é a diferença entre o modo ler-e-apagar e o modo ler-e-guardar no POP3?

O modo ler e apagar impede que as mensagens lidas em um hospedeiro sejam lidas em outro, mesmo que para uma mesma conta. Entao se usuario recuperar as mensangens em seu PC de trabalho usando o POP3 dessa forma, nao poderá recuperar a mesma mensagem em seu PC em casa. Já no ler e guardar as mensagens são mantidas no servidor de correio.

#### Questão 19 – É possível que o servidor Web e o servidor de correio de uma organização tenham exatamente o mesmo apelido para um nome de hospedeiro (por exemplo, foo.com)? Qual seria o tipo de RR que contém o nome de hospedeiro do servidor de correio?

Sim.

#### Questão 22 – O que é uma rede de sobreposição em um sistema de compartilhamento de arquivos P2P? Ela inclui roteadores? Como a rede de sobreposição de inundação de consultas é criada e como é mantida?

#### Questão 24 – Considere uma DHT com uma topologia da rede de sobreposição (ou seja, cada par rastreia todos os pares no sistema). Quais são as vantagens e desvantagens de uma DHT circular (sem atalhos)?