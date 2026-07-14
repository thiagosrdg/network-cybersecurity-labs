# Nmap Labs

![Status](https://img.shields.io/badge/status-planejado-lightgrey)
![Foco](https://img.shields.io/badge/foco-cybersecurity-blue)
![Ferramenta](https://img.shields.io/badge/ferramenta-Nmap-2f7fd1)
![Licença](https://img.shields.io/badge/licença-MIT-green)

> Esta pasta é um dos tracks de laboratórios do repositório
> [network-cybersecurity-labs](../README.md). Veja também o track
> [wireshark/](../wireshark/README.md).

## Descrição

Este track documenta laboratórios práticos de **descoberta de rede e
varredura de portas com o Nmap**, com foco em cybersecurity, reconhecimento
de rede, enumeração de serviços e compreensão de como essas técnicas se
manifestam no tráfego de rede.

Assim como o track [wireshark/](../wireshark/README.md), o objetivo é
construir, de forma incremental e documentada, um portfólio técnico —
neste caso, com foco na perspectiva do host que realiza o scan e na
interpretação dos resultados obtidos.

Todos os laboratórios devem ser realizados exclusivamente em ambientes
próprios ou explicitamente autorizados (ver
[Aviso ético e legal](#aviso-ético-e-legal)).

## Objetivos de aprendizado

- Compreender os principais tipos de scan do Nmap (host discovery, TCP
  connect, SYN scan, UDP scan).
- Interpretar os estados de porta (`open`, `closed`, `filtered`).
- Praticar a detecção de serviços, versões e sistemas operacionais.
- Relacionar os resultados de um scan com o comportamento observado na
  camada de rede (complementando o track de Wireshark).
- Documentar análises técnicas de forma clara, objetiva e reprodutível.
- Reforçar a importância da autorização prévia em qualquer atividade de
  scanning.

## Estrutura do track

```text
nmap/
├── README.md
├── docs/                       # Segurança, ética e conceitos de apoio
├── labs/                       # Laboratórios práticos numerados
│   └── 01-host-discovery-and-port-scanning/
├── templates/                  # Modelo reutilizável para novos laboratórios
└── resources/                  # Comandos e referências úteis
```

Os arquivos `LICENSE`, `.gitignore`, `CONTRIBUTING.md` e `SECURITY.md` são
compartilhados por todos os tracks e ficam na raiz do repositório
[network-cybersecurity-labs](../README.md).

Cada laboratório em `labs/` contém:

- `README.md` — documentação completa do laboratório.
- `outputs/` — saídas do Nmap (`-oN`/`-oX`/`-oG`) anonimizadas, quando
  aplicável.
- `screenshots/` — evidências visuais anonimizadas, quando aplicável.

## Laboratórios

| # | Laboratório | Técnica/Tema | Objetivo | Status |
|---|---|---|---|---|
| 01 | [Host Discovery and Port Scanning](labs/01-host-discovery-and-port-scanning/README.md) | Host discovery, TCP scan | Descobrir hosts ativos e identificar portas abertas | `Planned` |

Status possíveis: `Planned`, `In Progress`, `Completed`.

Este track está apenas com a base estrutural criada — novos laboratórios
(ex.: detecção de serviço/versão, detecção de SO, uso do NSE) serão
adicionados conforme forem efetivamente realizados.

## Aviso ético e legal

> ⚠️ **Aviso importante**
>
> Diferente de uma captura passiva de tráfego, um scan de portas é uma
> **ação ativa** contra um alvo. Realizar varreduras contra hosts, redes
> ou sistemas sem autorização explícita pode violar leis locais, mesmo
> quando não causa dano direto.
>
> Este track tem finalidade **exclusivamente educacional e defensiva**.
> Todos os scans devem ser realizados em ambientes próprios, isolados ou
> explicitamente autorizados para teste.
>
> Antes de executar qualquer laboratório, leia
> [docs/scanning-safety-and-ethics.md](docs/scanning-safety-and-ethics.md),
> que trata de autorização, ambientes recomendados, boas práticas de
> impacto reduzido e anonimização de resultados.

## Instruções para executar ou reproduzir os laboratórios

1. Instale o [Nmap](https://nmap.org/download.html) no seu sistema
   operacional.
2. Prepare um ambiente de laboratório isolado e próprio (máquina virtual
   ou rede virtual) como alvo do scan.
3. Acesse o diretório do laboratório desejado em `labs/`.
4. Leia o `README.md` do laboratório para entender objetivo, cenário e
   procedimento.
5. Reproduza os comandos sugeridos no seu próprio ambiente.
6. Documente suas observações seguindo o mesmo modelo utilizado no
   laboratório (ver [templates/lab-template.md](templates/lab-template.md)).
7. Antes de versionar qualquer saída de scan ou screenshot, revise o
   conteúdo conforme
   [docs/scanning-safety-and-ethics.md](docs/scanning-safety-and-ethics.md).

## Referências gerais

- [Documentação oficial do Nmap](https://nmap.org/book/man.html)
- [resources/useful-commands.md](resources/useful-commands.md)

---

*Este é um track de estudo pessoal em cybersecurity e reconhecimento de
rede. Sugestões e correções técnicas são bem-vindas — consulte
[CONTRIBUTING.md](../CONTRIBUTING.md).*
