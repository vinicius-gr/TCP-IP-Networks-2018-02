src.html

# Wireshark Lab: UDP

#### Nome:

Vinícius Gonzaga Rocha

#### Matrícula:

11511BCC019

#### Descrição:

Atividade realizada para o aprofundamento do conhecimento do protocolo UDP.

----------

#### 1. Select one UDP packet from your trace. From this packet, determine how many fields there are in the UDP header. (You shouldn’t look in the textbook! Answer these questions directly from what you observe in the packet trace.) Name these fields.

São 4 campos, conforme imagem: Source Port, Destination Port, Length, Checksum.

![GET](imgs/1.png)

#### 2. By consulting the displayed information in Wireshark’s packet content field for this packet, determine the length (in bytes) of each of the UDP header fields. 

2 bytes

![GET](imgs/2.png)

#### 3. The value in the Length field is the length of what? (You can consult the text for this answer). Verify your claim with your captured UDP packet.

É o comprimento da mensagem carregada pelo pacote UDP + o cabeçalho.

![GET](imgs/3.png)


#### 4. What is the maximum number of bytes that can be included in a UDP payload? (Hint: the answer to this question can be determined by your answer to 2. above)

65535 bytes, pois esse é o meior numero que pode ser representado por 2 bytes hexadecimais.

#### 5. What is the largest possible source port number? (Hint: see the hint in 4.) 

65535 bytes, pois esse é o meior numero que pode ser representado por 2 bytes hexadecimais.

#### 6. What is the protocol number for UDP? Give your answer in both hexadecimal and decimal notation. To answer this question, you’ll need to look into the Protocol field of the IP datagram containing this UDP segment (see Figure 4.13 in the text, and the discussion of IP header fields). 

Decimal | Hexadeciaml
---     | ---
17      | 11

![GET](imgs/6.png) 

#### 7. Examine a pair of UDP packets in which your host sends the first UDP packet and the second UDP packet is a reply to this first UDP packet. (Hint: for a second packet to be sent in response to a first packet, the sender of the first packet should be the destination of the second packet). Describe the relationship between the port numbers in the two packets.

Podemos observar que a porta de destino no primeiro pacote passa a ser a porta fonte no pacote de resposta. Essa inversão também ocorre com a porta fonte do primeiro pacote, que passou a ser a porta de destino na resposta.

![GET](imgs/7-1.png)
![GET](imgs/7-2.png)
