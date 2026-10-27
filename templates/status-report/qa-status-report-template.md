# QA Status Report — Template

> **Objetivo:** comunicar o progresso dos testes, os riscos remanescentes e as informações necessárias para uma decisão consciente sobre a liberação.  
> **Uso:** acompanhamento semanal, encerramento de sprint, homologação ou avaliação pré-release.  
> **Nota:** este é um modelo educacional. Adapte indicadores e critérios ao contexto do produto.

## 1. Identificação

| Campo | Preenchimento |
|---|---|
| Produto / Projeto | `[Nome]` |
| Release / Sprint | `[Versão ou período]` |
| Período analisado | `[DD/MM/AAAA a DD/MM/AAAA]` |
| Data de emissão | `[DD/MM/AAAA]` |
| Responsável por QA | `[Nome]` |
| Ambiente | `[Homologação / Staging / Outro]` |
| Escopo avaliado | `[Funcionalidades / histórias / integrações]` |
| Fontes de dados | `[Ferramenta de testes, issue tracker, pipeline etc.]` |

## 2. Resumo executivo

**Situação geral:** `[Verde / Amarelo / Vermelho]`  
**Tendência em relação ao relatório anterior:** `[Melhorou / Estável / Piorou / Sem comparação]`  
**Recomendação de QA:** `[Favorável / Favorável com ressalvas / Desfavorável / Dados insuficientes]`

**Síntese (3 a 5 frases):**

> `[Descreva o que foi validado, o progresso, os principais problemas, o impacto para o negócio e o que ainda precisa acontecer.]`

### Critérios sugeridos para o semáforo

| Cor | Interpretação sugerida |
|---|---|
| 🟢 Verde | Critérios acordados atendidos; riscos residuais conhecidos e aceitos pelas partes responsáveis. |
| 🟡 Amarelo | Existem pendências ou riscos relevantes; é necessária mitigação, decisão explícita ou acompanhamento. |
| 🔴 Vermelho | Há impedimento crítico, risco inaceitável ou ausência de evidência essencial para recomendar a liberação. |

> **Atenção:** o semáforo é uma síntese contextual, não um cálculo automático pela taxa de aprovação. Defina os critérios com o time antes de utilizá-lo.

## 3. Escopo e cobertura

| Item de escopo | Planejado | Coberto por testes? | Resultado / observação |
|---|---|---|---|
| `[Funcionalidade A]` | Sim | `[Sim/Parcial/Não]` | `[Observação]` |
| `[Funcionalidade B]` | Sim | `[Sim/Parcial/Não]` | `[Observação]` |
| `[Integração C]` | Sim | `[Sim/Parcial/Não]` | `[Observação]` |

**Fora do escopo / limitações:** `[Liste exclusões, ambientes indisponíveis, integrações simuladas e lacunas de cobertura.]`

> Cobertura deve ser interpretada conforme o critério adotado: requisitos, riscos, fluxos, regras de negócio ou outro. Quantidade de casos não equivale automaticamente a cobertura funcional.

## 4. Execução dos testes

| Indicador | Valor | Como interpretar |
|---|---:|---|
| Casos planejados | `[N]` | Total previsto para o escopo do relatório. |
| Casos executados | `[N]` | Casos com resultado de execução registrado. |
| Aprovados | `[N]` | Casos executados que atenderam ao resultado esperado. |
| Reprovados | `[N]` | Casos executados com comportamento divergente. |
| Bloqueados | `[N]` | Casos que não puderam ser executados/concluídos. |
| Não executados | `[N]` | Casos ainda pendentes de execução. |
| Taxa de execução | `[%]` | Executados ÷ planejados × 100. |
| Taxa de aprovação | `[%]` | Aprovados ÷ (aprovados + reprovados) × 100. |

**Convenção adotada:** neste modelo, *bloqueados* e *não executados* não entram no denominador da taxa de aprovação. Ajuste se a equipe tiver outra convenção e documente-a. Verifique a consistência: `planejados = aprovados + reprovados + bloqueados + não executados` quando cada caso possui um único status vigente.

## 4.1 Régua de progresso das atividades de QA

Use a régua abaixo para mostrar **em que etapa está o trabalho**, sem confundi-la com o resultado dos casos de teste. Atualize o estado de cada fase conforme evidências verificáveis.

| Etapa | Situação | Evidência ou pendência |
|---|---|---|
| Planejamento e escopo | `[Concluída / Em andamento / Não iniciada / Não aplicável]` | `[Link ou observação]` |
| Análise de riscos | `[Situação]` | `[Link ou observação]` |
| Design e revisão de testes | `[Situação]` | `[Link ou observação]` |
| Preparação de ambiente e dados | `[Situação]` | `[Link ou observação]` |
| Execução funcional / integração | `[Situação]` | `[Link ou observação]` |
| Retestes e regressão | `[Situação]` | `[Link ou observação]` |
| Avaliação dos critérios de saída | `[Situação]` | `[Link ou observação]` |

**Leitura rápida (substitua pelos estados reais):**

`[✓ Planejamento] → [✓ Riscos] → [✓ Design] → [~ Ambiente] → [~ Execução] → [· Regressão] → [· Saída]`

Legenda: `✓` concluída · `~` em andamento · `·` não iniciada · `!` bloqueada. A régua é uma **visão de atividades**, não uma porcentagem de qualidade. Etapas podem ocorrer em paralelo; adapte-as ao processo do time.

## 4.2 Régua de execução dos casos de teste

Exiba a composição dos **casos planejados** em uma barra de 20 blocos, acompanhada dos números exatos. Cada bloco representa aproximadamente 5% do total; arredondamentos são apenas visuais.

**Modelo para preencher:**

`[Aprovados ████████ | Reprovados ███ | Bloqueados ██ | Não executados ███████]`

| Status | Quantidade | % dos planejados |
|---|---:|---:|
| 🟩 Aprovados | `[N]` | `[N ÷ total × 100]` |
| 🟥 Reprovados | `[N]` | `[N ÷ total × 100]` |
| 🟨 Bloqueados | `[N]` | `[N ÷ total × 100]` |
| ⬜ Não executados | `[N]` | `[N ÷ total × 100]` |
| **Total** | **`[N]`** | **100%** |

> **Importante:** a barra é um apoio visual e deve sempre vir acompanhada da tabela numérica, para acessibilidade e precisão. Não inclua casos bloqueados entre os executados na convenção deste template. Se o escopo mudar, informe a alteração do denominador.

**Evolução desde o relatório anterior:** `[Ex.: +12 executados, -3 bloqueados, 2 defeitos corrigidos.]`

## 5. Defeitos e pendências

### Visão consolidada

| Severidade | Abertos | Em correção | Prontos para reteste | Observação |
|---|---:|---:|---:|---|
| Crítica | `[N]` | `[N]` | `[N]` | `[Impacto]` |
| Alta | `[N]` | `[N]` | `[N]` | `[Impacto]` |
| Média | `[N]` | `[N]` | `[N]` | `[Impacto]` |
| Baixa | `[N]` | `[N]` | `[N]` | `[Impacto]` |

> Para evitar dupla contagem, use **Abertos** como total de defeitos ainda não encerrados e as colunas seguintes como subconjuntos desse total. Se sua ferramenta usar outros estados, adapte a tabela.

### Defeitos prioritários

| ID / Link | Descrição objetiva | Severidade | Impacto | Responsável | Previsão / decisão |
|---|---|---|---|---|---|
| `[BUG-001]` | `[Descrição]` | `[Crítica/Alta/...]` | `[Negócio/usuário]` | `[Nome/time]` | `[Data/ação]` |

## 6. Riscos, bloqueios e dependências

| ID | Risco / impedimento | Probabilidade | Impacto | Mitigação / ação | Responsável | Prazo | Situação |
|---|---|---|---|---|---|---|---|
| `[R-001]` | `[Descrição]` | `[1–5]` | `[1–5]` | `[Ação]` | `[Nome]` | `[Data]` | `[Aberto/Em andamento/Resolvido]` |

**Risco residual relevante:** `[Descreva o que permanece mesmo após a mitigação e quem deve aceitar esse risco.]`

## 7. Critérios de saída e avaliação de release

| Critério acordado | Evidência / situação | Atendido? |
|---|---|---|
| `[Ex.: fluxos críticos executados]` | `[Link / resumo]` | `[Sim/Não/Parcial]` |
| `[Ex.: nenhum defeito crítico aberto]` | `[Consulta / resumo]` | `[Sim/Não/Parcial]` |
| `[Ex.: integrações essenciais validadas]` | `[Evidência]` | `[Sim/Não/Parcial]` |
| `[Ex.: riscos residuais avaliados]` | `[Registro / responsável]` | `[Sim/Não/Parcial]` |

**Recomendação fundamentada de QA:**

> `[Declare se recomenda ou não a liberação, quais evidências sustentam a posição e quais condições precisam ser atendidas. A decisão final de negócio/release cabe aos responsáveis definidos pela organização.]`

**Aceite de riscos / decisão de release (se aplicável):** `[Responsável, data, registro da decisão e condições.]`

## 8. Próximos passos

| Ação | Responsável | Prazo | Critério de conclusão |
|---|---|---|---|
| `[Retestar BUG-001]` | `[Nome]` | `[Data]` | `[Evidência de correção]` |
| `[Executar regressão crítica]` | `[Nome]` | `[Data]` | `[Casos prioritários concluídos]` |

## 9. Evidências e referências

- Plano / estratégia de testes: `[Link relativo ou URL]`
- Matriz de rastreabilidade: `[Link]`
- Execuções e evidências: `[Link]`
- Defeitos: `[Link]`
- Matriz de riscos: `[Link]`
- Dashboard de métricas: `[Link]`

---

## Exemplo didático preenchido — Login (dados fictícios)

**Contexto:** release de autenticação web, ambiente de homologação, 20 casos planejados.

| Indicador | Valor |
|---|---:|
| Planejados | 20 |
| Aprovados | 12 |
| Reprovados | 3 |
| Bloqueados | 2 |
| Não executados | 3 |
| Executados | 15 |
| Taxa de execução | 75% |
| Taxa de aprovação | 80% |

**Régua de execução (20 casos):**

`[🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 | 🟥🟥🟥 | 🟨🟨 | ⬜⬜⬜]`

- **Aprovados:** 12/20 (60% do planejado)
- **Reprovados:** 3/20 (15%)
- **Bloqueados:** 2/20 (10%)
- **Não executados:** 3/20 (15%)

**Régua das atividades (exemplo):**

`[✓ Planejamento] → [✓ Riscos] → [✓ Design] → [✓ Ambiente] → [~ Execução] → [! Reteste] → [· Saída]`

O reteste está impedido pela correção pendente; a etapa de avaliação de saída ainda não foi concluída.

**Resumo executivo:** status **🔴 Vermelho**. A execução avançou para 75%, porém existe um defeito de severidade alta que permite comportamento incorreto na recuperação de senha, além de dois casos bloqueados por indisponibilidade do serviço de e-mail. A taxa de aprovação de 80% não neutraliza esses riscos.

**Recomendação de QA:** **desfavorável à liberação neste momento**. Corrigir e retestar o defeito prioritário, restabelecer a dependência, executar os casos bloqueados e concluir a regressão dos fluxos críticos antes de uma nova avaliação.

> Os dados deste exemplo são fictícios e ilustram como interpretar indicadores em conjunto com riscos, não uma regra universal de aprovação.

## Checklist antes de publicar o relatório

- [ ] O período, a versão e o ambiente estão identificados.
- [ ] Os números são consistentes e possuem fonte verificável.
- [ ] As fórmulas e convenções estão explícitas.
- [ ] As réguas correspondem aos números e às evidências do período.
- [ ] A cobertura e as limitações estão descritas.
- [ ] Defeitos relevantes incluem impacto e encaminhamento.
- [ ] Riscos e impedimentos têm responsáveis e ações.
- [ ] A recomendação de QA está sustentada por evidências.
- [ ] A decisão final e o aceite de riscos não são atribuídos automaticamente ao QA.
- [ ] Não há dados sensíveis, credenciais ou informações internas indevidas.

## Como utilizar no QA Engineering Lab

1. Copie este arquivo para o projeto que será acompanhado e renomeie-o com o período ou release, por exemplo `qa-status-report-release-1.2.md`.
2. Preencha os dados a partir de fontes verificáveis e mantenha links para as evidências.
3. Use o guia `docs/qa-metrics-and-indicators.md` para interpretar as métricas.
4. Se necessário, utilize `exercises/qa-metrics-dashboard.xlsx` como apoio didático para cálculos.
5. Atualize o relatório na cadência acordada; preserve relatórios anteriores para análise de tendência.

**Licenciamento:** consulte as condições de reutilização dos materiais educacionais em `LICENSE-CONTENT.md` na raiz do repositório.
