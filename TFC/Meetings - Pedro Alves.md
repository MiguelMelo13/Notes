# Meeting 1

## Fase de análise - Interlocutores

- Formadas em psicologia
- Reuniao com o departamento de RH → 2/09/2024
- Elisabete Cipriano → A terminar tese mestrado sobre as competências que um lider (diretor de departamento → **chefias intermédias**) deve ter na ULHT. Foco nas caracteristicas comportamentais. [elisabete.cipriano@ulusofona.pt](mailto:elisabete.cipriano@ulusofona.pt)
- Paula Cipriano → Trabalho focado nos alunos em que se pretende perceber o perfil dos alunos de cada curso. Perceber se o aluno tem o perfil adequado à profissão que pode vir a desempenhar no final do curso. Comparação do perfil médio de alunos atuais com o perfil ideal. A ser feito/avalido ao longo do seu percurso na faculdade para que o aluno e departamento tenham feedback da evolução das competências desenvolvidas. [paula.cipiriano@ulusofona.pt](mailto:paula.cipiriano@ulusofona.pt)
- Orientador das irmãs Cipriano - Carlos Rouco → [p5540@ulusofona.pt](mailto:p5540@ulusofona.pt)

---

## Requisitos Técnicos

- Profs sem foco no telemóvel
- Alunos com foco no telemóvel, sem ser app mas sim site responsivo
- Login do moodle igual ao DP e plataforma de TFCs. Ambos feitos em Spring
    - Autenticação própria da ULHT desenvolvida pelo P.A.

---

### Professores → Elisabete C.

- Formulário disponível apenas para os profs. listar os “Ps” (email profs)
    - 8 perguntas de resposta aberta → tem que ficar definido na reunião com RH
    - Cruzar respostas para avaliação
        - Guardar avaliações e perceber se se identifica com o que é respondido
    - Submete → BD
    - Construção do perfil com NLP → Extrair conceitos/keywords
        - Ex: Coragem sem que seja utilizada a palavra coragem especificamente
        - Complexidade de semântica com algoritmos pré cosntruídos
        - Recolher exemplos de transformações e extrações. Pedir exemplos à E.C. que fez manualmente para garantirmos termos de comparação.
- Apresentação de resultados
    - Rever com E.C. e P.C.
    - Mostrar a quem respondeu ao formulário
    - 8+ respostas já é estatiscamente signidicativo
    - Acesso ao perfil público ou por grupos?  
- Tratamento de dados “anónimo”
    - Dados não podem ser ligados a quem respondeu

---

### Alunos → Paula C.

- Sem perguntas abertas
- Pedir documento de perguntas e respostas possíveis
    - Perguntas curtas por ser focado em telemóvel
- Dados socio-demográficos a recolher → Perguntar P.C
- Anonimidade semelhante aos profs.
    - Ou vê no momento de submissão ou nunca mais vê a avaliação
    - Botão para gravar avaliação
    - E se o aluno responder várias vezes?
- Programa calcula perfil sem NLP
    - Pedir algoritmo → Escadinha de ifs. Procurar forma melhor de programar o cálculo
    - Geral e por curso e por departamento → Confirmar P.C.
- O aluno é suposto ver as competências calculadas?
    - Notificação de submissão
- RH tem que ter acesso ao resultado
    - mostrar competências que mais aparecem?
    - perguntar forma de apresentação de resultados

---

### RoadMap

1. Marcar reunião com RH após email do P.A.
    1. 2 separadas, para alunos e para profs.
    2. Validar features pedidas com P.A. após reunião
2. Levantamento de Requisitos
3. Protótipo em NÃO Axure → Desenho de ecrãs
    1. Muito back and forward
4. Final de Dezembro estão feitos 2. e 3. e aprovados pelo cliente
5. Entrega 1º relatório → Dezembro
    1. Levantamento de Requisitos
    2. Mock-ups
    3. Esquema de base de dados
6. Janeiro começa-se com SpringBoot → Implementação
7. Versão de Teste em Maio (mais tardar), apontar para Abril
    1. Conjunto de alunos para teste
    2. Chefias Intermédias para testar
    3. RH para testar
    4. Avaliação de teste → IHM
8. Aplicação fechada em Junho


---
---

# Meeting 2

"Mais vale ter menos do que não ter nada"

- incluir no portal do colaborador do link externo
- Reduzir o numero de perguntas para alunos e testar para ver quem responde ou não, ver a adesão
- Fazer inquérito para ver a adesão
	- recompensa será a lista de competências do curso que estão a tirar
- Apros preencher recebe um email com um ID 10+ digitos

Documento de requisitos para validar com RH e ser firme com o estabelecido

Proximos passos:

Inquerito
Lista de requisitos
