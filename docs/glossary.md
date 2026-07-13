# Glossário

Termos técnicos utilizados ao longo deste repositório, com definições
resumidas para referência rápida.

**Packet (pacote)**
Unidade de dados transmitida em uma rede na camada de rede (IP), composta
por cabeçalho e payload.

**Frame (quadro)**
Unidade de dados na camada de enlace (ex.: Ethernet), que encapsula um
pacote IP para transmissão física na rede.

**Capture (captura)**
Processo de interceptar e registrar o tráfego de rede que passa por uma
interface, geralmente salvo em um arquivo `.pcap` ou `.pcapng`.

**Protocol (protocolo)**
Conjunto de regras que define como os dados são formatados, transmitidos e
interpretados entre dispositivos em uma rede (ex.: TCP, DNS, HTTP).

**Port (porta)**
Número que identifica um serviço ou aplicação específica em um host,
utilizado junto ao endereço IP para endereçar comunicações (ex.: porta 443
para HTTPS).

**Socket**
Combinação de endereço IP e porta que identifica de forma única um ponto
de comunicação em uma conexão de rede.

**Payload**
Dados efetivamente transportados por um pacote ou frame, excluindo os
cabeçalhos de protocolo.

**Header (cabeçalho)**
Parte inicial de um pacote ou frame que contém metadados de controle
(endereços, flags, tamanhos etc.), utilizados pelos protocolos para
processar a comunicação.

**Three-way handshake**
Processo de estabelecimento de uma conexão TCP, composto pelas etapas
SYN, SYN-ACK e ACK.

**Retransmission (retransmissão)**
Reenvio de um segmento TCP que não teve sua confirmação (ACK) recebida a
tempo, indicando possível perda de pacote na rede.

**TTL (Time to Live)**
Campo do cabeçalho IP que limita o número de saltos (hops) que um pacote
pode percorrer antes de ser descartado, evitando loops infinitos de
roteamento.

**DNS query (consulta DNS)**
Requisição enviada por um cliente a um servidor DNS solicitando a
resolução de um nome (ex.: para um endereço IP).

**DNS response (resposta DNS)**
Resposta enviada por um servidor DNS a uma consulta, contendo o resultado
da resolução ou um código de erro.

**Display filter (filtro de exibição)**
Filtro aplicado no Wireshark após a captura, para exibir apenas pacotes
que atendam a determinados critérios, sem alterar os dados capturados.

**Capture filter (filtro de captura)**
Filtro aplicado antes ou durante a captura, baseado em sintaxe BPF, que
determina quais pacotes serão efetivamente capturados e gravados.

**PCAP**
Formato de arquivo tradicional para armazenamento de capturas de tráfego
de rede.

**PCAPNG**
Formato de arquivo mais moderno para capturas de tráfego, sucessor do
PCAP, com suporte a múltiplas interfaces, comentários e metadados
adicionais.

**Network forensics (perícia de rede)**
Área da segurança da informação voltada à captura, preservação e análise
de tráfego de rede como evidência, com o objetivo de investigar incidentes
de segurança.

**Indicator of Compromise (IoC / indicador de comprometimento)**
Evidência técnica (ex.: endereço IP, domínio, padrão de tráfego) que
sugere a ocorrência de uma atividade maliciosa ou de um possível
comprometimento de sistema.
