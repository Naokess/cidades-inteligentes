# Registro de Decisões (ADR)

Decisões do projeto em uma linha do tempo — para a equipe não re-discutir o que já foi decidido. Formato: `status | data | decisão | motivo`.

## Decidido

| Data | Decisão | Motivo |
|---|---|---|
| 04/09 | Repositório único (monorepo) `cidades-inteligentes` | Um único histórico e uma história contínua no currículo; o evento de 19/09 é o Marco 1, não um projeto paralelo |
| 04/09 | Backend: NestJS + Prisma + PostgreSQL | Mesma base do projeto anterior da equipe (reuso de conhecimento); pilar "Dados e API" do documento de ideias |
| 04/09 | Dashboard web separado (`apps/web`) | Pilar "Engajamento"; telas do evento (placar) e do monitoramento (mapa) são a mesma aplicação |
| 04/09 | Código e commits em inglês; documentação em pt-BR | Convenção de mercado + legibilidade para a equipe e o professor |
| 04/09 | Conventional commits (`docs:`, `feat:`, `fix:`) | Histórico legível como um jornal; padrão usado na indústria |
| 04/09 | Toda mudança entra na `main` via Pull Request | Code review obrigatório com 6 pessoas; `main` sempre funcional (ver ROADMAP) |
| 04/09 | Banco e serviços via Docker Compose local | Todo mundo roda o mesmo ambiente; modo simulação sem hardware (diferencial do repo) |
| 04/09 | Evento de 19/09 = Marco 1 do roteiro | O ranking por kg É a Camada 3 (Engajamento) do projeto final; dados reais para a IA depois |
| 04/09 | Modelo de dados inicial: `Equipe` + `Pesagem` | Só o que o evento precisa agora (YAGNI); sensores entram no Marco 2 |
| 04/09 | Idiomas dos documentos da equipe: português | Público (professor, escola, relatório de extensão) é pt-BR |

## Pendente

| Decisão | Quando resolver |
|---|---|
| Sistema de monitoramento concreto validado com a escola (ex.: lixo) | Reunião com a escola |
| Público alvo das camadas 2 e 3 (visão computacional, chatbot, totem — provavelmente adiados) | Fim do Marco 1 |
| Deploy: rodar local no evento vs nuvem | Reunião com a escola (depende de WiFi/internet de lá) |
| Framework do dashboard web | Aula 4 (scaffold) |
| Nomes/papéis da equipe no README | Reunião de kickoff |
| Licença (sugestão: MIT) | Reunião de kickoff |
| Nome "oficial" do projeto para o relatório | Reunião de kickoff |

## Pauta para a reunião com a escola (issue #1)

- [ ] Validar o foco: monitoramento de lixo é o sistema escolhido pela escola?
- [ ] No dia 19/09: quem pesa? onde? quantas equipes? onde o placar fica (projetor/TV)?
- [ ] A escola tem WiFi disponível para o sistema rodar no evento (ou usamos notebook local)?
- [ ] Depois do evento: onde instalar a lixeira inteligente (Marco 2)? quem autoriza?
- [ ] Uso de fotos/dados anonimizados para relatório e README (autorização da direção)