#Tópicos da Aula 02

* código referente em code/aula02.html

##Teoria sobre Lambda

* Lambda (λ) é uma regra de transformação, exprime argumento que entra na função;
* Cálculo lambda foi criado na década de 30, por Alonzo Church, como parte da investigação dos fundamentos da matemática
* Tipagem é importante quando se trabalha com paradgma funcional (JS trabalha com tipagem dinâmica. http://www.typescriptlang.org/ -> "superset" do javascript para tipagem)

* Numa expressão lambda básica não há conversão de tipo

* Sintaxe

<pre>
X: int
f: int -> int (função f recebe um valor do tipo int e retorna um int)

x: a
f: a -> a (função f recebe um valor do tipo a e retorna outro valor do tipo a)
</pre>

* Composição de funções

<pre>
(f . g) = h : a -> a
</pre>

###Uma expressão lambda pode ser:
* uma variável
* uma abstração lambda (criação da função), por exemplo:

<pre>
(λx.x) -> função recebe x e retorna x
(λy.x) -> função recebe y e retorna x (conceitual, função não retornaria nada porque x não existiria)
(λx.(λy.x)) -> função recebe x e retorna outra função, que recebe y e retorna x
</pre>

* Aplicação (uso ou chamada dessa função com parâmetro), por exemplo:

<pre>
(λx.x) y -> função recebe parâmetro x e retorna x, usando y como valor do parâmetro
(λx.E) F -> função recebe x e retorna E (função), recebe como parâmetro um valor ou outra expressão lambda (F -> parâmetro X -> aplica na função E)

(λx.x) UNICORNIO -> UNICORNIO -> Passa UNICORNIO como valor para X, e retona X (UNICORNIO)
"UNICORNIO" pode ser qualquer coisa, variável ou outra expressão
</pre>

* Conversão β - Regra de substituição que diz como a aplicação deve funcionar. Exemplo:

<pre>
(λx. + x 1) 4 -> (função recebe x com valor 4, retorna + 4 1 -> 4 + 1)
</pre>

##Referências##
* http://webschool.io/jsfuncional/
* https://github.com/Webschool-io/workshop-js-funcional-free/blob/master/README.md
* https://pt.wikipedia.org/wiki/C%C3%A1lculo_lambda
* http://www.typescriptlang.org/