# Mini Tutorial PSR-4 autoload com Composer.

## Dentro do diretório que vamos trabalhar execute
```bash
composer init
```
![Alt text](images/1.png?raw=true "Title")
## Neste tutorial vou apertar enter para usar os defaults, mas você pode detalhar seu projeto melhor.
![Alt text](images/2.png?raw=true "Title")

![Alt text](images/3.png?raw=true "Title")
## Após alguns enters chegamos a seguinte tela:
![Alt text](images/4.png?raw=true "Title")

## O composer terá criado um arquivo chamado composer.json, vamos editar ele
![Alt text](images/5.png?raw=true "Title")
## Vamos adicionar o seguinte atributo a esse json
```json
"autoload": {
    "psr-4": {
        "Tutorial\\": "src/"
    }
}
```
![Alt text](images/6.png?raw=true "Title")

## Após modificar o arquivo, vamos no terminal na pasta e executamos
```bash
composer install
```
![Alt text](images/7.png?raw=true "Title")

## Após a instalação realizada, teremos a seguinte mensagem:

![Alt text](images/8.png?raw=true "Title")

## Ele vai criar uma pasta chamada vendor/ , e nela haverá um arquivo chamado autoload.php

![Alt text](images/9.png?raw=true "Title")

## Vamos criar uma pasta src/ e criar uma classe chamada Exemplo.php, da seguinte forma:

![Alt text](images/10.png?raw=true "Title")

## Vamos criar um index.php, nele vamos incluir o autoload (gerado pelo composer e vamos declarar que queremos usar a classe Tutorial da seguinte forma:)
```php
<?php

use Tutorial\Exemplo;
```
![Alt text](images/12.png?raw=true "Title")

## Se executarmos o index.php, neste caso utilizarei o terminal para poupar tempo de montar um servidor, teremos o seguinte resultado:
![Alt text](images/13.png?raw=true "Title")

## Resultado:
![Alt text](images/14.png?raw=true "Title")


## Também podemos nos aprofundar mais nos caminhos de classes, nesse exemplo vamos criar uma pasta Foo dentro de src, e criar nela uma classe Bar, da seguinte forma:
![Alt text](images/15.png?raw=true "Title")

## No index.php vamos declarar que queremos usar Bar, da seguinte forma:
```php
<?php

use Tutorial\Foo\Bar;
```
![Alt text](images/16.png?raw=true "Title")

## E se executarmos index.php teremos o seguinte resultado:

![Alt text](images/17.png?raw=true "Title")

Namespaces são diretórios para separar e organizar as classes, usamos composer para gerenciar o carregamento de forma padronizada, assim podemos misturar nossas classes, e classes de terceiros, neste pequeno tutorial declaramos um namespace "Tutorial", mas você é livre para declarar seus namespaces e fazer da sua forma, espero ter ajudado.
