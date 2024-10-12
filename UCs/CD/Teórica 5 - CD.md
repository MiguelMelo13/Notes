
### RPC

Um pedido de cada vez
- Serialização de pedidos
- Uma única thread para todos os pedidos

Vários pedidos em paralelo
- Uma thread por pedido
- A biblioteca de RPC tem que suportar paralelismo
	- Sincronização no acesso a binding handies
	- Sincronização no acesso a canais de comunicação

Fluxos de execução complexos
- Chamadas em ricochete -> Callbacks
	- Um "cliente" é contactado como sendo um servidor no fluxo da sua chamada

---
### Sun RPC

-> Ver moodle 4.48 para exemplo de interface
-> XDR - External Data Representation 4.49
	 Definição da estrutura
	 Utilização do utiliário rpcgen
	 Geração automática do código marshalling

