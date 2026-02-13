# ⚔️ Classes de um Jogo: Abstração de Heróis

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) ![POO](https://img.shields.io/badge/POO-Object_Oriented-orange?style=for-the-badge) ![DIO.me](https://img.shields.io/badge/DIO.me-Bootcamp-blue?style=for-the-badge)

> "A complexidade de um sistema deve ser gerida através da abstração, não da força bruta."

Este repositório contém a solução para o desafio de **Programação Orientada a Objetos (POO)** da [DIO.me](https://www.dio.me/). O objetivo foi modelar a lógica de combate de um jogo RPG, utilizando Classes, Construtores e Métodos para padronizar o comportamento de diferentes tipos de heróis.

## 💻 O Desafio

O projeto exigia a criação de uma classe genérica `Heroi` que pudesse instanciar personagens com características (Nome, Idade, Tipo) e comportamentos (Ataque) distintos, mas compartilhando a mesma estrutura de código.

## 🧠 Engineering & Security Mindset

Por que este projeto é relevante para minha jornada em **Engenharia da Computação** e **Cibersegurança**?

1.  **Arquitetura de Código:** Em segurança, entender POO é crucial. Muitos malwares avançados e ferramentas de *pentest* são escritos em linguagens orientadas a objeto (como C++ ou Python) para reutilizar módulos de ataque.
2.  **Manutenibilidade e Segurança:** Ao centralizar a lógica de ataque em um único método (`atacar`), reduzimos a superfície de erros. Se precisarmos corrigir uma falha na lógica de ataque, corrigimos em um só lugar (na Classe), e todos os objetos (Guerreiros, Magos, etc.) são atualizados automaticamente. Isso é o princípio do *Secure by Design*.
3.  **Clean Code:** O uso de `switch/case` dentro do método encapsula a complexidade, mantendo o código limpo e auditável.

## 🛠️ Estrutura do Código

A solução foi implementada utilizando conceitos modernos de JavaScript:

* **Classes (`class`):** O molde para criar os heróis.
* **Construtor (`constructor`):** Para inicializar os atributos `nome`, `idade` e `tipo`.
* **Métodos:** A função `atacar()` que decide a arma baseada no tipo do herói.
* **Estruturas de Decisão:** Uso de `switch` para mapear tipos de heróis aos seus respectivos ataques.

### Exemplo de Lógica Implementada

```javascript
// A estrutura segue este padrão lógico
class Heroi {
    constructor(nome, idade, tipo) {
        this.nome = nome;
        this.idade = idade;
        this.tipo = tipo;
    }

    atacar() {
        let ataque;
        switch (this.tipo) {
            case 'Mago': ataque = 'magia'; break;
            case 'Guerreiro': ataque = 'espada'; break;
            // ... outros casos
        }
        console.log(`O ${this.tipo} atacou usando ${ataque}`);
    }
}
