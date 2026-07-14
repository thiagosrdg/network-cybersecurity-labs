# Laboratórios

Este diretório reúne todos os laboratórios práticos de análise de tráfego
de rede com Wireshark. Cada laboratório é independente, mas todos seguem a
mesma estrutura de documentação, definida em
[templates/lab-template.md](../templates/lab-template.md), e a mesma
[metodologia de análise](../docs/network-analysis-methodology.md).

## Estrutura de cada laboratório

```text
labs/NN-nome-do-laboratorio/
├── README.md         # Documentação completa do laboratório
├── captures/          # Arquivos .pcap/.pcapng anonimizados (quando aplicável)
└── screenshots/        # Evidências visuais anonimizadas (quando aplicável)
```

Os diretórios `captures/` e `screenshots/` contêm um arquivo `.gitkeep`
enquanto não houver material real, para manter a estrutura versionada no
Git.

## Lista de laboratórios

| # | Laboratório | Protocolo/Tema | Status |
|---|---|---|---|
| 01 | [ICMP Analysis](01-icmp-analysis/README.md) | ICMP | `Planned` |
| 02 | [DNS Analysis](02-dns-analysis/README.md) | DNS | `Planned` |
| 03 | [TCP Three-Way Handshake](03-tcp-three-way-handshake/README.md) | TCP | `Planned` |
| 04 | [HTTP Traffic Analysis](04-http-traffic-analysis/README.md) | HTTP | `Planned` |
| 05 | [Suspicious Traffic Analysis](05-suspicious-traffic-analysis/README.md) | Diversos | `Planned` |

Antes de adicionar capturas ou screenshots a qualquer laboratório, leia
[docs/packet-capture-safety.md](../docs/packet-capture-safety.md).
