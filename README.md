# Network & Cybersecurity Labs

![Status](https://img.shields.io/badge/status-em%20andamento-yellow)
![Foco](https://img.shields.io/badge/foco-cybersecurity-blue)
![Licença](https://img.shields.io/badge/licença-MIT-green)

## Descrição

Este repositório reúne laboratórios práticos de **redes e cybersecurity**,
organizados por ferramenta/tema em tracks independentes. Cada track
documenta laboratórios de análise, investigação ou reconhecimento de rede,
seguindo uma metodologia consistente e uma estrutura de documentação
padronizada.

O objetivo é construir, de forma incremental, um portfólio técnico que
demonstre a capacidade de operar ferramentas de rede e segurança,
interpretar seus resultados e documentar análises de forma clara e
reprodutível — sempre em ambientes próprios ou explicitamente autorizados.

## Tracks

| Track | Ferramenta/Tema | Descrição | Status |
|---|---|---|---|
| [wireshark/](wireshark/README.md) | Wireshark | Análise de tráfego de rede, protocolos e investigação de pacotes | `Em andamento` |
| [nmap/](nmap/README.md) | Nmap | Descoberta de rede, varredura de portas e enumeração de serviços | `Planejado` |

Novos tracks podem ser adicionados a qualquer momento — basta criar uma
nova pasta na raiz do repositório (ex.: `zeek/`, `tcpdump/`,
`log-analysis/`) seguindo o mesmo padrão de organização descrito abaixo.

## Estrutura do repositório

```text
network-cybersecurity-labs/
├── README.md               # Este arquivo — índice geral do repositório
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── SECURITY.md
├── wireshark/               # Track de análise de tráfego com Wireshark
│   ├── README.md
│   ├── docs/
│   ├── labs/
│   ├── templates/
│   └── resources/
└── nmap/                    # Track de scanning e enumeração com Nmap
    ├── README.md
    ├── docs/
    ├── labs/
    ├── templates/
    └── resources/
```

Cada track segue a mesma organização interna:

- `README.md` — descrição do track, objetivos, laboratórios e aviso
  ético/legal específico da ferramenta.
- `docs/` — metodologia, conceitos de apoio e diretrizes de segurança.
- `labs/` — laboratórios práticos numerados (`NN-nome-do-laboratorio/`),
  cada um com seu próprio `README.md` e diretórios para evidências
  (`captures/`, `outputs/`, `screenshots/`, conforme a ferramenta).
- `templates/` — modelos reutilizáveis para novos laboratórios.
- `resources/` — referências rápidas, filtros e comandos úteis.

Os arquivos `LICENSE`, `.gitignore`, `CONTRIBUTING.md` e `SECURITY.md` são
únicos e compartilhados entre todos os tracks.

## Competências demonstradas

- Análise de pacotes e interpretação de cabeçalhos em múltiplas camadas.
- Compreensão prática de protocolos TCP/IP (Ethernet, ARP, IPv4/IPv6,
  ICMP, TCP, UDP, DNS, HTTP).
- Uso de filtros de captura e de exibição no Wireshark.
- Reconhecimento de rede e enumeração de serviços com o Nmap.
- Troubleshooting de rede a partir de evidências técnicas.
- Identificação inicial de tráfego suspeito e indicadores de
  comprometimento.
- Fundamentos de network forensics.
- Documentação técnica estruturada e uso responsável de ferramentas de
  rede e segurança.

## Metodologia de análise

Cada track segue uma metodologia própria, adaptada à ferramenta e ao tipo
de evidência analisada, mas todas compartilham os mesmos princípios:

1. Definição clara do objetivo da análise.
2. Validação da origem da evidência (captura, scan, log).
3. Identificação de hosts, protocolos ou serviços predominantes.
4. Aplicação progressiva de filtros/comandos, do mais amplo ao mais
   específico.
5. Identificação de anomalias, sem conclusões precipitadas.
6. Validação de hipóteses com evidências concretas.
7. Registro estruturado de evidências.
8. Proteção de dados sensíveis antes de qualquer publicação.
9. Documentação de conclusões, limitações e recomendações.

Veja a metodologia detalhada de cada track em
[wireshark/docs/network-analysis-methodology.md](wireshark/docs/network-analysis-methodology.md).

## Aviso ético e legal

> ⚠️ **Aviso importante**
>
> Todos os laboratórios deste repositório — captura de tráfego, varredura
> de portas ou qualquer outra técnica — devem ser realizados **apenas em
> ambientes próprios ou explicitamente autorizados**. Capturar tráfego ou
> escanear redes, sistemas ou dispositivos de terceiros sem autorização
> pode violar leis locais e políticas de uso aceitável.
>
> Este repositório tem finalidade **exclusivamente educacional e
> defensiva**. Nenhum laboratório aqui documentado tem como objetivo
> comprometer sistemas de terceiros.
>
> Cada track possui um aviso ético específico e orientações detalhadas de
> anonimização — consulte:
> - [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md)
> - [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md)

## Instruções para executar ou reproduzir os laboratórios

1. Escolha o track desejado (`wireshark/` ou `nmap/`).
2. Leia o `README.md` do track para entender objetivos e pré-requisitos.
3. Prepare um ambiente de laboratório isolado e próprio (máquina virtual
   ou rede virtual).
4. Acesse o laboratório específico dentro de `labs/` e siga o
   procedimento descrito.
5. Antes de versionar qualquer captura, saída de scan ou screenshot,
   revise o conteúdo conforme as diretrizes de segurança do respectivo
   track.

## Progresso

Este repositório está em fase de estruturação. O track `wireshark/` possui
a documentação base de cinco laboratórios criada, ainda **sem capturas ou
resultados reais registrados**. O track `nmap/` foi recém-criado, com a
estrutura base e um laboratório inicial planejado. O progresso de cada
laboratório é acompanhado pelo campo `Status` em seu respectivo
`README.md`.

## Próximos passos

- Executar e documentar os primeiros laboratórios reais em `wireshark/` e
  `nmap/`.
- Expandir o track `nmap/` com laboratórios de detecção de
  serviço/versão, detecção de SO e uso do NSE.
- Avaliar a criação de novos tracks (ex.: `tcpdump/`, `zeek/`,
  `log-analysis/`) conforme novos laboratórios forem realizados.

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

*Este é um projeto de estudo pessoal em redes e cybersecurity. Sugestões e
correções técnicas são bem-vindas — consulte [CONTRIBUTING.md](CONTRIBUTING.md).*
