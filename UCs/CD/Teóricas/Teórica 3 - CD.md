#### #ArquiteturasMulti-Nível

![[Pasted image 20241014221917.png]]

A partição das funcionalidades entre cliente e servidor pode ser feita a vários níveis:
- Terminais alfanuméricos clássicos
- Terminais X - Cliente corre SO e um servidor X
- Network Computers - cliente corre SO mas não tem disco
- Browser (Thin Client) - cliente só executa interface utilizador
- Aplicações Empresariais interativas têm geralmente 3 camadas #ThreeTier 

---
#### #ThreeTier 

1. Nível de Apresentação - Nível mais elevado, interface. Principal função é traduzir as tarefas e resultados de forma a que o utilizador compreenda.
2. Nível Lógico - Coordena a aplicação, processa os comandos, toma decisões lógicas e faz avaliações. Move e processa dados entre os dois outros níveis.
3. Nível de Dados - Onde é guardada a informação e consultada a partir de uma base de dados ou sistema de ficheiros. A informação é então passada de volta para o nível lógico para ser processada e enviada para o utilizador.

##### Qual é a vantagem de separar os 3 níveis numa arquitetura a 3 níveis?

A separação dos três níveis numa arquitetura #ThreeTier é uma abordagem comum nu desenvolvimento de sistemas distribuídos, particularmente para aplicações web e empresariais. Cada camada tem responsabilidades distintas e a separação entre elas oferece várias vantagens importantes, tanto no desenvolvimento quanto na manutenção e escalabilidade de sistemas.

- **Manutenção e modularidade**: Cada camada pode ser mantida e atualizada de forma independente.
- **Escalabilidade**: Capacidade de escalar individualmente cada camada conforme necessário.
- **Segurança**: Melhor isolamento e controle de acessos.
- **Desenvolvimento paralelo**: Equipas podem trabalhar em paralelo, maximizando a eficiência.
- **Desempenho**: Melhor utilização de cache e distribuição de carga.
- **Testabilidade**: Testes mais fáceis e isolados.

Essa separação em três níveis melhora tanto o desenvolvimento quanto a gestão de sistemas complexos, tornando-os mais flexíveis, escaláveis e fáceis de manter.

---

#### #ArquiteturasEmpresariais

![[Pasted image 20241014223845.png]]

- User interface: aplicação a correr no equipamento do utilizador
- Aplicação: Geralmente com 2 componentes
	- Front-End - Gere a interface com os utilizadores
	- Back-End - Contém a lógica de negócio e é acedido exclusivamente através de Front-End servers
- Database: Servidor gere a base de dados, armazenada em dispositivos separados
- A rede da empresa é composta pela DMZ, acessível da rede externa através da Firewall1 e pela rede interna, não acessível do exterior e protegida adicionalmente pela Firewall2.
- Todos os serviços podem ser replicados
- Os serviços podem também ser acedidos por outras empresas através de uma API Server.

Uma empresa que tenha vários servidores de back-end, cada um terá associado uma aplicação. Estes servidores não usam todos a mesma tecnologia e protocolo para receberem pedidos e enviarem respostas aos clientes, servidores de Front-End.
Várias operações dos clientes necessitam de orquestração entre diversas chamadas a vários servidores de Back-End. Estas chamadas têm que ter serviços comuns, como por exemplo, autenticação ou login. Estes fatores levam a que cada cliente tenha ou construa adaptadores para comunicar com cada tipo de servidor Back-end, implicando elevados custos e complexidade.

---
##### #Middleware

Componente que intermedeia a comunicação entres os clientes e os servidores.

Cada cliente ou servidor comunica apenas com o Middleware
- O cliente envia o pedido ao Middleware, usando um protocolo standard, igual para todos os clientes
- O middleware comunica com cada servidor, usando o seu protocolo específico
Os sistemas de middleware oferecem apenas adaptadores para comunicar com os tipos mais comuns de servidores.

![[Pasted image 20241014224838.png]]

- O middleware oferece uma interface normalizada aos clientes.
- Faz a orquestração de chamadas a vários servidores para responder ais pedidos dos clientes
	- Pedidos simples: apenas a um servidor
	- Pedidos complexos: chamada vários servidores, em série e/ou em paralelo para obter a resposta final e enviar de volta para o cliente
- Uniformiza os serviços comuns

---

#### #DMZ

Sub-rede ou uma pequena rede que atua como uma camada adicional de segurança entre a rede interna, privada, de uma organização e a internet, externa. A DMZ é usada para expor certos serviços ou servidores ao público sem comprometer diretamente a segurança da rede interna.

A principal ideia da DMZ é isolar os recursos que precisam ser acessíveis ao público da rede interna mais sensível, protegendo-a de possíveis ataques. Na prática, qualquer serviço público colocado na DMZ pode ser comprometido sem afetar diretamente a rede interna, pois a comunicação entre eles é rigorosamente controlada por firewalls.

- Firewall Externo:
	- Primeira linha de defesa entre a internet e a DMZ. A sua função é proteger os serviços expostos na DMZ de ataques externos e controlar o tráfego que pode entrar na DMZ.
- Firewall Interno:
	- Segunda linha de defesa, protegendo a rede interna da DMZ. Mesmo que um servidor na DMZ seja comprometido, a firewall interna garante que o acesso à rede interna seja limitado ou bloqueado.

A **DMZ** atua como uma zona intermediária onde serviços acessíveis ao público podem ser disponibilizados de forma segura, sem expor a rede interna diretamente. A utilização de **duas firewalls** — uma entre a rede externa e a DMZ, e outra entre a DMZ e a rede interna — fornece uma proteção adicional, criando várias camadas de segurança que aumentam a resiliência do sistema a ataques externos e violações de segurança.

---

#### #P2P 

![[Pasted image 20241014230304.png]]

Arquitetura baseada em componentes que desempenham papéis idênticos.
- Interagem cooperativamente assumindo o papel de cliente e/ou servidor simultaneamente
- Permite explorar a capacidade de processamento e armazenamento de múltiplos computadores numa rede.
- Modelo de interação complexo
	- Dificuldade de implementação
	- Administração problemática
- Dispersão e número elevado de componentes
	- Problemas de Segurança
- Vantagens
	- Escalabilidade facilitada
	- Maior fiabilidade do serviço como um todo
- Os problemas de registo e pesquisa de serviço necessitam de um serviço centralizado ou a utilização de algoritmos distribuídos complexos

---

#### #MobileCode 

![[Pasted image 20241014231021.png]]

O objeto é enviado para o cliente e executado localmente.

A interação com o cliente é feita localmente com o objeto
- Melhora desempenho e interatividade
- Incrementa dinamicamente a funcionalidade do cliente
O objeto pode interagir com o servidor para prestar serviços adicionais.
Necessita de regras de carregamento e acesso ao código móvel a recursos locais.

---

#### #CloudComputing 

