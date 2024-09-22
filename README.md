# Projeto: Implementação de Contratos na Blockchain Ethereum

Este projeto foi desenvolvido utilizando o **Remix IDE** e envolve a implementação de três contratos inteligentes diferentes na blockchain Ethereum. Utilizamos **Ganache** para simular a rede, **Metamask** como carteira para gerenciar as contas e **Remix IDE** para desenvolvimento e teste dos contratos.

## 1. Contrato de Votação na Blockchain (DIOVoting)

### Descrição:
Este contrato implementa um sistema básico de votação em blockchain. Os eleitores podem votar em candidatos previamente cadastrados no sistema, e o contrato mantém um registro de quantos votos cada candidato recebeu.

### Funcionalidades principais:
- **Votos por candidato**: O contrato permite que usuários votem em candidatos a partir de uma lista pré-definida.
- **Validação de candidatos**: Antes de registrar um voto, o contrato verifica se o candidato existe na lista de candidatos.
- **Armazenamento seguro**: Os votos de cada candidato são armazenados utilizando a estrutura de mapeamento `votesReceived`.

### Fluxo de funcionamento:
- A votação é realizada invocando a função `votesForCandidate`, que incrementa o número de votos do candidato escolhido.
- A função `totalVotesFor` permite que qualquer pessoa consulte o número de votos recebidos por um candidato específico.
- A função `validCandidate` é usada internamente para garantir que o candidato votado seja válido.

### Testes:
O contrato foi testado no **Remix** e na rede de testes **Ganache**, onde diferentes candidatos foram adicionados e validados, e os votos foram registrados e contados corretamente.

---

## 2. Contrato Hello World

### Descrição:
O contrato "Hello World" é um exemplo simples de contrato inteligente para a introdução a Ethereum e Solidity. Ele permite a personalização e exibição de uma mensagem "Hello World".

### Funcionalidades principais:
- **Definir uma mensagem**: O contrato permite que qualquer pessoa atualize a mensagem armazenada, seja a saudação "Hello World" ou qualquer outra string personalizada.
- **Visualizar a mensagem**: Qualquer usuário pode visualizar a mensagem atual armazenada no contrato.

### Fluxo de funcionamento:
- A função `setHello` permite que o usuário altere a mensagem.
- A função `setName` armazena o nome de um usuário no contrato.
- Ambas as variáveis, `hello` e `name`, podem ser lidas publicamente sem custo de gás.

### Testes:
Testado no **Remix** e **Ganache**, permitindo a atualização e visualização da mensagem e nome sem falhas. O contrato é de fácil compreensão e eficiente para mostrar a estrutura básica de um contrato Ethereum.

---

## 3. Criação de um Token ERC-20 na Rede Ethereum (DIOCoin)

### Descrição:
Este contrato implementa um token ERC-20 chamado **DIOCoin**. Ele segue o padrão ERC-20 da Ethereum, com funcionalidades básicas como transferência de tokens, delegação e verificação de saldo. Os testes foram realizados utilizando **Ganache**, **Metamask** e o **Remix IDE**.

### Funcionalidades principais:
- **Total de tokens**: O contrato gera um total fixo de tokens (10 DIOCoin) distribuídos inicialmente para o criador do contrato.
- **Transferência de tokens**: Os tokens podem ser transferidos entre contas, e o contrato verifica se a conta de origem possui saldo suficiente.
- **Aprovação e delegação**: Um usuário pode aprovar outra conta para gastar uma quantidade definida de tokens em seu nome.
- **Verificação de saldo e permissão**: Qualquer usuário pode verificar o saldo de uma conta específica, assim como a quantidade de tokens que uma conta está autorizada a gastar em nome de outra.

### Fluxo de funcionamento:
- A função `transfer` permite transferir tokens diretamente entre contas.
- A função `approve` autoriza outra conta a gastar uma quantidade definida de tokens em nome do proprietário.
- A função `transferFrom` é usada para realizar a transferência em nome do proprietário, utilizando a permissão concedida com `approve`.
- Eventos `Transfer` e `Approval` são emitidos para registrar as transferências e aprovações realizadas.

### Testes:
- **Ganache** foi utilizado para simular o ambiente local da blockchain.
- As funcionalidades de transferência, aprovação e delegação foram testadas utilizando contas diferentes configuradas no **Metamask**.
- O contrato foi validado no **Remix IDE**, garantindo que as transferências e aprovações funcionam conforme esperado, e todos os eventos são emitidos corretamente.

---

## Ferramentas Utilizadas:
- **Remix IDE**: Ambiente de desenvolvimento para criação e teste de contratos inteligentes.
- **Ganache**: Rede local de simulação de blockchain Ethereum.
- **Metamask**: Carteira digital para gerenciar contas Ethereum e interagir com contratos inteligentes.
- **Solidity**: Linguagem de programação utilizada para desenvolver os contratos inteligentes.

---

## Como Executar o Projeto:

1. Clone o repositório em sua máquina local.
2. Importe os arquivos de contrato no **Remix IDE**.
3. Configure sua carteira **Metamask** para conectar-se à rede **Ganache** ou outra testnet da Ethereum.
4. Compile e deploy os contratos através do **Remix**.
5. Utilize as funções públicas de cada contrato para testar suas funcionalidades de acordo com as instruções fornecidas.
