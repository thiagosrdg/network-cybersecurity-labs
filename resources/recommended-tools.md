# Ferramentas Recomendadas

Ferramentas complementares que podem ser utilizadas ao longo dos
laboratórios deste repositório, além do próprio Wireshark. A lista tem
finalidade defensiva e educacional — nenhuma ferramenta listada é
apresentada como requisito para uso ofensivo.

## Wireshark

Analisador de protocolos de rede com interface gráfica, utilizado como
ferramenta principal deste repositório para inspecionar capturas de
tráfego, aplicar filtros e investigar o comportamento de protocolos em
detalhe.

## TShark

Versão de linha de comando do Wireshark, útil para automação, análise em
servidores sem interface gráfica e processamento de capturas em scripts.

## tcpdump

Ferramenta de captura de pacotes via linha de comando, amplamente
disponível em sistemas Unix-like. Frequentemente utilizada para gerar
capturas `.pcap` em ambientes de laboratório que depois são analisadas em
detalhe no Wireshark.

## Nmap

Ferramenta de descoberta de rede e varredura de portas. Neste repositório,
é mencionada apenas como geradora de tráfego controlado em laboratórios
próprios (ex.: para estudar como uma varredura de portas se manifesta em
uma captura), e não como ferramenta de ataque a terceiros.

## Zeek

Framework de análise de tráfego de rede voltado a monitoramento de
segurança, capaz de gerar logs estruturados de conexões e protocolos a
partir de capturas de tráfego. Útil como complemento ao Wireshark em
análises de maior escala.

## NetworkMiner

Ferramenta de análise forense de rede que extrai artefatos (arquivos,
credenciais, sessões) a partir de capturas `.pcap`. Utilizada para
complementar a investigação manual feita no Wireshark, sempre em
ambientes de laboratório controlados.

## CyberChef

Aplicação web para transformação, decodificação e análise de dados (ex.:
decodificação Base64, hashes, extração de payloads). Útil para examinar
conteúdos extraídos de pacotes durante uma investigação.

## Python

Linguagem utilizada para automatizar tarefas de análise, processar
capturas programaticamente (ex.: com bibliotecas como `pyshark`) e apoiar
a geração de relatórios técnicos.

## Scapy

Biblioteca Python para criação, manipulação e envio de pacotes de rede.
Utilizada em laboratórios controlados para gerar tráfego sintético
específico (ex.: pacotes ICMP customizados) que depois é analisado no
Wireshark.
