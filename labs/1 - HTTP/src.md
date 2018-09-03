### 2. The HTTP CONDITIONAL GET/response interaction

#### 8. Inspect the contents of the first HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE” line in the HTTP GET?

Esta linha não existe no primeiro GET.

#### 9. Inspect the contents of the server response. Did the server explicitly return the contents of the file? How can you tell?

Sim, pois é possível expandir o item Line-based text data: text/html (10 lines) e obter o conteúdo da página.

#### 10. Now inspect the contents of the second HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE:” line in the HTTP GET? If so, what information follows the “IF-MODIFIED-SINCE:” header?

Sim, o contéudo deste item é:  Mon, 03 Sep 2018 05:59:01 GMT.

#### 11. What is the HTTP status code and phrase returned from the server in response to this second HTTP GET? Did the server explicitly return the contents of the file? Explain.

O status retornado é o 304 - Not Modified. O servidor não retornou o conteúdo novamente. Este fato ocorre pois o conteúdo da página não foi modificado desde o último carregamento. Isso faz com que seja desnecessário reenviar os conteúdos novamente, uma vez que o browser já está exibindo o conteúdo presente no servidor. Isso otimiza e descongestiona a rede, uma vez que conteúdos redundantes não são reenviados desnecessariamente.

### 3. Retrieving Long Documents

#### 12. How many HTTP GET request messages did your browser send? Which packet number in the trace contains the GET message for the Bill of Rights?

Apenas 1 GET foi enviado. O pacote 215, conforme item [Request in frame: 215]

#### 13. Which packet number in the trace contains the status code and phrase associated with the response to the HTTP GET request?

O pacote 215, conforme item [Request in frame: 215]

#### 14. What is the status code and phrase in the response?

200 - OK, conforme itens Status Code: 200 e Response Phrase: OK.

#### 15. How many data-containing TCP segments were needed to carry the single HTTP response and the text of the Bill of Rights?

4 segmentos foram necessários, conforme item Segment count. 

### 4. HTML Documents with Embedded Objects

#### 16. How many HTTP GET request messages did your browser send? To which Internet addresses were these GET requests sent? 

4 requisições GET foram enviadas. O endereço foi 10.216.8.100

#### 17. Can you tell whether your browser downloaded the two images serially, or whether they were downloaded from the two web sites in parallel? Explain.

Analisando os tempos, é possível perceber que os downloads foram em paralelo, pois o download da primeira imagem foi solicitado no tempo 1.999151 e finalizado no tempo 2.146213. Enquanto isso, o download da segunda imagem foi solicitado no tempo 2.026699 e finalizado no tempo 3.428390, pois a segunda imagem mudou de localização e por isso foi feito um quarto GET para o real endereço da imagem, uma vez que o terceiro retornou a nova localização desta.

### 5 HTTP Authentication

#### 18. What is the server’s response (status code and phrase) in response to the initial HTTP GET message from your browser? 

401 - Unauthorized, conforme os itens Status Code e Status Response.

#### 19. When your browser’s sends the HTTP GET message for the second time, what new field is included in the HTTP GET message?

O novo campo incluído é o Authorization, que contém as credenciais de autenticação.