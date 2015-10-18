#Tópicos da Aula 01

##Paradigmas de desenvolvimento:##

* Funcional
	* Avaliação de funções matemáticas
	* Inspirada no cálculo λ
	* "menor parte" do sistema é uma função
	* valores de entrada de uma função são o retorno de outras funções
	* execução do programa = avaliação de expressões
	* Não existe conteito de variáveis ou atribuição
	* Iterações devem ser construídas com recursão (não há laços de repetição, como na programação imperativa)

Programação funcional é um estilo de programação diferente das linguagens procedurais, enfatizando a avaliação de expressões ao invés da execução de comandos. Utiza-se funções como valores básicos e, dessa forma, evita estados ou dados estados. Ex.:

```js
var teste = 'Olá'; //a variável "teste" poderá assumir qualquer outro valor: teste = 'Oi', teste = 'Tchau' etc.

funtion saudacao(txt){
	return txt;
}

saudacao('Olá'); //o valor de retorno não muda, sempre será "Olá".
```


* Imperativo
	* O programa é baseado numa sequencia de instruções explícitas (condicionais, laços de repetição etc)
	* Mudança de estados do programa	
	* Arquitetura de Von Neumann

##Por que usar Programação funcional:##

* Concorrência (não tem deadlocks ou race condition)
* Testes (não precisa de preocupar com estado, análise das expressões pode ser feita matematicamente)
* Debugging (facilidade de rastrear valor no stack trace)
* Base teórica (linguagem é baseada no cálculo Lambda)

##Aplicações##
* BI
* Sistemas altamente concorrentes (como sistema de estatística, análise financeira etc)

##Conceitos/Definições##
* Implementação de Map/Reduce (percorre uma lista e aplica uma função a cada item da lista)
* Toda função precisa retornar um valor
* Função identidade: função que recebe um valor e retorna ele mesmo
* Atomic design: pequenos átomos independentes compõe funções maiores


##Linguagens funcionais:##
* Erlang
* F#
* Haskell
* Lisp (introduziu caracteristicas da linguagem, inspirada no cálculo λ)
* Scheme ("simplificação" do Lisp, foi base para a linguagem JavaScript)
* OCaml
* R
* ...
* Elixir (linguagem de alto nível, sintaxe mais convidativa, que roda na VM do Erlang)


##Javascript##
* Função anônima
* IIFE (função auto executável -> Immediately-Invoked Function Expression)


##Referências##
* http://webschool.io/jsfuncional/
* https://github.com/Webschool-io/workshop-js-funcional-free/blob/master/README.md
* http://www.dcc.fc.up.pt/~pbv/aulas/pf/slides/aula1.pdf
* https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_funcional
* ftp://ftp.dca.fee.unicamp.br/pub/docs/ea877/lingpro.pdf
* http://www.cin.ufpe.br/~if686/aulas/02-Introducao_Haskell.pdf