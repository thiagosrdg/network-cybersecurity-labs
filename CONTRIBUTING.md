# Guia de Contribuição

Obrigado por considerar contribuir com o **Wireshark Security Labs**. Este é
um repositório de estudo e portfólio pessoal, mas sugestões, correções
técnicas e melhorias na documentação são bem-vindas.

## Padrão de nomes

- Utilize nomes de arquivos e diretórios em **inglês**, em `kebab-case`
  (ex.: `dns-analysis`, `packet-capture-safety.md`).
- Novos laboratórios devem seguir o padrão `NN-nome-do-laboratorio`, com
  numeração sequencial de dois dígitos (ex.: `06-arp-spoofing-detection`).
- Cada laboratório deve manter os subdiretórios `captures/` e
  `screenshots/`, mesmo que inicialmente vazios (use `.gitkeep`).

## Documentação dos laboratórios

- Todo laboratório deve seguir a estrutura definida em
  [templates/lab-template.md](templates/lab-template.md).
- A documentação deve ser escrita em **português brasileiro**, com
  linguagem técnica e objetiva.
- Não registre resultados, capturas ou conclusões de laboratórios que ainda
  não foram efetivamente realizados.
- Atualize o campo `Status` (`Planned`, `In Progress`, `Completed`) tanto no
  `README.md` do laboratório quanto na tabela do `README.md` principal.

## Anonimização

- Antes de adicionar qualquer arquivo `.pcap`, `.pcapng` ou screenshot,
  siga as orientações de
  [docs/packet-capture-safety.md](docs/packet-capture-safety.md).
- Nunca inclua IPs públicos pessoais, credenciais, cookies, tokens ou dados
  de terceiros.
- Prefira gerar tráfego sintético em ambientes de laboratório controlados.

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

- Descreva claramente o que foi alterado e por quê.
- Indique se o PR adiciona resultados reais de laboratório, apenas
  documentação/estrutura, ou correções.
- Confirme que nenhum arquivo sensível foi incluído (ver
  [SECURITY.md](SECURITY.md)).

## Conteúdo proibido

Não serão aceitas contribuições que incluam:

- Conteúdo ilegal, ofensivo ou antiético.
- Tráfego capturado sem autorização explícita do proprietário da rede.
- Dados pessoais, credenciais, tokens, cookies ou informações sensíveis de
  terceiros.
- Técnicas ou materiais com finalidade ofensiva contra sistemas de
  terceiros.
