# [DIO] - Criando um Banco Digital com Java e POO

Este projeto tem como objetivo aplicar os pilares fundamentais da Programação Orientada a Objetos (POO) em Java, através da simulação de um sistema bancário simples.

## 🚀 Objetivo do Desafio
Abstrair uma solução bancária onde um banco oferece aos seus clientes dois tipos de contas: **Corrente** e **Poupança**. Ambas as contas devem permitir operações de depósito, saque e transferência.

## 🧠 Conceitos de POO Aplicados

Neste projeto, você encontrará a aplicação prática de:

* **Abstração:** Criação da classe base `Conta`, concentrando apenas os atributos essenciais (agência, número, saldo) e ignorando detalhes irrelevantes para este domínio.
* **Encapsulamento:** Os atributos da conta (como o saldo) são protegidos (private/protected) e só podem ser manipulados através de métodos específicos (getters/setters e métodos de operação), garantindo a segurança dos dados.
* **Herança:** As classes `ContaCorrente` e `ContaPoupanca` herdam as características e comportamentos da classe pai `Conta`, reutilizando código e facilitando a manutenção.
* **Polimorfismo:** Capacidade de tratar diferentes tipos de contas de forma genérica. Por exemplo, uma lista de contas pode conter tanto Correntes quanto Poupanças, e o sistema saberá qual método específico chamar.

## 🛠️ Funcionalidades Modeladas
* **Depósito:** Incrementa o saldo da conta.
* **Saque:** Decrementa o saldo, respeitando a disponibilidade financeira.
* **Transferência:** Permite enviar valores entre contas da própria instituição, utilizando os métodos de saque e depósito de forma combinada.

## 📂 Estrutura Sugerida
* `IConta`: Interface que define o contrato das operações bancárias.
* `Conta`: Classe abstrata que implementa a lógica comum.
* `ContaCorrente` e `ContaPoupanca`: Classes que estendem `Conta`.
* `Banco` e `Cliente`: Classes auxiliares para gerenciamento.

## 💻 Exemplo de Execução
```java
Cliente venilton = new Cliente();
venilton.setNome("Venilton");

Conta cc = new ContaCorrente(venilton);
Conta poupanca = new ContaPoupanca(venilton);

cc.deposito(100);
cc.transferir(100, poupanca);

cc.imprimirExtrato();
poupanca.imprimirExtrato();
