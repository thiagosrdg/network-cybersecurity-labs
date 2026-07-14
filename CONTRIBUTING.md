# Guia de Contribuição

Obrigado por considerar contribuir com o **Network & Cybersecurity Labs**.
Este é um repositório de estudo e portfólio pessoal, organizado em tracks
por ferramenta/tema (ex.: `wireshark/`, `nmap/`), mas sugestões, correções
técnicas e melhorias na documentação são bem-vindas.

## Padrão de nomes

- Utilize nomes de arquivos e diretórios em **inglês**, em `kebab-case`
  (ex.: `dns-analysis`, `packet-capture-safety.md`).
- Novos tracks devem ser criados como uma pasta na raiz do repositório,
  com o nome da ferramenta/tema em minúsculas (ex.: `zeek/`, `tcpdump/`).
- Dentro de cada track, novos laboratórios devem seguir o padrão
  `NN-nome-do-laboratorio`, com numeração sequencial de dois dígitos
  (ex.: `06-arp-spoofing-detection`).
- Cada laboratório deve manter os subdiretórios de evidência apropriados
  (ex.: `captures/` e `screenshots/` no track Wireshark; `outputs/` e
  `screenshots/` no track Nmap), mesmo que inicialmente vazios (use
  `.gitkeep`).

## Estrutura de um novo track

Ao criar um novo track, siga a mesma organização já usada em
`wireshark/` e `nmap/`:

```text
nome-do-track/
├── README.md      # Descrição, objetivos, laboratórios e aviso ético
├── docs/           # Metodologia e diretrizes de segurança específicas
├── labs/           # Laboratórios numerados
├── templates/      # Modelo reutilizável de laboratório
└── resources/      # Referências rápidas (filtros, comandos etc.)
```

Adicione o novo track à tabela da seção "Tracks" no
[README.md principal](README.md).

## Documentação dos laboratórios

- Todo laboratório deve seguir a estrutura definida no
  `lab-template.md` do respectivo track (ex.:
  [wireshark/templates/lab-template.md](wireshark/templates/lab-template.md),
  [nmap/templates/lab-template.md](nmap/templates/lab-template.md)).
- A documentação deve ser escrita em **português brasileiro**, com
  linguagem técnica e objetiva.
- Não registre resultados, capturas, saídas de scan ou conclusões de
  laboratórios que ainda não foram efetivamente realizados.
- Atualize o campo `Status` (`Planned`, `In Progress`, `Completed`) tanto
  no `README.md` do laboratório quanto na tabela do `README.md` do track.

## Anonimização

- Antes de adicionar qualquer arquivo `.pcap`, `.pcapng`, saída de scan ou
  screenshot, siga as orientações de segurança do respectivo track (ex.:
  [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md),
  [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md)).
- Nunca inclua IPs públicos pessoais, credenciais, cookies, tokens ou
  dados de terceiros.
- Prefira gerar tráfego ou resultados sintéticos em ambientes de
  laboratório controlados e próprios.

## Criação de branches

- Crie branches a partir de `main` com nomes descritivos:
  - `feat/nome-da-feature`
  - `docs/nome-do-documento`
  - `fix/descricao-da-correcao`

## Commits claros

Este projeto segue a convenção de
[Conventional Commits](https://www.conventionalcommits.org/):

```text
docs: add DNS analysis notes
feat: add ICMP packet capture lab
fix: correct TCP filter example
refactor: reorganize lab structure
chore: update repository metadata
```

## Pull requests

- Descreva claramente o que foi alterado e por quê, incluindo a qual
  track a alteração pertence.
- Indique se o PR adiciona resultados reais de laboratório, apenas
  documentação/estrutura, ou correções.
- Confirme que nenhum arquivo sensível foi incluído (ver
  [SECURITY.md](SECURITY.md)).

## Conteúdo proibido

Não serão aceitas contribuições que incluam:

- Conteúdo ilegal, ofensivo ou antiético.
- Tráfego capturado ou scans realizados sem autorização explícita do
  proprietário da rede/sistema.
- Dados pessoais, credenciais, tokens, cookies ou informações sensíveis de
  terceiros.
- Técnicas ou materiais com finalidade ofensiva contra sistemas de
  terceiros.
