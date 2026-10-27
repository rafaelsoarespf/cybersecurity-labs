# Wireshark: DNS Traffic Analysis

## 🇺🇸 English

### Objective

Analyze DNS traffic using Wireshark to understand DNS queries and responses, identify resource records, and examine how domain names are resolved to IP addresses.

### Tools and Resources

- **Wireshark:** Network protocol analyzer.
- **Capture file:** `dns_port.pcap` (used locally for analysis).
- **Data source:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Analysis

The capture was inspected using the display filter `dns`. Two DNS packets were observed: a query and its corresponding response.

The query requested IPv4 address records for `us.pool.ntp.org`.

#### DNS Query

- **Query name:** `us.pool.ntp.org`
- **Query type:** A (IPv4 address)
- **Transaction ID:** `0x002b`
- **Transport protocol:** UDP
- **Source IP:** `192.168.50.50`
- **Destination IP:** `192.168.0.1`
- **Source port:** `65282`
- **Destination port:** `65333`

#### DNS Response

The response used the same transaction ID, `0x002b`, allowing it to be correlated with the query.

The response contained 15 answer records of type A, as well as NS records in the authority section and additional address records.

Examples of observed IPv4 addresses included:

| Queried name | Observed IPv4 address |
|---|---|
| `us.pool.ntp.org` | `67.129.68.9` |
| `us.pool.ntp.org` | `69.44.57.60` |
| `us.pool.ntp.org` | `207.234.209.181` |
| `us.pool.ntp.org` | `209.132.176.4` |
| `us.pool.ntp.org` | `216.27.185.42` |

The observed query-to-response time was approximately **6.946 milliseconds**.

The DNS query used UDP destination port `65333` instead of the conventional DNS port `53`. This capture therefore provides an example of DNS traffic using a non-standard port.

### Key Findings

- Identified a DNS query and its corresponding response.
- Examined the transaction ID used to correlate the two packets.
- Identified A records, NS records, and additional address records.
- Observed multiple IPv4 addresses associated with `us.pool.ntp.org`.
- Examined DNS traffic using a non-standard destination port.

### Conclusion

This activity provided practical experience inspecting DNS traffic in Wireshark and interpreting DNS message fields and resource records. It also demonstrated that DNS traffic can use a non-standard port.

### Data Source and Attribution

The `dns_port.pcap` file was obtained from the [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) collection and used for educational packet analysis.

The capture was used locally for this investigation. Please consult the original source for applicable licensing and redistribution conditions before redistributing the file.

---

## 🇧🇷 Português (Brasil)

### Objetivo

Analisar o tráfego DNS utilizando o Wireshark para compreender consultas e respostas DNS, identificar registros de recursos e examinar como nomes de domínio são associados a endereços IP.

### Ferramentas e recursos

- **Wireshark:** Analisador de protocolos de rede.
- **Arquivo de captura:** `dns_port.pcap` (utilizado localmente para a análise).
- **Fonte dos dados:** [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).

### Análise

A captura foi examinada utilizando o filtro de exibição `dns`. Foram observados dois pacotes DNS: uma consulta e sua resposta correspondente.

A consulta solicitou registros de endereço IPv4 para `us.pool.ntp.org`.

#### Consulta DNS

- **Nome consultado:** `us.pool.ntp.org`
- **Tipo de consulta:** A (endereço IPv4)
- **ID da transação:** `0x002b`
- **Protocolo de transporte:** UDP
- **IP de origem:** `192.168.50.50`
- **IP de destino:** `192.168.0.1`
- **Porta de origem:** `65282`
- **Porta de destino:** `65333`

#### Resposta DNS

A resposta utilizou o mesmo ID de transação, `0x002b`, permitindo relacioná-la à consulta.

A resposta continha 15 registros de resposta do tipo A, além de registros NS na seção de autoridade e registros adicionais de endereço.

Exemplos de endereços IPv4 observados:

| Nome consultado | Endereço IPv4 observado |
|---|---|
| `us.pool.ntp.org` | `67.129.68.9` |
| `us.pool.ntp.org` | `69.44.57.60` |
| `us.pool.ntp.org` | `207.234.209.181` |
| `us.pool.ntp.org` | `209.132.176.4` |
| `us.pool.ntp.org` | `216.27.185.42` |

O intervalo observado entre a consulta e a resposta foi de aproximadamente **6,946 milissegundos**.

A consulta DNS utilizou a porta UDP de destino `65333`, em vez da porta convencional `53`. Portanto, essa captura oferece um exemplo de tráfego DNS utilizando uma porta não convencional.

### Principais descobertas

- Identificação de uma consulta DNS e sua resposta correspondente.
- Análise do ID de transação utilizado para correlacionar os dois pacotes.
- Identificação de registros A, NS e registros adicionais de endereço.
- Observação de múltiplos endereços IPv4 associados a `us.pool.ntp.org`.
- Análise de tráfego DNS utilizando uma porta de destino não convencional.

### Conclusão

Esta atividade proporcionou experiência prática na inspeção de tráfego DNS com o Wireshark e na interpretação dos campos das mensagens e dos registros de recursos DNS. Também demonstrou que o tráfego DNS pode utilizar uma porta não convencional.

### Fonte dos dados e atribuição

O arquivo `dns_port.pcap` foi obtido na coleção [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) e utilizado para análise educacional de pacotes.

A captura foi utilizada localmente nesta investigação. Consulte a fonte original para verificar as condições de licenciamento e redistribuição aplicáveis antes de redistribuir o arquivo.