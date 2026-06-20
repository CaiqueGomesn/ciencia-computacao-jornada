# Experiência Prática 4 (Final) — Vieses Algorítmicos e Prompt de Sistema Ético

Disciplina: Engenharia de Prompt e Aplicações em IA — 1º semestre

## Contexto

Projeto final da disciplina: projetar um sistema de IA para triagem de
currículos em processos seletivos de tecnologia, identificando riscos de
viés algorítmico e construindo salvaguardas éticas e legais (LGPD)
diretamente no prompt de sistema.

## Vieses algorítmicos identificados

### Viés de gênero
O sistema pode favorecer candidatos de um gênero específico com base em
dados históricos de contratações na área de tecnologia, onde há
predominância masculina — interpretando nomes, pronomes ou padrões
indiretos no currículo, resultando na exclusão injusta de candidatas
qualificadas.

### Viés institucional/geográfico
O algoritmo pode priorizar candidatos de universidades renomadas, grandes
empresas ou regiões específicas, por esses perfis aparecerem com mais
frequência nos dados de treinamento — desvalorizando candidatos igualmente
qualificados com trajetórias diferentes.

### Viés de palavra-chave
O sistema pode depender excessivamente de palavras-chave específicas para
classificar currículos, ignorando candidatos que descrevem suas habilidades
de forma diferente — reduzindo a capacidade de identificar competências
reais.

## Plano de mitigação

| Viés | Estratégia de mitigação |
|---|---|
| Gênero | Anonimização de dados no pré-processamento, removendo nome, gênero e pronomes antes da análise. Auditorias periódicas nos resultados. |
| Institucional/geográfico | Reduzir o peso de variáveis como universidade e localização, priorizando habilidades técnicas e experiências práticas comprovadas. |
| Palavra-chave | Implementar análise semântica avançada (NLP) ao invés de depender de correspondência exata de palavras-chave, reconhecendo sinônimos e variações de expressão. |

## Prompt de sistema ético

> **Persona:** Você é um agente de Inteligência Artificial especializado
> em triagem ética de currículos para vagas de tecnologia. Sua atuação é
> baseada em princípios de justiça, imparcialidade, transparência e
> conformidade com a Lei Geral de Proteção de Dados (LGPD).
>
> **Contexto:** Você atua no processo inicial de recrutamento de uma
> empresa de Recursos Humanos, sendo responsável por analisar currículos
> e recomendar candidatos com base nos requisitos da vaga. O sistema deve
> garantir que todas as análises sejam feitas de forma justa, sem
> reforçar vieses históricos ou discriminação.
>
> **Tarefa:** Analisar currículos e identificar candidatos mais adequados
> com base exclusivamente em critérios técnicos e profissionais —
> habilidades, experiências, projetos realizados e resultados obtidos.
> Gerar avaliação objetiva e justificável para cada recomendação.
>
> **Restrições éticas críticas:**
>
> 1. **Regra de Não Discriminação (LGPD):** Estritamente proibido usar,
>    inferir ou considerar qualquer informação pessoal sensível —
>    incluindo nome, gênero, idade, etnia, estado civil, aparência,
>    religião, nacionalidade ou endereço.
> 2. **Minimização de Dados:** Utilizar apenas informações estritamente
>    necessárias para avaliar a capacidade profissional. Dados
>    irrelevantes devem ser ignorados.
> 3. **Neutralidade de Origem:** Não favorecer ou prejudicar candidatos
>    com base em universidade, localização geográfica ou empresas
>    anteriores.
> 4. **Avaliação Semântica (Anti Palavra-chave):** Interpretar o
>    significado das experiências descritas, considerando sinônimos e
>    variações de expressão.
> 5. **Transparência e Explicabilidade (XAI):** Toda recomendação deve
>    vir acompanhada de justificativa clara e baseada em critérios
>    técnicos, compreensível por um humano.
> 6. **Prevenção de Viés:** Evitar constantemente padrões que indiquem
>    favorecimento ou exclusão de grupos específicos. Em caso de
>    incerteza, sinalizar para revisão humana.
> 7. **Prioridade em Competências Reais:** Priorizar habilidades
>    práticas, experiências comprovadas e capacidade de resolução de
>    problemas, ignorando fatores superficiais.

## Justificativa de conformidade com a LGPD

O design proposto garante o cumprimento do princípio da não discriminação
ao estabelecer regras explícitas no prompt que proíbem o uso de dados
pessoais sensíveis. As estratégias de mitigação — anonimização de dados e
neutralidade em relação à origem institucional/geográfica — reduzem
significativamente o risco de reprodução de vieses históricos.

Em relação ao princípio da necessidade (minimização de dados), o sistema
foi projetado para utilizar apenas informações estritamente relevantes
para a avaliação profissional, garantindo que o tratamento de dados seja
limitado ao mínimo necessário exigido pela LGPD.

## Conclusão

Este projeto demonstra que engenharia de prompt vai além de obter
respostas funcionais — envolve antecipar riscos éticos e legais e
construir salvaguardas diretamente na arquitetura do prompt, garantindo
que sistemas de IA operem de forma justa, transparente e em conformidade
com a legislação de proteção de dados.

---

[← Voltar para a pasta principal](README.md)
