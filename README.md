# Estágio em Análise de Dados – SmartEnvios

Este repositório contém minha solução para o teste técnico da vaga de Estágio em Análise de Dados na **SmartEnvios**.

---

## Contexto

A SmartEnvios conecta lojas virtuais com transportadoras em todo o Brasil e lida com grandes volumes de dados logísticos e de atendimento. O time de Customer Success precisa entender:

1. Quais clientes estão com problemas recorrentes de entrega;
2. Qual o impacto disso no NPS e na recompra;
3. Quais transportadoras estão mais associadas a essas ocorrências;
4. Como isso varia por região e tipo de produto.

---

## Análises Desenvolvidas

### 1. Análise Exploratória

- Mais da metade (53,7%) dos chamados **não foram resolvidos**, indicando uma possível ineficiência no atendimento.
- O IV do canal e tipo de atendimento são **muito baixos**, sugerindo que eles não influenciam fortemente a resolução, mas há **padrões úteis**:
  - Atendimento do tipo **cadastro** tem 50,5% de resolução (acima da média).
  - Canal **chat** tem a maior taxa (48,7%), **email** a menor (43,9%).
  - Há combinações mais eficazes: **cadastro por telefone**, **financeiro por email**, **entrega por chat**.

### Hipóteses

- Chat está associado à agilidade?
- Cadastro é mais simples, por isso mais resolvido?
- Financeiro requer rastreabilidade, por isso melhor via email?
- Entrega precisa de informação em tempo real, por isso o chat é mais eficaz?

### Ações sugeridas

- Redirecionar atendimentos por canal mais eficaz (ex: **entrega no chat**, **financeiro no email**).
- Treinar equipe de **telefone para casos de entrega**.
- Evitar **chat para financeiro**, usar email ou formulário estruturado.
- Implementar sistema de **feedback por atendimento**.

---

### 2. Perfil dos Clientes

- **65%** dos clientes cadastrados vieram do **Norte e Nordeste**.
- **Norte e Nordeste somam R$ 45 milhões** em valor de pedidos.
- Os segmentos **eletrônicos e moda** representam **R$ 34 milhões** com taxa de recompra próxima de **99%**.
- Não há concentração em um único segmento.

### Hipóteses

- Clientes dessas regiões têm maior recompra ou NPS?
- Também apresentam menos problemas logísticos?

---

### 3. Problemas Logísticos e NPS

- **Problemas logísticos têm pouco impacto no NPS** (IV = 0,036).
- **Clientes que dão nota 0** têm maior taxa de resolução do que outros.
- **Não há correlação clara entre resolução e nota NPS**.
- Atendimento explica um pouco mais do NPS que logística, mas ainda assim é **baixo**.

#### Transportadoras com mais problemas por região.
- Norte e Nordeste concentram a maior parte dos problemas logísticos, totalizando 194 ocorrências (69% dos casos).
- Distribuição indica que nenhuma transportadora está isenta de problemas em regiões críticas.

#### Clientes com maior volume de problemas logísticos
- Ana Beatriz Freitas (5)

- Bruno Cunha, Luiz Felipe Silva, Pietro da Luz, Srta. Sarah Nogueira e Stephany Duarte (todos com 4)

### Dúvidas geradas

- Por que clientes com nota 0 têm **maior taxa de resolução**?
- Existe priorização de casos mais críticos?
- A infraestrutura ou cobertura logística no Norte e Nordeste pode estar impactando diretamente a qualidade da entrega.
- Determinados clientes podem estar localizados em áreas com baixa cobertura ou alta taxa de erro logístico.
- A falta de padronização entre transportadoras pode causar discrepâncias regionais de desempenho.
- Alguns clientes com múltiplas ocorrências talvez representem perfis com alta frequência de compra ou localização crítica.

---

### 4. Recompra e Satisfação

- Mesmo clientes com problemas **continuam recomprando**.
- **63% dos atendimentos** têm NPS até 6 → Indica insatisfação geral?

### Sugestão de melhoria no DW
- criar coluna "tempo de resposta" para medir SLA.

  ## 📌 Conclusão

- **Nem problemas logísticos nem atendimento são os principais drivers do NPS.**
- Mais da metade dos chamados (53,7%) não são resolvidos, indicando ineficiência.
- Atendimento e logística têm baixo IV, sugerindo baixo impacto direto no NPS, mas podem atuar de forma indireta.
- Existem diferenças claras por canal e tipo de atendimento, e a efetividade depende da combinação entre ambos.
- Clientes do Norte e Nordeste têm forte peso tanto em valor de pedidos quanto em problemas logísticos.
- Clientes com nota 0 são mais propensos a terem o problema resolvido, o que pode indicar priorização nos atendimentos mais críticos.
