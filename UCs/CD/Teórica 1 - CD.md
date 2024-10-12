15 Out → Mini-Teste

19 Nov → Mini-Teste

14 Jan → Freq. Final

---

### Distributed Systems → Livro

---

## Sistemas Distribuídos

Conjunto de componentes de software e hardware ligados por uma infraestrutura de comunicação. Os componentes cooperam e coordenam-se para realizar um objetivo comum.
- Aplicação distribuída
- Sistema Operativo distribuído
### Processadores em Rede

Cada processador executa uma instância distinta do SO, podendo ou não oferecer uma imagem de sistema único às aplicações.
A distribuição é gerida exclusivamente por software


### Razões para a distribuição

- Geografia
	- Organização com instalações em diferentes geografias com necessidade de ligações entre os seus diferentes pontos
- Extensabilidade e Modularidade
	- Crescimento gradual
- Partilha de recursos
	- Troca de informação entre departamentos, empresas
- Maior disponibilidade
	- Replicação
- Maior desempenho
	- Distribuição de carga

---
### Requisitos

- Utilizadores
	1. Transparência
	2. Partilha de Informação
	3. Melhoria da comunicação entre as pessoas
	4. Segurança e Proteção
	5. Fiabilidade e Disponibilidade
- Programadores
	1. Interfaces normalizadas
	2. Ambiente de programação independente das características do hardware e das redes
	3. Controlo sobre o desempenho, fiabilidade, disponibilidade e segurança
- Gestores de Recursos
	1. Investimento reduzido
	2. Modularidade e extensabilidade na evolução do sistema
		- Proteção do investimento
	3. Optimização da gestão dos recursos
	4. Desempenho, disponibilidade, fiabilidade e segurança

---
### Desafios dos Sistemas Distribuídos

Para que permitam uma melhor resolução dos problemas apontados, os Sistemas Distribuídos devem responder a um conjunto de desafios:

1. Heterogeneidade
2. Abertura
3. Segurança
4. Escabilidade
5. Gestão de falhas
6. Concorrência
7. Transparência

#### Heterogeneidade

Capacidade para suportar a variedade e a diferença.

- Redes e protocolos de comunicação
	- Diversidade de protocolos e meios de comunicação
- Hardware
	- A diversidade dos dispositivos com capacidades de programação é ilimitada
- Sistemas Operativos
	- Embora o Windows seja a plataforma dominante, existem outsiders que são cada vez mais significativos
- Linguagens de progrmação

É impossível um memso sistema suportar toda a diversidade fornecendo uma imagem única e integrada, para colmatar estas lacunas:

- Middleware
	- Camada intermédia de software que fornece um conjunto de serviços específicos e esconde a disparidade dos sistemas existentes
- Máquina Virtual
	- Nível de abstração que simula um processador uniforme que permite executar os mesmos programas em plataformas distintas -> mobilidade do código

---
#### Abertura

Característica de um sistema que determina a sua capacidade de extensão e modificação
- Num SD indica a possibilidade de adicionar novos serviços e de os tornar acessíveis às aplicações

A abertura pressupõe a especificação e documentação das interfaces de programação
- Publicação e/ou standardização de APIs
	- Protocolos de Internet alvo de RFCs da IETF, ISO e ITU
	- Interfaces de objetos especificadas pela OMG

Sistemas:
 - Abertos - Interfaces públicas e evolução controlada por orgnaismos de nomalização independentes
 - Prioritários - Interfaces desconhecidas e evolução dependendo dass leis do mercado e da estratégia comercial do fabricante

---

#### Segurança

A natureza dos SDs torna-os mais permeáveis a ataques
- Intrusos podem ler mensagens em trânsito, injetar novas mensagens
- Não existe controlo sobre o software, sistema e aplicações remotas

A utilização de sistemas distribuídos para realizar tarefas com valor acrescentado sobre dados sensíveis implica a necessidade de proteção eficaz.

Os SD têm portanto de fornecer:
- Autenticação dos interlocutores
- Controlo de acessos
- Confidencialidade e integridade dos dados enviados
- Disponibilidade dos serviços e canais de comunicação

Os requisitos de segurança mais difíceis de atingir:
- Proteção contra ataques de negação de serviço -> *Denial of Service*
- Certifica;\ao do c]odigo m]ovel na internet

---

#### Escalabilidade

A escalabilidade é a propriedade de um sistema que indica a sua capacidade em responder de forma linear a aumentos significativos da carga, número de utilizadores ou área de abrangência.

Aparente Paradoxo:
- Distribuição de carga -> Melhor desempenho
- Acesso remoto e não local -> Pior desempenho

Para garantir a escalabilidade de um SD:
- Limitar a necessidade de aumento do número de recursos:
	- O aumento da dimensão do sistema deve traduzir-se num aumento linear do número de recursos necessários -> O(n)
- Limitar a degradação de performance:
	- O aumento das necessidades de computação não deve conduzir a uma degradação de desempenho
- Evitar pontos de estrangulamento - *choke points*
	- Utilizar algoritmos descentralizados
	- Reduzir o número de mensagens através de caching e replicação
- Evitar limitações na previsão do número de recursos
	- As definições básicas do sistema devem prever a escalabilidade

Garantir a escalabilidade é um dos desafios dominantes no desenvolvimenot de um SD

---

#### Gestão de Falhas

Modelo de faltas mais complexo
- Máquinas falham independentemente
- Redes podem perder pacotes, trocar a sua ordem

Conhecimento parcial do estado do sistema
- Das outras máquinas, só se sabe realmente que uma mensagem chegou ou não
- Uma mensagem não chegou, porquê?
	- Perdeu-se
	- O emissor falhou
	- O emissor está muito lento

Aparente Paradoxo:
- Replicação -> Melhor disponibilidade
- Mais máquinas que podem falhar -> Pior disponibilidade

Deteção de Falhas
- Algumas falhas podem ser detetadas

Mascarar falhas
- Depois de detetadas, algumas falhas podem ser mascaradas

Tolerância a falhas
- Capacidade de tratar um erro previamente identificado, continuando a oferecer parte do serviço
- Especificação do comportamento na ocorrência de falhas

Recuperação de falhas
- Envolve a capacidade de recuperar o estado do sistema antes da falha e reconstitui-lo *rollback*
- Mecanismos complexos que envolvem a noção de transação

---
#### Concorrência

A existência de vários fluxos de execução implica acessos simultâneos a recursos partilhados.
Torna-se portanto necessário garantir a sincronização de certas operações para assegurar a coerência de dados
- Em cada componente, as instâncias de execução de objetos concorrentes utilizam os mecanismos clássicos de sincronização
- A nível global, são necessárias técnicas de sincronização específicas para algoritmos distribuídos

---

#### Transparência

A transparência é definida como a capacidade de esconder do utilizador e das aplicações a natureza distribuída do sistema
- O sistema aparece como um todo *Single System Image* e não como um conjunto de componentes

O projeto ANSA *Advanced Networked Systems Architecture* - 1989 foi um dos primeiros consórcios de empresas a abordar a normalização da arquitetura dos SDs e define os tipos de transparência

O modelo RM-ODP da ISO-ITU *Reference Model for Open Distributed Processing* introduz os seguintes 8 tipos de transparência:
1. Acesso
	- Permite acessos locais e remotos através de operações idênticas
2. Localização
	- Permite acessos a recursos sem conhecimento da sua localização física ou do seu endereço de rede
3. Concorrência
	- Permite que vários processos funcionem simultaneamente sem interferências utilizando recursos partilhados
4. Replicação
	- Permite que múltiplas instâncias de recursos sejam utilizadas para aumentar a fiabilidade e o desempenho sem conhecimento dos utilizadores ou dos programadores das aplicações
5. Falha
	- Permite o isolamento das falhas, fazendo com que os utilizadores e os programadores possam completar as suas tarefas em caso de mau funcionamento de componentes hardware ou software
6. Mobilidade
	- Permite a movimentação de recursos e componentes do sistema sem afetar o normal funcionamento dos programas e dos seus utilizadores
7. Desempenho
	- Permite que o sistema seja reconfigurado sem descontinuidade quando a sua carga varia
8. Escalabilidade
	- Permite que o sistema e as aplicações sejam expandidas sem modificação da sua arquitetura e dos seus algoritmos de funcionamento