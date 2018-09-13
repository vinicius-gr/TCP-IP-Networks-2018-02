# Wireshark Lab: HTTP

#### Nome: Vinícius Gonzaga Rocha
#### Matrícula: 11511BCC019
#### Descrição: Atividade realizada para o aprofundamento do conhecimento do protocolo HTTP. Foram desenvolvidas 5 partes, cada uma com um foco diferente. Cada seção representa uma parte e dentro de cada uma existem capturas de telas para as respostas da questões levantadas nas seções. Nem todo o conteúdo exibido na tela do Wireshark foi documentado, apenas o conteúdo pertinente as respostas.

---
#### 1. The Basic HTTP GET/response interaction

##### Mensagens capturadas:
![enter image description here](https://lh3.googleusercontent.com/InOcxJghBxrsEXDSKgLeCbEf-g3aPt9HjgP2naqFo_6Ii9lgGjocSHAzQCNOt57kmRyzlB2gleA)

##### GET:
![GET](https://lh3.googleusercontent.com/KuM2SBXcx2CtyMI_QfWSqJ_-VLw72U-HB9Q9Bs9_WmLvKw65HfgpYGQqp1hrU20IzrmwVlo-MZs)

##### Response:
![Response](https://lh3.googleusercontent.com/A_FCdX5MgLA-BbGYHXweF_q-c9CCYXgRpFFRwemNrMkmRLuAIO1MtZG-IJ8RyVVDpGfvrUiC_Ic)

##### Packet Content (GET):
![enter image description here](https://lh3.googleusercontent.com/2cWpHyfeUQoDLNkyyQczHmW5gJKtIDbuU1E2R0m-tZT6eHkudzILKXTJ41jx6Qqp10LJxnoKHmE)

##### Packet Content (Response):
![enter image description here](https://lh3.googleusercontent.com/7myR2ZAq7QFnNbuQmWMqGUmTRnqwxWYrrYVumlwq3FV9m8qujZwtWwKrIutmZ5lqMWAGrqEqTks)


#### 1. Is your browser running HTTP version 1.0 or 1.1? What version of HTTP is the server running?

Tanto o browser cliente quanto o servidor rodam a versão 1.1 do protocolo. Isso pode ser verificado nos itens Request Version e Response Version.

#### 2. What languages (if any) does your browser indicate that it can accept to the server?

En-GB é aceito, conforme o item Accept-Language.

#### 3. What is the IP address of your computer? Of the gaia.cs.umass.edu server?

Conforme as colunas Source e Destination:
 - Minha máquina:  192.168.0.11
 - Servidor: 128.119.245.12  

#### 4. What is the status code returned from the server to your browser?

200 Ok, conforme o item Status Code.

#### 5. When was the HTML file that you are retrieving last modified at the server?

Em 2 de Setembro de 2018 às 05:59:01, conforme o item Last-Modified.

#### 6. How many bytes of content are being returned to your browser?

128 bytes, conforme o item File Data.

#### 7. By inspecting the raw data in the packet content window, do you see any headers within the data that are not displayed in the packet-listing window? If so, name one.

Não.

---
#### 2. The HTTP CONDITIONAL GET/response interaction

##### Mensagens capturadas:
![enter image description here](https://lh3.googleusercontent.com/psYjXirMSIiiR5-K0UAlPfTQnPSU6EOuPj5-GyfFpU9p37Kr6az-kSkbuZR-NwQCF6k3LKfbc1M)

##### GET 1:
![enter image description here](https://lh3.googleusercontent.com/KQDT0T4KFXqaJyHi40ghlMHJJ-iajJmOxT3oBmKOibzqlrWW2p5KDIcKF37jGhLgCEpkDggQk3s)

##### Response 1:
![enter image description here](https://lh3.googleusercontent.com/YF6nEhtc6iszDmKQbf5LP4qu_96LjG8_htdNMH7dDJs2J3UZTqXpQ7rI4-A7wq4465zyUEf3O9g)

##### GET 2:
![enter image description here](https://lh3.googleusercontent.com/LhvEcBF_H6qyoiBURzMugIKu6C1hYSeRJnBszwNLxDd2JVRaV0Maasi4gF8VBIF2h_hbKC7mkBA)

##### Response 2:
![enter image description here](https://lh3.googleusercontent.com/-cf6hBUlJKsvuyFBHFCRHpqu9Xm1Wr96QUOxNOtYjI4IFRSeTJ-46vq-eEv-WVhPXK3K-rQUXBE)

#### 8. Inspect the contents of the first HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE” line in the HTTP GET?

Esta linha não existe no primeiro GET.

#### 9. Inspect the contents of the server response. Did the server explicitly return the contents of the file? How can you tell?

Sim, pois é possível expandir o item Line-based text data: text/html (10 lines) e obter o conteúdo da página.

#### 10. Now inspect the contents of the second HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE:” line in the HTTP GET? If so, what information follows the “IF-MODIFIED-SINCE:” header?

Sim, o contéudo deste item é:  Mon, 03 Sep 2018 05:59:01 GMT.

#### 11. What is the HTTP status code and phrase returned from the server in response to this second HTTP GET? Did the server explicitly return the contents of the file? Explain.

O status retornado é o 304 - Not Modified. O servidor não retornou o conteúdo novamente. Este fato ocorre pois o conteúdo da página não foi modificado desde o último carregamento. Isso faz com que seja desnecessário reenviar os conteúdos novamente, uma vez que o browser já está exibindo o conteúdo presente no servidor. Isso otimiza e descongestiona a rede, uma vez que conteúdos redundantes não são reenviados desnecessariamente.

---
#### 3. Retrieving Long Documents


##### Mensagens capturadas:
![enter image description here](https://lh3.googleusercontent.com/Wuo1hpMcD878lfhlTeNQaUh4iBttc1i1ImF2Cxkt7_zPY1qwKENiQ-z6WvO2EMVT5uQL0-Vtt34)

##### GET:
![enter image description here](https://lh3.googleusercontent.com/s-65he6KbSppA08SCIeN1sOfgcY4XJtCgizEBChNrGpEzi6bt5ztunsCsZ3WAirbHVAicKTxehs)

##### Response e TCP segments:
![enter image description here](https://lh3.googleusercontent.com/guhmlxsTgtyqnueUri4xpTTWNOYBg3EnTpeP87jTO9XPytMdy1TaU17_psw989A3hADAlVEmU3Y)


#### 12. How many HTTP GET request messages did your browser send? Which packet number in the trace contains the GET message for the Bill of Rights?

Apenas 1 GET foi enviado. O pacote 215, conforme item [Request in frame: 215]

#### 13. Which packet number in the trace contains the status code and phrase associated with the response to the HTTP GET request?

O pacote 215, conforme item [Request in frame: 215]

#### 14. What is the status code and phrase in the response?

200 - OK, conforme itens Status Code: 200 e Response Phrase: OK.

#### 15. How many data-containing TCP segments were needed to carry the single HTTP response and the text of the Bill of Rights?

4 segmentos foram necessários, conforme item Segment count. 

---
#### 4. HTML Documents with Embedded Objects

##### Mensagens capturadas:
![enter image description here](https://lh3.googleusercontent.com/8l-UcJeaXmn1JU2RImNN-MFc3zd0mbp0eXMZXrm_b7a1wrRa3d3J5HuBkCC75I3_GLmgfYoVOdU)

#### 16. How many HTTP GET request messages did your browser send? To which Internet addresses were these GET requests sent? 

4 requisições GET foram enviadas. O endereço foi 10.216.8.100

#### 17. Can you tell whether your browser downloaded the two images serially, or whether they were downloaded from the two web sites in parallel? Explain.

Analisando os tempos, é possível perceber que os downloads foram em paralelo, pois o download da primeira imagem foi solicitado no tempo 1.999151 e finalizado no tempo 2.146213. Enquanto isso, o download da segunda imagem foi solicitado no tempo 2.026699 e finalizado no tempo 3.428390, pois a segunda imagem mudou de localização e por isso foi feito um quarto GET para o real endereço da imagem, uma vez que o terceiro retornou a nova localização desta.

---

#### 5 HTTP Authentication

##### Mensagens capturadas:

![enter image description here](https://lh3.googleusercontent.com/uzrNeSxpaH5P_PD1Hcl8MGT0U7Eo1AAUkAFcpuBt6FZAE_GIBk8zxt74nDn2bSgIhhwvlGnmlJE)

##### Response 1:

![enter image description here](https://lh3.googleusercontent.com/4q6aWSMbYx2jrfXz2mSWZ1iv6RjyKIx2XAr_q2_wlFhllPzxK8BuKCab47cNGPof1K9KTE7QSmk)

##### GET 2:

![enter image description here](https://lh3.googleusercontent.com/0LiJTqPJ438PurNf14HUd5eeI97EiEb959LSXFA2qpQOGPQapNemMIhdLrr4QIWVhIgVWAYl8Vs)

#### 18. What is the server’s response (status code and phrase) in response to the initial HTTP GET message from your browser? 

401 - Unauthorized, conforme os itens Status Code e Status Response.

#### 19. When your browser’s sends the HTTP GET message for the second time, what new field is included in the HTTP GET message?

O novo campo incluído é o Authorization, que contém as credenciais de autenticação.

---






