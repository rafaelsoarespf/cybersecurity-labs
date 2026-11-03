# Wireshark: TCP Traffic Analysis

## 🇺🇸 English

### Objective

Analyze TCP traffic using Wireshark to understand connection behavior, data transmission, acknowledgments, connection termination, and TCP window scaling negotiation.

### Tools and Resources

- **Wireshark:** Network protocol analyzer.
- **Capture file:** `200722_win_scale_examples_anon.pcapng` (used locally for analysis).
- **Data source:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Analysis

The capture was examined to identify TCP connections and inspect representative packets, focusing on TCP flags, sequence numbers, acknowledgment numbers, and window scaling options.

#### Data Transmission and Acknowledgment

In the first connection, a packet with the `PSH, ACK` flags transmitted 6 bytes of application data.

The payload contained the ASCII text `hello\n`.

The packet used sequence number `1`, and the receiver subsequently acknowledged the data with acknowledgment number `7`, indicating that the next expected byte was sequence number 7.

This illustrates how TCP uses sequence and acknowledgment numbers to track reliable data delivery.

#### Connection Termination

The first connection also demonstrated the TCP connection termination process using `FIN, ACK` and `ACK` packets.

The observed exchange showed:

- The server sent a `FIN, ACK` packet to initiate termination.
- The client acknowledged the server's FIN.
- The client then sent its own `FIN, ACK`.
- The server acknowledged the client's FIN.

A FIN flag consumes one sequence number, even when the packet carries no application data.

#### TCP Window Scaling

The capture contained connections with different Window Scaling negotiation outcomes.

In the second connection, the client announced a Window Scale factor of 8 (multiplier 256) in its SYN packet. However, the server's SYN/ACK did not include the Window Scale option.

Therefore, Window Scaling was not negotiated for that connection. The option must be supported and announced by both endpoints during the connection establishment process.

This demonstrates why examining both SYN and SYN/ACK packets is important when analyzing TCP options.

### Key Findings

- TCP uses sequence numbers and acknowledgments to track transmitted data.
- The `PSH, ACK` flags were observed during application data transmission.
- The `FIN, ACK` and `ACK` exchange illustrated the TCP connection termination process.
- Window Scaling must be announced by both endpoints during the handshake to be enabled.
- A client announcing Window Scaling does not guarantee that the feature will be negotiated.

### Conclusion

This activity provided practical experience analyzing TCP communication in Wireshark, including data transmission, acknowledgment behavior, connection termination, and TCP option negotiation.

Understanding these mechanisms is relevant to network troubleshooting and cybersecurity investigations, where interpreting connection behavior can help identify abnormal or unexpected communication patterns.

### Evidence

Screenshots documenting representative TCP packets, data transmission, acknowledgment behavior, connection termination, and Window Scaling negotiation are available in the `evidence/` directory.

### Data Source and Attribution

The `200722_win_scale_examples_anon.pcapng` file was obtained from the [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) collection and used for educational packet analysis.

The capture file is not included in this repository. Please consult the original source for applicable licensing and redistribution conditions before redistributing the file.

---

## 🇧🇷 Português (Brasil)

### Objetivo

Analisar o tráfego TCP utilizando o Wireshark para compreender o comportamento das conexões, a transmissão de dados, as confirmações de recebimento, o encerramento de conexões e a negociação do TCP Window Scaling.

### Ferramentas e recursos

- **Wireshark:** Analisador de protocolos de rede.
- **Arquivo de captura:** `200722_win_scale_examples_anon.pcapng` (utilizado localmente para análise).
- **Fonte dos dados:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Análise

A captura foi examinada para identificar conexões TCP e inspecionar pacotes representativos, com foco nas flags TCP, nos números de sequência, nos números de confirmação e nas opções de Window Scaling.

#### Transmissão de dados e confirmação de recebimento

Na primeira conexão, um pacote com as flags `PSH, ACK` transmitiu 6 bytes de dados da aplicação.

O conteúdo transmitido correspondia ao texto ASCII `hello\n`.

O pacote utilizou o número de sequência `1`, e o receptor confirmou posteriormente o recebimento dos dados com o número de confirmação `7`, indicando que o próximo byte esperado era o de sequência 7.

Isso demonstra como o TCP utiliza números de sequência e confirmação para acompanhar a entrega confiável dos dados.

#### Encerramento da conexão

A primeira conexão também demonstrou o processo de encerramento de uma conexão TCP por meio de pacotes `FIN, ACK` e `ACK`.

A troca observada apresentou a seguinte sequência:

- O servidor enviou um pacote `FIN, ACK` para iniciar o encerramento.
- O cliente confirmou o recebimento do FIN enviado pelo servidor.
- Em seguida, o cliente enviou seu próprio `FIN, ACK`.
- O servidor confirmou o recebimento do FIN do cliente.

A flag FIN consome um número de sequência, mesmo quando o pacote não transporta dados da aplicação.

#### TCP Window Scaling

A captura apresentou conexões com diferentes resultados na negociação do Window Scaling.

Na segunda conexão, o cliente anunciou um fator de Window Scale igual a 8 (multiplicador 256) em seu pacote SYN. Entretanto, o pacote SYN/ACK enviado pelo servidor não incluiu a opção Window Scale.

Portanto, o Window Scaling não foi negociado nessa conexão. Para que a opção seja habilitada, ambos os dispositivos precisam suportá-la e anunciá-la durante o estabelecimento da conexão.

Isso demonstra por que é importante examinar tanto os pacotes SYN quanto os SYN/ACK ao analisar as opções TCP.

### Principais descobertas

- O TCP utiliza números de sequência e confirmação para acompanhar os dados transmitidos.
- As flags `PSH, ACK` foram observadas durante a transmissão de dados da aplicação.
- A troca de pacotes `FIN, ACK` e `ACK` demonstrou o processo de encerramento de uma conexão TCP.
- O Window Scaling precisa ser anunciado por ambos os dispositivos durante o handshake para ser habilitado.
- O anúncio do Window Scaling pelo cliente não garante que o recurso será negociado.

### Conclusão

Esta atividade proporcionou experiência prática na análise de comunicações TCP utilizando o Wireshark, incluindo transmissão de dados, comportamento das confirmações de recebimento, encerramento de conexões e negociação de opções TCP.

A compreensão desses mecanismos é relevante para a resolução de problemas de rede e investigações de cibersegurança, nas quais a interpretação do comportamento das conexões pode ajudar a identificar padrões de comunicação anormais ou inesperados.

### Evidências

As capturas de tela que documentam pacotes TCP representativos, transmissão de dados, confirmações de recebimento, encerramento de conexões e negociação do Window Scaling estão disponíveis no diretório `evidence/`.

### Fonte dos dados e atribuição

O arquivo `200722_win_scale_examples_anon.pcapng` foi obtido na coleção [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) e utilizado para análise educacional de pacotes.

O arquivo de captura não está incluído neste repositório. Consulte a fonte original para verificar as condições de licenciamento e redistribuição aplicáveis antes de redistribuir o arquivo.