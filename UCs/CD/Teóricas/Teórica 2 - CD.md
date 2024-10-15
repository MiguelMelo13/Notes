### Arquiteturas de Sistemas Distribuídos

A arquitetura defie a estrutura de um sistema distribuído em termos de componentes especificáveis separadamente, fornecendo um modelo para:
- Especificação
- Desenvolvimento
- Funcionamento
- Evolução

O modelo de arquitetura
- Define a funcionalidade e localização dos componentes do sistema
- Identifica as relações e os padrões de comunicação existentes entre eles

A correta definição de uma arquitetura é importante para garantir
- Desempenho
- Fiabilidade
- Segurança
- Modularidade

---

#### Componentes da Arquitetura

- Processo
	- Unidade de execução de programas num sistema
- Objeto
	- Unidade de encapsulamento de código e/ou dados
	- Os objetos são instanciados e executados em processos
- Serviço
	- Unidade funcional de distribuição que gere recursos e fornece funcionalidades a aplicações e utilizadores
	- É implementado por objetos executados num ou vários processos
	- É definido por uma interface e um protocolo
	- Deve poder ser identificado e localizado
- Servidor
	- Componente que fornce um ou mais serviços, podendo abranger u ou mais componentes de hardware
- Cliente
	- Entidade que invoca os serviços num servidor

---

#### Tipos de Arquitetura

- Multi-nível
- Service-Oriented Architectures -> SOA #Soa 
	- Cliente - Servidor, Servidor com cache
	- Object-based architectures
	- Resource-based Architectures
- Peer to Peer #P2P
- Código Móvel #MobileCode 
- Cloud Computing #CloudComputing

---

####  #Soa 

Arquitetura tradicional dos Sistemas Distribuídos

- Caracteriza um sistema em que só há dois tipos de componentes
	- ==Simples e fácil de implementar==
- Servidor executa operações invocadas pelos clientes retornando resultados
- Cliente invoca operações em servidores
- Mensagem composta por dados trocados entre cliente e servidor obecendo a um formato específico do serviço

Modelo de invocação de request/reply com envio e retorno de mensagens. Geralmente síncrono, o cliente espera pelo retorno da invocação

Relação de N para 1 pode trazer problemas de desempenho e fiabilidade
- Toda a carga é concentrada no servidor -> bottleneck
- A escalabilidade é probemática
- ==Ponto de falha único: Servidor==

---

#### O que define a arquitetura de uma aplicação distribuída?

A arquitetura de uma aplicação distribuída refere-se à forma como os componentes da aplicação são organizados e interagem entre si através de diferentes sistemas ou nodos conectados por uma rede.

1. Componentes - As aplicações distribuídas geralmentes são divididas em componentes ou serviços que podem ser executados independentemente em diferentes sistemas.
	1. Servidores
	2. Clientes
	3. Mediadores
2. Modelo de Comunicação - A maneira como os componentes comunicam uns com os outros pode ser síncrona ou assíncrona e envolve protocolos de comunicação como HTTP.
3. Escalabilidade e Disponibiliade - Assegura que a aplicação pode crescer em termos de carga e número de usuários e garante que os serviços estejam disponíveis mesmo quando alguns componentes falham.
4. Consistência
5. Segurança
6. Middleware - Utilizado para abstrair a comunicação entre os componentes e facilitar a integração de diferentes plataformas e linguagens.

#### Porque é que a programação de servidores replicados pode ser mais complexa?

Principalmente devido à necessidade de manter a consistência, coordenação e tolerância a falhas entre múltiplas réplicas de servidores. É necessário manter um estado consistente nas várias réplicas de servidor. A consistência forte é difícil manter devido à latência da rede e à possibilidade de falhas; a consitência individual é mais flexível mas de maior complexidade de implementação.

A replicação de servidores oferece benefícios em termos de escalabilidade, desempenho e tolerância a falhas, mas também requer uma gestão cuidadosa de consistência, comunicação e sincronização entre as réplicas. O uso de algoritmos de consenso, gestão de conflitos, e otimização de latência e balanceamento de carga contribui para tornar a programação de servidores replicados um desafio complexo.

#### Resposta Iterativa != Resposta Recursiva

==Iterativa== - Um servidor recebe um pedido e, se não puder satisfazê-lo diretamente, repsonde ao cliente com a informação necessária para que o cliente faça o próximo pedido a outro servidor. O servidor não faz mais do que encaminhar o cliente para o próximo passo.

==Recursiva== - O servidor que recebe o pedido assume a responsabilidade por resolver o pedido na totalidade. Se ele não tiver a resposta, consulta outros servidores até obter a informação correta e só então retorna a resposta final ao cliente.

Uma **resposta iterativa** coloca o trabalho de resolver o pedido nas mãos do cliente, enquanto uma **resposta recursiva** coloca essa responsabilidade no servidor.

A escolha entre uma abordagem iterativa ou recursiva depende do contexto e dos requisitos da aplicação, como a carga que se pretende no servidor versus a simplicidade para o cliente e a latência aceitável.

### Comparação entre Resposta Iterativa e Recursiva:

|**Característica**|**Resposta Iterativa**|**Resposta Recursiva**|
|---|---|---|
|**Responsabilidade**|Cliente faz vários pedidos a diferentes servidores.|Servidor lida com todas as consultas até obter a resposta final.|
|**Carga no cliente**|Alta, pois o cliente faz múltiplos pedidos.|Baixa, o cliente faz apenas um pedido.|
|**Carga no servidor**|Baixa, o servidor apenas fornece dicas ou respostas parciais.|Alta, o servidor faz todo o trabalho de consulta.|
|**Latência**|Maior, pois o cliente faz múltiplos pedidos sequenciais.|Menor, o cliente espera por uma única resposta.|
|**Complexidade no servidor**|Menor, o servidor não precisa de realizar consultas adicionais.|Maior, o servidor deve lidar com consultas recursivas.|


#### Quais são as vantagens da utilização de um servidor proxy com cache?

A utilização de um servidor proxy com cache oferece vantagens em termos de desempenho, eficiência de rede e segurança. Um proxy com cache armazena localmente os conteúdos que foram previamente requisitados, permitindo que esses mesmos conteúdos sejam fornecidos a outros utilizadores sem necessidade de refazer o pedido ao servidor original.

- **Desempenho**: Respostas mais rápidas e menos carga nos servidores de origem.
- **Economia de largura de banda**: Redução de tráfego externo, poupando recursos de rede.
- **Escalabilidade**: Suporte a um maior número de utilizadores sem sobrecarregar o servidor principal.
- **Disponibilidade**: Continuação do acesso a conteúdos durante falhas no servidor de origem.
- **Segurança**: Proteção adicional contra ataques e filtragem de conteúdos indesejados.
- **Controle**: Monitorização e gestão detalhada do tráfego.

A implementação de um servidor proxy com cache é uma solução eficaz para melhorar a eficiência e a experiência do utilizador em redes empresariais, educacionais, ou em qualquer ambiente onde haja grande tráfego de dados.