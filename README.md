# Cidades Inteligentes — Sistema de Monitoramento Escolar

Projeto de Extensão Universitária (faculdade + escola) que aplica o conceito de **cidades inteligentes** em escala escolar. Uma escola é uma minicidade: gera resíduos, consome energia e água, tem fluxo de pessoas e espaços que precisam de manutenção. Monitorar e otimizar esses recursos em escala escolar é exatamente o que cidades inteligentes fazem em escala urbana — com impacto social direto.

Fluxo dos dados: **sensor → API/banco → dashboard + IA → ações** (alertas de coleta, ranking de equipes, relatórios).

## Marcos

| Marco | O quê | Quando |
|---|---|---|
| **M1 — Evento de coleta** | Separação de equipes + competição de quem coleta mais lixo (pesagem em kg). MVP de ranking ao vivo: cadastro de equipes, registro de pesagem, placar. | 19/09 |
| **M2 — Lixeira inteligente** | Camada 0 completa: ESP32 + sensor ultrassônico, modo simulação, dashboard com mapa da escola e alertas. | Semanas 5–8 |
| **M3 — IA preditiva** | Previsão de enchimento em 3 degraus didáticos (baseline → scikit-learn → XGBoost/Prophet), usando também os dados reais do evento. | Semanas 9–13 |

## Arquitetura (4 pilares)

| Pilar | O que faz | Tecnologias |
|---|---|---|
| 1. Sensoriamento (IoT) | Coleta dados reais do ambiente (nível de lixo, presença) | ESP32, sensor ultrassônico HC-SR04, WiFi |
| 2. Dados e API | Recebe, armazena e expõe os dados de forma estruturada | NestJS, Prisma, PostgreSQL |
| 3. Inteligência (IA/ML) | Prevê, classifica e alerta sobre os dados | Python, scikit-learn, XGBoost/Prophet |
| 4. Engajamento (extensão) | Leva o resultado para a comunidade escolar e gera impacto | Dashboard web, ranking, relatórios |

Cada pilar conversa com o vizinho por interfaces bem definidas — essa separação também define como a equipe se organiza. Detalhes das camadas no [documento de ideias](docs/Documento-Ideias-Cidades-Inteligentes.pdf).

## Estrutura do repositório

```
apps/api        → Backend NestJS + Prisma + PostgreSQL (Em construção)
apps/web        → Dashboard web: ranking, mapa, alertas (Em construção)
docs/           → Documentos da equipe (ideias, roadmap, decisões)
firmware/       → Código do ESP32 (Futuro — Marco 2)
notebooks/      → Modelos de IA/ML (Futuro — Marco 3)
```

## Como rodar

Em construção — instruções completas chegam junto com o scaffold (docker-compose para o banco, API e dashboard rodando localmente sem hardware, com modo simulação).

## Convenções

- **Commits:** [conventional commits](https://www.conventionalcommits.org/) — `docs:`, `feat:`, `fix:`, `chore:`
- **Branches:** `tipo/descricao` (ex.: `docs/fundacao`, `feat/ranking`)
- **Code review:** toda mudança entra na `main` via Pull Request (revisão de pelo menos 1 pessoa)
- **Idioma:** código e commits em inglês; documentação em português

## Equipe

| Papel | Responsabilidades | Pessoas |
|---|---|---|
| Hardware / Embedded | ESP32, sensores, firmware, instalação na escola | 1–2 |
| Backend / API | NestJS, banco, integração com sensores e simulação | 1–2 |
| Dashboard / UI | Mapa, ranking, alertas | 1 |
| IA / ML | Previsão de enchimento + notebooks | 1 |
| Integrador | GitHub (PRs, CI, deploy), README, relatório de extensão | 1 |

**Nomes a preencher** — alinhados na reunião de kickoff (decisões em [docs/DECISOES.md](docs/DECISOES.md)).

## Licença

Pendente (sugestão: MIT) — a definir com a equipe.