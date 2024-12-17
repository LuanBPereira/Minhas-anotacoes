## Operadores Lógicos - JAVA

Os operadores lógicos do Java são usados para criar expressões lógicas (verdadeiras ou falsas). Os operadores lógicos mais comuns são:

- "&&" (E lógico): retorna verdadeiro se ambas as expressões forem verdadeiras. Exemplo: (x < 5 && y > 0) retornaria verdadeiro somente se x fosse menor que 5 e y fosse maior que 0.

- "||" (OU lógico): retorna verdadeiro se pelo menos uma das expressões for verdadeira. Exemplo: (x < 5 || y > 0) retornaria verdadeiro se x fosse menor que 5 ou y fosse maior que 0.

- "!" (Não lógico): inverte o valor lógico da expressão. Exemplo: !(x < 5) retornaria verdadeiro se x não fosse menor que 5.

- "&" (E lógico short-circuit): igual a &&, mas não avalia a segunda expressão se a primeira já for falsa. Exemplo: (x < 5 & y/x > 2) se x for menor que zero, y/x não será avaliado evitando um erro de divisão por zero.

- "|" (OU lógico short-circuit): igual a ||, mas não avalia a segunda expressão se a primeira já for verdadeira. Exemplo: (x < 5 | y/x > 2) se x for menor que cinco, y/x não será avaliado evitando um erro de divisão por zero.

- "^" (OU exclusivo): retorna verdadeiro se apenas uma das expressões for verdadeira. Exemplo: (x < 5 ^ y < 5) retornaria verdadeiro se x fosse menor que 5 ou y fosse menor que 5, mas não ambos.