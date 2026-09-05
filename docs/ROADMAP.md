# Roadmap

Três marcos, um só repositório. Cada marco entrega algo usável — e o que o marco anterior construiu nunca é descartado.

## Marco 1 — Evento de coleta (19/09) ✅ EM ANDAMENTO

**Contexto:** a escola fará a separação das equipes e uma competição de coleta de lixo, pesando em kg o que cada equipe juntar. Nosso sistema vira o placar oficial.

**Escopo (enxuto, YAGNI):**

- [ ] Cadastro de equipes (nome + cor)
- [ ] Registro de pesagem (equipe, kg, horário) — formulário rápido, usável no telemóvel
- [ ] Ranking ao vivo = soma de kg por equipe, atualizando sozinho (dashboard com polling)
- [ ] Seed com equipes fictícias + dados de teste
- [ ] Teste ponta a ponta antes do dia

**Critério de pronto:** no dia 19/09, qualquer pessoa da equipe registra uma pesagem pelo telemóvel e o placar atualiza em segundos.

**Por que isso é o Marco 1 do projeto final:** o ranking por kg é a Camada 3 (Engajamento) do documento de ideias — exatamente a gamificação que o projeto final mantém (por equipe/sala). E as pesagens viram o primeiro dataset REAL da escola para o modelo de previsão do Marco 3.

**Depois do evento:** o backend e o dashboard deste marco viram a base da Camada 0 (lixeiras inteligentes) — nada é jogado fora.

## Marco 2 — Lixeira inteligente (Camada 0 completa)

**Escopo:** 1 lixeira física real (ESP32 + sensor ultrassônico, ~R$45) + **modo simulação** (todo o resto roda sem hardware) + dashboard com mapa da escola, nível de enchimento em tempo real e alerta acima de 80%.

- [ ] Backend recebe leituras de nível (%) via HTTP/MQTT
- [ ] Modo simulação: script gera leituras sintéticas → fluxo ponta a ponta sem hardware
- [ ] Dashboard: mapa da escola + nível por lixeira + alertas
- [ ] Instalação da lixeira física na escola

**Critério de pronto:** um recrutador roda `docker compose up` e vê o sistema funcionando — sem comprar nada.

## Marco 3 — IA preditiva (Camada 1)

**Escopo:** previsão de enchimento em 3 degraus didáticos, cada um virando um notebook Jupyter publicado:

1. Baseline ingênuo (ex.: média histórica)
2. Regressão com features de tempo (scikit-learn)
3. XGBoost ou Prophet

**Fonte de dados:** histórico de leituras do Marco 2 + pesagens reais do evento do Marco 1 (19/09).

**Critério de pronto:** o modelo responde "a lixeira X vai encher na quinta às 14h" com erro razoável, e o dashboard sugere alertas de coleta preditiva.

## Fora de escopo (adiado de propósito — YAGNI)

- Visão computacional (YOLO/CNN) — documentar como "futuro" no README
- Chatbot educativo (Telegram/WhatsApp)
- Totem na escola
- Relatório mensal automático por IA

## Cronograma (16 semanas, conforme documento de ideias)

| Fase | Período | Entrega principal |
|---|---|---|
| 0. Evento | set/2026 (19/09) | Ranking de coleta por equipe funcionando no dia |
| 1. Fundação | Semanas 1–4 | Backend + modo simulação + dashboard (reaproveita o M1) |
| 2. Hardware real | Semanas 5–8 | ESP32 + sensor enviando dados; lixeira real no dashboard |
| 3. Inteligência | Semanas 9–13 | Previsão de enchimento (3 degraus) + alertas preditivos |
| 4. Extensão e GitHub | Semanas 14–16 | Demo na escola, ranking das salas, relatório de impacto, repositório polido (CI verde, README com fotos) |