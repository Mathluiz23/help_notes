const specialCharRegex = /[\\\[\].+*?^$(){}=!<>|:-]/g;


<!-- 
Delimitadores /.../: As barras (/) delimitam o início e o fim da expressão regular.

Caractere de escape \\: O caractere \ é usado para escapar caracteres especiais em expressões regulares. Neste caso, \\ escapa a própria barra invertida, permitindo que ela seja reconhecida como um caractere literal na expressão.

Conjunto de caracteres [ ... ]: Os colchetes definem um conjunto de caracteres. A expressão irá corresponder a qualquer um dos caracteres listados dentro dos colchetes.

Lista de caracteres especiais: Dentro dos colchetes, temos vários caracteres especiais que são escapados ou listados para corresponder literalmente a esses caracteres:

\ (barra invertida)
[ e ] (colchetes)
. (ponto)
+, *, ?, ^, $, (, ), {, }, =, !, <, >, |, :, - (outros caracteres especiais)
Flag g: A flag g no final da expressão regular significa "global", o que faz com que a expressão regular encontre todas as correspondências no texto de entrada, e não apenas a primeira. 

-->