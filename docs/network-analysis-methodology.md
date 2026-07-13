# Metodologia de Análise de Tráfego de Rede

Este documento descreve a metodologia utilizada em todos os laboratórios
deste repositório para investigar capturas de tráfego de forma consistente,
rastreável e defensável. A ideia é aplicar sempre a mesma sequência de
etapas, adaptando o nível de profundidade ao objetivo de cada laboratório.

## 1. Definir o objetivo da análise

Antes de abrir qualquer captura, defina claramente:

- O que está sendo investigado (ex.: comportamento de um protocolo,
  troubleshooting de conectividade, possível atividade suspeita).
- Qual pergunta a análise deve responder.
- Qual o escopo temporal e de hosts envolvidos.

Um objetivo bem definido evita análises genéricas e sem foco.

## 2. Validar a origem da captura

- Confirme onde, quando e como a captura foi realizada.
- Verifique se a captura foi feita em um ambiente autorizado e controlado.
- Registre a interface de rede, o host de captura e o contexto (laboratório,
  máquina virtual, rede isolada etc.).

## 3. Identificar hosts e protocolos predominantes

- Utilize estatísticas do Wireshark (ex.: *Statistics > Protocol
  Hierarchy*, *Statistics > Conversations*) para obter uma visão geral.
- Identifique os principais hosts de origem e destino.
- Identifique os protocolos mais relevantes para o objetivo da análise.

## 4. Estabelecer uma linha do tempo

- Ordene os eventos relevantes cronologicamente.
- Identifique o início e o fim da comunicação analisada.
- Observe picos de tráfego, intervalos incomuns ou eventos concentrados em
  curtos períodos de tempo.

## 5. Aplicar filtros progressivamente

- Comece com filtros amplos (ex.: `ip.addr == x.x.x.x`) e vá refinando.
- Combine filtros de forma incremental para isolar o tráfego relevante.
- Documente os filtros utilizados a cada etapa (ver
  [wireshark-display-filters.md](wireshark-display-filters.md)).

## 6. Identificar anomalias

- Compare o tráfego observado com o comportamento esperado do protocolo.
- Procure por retransmissões, resets inesperados, códigos de erro,
  latências anormais ou padrões de tráfego incomuns.
- Evite tirar conclusões precipitadas: uma anomalia é um ponto de atenção,
  não uma prova definitiva.

## 7. Validar hipóteses

- Para cada anomalia observada, formule uma hipótese explicável.
- Busque evidências adicionais na própria captura (ou em capturas
  complementares) que confirmem ou refutem a hipótese.
- Quando não houver evidência suficiente, registre a hipótese como
  **não confirmada**, em vez de apresentá-la como conclusão.

## 8. Registrar evidências

- Salve screenshots relevantes dos pacotes analisados.
- Referencie números de frame, timestamps e filtros aplicados.
- Mantenha rastreabilidade entre a evidência e a conclusão associada a ela.

## 9. Proteger dados sensíveis

- Antes de documentar ou publicar qualquer evidência, aplique as
  orientações de [packet-capture-safety.md](packet-capture-safety.md).
- Anonimize IPs, MACs, hostnames, nomes de usuário e qualquer dado que
  possa identificar pessoas ou sistemas reais.

## 10. Documentar conclusões e limitações

- Separe claramente **fatos observados** de **hipóteses** e **inferências**.
- Descreva as limitações da análise (ex.: captura parcial, ausência de
  contexto, falta de logs complementares).
- Inclua recomendações práticas quando aplicável (mitigação,
  troubleshooting, próximos passos de investigação).

Esta metodologia é utilizada de forma consistente em todos os laboratórios
deste repositório e serve como base para o
[template de análise de incidentes](../templates/incident-analysis-template.md).
