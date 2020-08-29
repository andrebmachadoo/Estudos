## Closures

> Funções anônimas, também conhecidas como closures, permitem a criação de funções que não tem o nome especificado. Elas são mais úteis como o valor de parâmetros callback, mas podem tem vários outros usos. Closures também podem ser utilizadas como valores de variáveis; o PHP automaticamente converte expressões assim em instancias da classe interna [Closure](https://www.php.net/manual/pt_BR/class.closure.php). Definindo um closure a uma variável usa a mesma sintaxe que qualquer outra definição, incluindo o ponto-e-vírgula:

```PHP
$greet = function($name)
{
    printf("Hello %s\r\n", $name);
};
$greet('World'); //Output: Hello World
$greet('PHP');  //Output: Hello PHP

```
> Closures também podem herdar variáveis do escopo pai. Essas variáveis precisam ser referenciadas utilizando a instrução ***use***. A partir do PHP 7.1, essas variáveis não devem incluir superglobals, $this, ou variáveis com o mesmo nome como um parâmetro. Veja no exemplo:

```php
<?php
$message = 'hello';

// Sem "use"
$example = function () {
    var_dump($message);
};
$example();

// Inherit $message
$example = function () use ($message) {
    var_dump($message);
};
$example();

// Herdando valor da variável quando a função é definina,
// não quando é chamada
$message = 'world';
$example();

// Reseta mensagem
$message = 'hello';

// Herdando por referência
$example = function () use (&$message) {
    var_dump($message);
};
$example();

// O valor modificado no escopo pai
// reflete quando a função é chamada
$message = 'world';
$example();

// Closures também aceitam argumentos normais
$example = function ($arg) use ($message) {
    var_dump($arg . ' ' . $message);
};
$example("hello");
```

[_Leia mais.._](https://www.php.net/manual/pt_BR/functions.anonymous.php)