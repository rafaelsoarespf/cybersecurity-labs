# Wireshark: HTTP Traffic Analysis

## 🇺🇸 English

### Objective

Analyze HTTP traffic using Wireshark to understand HTTP requests and responses, examine message headers, and identify information exchanged between a client and a web server.

### Tools and Resources

- **Wireshark:** Network protocol analyzer.
- **Capture file:** `http.cap` (used locally for analysis).
- **Data source:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Analysis

The capture was inspected using the display filter `http`. Four HTTP packets were displayed, including two requests and two successful responses.

#### HTTP Request — Packet 4

The first observed request was a `GET` request for `/download.html`.

- **HTTP method:** `GET`
- **Request URI:** `/download.html`
- **HTTP version:** `HTTP/1.1`
- **Source IP:** `145.254.160.237`
- **Destination IP:** `65.208.228.223`
- **Source port:** `3372`
- **Destination port:** `80`
- **Host:** `www.ethereal.com`
- **User-Agent:** A Mozilla-compatible browser identifying itself as Windows NT 5.1.

The request also included headers such as `Accept`, `Accept-Language`, `Accept-Encoding`, `Connection`, and `Referer`.

#### HTTP Response — Packet 38

Packet 38 was identified as the response to the request in packet 4.

- **HTTP version:** `HTTP/1.1`
- **Status code:** `200 OK`
- **Server:** Apache
- **Content-Type:** `text/html; charset=ISO-8859-1`
- **Content-Length:** `18070` bytes
- **Request-to-response time:** Approximately `3.936` seconds.

The response contained HTML content for the requested page. Wireshark associated the response with packet 4, allowing the request and response to be correlated.

#### Additional HTTP Traffic

Two additional HTTP packets were observed:

- **Packet 18:** A `GET` request to `pagead2.googlesyndication.com` for an advertising resource.
- **Packet 27:** An `HTTP/1.1 200 OK` response associated with packet 18.

The response in packet 27 included headers such as `Content-Type`, `Content-Encoding`, `Server`, and `Content-Length`.

### Key Findings

- Identified HTTP `GET` requests and their corresponding responses.
- Examined HTTP request headers, including `Host`, `User-Agent`, and `Referer`.
- Identified the `200 OK` status code, indicating successful HTTP responses.
- Examined response metadata, including server information, content type, and content length.
- Observed that unencrypted HTTP traffic can expose readable request details and response content.
- Correlated HTTP requests and responses using Wireshark's packet references.

### Conclusion

This activity provided practical experience analyzing HTTP traffic in Wireshark. It demonstrated how to inspect request methods, headers, response status codes, and server responses, as well as how to correlate requests with their corresponding responses.

### Data Source and Attribution

The `http.cap` file was obtained from the [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) collection and used locally for educational packet analysis.

The capture is not included in this repository. Consult the original source for applicable licensing and redistribution conditions before redistributing the file.

---

## 🇧🇷 Português (Brasil)

### Objetivo

Analisar o tráfego HTTP utilizando o Wireshark para compreender solicitações e respostas HTTP, examinar os cabeçalhos das mensagens e identificar informações trocadas entre um cliente e um servidor web.

### Ferramentas e recursos

- **Wireshark:** Analisador de protocolos de rede.
- **Arquivo de captura:** `http.cap` (utilizado localmente para a análise).
- **Fonte dos dados:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Análise

A captura foi examinada utilizando o filtro de exibição `http`. Foram exibidos quatro pacotes HTTP, incluindo duas solicitações e duas respostas bem-sucedidas.

#### Solicitação HTTP — Pacote 4

A primeira solicitação observada foi uma requisição `GET` para `/download.html`.

- **Método HTTP:** `GET`
- **URI solicitada:** `/download.html`
- **Versão HTTP:** `HTTP/1.1`
- **IP de origem:** `145.254.160.237`
- **IP de destino:** `65.208.228.223`
- **Porta de origem:** `3372`
- **Porta de destino:** `80`
- **Host:** `www.ethereal.com`
- **User-Agent:** Navegador compatível com Mozilla, identificando-se como Windows NT 5.1.

A solicitação também continha cabeçalhos como `Accept`, `Accept-Language`, `Accept-Encoding`, `Connection` e `Referer`.

#### Resposta HTTP — Pacote 38

O pacote 38 foi identificado como a resposta à solicitação do pacote 4.

- **Versão HTTP:** `HTTP/1.1`
- **Código de status:** `200 OK`
- **Servidor:** Apache
- **Content-Type:** `text/html; charset=ISO-8859-1`
- **Content-Length:** `18070` bytes
- **Tempo entre solicitação e resposta:** Aproximadamente `3,936` segundos.

A resposta continha conteúdo HTML referente à página solicitada. O Wireshark associou a resposta ao pacote 4, permitindo correlacionar a solicitação e a resposta.

#### Tráfego HTTP adicional

Foram observados outros dois pacotes HTTP:

- **Pacote 18:** Uma solicitação `GET` para `pagead2.googlesyndication.com`, requisitando um recurso publicitário.
- **Pacote 27:** Uma resposta `HTTP/1.1 200 OK` associada ao pacote 18.

A resposta do pacote 27 continha cabeçalhos HTTP como `Content-Type`, `Content-Encoding`, `Server` e `Content-Length`.

### Principais descobertas

- Identificação de solicitações HTTP `GET` e suas respectivas respostas.
- Análise de cabeçalhos HTTP, incluindo `Host`, `User-Agent` e `Referer`.
- Identificação do código de status `200 OK`, indicando respostas HTTP bem-sucedidas.
- Análise de metadados das respostas, incluindo informações do servidor, tipo e tamanho do conteúdo.
- Observação de que o tráfego HTTP sem criptografia pode expor detalhes legíveis das solicitações e o conteúdo das respostas.
- Correlação entre solicitações e respostas utilizando as referências de pacotes do Wireshark.

### Conclusão

Esta atividade proporcionou experiência prática na análise de tráfego HTTP com o Wireshark. Demonstrou como inspecionar métodos de solicitação, cabeçalhos, códigos de status e respostas do servidor, além de correlacionar solicitações com suas respectivas respostas.

### Fonte dos dados e atribuição

O arquivo `http.cap` foi obtido na coleção [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) e utilizado localmente para análise educacional de pacotes.

A captura não está incluída neste repositório. Consulte a fonte original para verificar as condições de licenciamento e redistribuição aplicáveis antes de redistribuir o arquivo.