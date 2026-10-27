# Wireshark: DHCP Traffic Analysis

## 🇺🇸 English

### Objective

Analyze DHCP traffic using Wireshark to understand the dynamic IP address assignment process and identify relevant network information.

### Tools and Resources

- **Wireshark:** Network protocol analyzer.
- **Capture file:** `dhcp.pcapng` (used locally for analysis).
- **Data source:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Analysis

The capture was inspected to identify DHCP messages and examine relevant protocol fields.

The following messages were observed:

- **DHCP Discover:** The client searched for a DHCP server.
- **DHCP Offer:** The server offered the IP address `192.168.0.10`.
- **DHCP Request:** The client requested the offered configuration.
- **DHCP ACK:** The server acknowledged the configuration.

#### Observed Network Information

| Field | Observed value |
|---|---|
| DHCP server | `192.168.0.1` |
| Offered client IP | `192.168.0.10` |
| Subnet mask | `255.255.255.0` |
| Client MAC address | `00:0b:82:01:fc:42` |

The capture also showed DHCP communication over UDP ports 67 and 68.

#### Transaction ID Observation

The DHCP Discover and Offer packets share transaction ID `0x00003d1d`, while the Request and ACK packets use transaction ID `0x00003d1e`.

Therefore, the capture does not establish that all four messages belong to the same DHCP transaction. The observed messages are documented individually without assuming that they represent a single complete negotiation.

### Key Findings

The capture illustrates how DHCP messages support dynamic network configuration. The observed IP addresses belong to the sample capture and do not necessarily represent the analyst's actual network.

The differing transaction IDs highlight the importance of correlating packet fields before drawing conclusions about a network exchange.

### Conclusion

This activity provided practical experience identifying DHCP messages, examining packet fields, and interpreting transaction identifiers in Wireshark.

### Evidence

Screenshots documenting the packet overview and the details of the DHCP Discover, Offer, Request, and ACK messages are available in the `evidence/` directory.

### Data Source and Attribution

The `dhcp.pcapng` file was obtained from the [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) collection and used for educational packet analysis.

The capture file is not included in this repository. Please consult the original source for applicable licensing and redistribution conditions before redistributing the file.

---

## 🇧🇷 Português (Brasil)

### Objetivo

Analisar o tráfego DHCP utilizando o Wireshark para compreender o processo de atribuição dinâmica de endereços IP e identificar informações relevantes da rede.

### Ferramentas e recursos

- **Wireshark:** Analisador de protocolos de rede.
- **Arquivo de captura:** `dhcp.pcapng` (utilizado localmente para análise).
- **Fonte dos dados:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Análise

A captura foi examinada para identificar mensagens DHCP e analisar os campos relevantes do protocolo.

Foram observadas as seguintes mensagens:

- **DHCP Discover:** O cliente procurou um servidor DHCP.
- **DHCP Offer:** O servidor ofereceu o endereço IP `192.168.0.10`.
- **DHCP Request:** O cliente solicitou a configuração oferecida.
- **DHCP ACK:** O servidor confirmou a configuração.

#### Informações de rede observadas

| Campo | Valor observado |
|---|---|
| Servidor DHCP | `192.168.0.1` |
| IP oferecido ao cliente | `192.168.0.10` |
| Máscara de sub-rede | `255.255.255.0` |
| Endereço MAC do cliente | `00:0b:82:01:fc:42` |

A captura também apresentou comunicação DHCP utilizando as portas UDP 67 e 68.

#### Observação sobre os identificadores de transação

Os pacotes DHCP Discover e Offer compartilham o identificador de transação `0x00003d1d`, enquanto Request e ACK utilizam o identificador `0x00003d1e`.

Portanto, a captura não comprova que as quatro mensagens pertencem à mesma transação DHCP. As mensagens observadas são documentadas individualmente, sem presumir que representam uma única negociação completa.

### Principais descobertas

A captura demonstra como as mensagens DHCP são utilizadas durante a configuração dinâmica de uma rede. Os endereços IP observados pertencem à captura de exemplo e não necessariamente representam a rede real do analista.

A diferença entre os identificadores de transação destaca a importância de correlacionar os campos dos pacotes antes de tirar conclusões sobre uma comunicação de rede.

### Conclusão

Esta atividade proporcionou experiência prática na identificação de mensagens DHCP, na análise dos campos dos pacotes e na interpretação de identificadores de transação utilizando o Wireshark.

### Evidências

As capturas de tela que documentam a visão geral dos pacotes e os detalhes das mensagens DHCP Discover, Offer, Request e ACK estão disponíveis no diretório `evidence/`.

### Fonte dos dados e atribuição

O arquivo `dhcp.pcapng` foi obtido na coleção [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) e utilizado para análise educacional de pacotes.

O arquivo de captura não está incluído neste repositório. Consulte a fonte original para verificar as condições de licenciamento e redistribuição aplicáveis antes de redistribuir o arquivo.