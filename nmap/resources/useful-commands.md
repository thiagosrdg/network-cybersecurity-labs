# Comandos Úteis do Nmap

Referência rápida de comandos e flags comuns do Nmap, para consulta
durante os laboratórios. Todos os exemplos devem ser executados apenas
contra alvos próprios ou autorizados (ver
[docs/scanning-safety-and-ethics.md](../docs/scanning-safety-and-ethics.md)).

## Descoberta de hosts (host discovery)

```text
nmap -sn 192.168.1.0/24
```

Realiza apenas a descoberta de hosts ativos na rede, sem varredura de
portas (equivalente a um "ping scan").

## Varredura de portas básica

```text
nmap 192.168.1.10
nmap -p 1-1000 192.168.1.10
nmap -p- 192.168.1.10
```

- `-p 1-1000` — limita o scan a um intervalo de portas.
- `-p-` — varre todas as 65535 portas TCP.

## Tipos de scan

```text
nmap -sS 192.168.1.10
nmap -sT 192.168.1.10
nmap -sU 192.168.1.10
```

- `-sS` — SYN scan (half-open), requer privilégios elevados.
- `-sT` — TCP connect scan, completa o three-way handshake.
- `-sU` — varredura de portas UDP.

## Detecção de serviço e versão

```text
nmap -sV 192.168.1.10
```

Tenta identificar o serviço e a versão em execução em cada porta aberta.

## Detecção de sistema operacional

```text
nmap -O 192.168.1.10
```

Tenta inferir o sistema operacional do alvo com base em características
da pilha TCP/IP.

## Nmap Scripting Engine (NSE)

```text
nmap -sC 192.168.1.10
nmap --script=default 192.168.1.10
```

Executa scripts de reconhecimento padrão do NSE. Scripts mais invasivos
devem ser usados com cautela redobrada e apenas em ambientes autorizados.

## Scan completo de reconhecimento

```text
nmap -sS -sV -O -p- 192.168.1.10
```

Combina SYN scan, detecção de versão, detecção de SO e varredura de todas
as portas. Scan mais demorado e mais "ruidoso" — use com moderação.

## Controle de velocidade (timing)

```text
nmap -T2 192.168.1.10
nmap -T4 192.168.1.10
```

Controla a agressividade temporal do scan (`-T0` mais lento/discreto a
`-T5` mais rápido/agressivo). Prefira valores mais conservadores em
laboratórios com recursos limitados.

## Exportação de resultados

```text
nmap -oN output.txt 192.168.1.10
nmap -oX output.xml 192.168.1.10
nmap -oG output.gnmap 192.168.1.10
```

- `-oN` — saída normal em texto.
- `-oX` — saída em XML (útil para processamento posterior).
- `-oG` — saída "grepable" (formato legado, ainda útil em scripts).

Lembre-se de revisar e anonimizar qualquer arquivo de saída antes de
adicioná-lo a `labs/**/outputs/`.
