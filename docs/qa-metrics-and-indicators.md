# Métricas e Indicadores de Qualidade de Software

> **QA Engineering Lab** · Guia educacional e exercício prático  
> **Objetivo:** interpretar indicadores de testes sem confundir atividade, cobertura e qualidade do produto.

## 1. Por que medir?

Métricas ajudam a responder perguntas sobre progresso, riscos, estabilidade e eficiência do processo de testes. **Nenhuma métrica isolada demonstra que um produto é de qualidade.** A interpretação depende de contexto, criticidade, escopo e confiabilidade dos dados.

**Métrica** é uma medida observável (por exemplo, quantidade de testes reprovados). **Indicador** combina medidas e contexto para apoiar decisões (por exemplo, tendência de falhas críticas antes de uma liberação).

## 2. Indicadores fundamentais

| Indicador | Cálculo | O que informa | Cuidado na interpretação |
|---|---|---|---|
| Progresso de execução | (Aprovados + Reprovados) / Casos cadastrados × 100 | Parcela de casos efetivamente executados | Casos bloqueados não contam como executados |
| Taxa de aprovação | Aprovados / (Aprovados + Reprovados) × 100 | Proporção de execuções aprovadas | Não mede cobertura de requisitos nem risco residual |
| Taxa de reprovação | Reprovados / (Aprovados + Reprovados) × 100 | Proporção de execuções com falha | Uma falha pode afetar muitos casos; casos podem repetir o mesmo defeito |
| Proporção automatizada | Casos marcados como automatizados / Casos cadastrados × 100 | Distribuição de casos com automação | Não mede valor, estabilidade ou eficácia da automação |
| Cobertura de requisitos | Requisitos cobertos por testes / Requisitos identificados × 100 | Rastreabilidade do escopo | Um requisito coberto não está necessariamente bem testado |
| Densidade de defeitos | Defeitos confirmados / Unidade de tamanho definida | Distribuição de defeitos em um escopo | Comparações exigem mesma unidade e critérios consistentes |
| Defeitos escapados | Defeitos encontrados após liberação / Defeitos encontrados antes e após liberação × 100 | Parcela de defeitos detectada após a liberação | Defina período, escopo e método de identificação |

**Regra importante:** defina claramente o denominador, o período de análise, a unidade de observação e o tratamento de casos bloqueados, não executados e repetidos.

## 3. Exemplo: ciclo de testes de um e-commerce

Considere 10 casos cadastrados: 6 aprovados, 2 reprovados, 1 bloqueado e 1 não executado.

- **Progresso:** (6 + 2) / 10 = **80%**.
- **Aprovação entre executados:** 6 / (6 + 2) = **75%**.
- **Reprovação entre executados:** 2 / (6 + 2) = **25%**.
- **Pendências de execução:** 2 casos (um bloqueado e outro não executado).

### Qual decisão tomar?

Não é possível aprovar uma liberação apenas com esses percentuais. Investigue a severidade dos defeitos, o motivo do bloqueio, a criticidade dos fluxos afetados e a cobertura de riscos prioritários. Uma única falha crítica de pagamento pode impedir a liberação, mesmo com alta taxa de aprovação.

## 4. Métricas de execução versus métricas de produto

**Execução e processo:** progresso, tempo, casos bloqueados, estabilidade de testes, tempo de reteste e tendência de defeitos.

**Produto e risco:** defeitos críticos em aberto, cobertura de funcionalidades essenciais, incidentes em produção, disponibilidade e confiabilidade observada.

Não use a quantidade de bugs encontrados como avaliação individual de produtividade. Mais bugs podem refletir maior complexidade, melhor investigação ou pior qualidade inicial — não necessariamente melhor desempenho do testador.

## 5. Como utilizar a planilha

Arquivo complementar: [`qa-metrics-dashboard.xlsx`](../exercises/qa-metrics-dashboard.xlsx)

1. Abra a aba **Execucoes** e examine os 10 casos fictícios.
2. Altere o resultado de `CT-002` de **Reprovado** para **Aprovado**.
3. Observe na aba **Painel** como mudam a taxa de aprovação e a quantidade de falhas.
4. Marque um caso como **Bloqueado** e verifique o efeito no progresso.
5. Discuta se alguma dessas alterações, isoladamente, justificaria uma liberação.

**Atenção:** a planilha usa linhas 2–101 como área de dados e considera cada linha um caso com um resultado corrente. Ela **não** é um histórico de múltiplas execuções, nem calcula automaticamente cobertura de requisitos ou defeitos escapados. Os dados são fictícios.

## 6. Exercícios de interpretação

**Exercício A — Aprovação alta, risco alto:** 98% dos casos passaram, mas o checkout apresenta falha crítica. Qual recomendação você faria ao time de produto? Justifique.

**Exercício B — Automação:** 90% dos casos estão automatizados, porém 30% dos testes são instáveis. Que indicadores adicionais você acompanharia?

**Exercício C — Cobertura:** 100% dos requisitos possuem ao menos um teste. Isso garante cobertura de limites, exceções e combinações? Proponha uma análise complementar.

## 7. Checklist para um painel confiável

- [ ] Cada indicador responde a uma pergunta ou decisão real.
- [ ] Numerador, denominador e período estão documentados.
- [ ] Casos bloqueados e não executados são diferenciados.
- [ ] Resultados não são confundidos com quantidade de defeitos únicos.
- [ ] Indicadores são analisados por criticidade e risco.
- [ ] Tendências são consideradas, não apenas fotografias de um dia.
- [ ] Dados fictícios e reais estão claramente identificados.
- [ ] O painel não é usado para classificar pessoas por número de bugs.

## 8. Como evoluir este laboratório

Uma próxima versão poderá incluir histórico por execução, análise de tendência por sprint, cobertura por risco e um catálogo de defeitos com identificadores únicos. Essas evoluções devem ser feitas apenas quando houver dados consistentes e perguntas concretas a responder.

---

**Referências para aprofundamento:** ISTQB CTFL (fundamentos de testes), ISO/IEC 25010 (modelo de qualidade de produto) e documentação de métricas e observabilidade adotada pela equipe.
