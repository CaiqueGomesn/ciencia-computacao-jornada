# Experiência Prática 2 — Segurança e Confiança Calibrada na Interação com IA

Disciplina: Engenharia de Prompt e Aplicações em IA — 1º semestre

## Cenário analisado

Um desenvolvedor júnior solicitou a uma IA a implementação de um sistema
de armazenamento de senhas, utilizando um prompt genérico sem requisitos
de segurança explícitos. O resultado foi uma implementação funcional, porém
insegura — usando o algoritmo MD5 para hash de senhas.

## Análise da falha técnica

O MD5 (Message Digest Algorithm 5) é considerado obsoleto e inadequado
para proteção de senhas atualmente. Os principais problemas:

- **Alta velocidade de processamento** — facilita ataques de força bruta,
  permitindo testar milhões de combinações por segundo.
- **Vulnerabilidade a colisões** — diferentes entradas podem gerar o mesmo
  hash, comprometendo a integridade do sistema.
- **Ausência de salt obrigatório** — torna o sistema vulnerável a ataques
  com rainbow tables (tabelas pré-computadas de hashes comuns).

Segundo NIST e OWASP, algoritmos como MD5 e SHA-1 não devem ser utilizados
para armazenamento de senhas — a recomendação é bcrypt, Argon2 ou PBKDF2,
que incorporam fatores de custo (work factor) para tornar o processo de
hash deliberadamente mais lento e resistente a ataques.

## O problema real: confiança calibrada

A falha não estava apenas na escolha técnica do algoritmo, mas em como o
desenvolvedor interagiu com a IA. O prompt original era genérico e não
especificava requisitos mínimos de segurança — o que levou a IA a gerar
uma solução funcional, mas insegura.

Isso evidencia a ausência do conceito de **confiança calibrada**: a
capacidade de usar a IA como ferramenta de apoio sem aceitar suas
respostas de forma automática, avaliando criticamente a saída e validando
com conhecimento técnico antes de aplicá-la.

## Prompt otimizado

> Crie uma implementação em Python para armazenamento seguro de senhas,
> seguindo as melhores práticas de segurança da informação.
>
> Requisitos obrigatórios:
> - Utilize um algoritmo moderno e seguro de hash de senha, como bcrypt
>   ou Argon2 (preferencialmente Argon2).
> - Gere automaticamente um salt único e seguro para cada senha.
> - Implemente um fator de custo (work factor) adequado para dificultar
>   ataques de força bruta.
> - Utilize bibliotecas confiáveis e amplamente adotadas
>   (ex: argon2-cffi ou bcrypt).
> - Garanta que o processo de hash seja lento o suficiente para aumentar
>   a segurança.
>
> Funcionalidades necessárias:
> 1. Função para gerar o hash da senha (armazenamento seguro).
> 2. Função para verificar a senha informada comparando com o hash
>    armazenado.
> 3. Tratamento seguro de comparação (evitar timing attacks, se
>    aplicável).
>
> Boas práticas e segurança:
> - Siga recomendações da OWASP e NIST para armazenamento de senhas.
> - Não utilize algoritmos inseguros ou obsoletos como MD5 ou SHA-1.
> - Não armazene senhas em texto puro em nenhuma hipótese.
> - Documente brevemente o código explicando as decisões de segurança
>   adotadas.

## Por que esse prompt funciona

O prompt otimizado elimina a ambiguidade que permitiu à IA escolher
livremente (inclusive uma solução insegura). Ao introduzir restrições
explícitas — algoritmos permitidos, proibição de algoritmos obsoletos,
exigência de salt e work factor — o desenvolvedor exerce o papel de
**Navegador** no processo de colaboração com a IA, fornecendo contexto e
padrões de segurança, enquanto a IA atua como **Piloto**, executando a
implementação dentro dos limites definidos.

## Conclusão

Esse caso reforça que desenvolvedores não devem apenas utilizar
ferramentas de IA, mas atuar de forma crítica — validando respostas com
base em boas práticas e padrões atualizados de segurança, ao invés de
aceitar qualquer saída funcional como automaticamente correta.

---

[← Voltar para a pasta principal](README.md)
