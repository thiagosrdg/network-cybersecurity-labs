# Política de Segurança

## Finalidade do projeto

O **Network & Cybersecurity Labs** é um repositório com finalidade
**exclusivamente educacional e defensiva**, criado para documentar
laboratórios de redes e cybersecurity organizados por track (ex.:
`wireshark/`, `nmap/`). Ele não tem como objetivo armazenar, distribuir ou
promover técnicas ofensivas contra sistemas de terceiros.

## Reporte de vulnerabilidades ou dados sensíveis

Se você identificar:

- uma vulnerabilidade relacionada ao conteúdo deste repositório;
- um arquivo de captura, saída de scan, screenshot ou trecho de
  documentação que contenha, por engano, dados sensíveis (IPs públicos
  pessoais, hostnames reais, credenciais, cookies, tokens ou informações
  de terceiros);

por favor, **não abra uma issue pública** descrevendo o problema em
detalhes. Em vez disso, entre em contato de forma privada com o mantenedor
através do e-mail ou canal indicado no `README.md` (seção "Contato e perfil
profissional"), descrevendo o problema de forma resumida.

## Diretrizes gerais

- **Credenciais e dados pessoais nunca devem ser publicados em issues,
  pull requests ou arquivos versionados.**
- Todo arquivo de captura (`.pcap`/`.pcapng`) ou saída de scanning deve
  ser revisado manualmente antes de ser adicionado ao repositório,
  conforme as diretrizes de cada track:
  - [wireshark/docs/packet-capture-safety.md](wireshark/docs/packet-capture-safety.md)
  - [nmap/docs/scanning-safety-and-ethics.md](nmap/docs/scanning-safety-and-ethics.md)
- Screenshots devem ser revisados para garantir que não exponham IPs
  públicos pessoais, hostnames reais, e-mails, tokens ou outros dados
  identificáveis.
- Caso um material sensível seja identificado após o merge, ele será
  removido do histórico assim que possível e a política de anonimização
  será reforçada.

## Escopo

Este repositório não hospeda aplicações em produção nem processa dados de
usuários reais. Portanto, o escopo de "segurança" aqui trata
principalmente da **proteção de dados eventualmente presentes em
capturas de tráfego, saídas de scan e demais evidências de laboratório**,
e não de vulnerabilidades de software em execução.
