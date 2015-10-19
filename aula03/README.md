#Tópicos da Aula 03

>[DICA] Biblioteca para trabalhar com funções anônimas em ES6 (objetivo da lib. é trazer funcionalidades do Heskell pra JS):
<https://github.com/alanrsoares/prelude-js>

##Por que Javascript é funcional?
- Porque a linguagem permite trabalhar com funções auto-executáveis, usar o retorno de uma função como parâmetro de outra função e demais características da programação funcional;

- Basicamente, programação funcional consiste em dividir a lógica em pequenos átomos (funções) que são chamados de forma encadeada, inclusive passando funções como parâmetro de outras funções, retornando valores;

- No Javascript, função é um objeto que possui atributos como:
	- **arguments:** Objeto semelhante a um *Array* que contém os argumentos passados para uma função, além de possuir alguns métodos úteis, como *arguments.callee* (referência para a função que está sendo executada) e *arguments.length* (que retorna o total de argumentos recebidos pela função);
	- **name:** Propriedade que retorna o nome de uma função ou método;
	- **length:** Propriedade que retorna o número de argumentos esperados por uma função.

- E também métodos como:
	- **apply:** Método que chama uma função passando os parâmetros em um *Array*;
	- **call:** Também é usado para chamar uma função, porém aqui os parâmetros são chamados numa lista de argumentos;
	- **bind:** Método para criar uma nova função *(bound function)* com o mesmo corpo da função chamada.

- Na programação funcional, toda função deve retornar um valor (mas isso é uma boa prática em qualquer caso);

- Dentro de um método, pode-se usar *this* para retonar a própria instância do objeto (isso é usado para encadear chamada de métodos, por exemplo);

- Função identidade é aquela que recebe e retorna o mesmo valor.


##Funções anônimas
- Função não nomeada, que pode ser atribuida a uma variável ou parâmetro;
- **Lambda** é uma função anônima que aceita apenas um parâmetro;
- É utilizada principalmente quando se quer passar a função como parâmetro que será utilizado futuramente (callback). Por exemplo:

```js
	// Função anônima atribuída a uma variável;
	var anon1 = function()
	{
		console.log('Agora a função foi chamada!');
	}
	anon1();
	
	// "Simulação" de um callback passado como função anônima;
	function anon2()
	{
		this.exemplo = function($callback){
			//Executa ajax, promise etc... e chama a função anônima no callback:
			$callback.call(this, 'Valor1', 'Valor2', 'Valor3');
		}
	}
	
	var $anon2 = new anon2();
		
	$anon2.exemplo(function($val1, $val2, $val3){
		console.log('Parâmetro 1: ' + $val1 + '.');
		console.log('Parâmetro 2: ' + $val2 + '.');
		console.log('Parâmetro 3: ' + $val3 + '.');
	});
```

##IIFE
>[DICA] Artigo do Ben Alman falando sobre a nomenclatura IIFE <http://benalman.com/news/2010/11/immediately-invoked-function-expression/>

- Immediately-Invoked Function Expression;
- Anteriormente esse tipo de função era chamada de *"self-executing anonymous function"* (função anônima auto-executável) porém, em 2010, **Ben Alman** publicou um artigo propondo a nova nomenclatura por questões semânticas (já que essa não é uma função que se "auto-executa", e sim uma declaração de função executada imediatamente);
- Trata-se de uma função de escopo fechado, imediatamente invocada no local onde é declarada;
- Seu principal uso é quando queremos "isolar" as variáveis dentro do escopo da função, para que não poluam o escopo global.

- Para executar uma IIFE basta colocar () após o nome da função:

```js
	// não funciona :|
	function(){
		console.log('Chamou!');
	}();
```

- Porém, nesse caso o Javascript vai entender o "function" como uma declaração de função e irá dar erro de token ao chegar em "(" (ele irá interpretar como uma tentativa de declarar uma função, e irá esperar um nome). Para resolver isso, basta envolver a função toda com parênteses:

```js
	// assim funciona;
	(function(){
		console.log('Foi!')
	}());

	// assim também;
	(function(){
		console.log('Também foi!')
	})();
```

- E para passar parâmetros para uma IIFE, fazemos assim:

```js
	(function($val1, $val2){
		console.log($val1 + ' ' + $val2 + '!');
	})('Alô', 'você');
```

##Referências##
* <http://webschool.io/jsfuncional/>
* <https://github.com/Webschool-io/workshop-js-funcional-free/blob/master/README.md>
* <https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/arguments>
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name>
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length>
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply>
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call>
* <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind>
* <http://tutsmais.com.br/blog/javascript-2/o-que-e-iife-no-javascript/>