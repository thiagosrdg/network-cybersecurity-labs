# Referência de Protocolos

Resumo dos principais protocolos utilizados nos laboratórios deste
repositório, com foco nos aspectos relevantes para análise de tráfego.

## Ethernet

Protocolo de camada de enlace responsável pelo endereçamento físico (MAC)
e pelo encapsulamento de pacotes para transmissão em redes locais.
Campos relevantes: endereço MAC de origem/destino, EtherType.

## ARP (Address Resolution Protocol)

Protocolo utilizado para associar endereços IP a endereços MAC em uma
rede local. Composto basicamente por requisições (*who-has*) e respostas
(*is-at*). Frequentemente analisado em investigações de ARP spoofing.

## IPv4

Protocolo de camada de rede responsável pelo endereçamento lógico e
roteamento de pacotes. Campos relevantes: endereço IP de origem/destino,
TTL, protocolo encapsulado, flags de fragmentação.

## IPv6

Sucessor do IPv4, com espaço de endereçamento expandido (128 bits) e
simplificação de alguns campos de cabeçalho. Utiliza endereços como
`fe80::/10` (link-local) e prefixos globais roteáveis.

## ICMP (Internet Control Message Protocol)

Protocolo utilizado para diagnóstico e relato de erros de rede (ex.:
`ping`, mensagens de destino inalcançável, time exceeded). Não é orientado
a conexão e não possui portas.

## TCP (Transmission Control Protocol)

Protocolo de camada de transporte orientado a conexão, responsável por
garantir entrega confiável e ordenada de dados. Utiliza o
*three-way handshake* (SYN, SYN-ACK, ACK) para estabelecer conexões e
possui mecanismos de controle de fluxo, retransmissão e encerramento
gracioso (FIN) ou abrupto (RST).

## UDP (User Datagram Protocol)

Protocolo de camada de transporte não orientado a conexão, mais simples e
com menor overhead que o TCP. Não garante entrega, ordem ou controle de
fluxo. Utilizado por protocolos como DNS e serviços sensíveis à latência.

## DNS (Domain Name System)

Protocolo responsável pela resolução de nomes de domínio em endereços IP
(e vice-versa). Opera tipicamente sobre UDP na porta 53 (com fallback
para TCP em respostas maiores). Estrutura básica: consultas (queries) e
respostas (responses), com diferentes tipos de registro (A, AAAA, CNAME,
MX, entre outros) e códigos de retorno (ex.: `NOERROR`, `NXDOMAIN`).

## HTTP (Hypertext Transfer Protocol)

Protocolo de camada de aplicação utilizado para comunicação web, baseado
em requisições e respostas. Opera tipicamente sobre a porta 80, em texto
claro — por isso, credenciais e dados sensíveis nunca devem trafegar por
HTTP sem criptografia (ver [Lab 04](../labs/04-http-traffic-analysis/README.md)).

## HTTPS/TLS

HTTPS é o HTTP operando sobre uma camada de criptografia TLS, tipicamente
na porta 443. O TLS estabelece uma sessão criptografada por meio de um
handshake (*Client Hello*, *Server Hello*, troca de certificados e chaves)
antes da transmissão de dados da aplicação. Sem as chaves de sessão, o
conteúdo da comunicação não é legível na captura — apenas os metadados do
handshake.

## DHCP (Dynamic Host Configuration Protocol)

Protocolo utilizado para atribuição automática de endereços IP e outras
configurações de rede a hosts em uma rede local. Segue tipicamente o fluxo
*Discover, Offer, Request, Ack* (DORA), operando sobre UDP nas portas 67 e
68.
