# Laboratórios — Nmap

Este diretório reúne os laboratórios práticos de scanning e enumeração de
rede com o Nmap. Cada laboratório segue a mesma estrutura de documentação,
definida em [templates/lab-template.md](../templates/lab-template.md), e
respeita as diretrizes de
[docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md).

## Estrutura de cada laboratório

```text
labs/NN-nome-do-laboratorio/
├── README.md         # Documentação completa do laboratório
├── outputs/            # Saídas do Nmap (-oN/-oX/-oG) anonimizadas
└── screenshots/         # Evidências visuais anonimizadas
```

Os diretórios `outputs/` e `screenshots/` contêm um arquivo `.gitkeep`
enquanto não houver material real, para manter a estrutura versionada no
Git.

## Lista de laboratórios

| # | Laboratório | Técnica/Tema | Status |
|---|---|---|---|
| 01 | [Host Discovery and Port Scanning](01-host-discovery-and-port-scanning/README.md) | Descoberta de hosts e varredura de portas | `Planned` |

Antes de adicionar saídas de scan ou screenshots a qualquer laboratório,
leia [docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md).
