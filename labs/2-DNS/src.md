src.html

# Wireshark Lab: DNS

#### Nome:

Vinícius Gonzaga Rocha

#### Matrícula:

11511BCC019

#### Descrição:

Atividade realizada para o aprofundamento do conhecimento do protocolo DNS.

----------

### 1\. nslookup

#### 1\. Run nslookup to obtain the IP address of a Web server in Asia. What is the IP address of that server?

O endereço obtido foi 92.242.140.6 para o site da Universidade de Seoul [www.useoul.edu](http://www.useoul.edu)

![GET](imgs/1.jpg)

#### 2\. Run nslookup to determine the authoritative DNS servers for a university in Europe.

Foi executado para o site da Universidade de Lisboa [www.ulisboa.pt](http://www.ulisboa.pt)

![GET](imgs/2.jpg)

#### 3\. Run nslookup so that one of the DNS servers obtained in Question 2 is queried for the mail servers for Yahoo! mail. What is its IP address?

O IP retornado foi 200.152.162.189. A operação sofreu time out pois o servidor é desconhecido.

![GET](imgs/3.jpg)

----------

### 3\. Tracing DNS with Wireshark

#### 4\. Locate the DNS query and response messages. Are then sent over UDP or TCP?

São enviadas via UDP, conforme imagem.

![GET](imgs/4.jpg)

#### 5\. What is the destination port for the DNS query message? What is the source port of DNS response message?

Destination Port da query: 53  
Source Port da resposta: 53  
Conforme imagens.

![GET](imgs/5-1.jpg)  
![GET](imgs/5-2.jpg)

#### 6\. To what IP address is the DNS query message sent? Use ipconfig to determine the IP address of your local DNS server. Are these two IP addresses the same?

Para o 200.225.197.34. São o mesmo, conforme imagens.

![GET](imgs/6-1.jpg)  
![GET](imgs/6-2.jpg)

#### 7\. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?

Tipo A (Host Adress) (1). Não possui respostas, conforme imagem.

![GET](imgs/7.jpg)

#### 8\. Examine the DNS response message. How many “answers” are provided? What do each of these answers contain?

Uma resposta foi provida. Contem o IP (Address) 92.242.140.6 além dos campos Name, Type, Class, Time to live, Data length, conforme imagem.

![GET](imgs/8.jpg)

#### 9\. Consider the subsequent TCP SYN packet sent by your host. Does the destination IP address of the SYN packet correspond to any of the IP addresses provided in the DNS response message?

Não. O endereço contido na resposta foi 92.242.140.6 enquanto o destino do pacote SYN foi para 181.114.114.80

![GET](imgs/9.jpg)

#### 10\. This web page contains images. Before retrieving each image, does your host issue new DNS queries?

Não, conforme imagem.

![GET](imgs/10.jpg)

#### 11\. What is the destination port for the DNS query message? What is the source port of DNS response message?

Destination Port da query: 53  
Source Port da resposta: 53  
Conforme imagens.

![GET](imgs/11-1.jpg)  
![GET](imgs/11-2.jpg)

#### 12\. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server?

Para o 200.225.197.34. São o mesmo, conforme imagens.

![GET](imgs/12-1.jpg)  
![GET](imgs/12-2.jpg)

#### 13\. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?

Tipo AAA (IPv6 Address) (28). Não possui respostas, conforme imagem.

![GET](imgs/13.jpg)

#### 14\. Examine the DNS response message. How many “answers” are provided? What do each of these answers contain?

Uma resposta foi provida. Contem o IP (Address) 92.242.140.6 além dos campos Name, Type, Class, Time to live, Data length, conforme imagem.

![GET](imgs/14.jpg)

#### 15\. Provide a screenshot.

![GET](imgs/15.jpg)

#### 16. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server?

Para o 200.225.197.34. São o mesmo, conforme imagens.

![GET](imgs/16-1.jpg)
![GET](imgs/16-2.jpg)

#### 17. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?

É do tipo PTR (domain name PoinTeR) (12), conforme imagem.

![GET](imgs/17.jpg)

#### 18. Examine the DNS response message. What MIT nameservers does the response message provide? Does this response message also provide the IP addresses of the MIT nameservers?

Responde o IP 34.197.225.200, conforme imagem.

![GET](imgs/18.jpg)

#### 19. Provide a screenshot.

![GET](imgs/19-1.jpg)
![GET](imgs/19-2.jpg)

#### 20. To what IP address is the DNS query message sent? Is this the IP address of your default local DNS server? If not, what does the IP address correspond to?

A primeira query foi para o mesmo IP local (200.225.197.34) enquanto a segunda foi para o IP (18.72.0.3), conforme imagens.

![GET](imgs/20-1.jpg)
![GET](imgs/16-2.jpg)
![GET](imgs/20-2.jpg)

#### 21. Examine the DNS query message. What “Type” of DNS query is it? Does the query message contain any “answers”?

É do tipo PTR (domain name PoinTeR) (12), conforme imagem.

![GET](imgs/21.jpg)

#### 22. Examine the DNS response message. How many “answers” are provided? What does each of these answers contain?

Uma resposta foi provida, contendo os campos nome do host, tipo, classe, 'time to live', tamanho dos dados e o endereço de IP 18.72.0.3 (bitsy.mit.edu).

![GET](imgs/22.jpg)

#### 23. Provide a screenshot.

![GET](imgs/23-1.jpg)
![GET](imgs/23-2.jpg)
