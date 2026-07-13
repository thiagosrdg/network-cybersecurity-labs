# Filtros de Exibição do Wireshark (Display Filters)

Display filters são aplicados **após a captura**, na barra de filtros do
Wireshark, para exibir apenas os pacotes relevantes dentro de uma captura
já realizada. Eles não reduzem o que é capturado, apenas o que é exibido.

Para a diferença entre display filters e capture filters, veja
[wireshark-capture-filters.md](wireshark-capture-filters.md).

## Ethernet

| Filtro | Descrição |
|---|---|
| `eth.addr == aa:bb:cc:dd:ee:ff` | Exibe frames com o MAC informado (origem ou destino). |
| `eth.src == aa:bb:cc:dd:ee:ff` | Exibe frames com o MAC de origem informado. |
| `eth.dst == aa:bb:cc:dd:ee:ff` | Exibe frames com o MAC de destino informado. |
| `eth.type == 0x0800` | Exibe frames Ethernet transportando IPv4. |

## ARP

| Filtro | Descrição |
|---|---|
| `arp` | Exibe todo o tráfego ARP. |
| `arp.opcode == 1` | Exibe requisições ARP (*who-has*). |
| `arp.opcode == 2` | Exibe respostas ARP (*is-at*). |
| `arp.duplicate-address-detected` | Sinaliza possíveis conflitos de endereço IP detectados pelo Wireshark. |

## IPv4

| Filtro | Descrição |
|---|---|
| `ip` | Exibe todo o tráfego IPv4. |
| `ip.addr == 192.168.1.10` | Exibe pacotes com o IP informado (origem ou destino). |
| `ip.src == 192.168.1.10` | Exibe pacotes com o IP de origem informado. |
| `ip.dst == 192.168.1.10` | Exibe pacotes com o IP de destino informado. |
| `ip.ttl < 10` | Exibe pacotes com TTL baixo (útil para investigar rotas/traceroute). |

## IPv6

| Filtro | Descrição |
|---|---|
| `ipv6` | Exibe todo o tráfego IPv6. |
| `ipv6.addr == fe80::1` | Exibe pacotes IPv6 com o endereço informado. |
| `ipv6.src == fe80::1` | Exibe pacotes IPv6 com o endereço de origem informado. |

## ICMP

| Filtro | Descrição |
|---|---|
| `icmp` | Exibe todo o tráfego ICMP. |
| `icmp.type == 8` | Exibe mensagens Echo Request. |
| `icmp.type == 0` | Exibe mensagens Echo Reply. |
| `icmp.type == 3` | Exibe mensagens Destination Unreachable. |
| `icmp.type == 11` | Exibe mensagens Time Exceeded (comum em traceroute). |

## DNS

| Filtro | Descrição |
|---|---|
| `dns` | Exibe todo o tráfego DNS. |
| `dns.flags.response == 0` | Exibe apenas consultas (queries). |
| `dns.flags.response == 1` | Exibe apenas respostas. |
| `dns.qry.name == "exemplo.com"` | Exibe consultas para um nome específico. |
| `dns.flags.rcode != 0` | Exibe respostas DNS com código de erro (ex.: NXDOMAIN). |

## TCP

| Filtro | Descrição |
|---|---|
| `tcp` | Exibe todo o tráfego TCP. |
| `tcp.port == 443` | Exibe tráfego TCP na porta 443 (origem ou destino). |
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Exibe pacotes SYN (início de conexão). |
| `tcp.flags.syn == 1 && tcp.flags.ack == 1` | Exibe pacotes SYN-ACK. |
| `tcp.flags.reset == 1` | Exibe pacotes com a flag RST (conexão resetada). |
| `tcp.analysis.retransmission` | Exibe retransmissões identificadas pelo Wireshark. |
| `tcp.analysis.zero_window` | Exibe situações de janela zero (possível congestionamento). |

## UDP

| Filtro | Descrição |
|---|---|
| `udp` | Exibe todo o tráfego UDP. |
| `udp.port == 53` | Exibe tráfego UDP na porta 53 (DNS). |
| `udp.length > 512` | Exibe datagramas UDP maiores que 512 bytes. |

## HTTP

| Filtro | Descrição |
|---|---|
| `http` | Exibe todo o tráfego HTTP. |
| `http.request` | Exibe apenas requisições HTTP. |
| `http.response` | Exibe apenas respostas HTTP. |
| `http.request.method == "GET"` | Exibe requisições GET. |
| `http.request.method == "POST"` | Exibe requisições POST. |
| `http.response.code >= 400` | Exibe respostas com erro de cliente ou servidor. |

## TLS

| Filtro | Descrição |
|---|---|
| `tls` | Exibe todo o tráfego TLS. |
| `tls.handshake.type == 1` | Exibe mensagens *Client Hello*. |
| `tls.handshake.type == 2` | Exibe mensagens *Server Hello*. |
| `tls.alert_message` | Exibe alertas TLS (possíveis falhas de handshake). |

> Observação: por padrão, o conteúdo de sessões TLS não é legível sem as
> chaves de sessão. A análise aqui se limita a metadados do handshake.

## DHCP

| Filtro | Descrição |
|---|---|
| `dhcp` | Exibe todo o tráfego DHCP. |
| `dhcp.option.dhcp == 1` | Exibe mensagens DHCP Discover. |
| `dhcp.option.dhcp == 2` | Exibe mensagens DHCP Offer. |
| `dhcp.option.dhcp == 3` | Exibe mensagens DHCP Request. |
| `dhcp.option.dhcp == 5` | Exibe mensagens DHCP Ack. |

## Análise de erros

| Filtro | Descrição |
|---|---|
| `tcp.analysis.flags` | Exibe pacotes marcados pelo Wireshark com alguma condição de análise (erros, retransmissões etc.). |
| `_ws.expert.severity == "error"` | Exibe pacotes classificados como erro pelo Expert Info. |
| `icmp.type == 3` | Exibe mensagens de erro ICMP (destino inalcançável). |

## Retransmissões

| Filtro | Descrição |
|---|---|
| `tcp.analysis.retransmission` | Exibe todas as retransmissões TCP identificadas. |
| `tcp.analysis.fast_retransmission` | Exibe retransmissões rápidas (fast retransmit). |
| `tcp.analysis.duplicate_ack` | Exibe ACKs duplicados, indicando possível perda de pacotes. |

## Combinação de filtros

| Filtro | Descrição |
|---|---|
| `ip.addr == 192.168.1.10 && tcp.port == 443` | Combina host e porta específicos. |
| `tcp.flags.syn == 1 && ip.dst == 192.168.1.20` | Exibe tentativas de conexão para um host específico. |
| `http.request && ip.src == 192.168.1.30` | Exibe requisições HTTP originadas de um host específico. |
| `dns.flags.rcode != 0 && dns.flags.response == 1` | Exibe apenas respostas DNS com erro. |

Estes filtros são um ponto de partida. Cada laboratório documenta, em sua
própria seção "Filtros utilizados", os filtros efetivamente aplicados
durante a análise.
