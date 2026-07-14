# Segurança e Ética no Uso do Nmap

O Nmap é uma ferramenta de descoberta de rede e varredura de portas.
Diferente de uma captura passiva de tráfego, um scan é uma ação **ativa**
contra um alvo — por isso, os cuidados de autorização aqui são ainda mais
críticos do que os descritos para o track
[wireshark](../../wireshark/docs/packet-capture-safety.md).

## Autorização é obrigatória

- **Nunca execute um scan contra hosts, redes ou sistemas que não sejam
  seus ou para os quais você não tenha autorização explícita e por
  escrito.**
- Varredura de portas sem autorização pode ser considerada crime em
  diversas jurisdições, mesmo quando não causa dano direto.
- Em ambientes corporativos, obtenha autorização formal (ex.: janela de
  teste aprovada, escopo definido) antes de qualquer scan, mesmo para
  fins de estudo.

## Ambientes recomendados para os laboratórios

- Máquinas virtuais próprias, em rede isolada (host-only/NAT).
- Alvos de teste legítimos e mantidos para fins educacionais (ex.:
  `scanme.nmap.org`, que é disponibilizado publicamente pelos
  mantenedores do Nmap especificamente para testes leves e respeitosos —
  consulte sempre a política de uso oficial antes de utilizá-lo).
- Ambientes de CTF ou laboratórios de segurança criados especificamente
  para prática (ex.: VMs vulneráveis próprias).

## Boas práticas durante os laboratórios

- Prefira scans com menor impacto quando o objetivo for apenas
  aprendizado (evite `-T5`/timing agressivo sem necessidade).
- Documente sempre o alvo, o horário e a justificativa do scan.
- Evite scans que possam gerar negação de serviço (ex.: grandes volumes
  de conexões simultâneas) contra sistemas com recursos limitados.

## Anonimização e proteção de dados

- Antes de publicar qualquer saída de scan (`outputs/`) ou screenshot:
  - Substitua IPs reais por endereços de documentação (`192.0.2.0/24`,
    `198.51.100.0/24`, `203.0.113.0/24`, conforme RFC 5737) ou por faixas
    privadas (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`).
  - Remova hostnames, banners de serviço ou versões que possam
    identificar um sistema real de terceiros.
  - Revise a saída completa (incluindo banners de serviço, que podem
    conter informações sensíveis) antes do commit.
- Nunca publique resultados de scans realizados contra sistemas de
  terceiros sem autorização explícita para divulgação.

## Armazenamento seguro

- Mantenha saídas brutas e não revisadas fora do controle de versão.
- Apenas versione saídas já revisadas e anonimizadas, seguindo os
  padrões definidos em [.gitignore](../../.gitignore).

## Finalidade deste track

Este track tem finalidade **exclusivamente educacional e defensiva**: o
objetivo é compreender como técnicas de scanning funcionam, como se
manifestam na rede e como podem ser detectadas e mitigadas — não realizar
testes contra sistemas de terceiros sem autorização.
