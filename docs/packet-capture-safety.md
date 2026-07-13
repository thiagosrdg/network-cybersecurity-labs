# Segurança e Ética na Captura de Pacotes

A captura e a análise de tráfego de rede envolvem, por natureza, dados
potencialmente sensíveis. Este documento define as orientações que devem
ser seguidas **antes de capturar, analisar ou versionar qualquer tráfego**
neste repositório.

## Autorização prévia

- Nunca capture tráfego em redes, sistemas ou dispositivos que não sejam
  seus ou para os quais você não tenha autorização explícita.
- Em ambientes corporativos ou de terceiros, obtenha autorização por
  escrito antes de qualquer captura, mesmo para fins de estudo.

## Ambientes próprios ou autorizados

- Realize os laboratórios em ambientes controlados: máquinas virtuais,
  redes isoladas (host-only/NAT) ou laboratórios de estudo próprios.
- Evite capturar tráfego em redes compartilhadas com terceiros (ex.: redes
  corporativas, redes públicas, redes domésticas com outros usuários) sem
  autorização explícita de todos os envolvidos.

## Anonimização de dados

Antes de publicar qualquer captura ou evidência, anonimize:

- **Endereços IP** — substitua IPs públicos reais por endereços de
  documentação (`192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24`,
  conforme RFC 5737) ou por faixas privadas (`10.0.0.0/8`,
  `172.16.0.0/12`, `192.168.0.0/16`).
- **Endereços MAC** — substitua por endereços genéricos ou utilize
  ferramentas de anonimização (ex.: `tracewrangler`).
- **Hostnames** — substitua nomes reais por identificadores genéricos
  (ex.: `host-lab-01`).
- **Nomes de usuário** — substitua por identificadores genéricos
  (ex.: `user-lab`).

## Remoção de credenciais e dados de sessão

- Nunca publique capturas contendo senhas, tokens de autenticação,
  cookies de sessão, chaves de API ou cabeçalhos de autorização em texto
  claro.
- Ao analisar tráfego HTTP (ver [Lab 04](../labs/04-http-traffic-analysis/README.md)),
  utilize apenas ambientes de laboratório com credenciais fictícias e
  descartáveis.
- Revise cabeçalhos HTTP (`Authorization`, `Cookie`, `Set-Cookie`) antes de
  incluir qualquer captura ou screenshot na documentação.

## Cuidado com dados pessoais

- Evite capturar tráfego que envolva contas pessoais reais, e-mails
  pessoais, dados bancários ou qualquer informação identificável.
- Prefira gerar tráfego sintético especificamente para fins do laboratório
  (ver seção abaixo).

## Armazenamento seguro

- Mantenha arquivos de captura brutos (não anonimizados) fora do controle
  de versão, em local seguro e com acesso restrito.
- Apenas versione capturas **já revisadas e anonimizadas**.
- Utilize os padrões definidos em [.gitignore](../.gitignore) para evitar o
  versionamento acidental de arquivos sensíveis (ex.: `*.private.pcap`,
  `*.sensitive.pcapng`, `captures/raw/`).

## Não publicação de tráfego de terceiros

- Não publique capturas realizadas em redes ou sistemas de terceiros, ainda
  que anonimizadas, sem autorização explícita para distribuição.
- Em caso de dúvida sobre a origem ou a autorização de uma captura,
  **não a publique**.

## Criação de tráfego sintético em laboratórios

- Sempre que possível, gere o próprio tráfego a ser analisado (ex.: `ping`,
  consultas DNS controladas, requisições HTTP em servidores locais de
  teste).
- Isso garante controle total sobre o conteúdo capturado e elimina o risco
  de exposição de dados de terceiros.

## Revisão antes do commit

Antes de cada commit que inclua arquivos de captura ou screenshots:

1. Abra o arquivo `.pcap`/`.pcapng` e confirme que não há dados sensíveis
   remanescentes.
2. Revise screenshots em busca de IPs públicos pessoais, hostnames reais,
   e-mails ou outras informações identificáveis visíveis na interface do
   Wireshark.
3. Confirme o tamanho do arquivo — evite versionar capturas muito grandes;
   quando necessário, utilize amostras representativas e menores do
   tráfego relevante.
4. Em caso de dúvida sobre a sensibilidade de um dado, **não publique** e
   consulte [SECURITY.md](../SECURITY.md).
