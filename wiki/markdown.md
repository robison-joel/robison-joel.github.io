MANUAL DO MARKDOWN
================================================================

1 TITULAÇÃO
--------------------------------------

# Título 1 
## Título 2
### Título 3
#### Título 4
##### Título 5

```
# Título 1
## Título 2
### Título 3
#### Título 4
##### Título 5
```

2 Texto comum
----------------------

Para texto comum não é necessário nenhum caracter.

3 Negrito
-----------------------

Para negrito, utiliza-se dois "*" (asteríscos) ou "_"(underscore).

```
**negrito** ou __negrito__
```

4 Itálico
----------------------------------------------------

Para itálico, utiliza-se um "*" (asterísco) ou "_"(underscore).

```
*itálico* ou _itálico_
```

5 Negritálico
----------------------------------------------------

Para negrito e itálico juntos, utiliza-se três "*" (asteríscos) ou "_"(underscore).

```
***negritoitalico***
```

6 Link's
----------------------------------------------------

Existem duas formas de escrever um link com o Markdown. Link direto e link com texto:

### 6.1 Link direto

<https://www.google.com.br>
```
<https://www.google.com.br>
```

### 6.2 Link com texto

[Google](http://google.com.br)
```
[Google](http://google.com.br)
```

7 Listas
----------------------------------------------------

Usam-se o "*" (asterísco) ou no caso das listas ordenadas, "número." número acompanhado do ponto á direita.
 
### 7.1 Lista normal

* Ítem
* Ítem
* Ítem
* Ítem
* Ítem

```
* Ítem
* Ítem
* Ítem
* Ítem
* Ítem
```

### 7.3 Listas ordenadas

1. Primeiro ítem
2. Segundo ítem
3. Terceiro ítem
4. Quarto ítem
5. Quinto ítem

```
1. Primeiro ítem
2. Segundo ítem
3. Terceiro ítem
4. Quarto ítem
5. Quinto ítem
```

8 Citações
----------------------------------------------------

Para escrever uma citação, basta colocar o caracter ">" no início da linha.

> Essa é uma citação.

```
> Essa é uma citação.
```

9 Bloco de código
----------------------------------------------------

### 9.1 Código em linha

O código em uma linha só é estilizado com três "~" (tils) ou três "`" (acento agudo) no início e no fim da linha.

```

``` Linha de código ```

ou

~~~ Linha de código ~~~
```

### 9.2 Código em bloco

O Bloco de código é delimitado por três "~" (tils) ou três "`" (acento agudo) no início e no fim do bloco.

```
Esse é um
Exemplo de
Bloco de Código
```

<pre>

``` ou ~~~
Esse é um
Exemplo de
Bloco de Código
``` ou ~~~

</pre>

10 Tabelas
----------------------------------------------------

N  | Descição      | Quantidade
--:|:------------: | ----------:
1  | Item 1        | Muitos
2  | Item 2        | Vários
2  | Item 2        | Vários
2  | Item 2        | Vários
2  | Item 2        | Vários

```
N  | Descição      | Quantidade
--:|:------------: | :----------
1  | Item 1        | Muitos
2  | Item 2        | Vários
2  | Item 2        | Vários
2  | Item 2        | Vários
2  | Item 2        | Vários
```
Você pode notar que a segunda linha da tabela, determina o cabeçalho. Ela também pode ser utilizada para passar informações sobre o **alinhamento** da coluna.

```
-----: = Alinhado á direita

:----- = Alinhado á esquerda (padrão)

:----: = Centralizado

```

Fontes
----------------------

* <https://markdown.net.br/sintaxe-estendida/>