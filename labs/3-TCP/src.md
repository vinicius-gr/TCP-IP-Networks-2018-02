src.html

# Wireshark Lab: DNS

#### Nome:

Vinícius Gonzaga Rocha

#### Matrícula:

11511BCC019

#### Descrição:

Atividade realizada para o aprofundamento do conhecimento do protocolo TCP.

----------

### 2. A first look at the captured trace 

#### 1. What is the IP address and TCP port number used by the client computer (source) that is transferring the file to gaia.cs.umass.edu? To answer this question, it’s probably easiest to select an HTTP message and explore the details of the TCP packet used to carry this HTTP message, using the “details of the selected packet header window” (refer to Figure 2 in the “Getting Started with Wireshark” Lab if you’re uncertain about the Wireshark windows.

192.168.1.102       porta 1161

![GET](imgs/1.png)

#### 2. What is the IP address of gaia.cs.umass.edu? On what port number is it sending and receiving TCP segments for this connection? 

128.119.245.12     porta 80

![GET](imgs/2.png)

#### 3. What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu? 

192.168.1.102       porta 1161

![GET](imgs/3.png)

----------

### 3. TCP Basics 

#### 4. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment?

É o número 0; A flag setada em SYN.

![GET](imgs/4.png)

#### 5. What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the Acknowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value? What is it in the segment that identifies the segment as a SYNACK segment?

É o número 0; O valor do ack é 1; Através do número de sequência; As flags de SYNACK.

![GET](imgs/5.png)  

#### 6. What is the sequence number of the TCP segment containing the HTTP POST command? Note that in order to find the POST command, you’ll need to dig into the packet content field at the bottom of the Wireshark window, looking for a segment with a “POST” within its DATA field.

É o número 1.

![GET](imgs/6.png) 

#### 7. Consider the TCP segment containing the HTTP POST as the first segment in the TCP connection. What are the sequence numbers of the first six segments in the TCP connection (including the segment containing the HTTP POST)? At what time was each segment sent? When was the ACK for each segment received? Given the difference between when each TCP segment was sent, and when its acknowledgement was received, what is the RTT value for each of the six segments? What is the EstimatedRTT value (see Section 3.5.3, page 239 in text) after the receipt of each ACK? Assume that the value of the EstimatedRTT is equal to the measured RTT for the first segment, and then is computed using the EstimatedRTT equation on page 239 for all subsequent segments.

\#  | Seq. Number   | Time      | Time ACK  | RTT       | EstimatedRTT 
--- |---            |---        |---        |---        | ---
1   | 1             | 0.026477  | 0.053937  | 0.027460  | 0.027460
2   | 566           | 0.041737  | 0.077294  | 0.035557  | 0.001151  
3   | 2026          | 0.050260  | 0.124085  | 0.073825  | 0.001173
4   | 3486          | 0.054690  | 0.169118  | 0.114428  | 0.001214
5   | 4946          | 0.077405  | 0.217299  | 0.139894  | 0.001251
6   | 6406          | 0.078157  | 0.267802  | 0.189645  | 0.001285

![GET](imgs/7-1.png)

#### 8. What is the length of each of the first six TCP segments?

\#  |   Length
--- |   ---
1   |   565
2   |   1460
3   |   1460  
4   |   1460
5   |   1460
6   |   1460

![GET](imgs/8.png)

#### 9. What is the minimum amount of available buffer space advertised at the received for the entire trace? Does the lack of receiver buffer space ever throttle the sender? 

O tamanho do buffer informado é 17520 bytes

![GET](imgs/9.png)

#### 10. Are there any retransmitted segments in the trace file? What did you check for (in the trace) in order to answer this question? 

Não, conforme imagem.

![GET](imgs/10.png)

#### 11. How much data does the receiver typically acknowledge in an ACK? Can you identify cases where the receiver is ACKing every other received segment (see Table 3.2 on page 247 in the text).

Os geralmente referem-se a 1460 bytes, que é o temanho médio de pacote sendo enviado.

#### 12. What is the throughput (bytes transferred per unit time) for the TCP connection? Explain how you calculated this value. 

Podemos observar uma média de 225000 bytes por segundo, conforme imagem.

![GET](imgs/12.png)

### 4. TCP congestion control in action 

#### 13. Use the Time-Sequence-Graph(Stevens) plotting tool to view the sequence number versus time plot of segments being sent from the client to the gaia.cs.umass.edu server. Can you identify where TCP’s slowstart phase begins and ends, and where congestion avoidance takes over? Comment on ways in which the measured data differs from the idealized behavior of TCP that we’ve studied in the text. 

Slowstart começa no pacote 1 e vai até o 11. Congestion avoidance começa a partir do 13. 

![GET](imgs/13.png) 