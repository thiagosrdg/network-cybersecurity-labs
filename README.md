# Wireshark Security Labs

![Status](https://img.shields.io/badge/status-em%20andamento-yellow)
![Foco](https://img.shields.io/badge/foco-cybersecurity-blue)
![Ferramenta](https://img.shields.io/badge/ferramenta-Wireshark-1679A7)
![Licença](https://img.shields.io/badge/licença-MIT-green)

## Descrição

Este repositório documenta laboratórios práticos de **análise de tráfego de
rede com Wireshark**, com foco em cybersecurity, análise de protocolos,
investigação de pacotes e identificação de comportamentos suspeitos.

O objetivo é construir, de forma incremental e documentada, um portfólio
técnico que demonstre a capacidade de capturar, analisar e interpretar
tráfego de rede em cenários controlados, aplicando fundamentos de
segurança da informação e network forensics.

Todos os laboratórios são realizados em ambientes próprios ou autorizados,
seguindo boas práticas éticas e de proteção de dados (ver
[Aviso ético e legal](#aviso-ético-e-legal)).

## Objetivos de aprendizado

- Compreender em profundidade o funcionamento dos protocolos TCP/IP.
- Desenvolver proficiência na captura e análise de tráfego com Wireshark.
- Praticar a construção e o uso de capture filters e display filters.
- Reconhecer padrões normais de comunicação de rede e identificar desvios.
- Aplicar uma metodologia estruturada de investigação de pacotes.
- Documentar análises técnicas de forma clara, objetiva e reprodutível.
- Desenvolver fundamentos de network forensics e resposta a incidentes.

## Competências demonstradas

- Análise de pacotes e interpretação de cabeçalhos em múltiplas camadas.
- Compreensão prática de protocolos TCP/IP (Ethernet, ARP, IPv4/IPv6, ICMP,
  TCP, UDP, DNS, HTTP).
- Análise de tráfego ICMP, DNS, TCP e HTTP.
- Construção de filtros de captura e de exibição.
- Troubleshooting de rede a partir de evidências de pacotes.
- Identificação inicial de tráfego suspeito e indicadores de comprometimento.
- Fundamentos de network forensics.
- Documentação técnica estruturada e uso responsável de ferramentas de
  análise de rede.

## Tecnologias e ferramentas utilizadas

- [Wireshark](https://www.wireshark.org/) — análise gráfica de pacotes.
- [TShark](https://www.wireshark.org/docs/man-pages/tshark.html) — análise de
  pacotes via linha de comando.
- Ambientes de laboratório virtualizados e/ou isolados.
- Markdown para documentação técnica.
- Git/GitHub para versionamento e portfólio.

Mais detalhes em [resources/recommended-tools.md](resources/recommended-tools.md).

## Estrutura do repositório

```text
wireshark-security-labs/
├── README.md
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── SECURITY.md
├── docs/                       # Metodologia, filtros e conceitos de apoio
├── labs/                       # Laboratórios práticos numerados
│   ├── 01-icmp-analysis/
│   ├── 02-dns-analysis/
│   ├── 03-tcp-three-way-handshake/
│   ├── 04-http-traffic-analysis/
│   └── 05-suspicious-traffic-analysis/
├── templates/                  # Modelos reutilizáveis para novos laboratórios
└── resources/                  # Filtros, referência de protocolos e ferramentas
```

Cada laboratório em `labs/` contém:

- `README.md` — documentação completa do laboratório.
- `captures/` — arquivos `.pcap`/`.pcapng` anonimizados (quando aplicável).
- `screenshots/` — evidências visuais anonimizadas (quando aplicável).

## Laboratórios

| # | Laboratório | Protocolo/Tema | Objetivo | Status |
|---|---|---|---|---|
| 01 | [ICMP Analysis](labs/01-icmp-analysis/README.md) | ICMP | Analisar Echo Request/Reply, TTL e latência | `Planned` |
| 02 | [DNS Analysis](labs/02-dns-analysis/README.md) | DNS | Analisar consultas, respostas e códigos de retorno | `Planned` |
| 03 | [TCP Three-Way Handshake](labs/03-tcp-three-way-handshake/README.md) | TCP | Analisar estabelecimento de conexão e falhas | `Planned` |
| 04 | [HTTP Traffic Analysis](labs/04-http-traffic-analysis/README.md) | HTTP | Analisar requisições/respostas e riscos de tráfego não criptografado | `Planned` |
| 05 | [Suspicious Traffic Analysis](labs/05-suspicious-traffic-analysis/README.md) | Diversos | Aplicar metodologia de investigação de tráfego incomum | `Planned` |

Status possíveis: `Planned`, `In Progress`, `Completed`.

## Metodologia de análise

Todos os laboratórios seguem uma metodologia consistente de investigação,
descrita em detalhes em
[docs/network-analysis-methodology.md](docs/network-analysis-methodology.md).
Em resumo, ela cobre:

1. Definição do objetivo da análise.
2. Validação da origem da captura.
3. Identificação de hosts e protocolos predominantes.
4. Construção de uma linha do tempo.
5. Aplicação progressiva de filtros.
6. Identificação de anomalias.
7. Validação de hipóteses.
8. Registro de evidências.
9. Proteção de dados sensíveis.
10. Documentação de conclusões e limitações.

## Aviso ético e legal

> ⚠️ **Aviso importante**
>
> A captura e a análise de tráfego de rede só devem ser realizadas em
> **ambientes próprios ou explicitamente autorizados**. Capturar tráfego de
> redes, sistemas ou terceiros sem autorização pode violar leis locais e
> políticas de uso aceitável.
>
> Este repositório tem finalidade **exclusivamente educacional e defensiva**.
> Nenhum laboratório aqui documentado tem como objetivo comprometer sistemas
> de terceiros. Todo o tráfego analisado é gerado em laboratórios controlados
> (máquinas virtuais, redes isoladas ou ambientes de teste próprios).
>
> Antes de publicar qualquer arquivo de captura, screenshot ou evidência,
> siga as orientações descritas em
> [docs/packet-capture-safety.md](docs/packet-capture-safety.md), que tratam
> de anonimização de IPs, MACs, hostnames, credenciais e demais dados
> sensíveis.

## Instruções para executar ou reproduzir os laboratórios

1. Instale o [Wireshark](https://www.wireshark.org/download.html) (versão
   estável mais recente) no seu sistema operacional.
2. Prepare um ambiente de laboratório isolado (máquina virtual, rede
   virtual ou ambiente de testes próprio).
3. Acesse o diretório do laboratório desejado em `labs/`.
4. Leia o `README.md` do laboratório para entender objetivo, cenário e
   procedimento.
5. Reproduza a captura no seu próprio ambiente, aplicando os filtros de
   captura e exibição sugeridos.
6. Documente suas observações seguindo o mesmo modelo utilizado no
   laboratório (ver [templates/lab-template.md](templates/lab-template.md)).
7. Antes de versionar qualquer captura ou screenshot, revise o conteúdo
   conforme [docs/packet-capture-safety.md](docs/packet-capture-safety.md).

## Progresso

Este repositório está em fase inicial de estruturação. Os laboratórios estão
com a documentação base criada, mas ainda **sem capturas ou resultados
reais registrados**. O progresso de cada laboratório é acompanhado pelo
campo `Status` na tabela acima e no respectivo `README.md`.

## Próximos laboratórios

Ideias para expansão futura do repositório (ainda não iniciadas):

- Análise de tráfego DHCP.
- Introdução à análise de tráfego TLS/HTTPS (metadados, sem quebra de
  criptografia).
- Análise de tráfego ARP e detecção de ARP spoofing em laboratório.
- Introdução a IDS/IPS e correlação com capturas de pacotes.
- Análise de exfiltração de dados simulada em ambiente controlado.

## Padrão de commits

Este repositório segue a convenção de
[Conventional Commits](https://www.conventionalcommits.org/):

```text
docs: add DNS analysis notes
feat: add ICMP packet capture lab
fix: correct TCP filter example
refactor: reorganize lab structure
chore: update repository metadata
```

## Contato e perfil profissional

- GitHub: [thiagosrdg](https://github.com/thiagosrdg)
- LinkedIn: `<adicionar link do LinkedIn>`
- E-mail de contato: `<adicionar e-mail de contato profissional>`

---

*Este é um projeto de estudo pessoal em cybersecurity e análise de tráfego
de rede. Sugestões e correções técnicas são bem-vindas — consulte
[CONTRIBUTING.md](CONTRIBUTING.md).*
