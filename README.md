Branch and bounds

B. Olímpiadas
Enunciado
Você tem 
n problemas. Você avaliou a dificuldade do i-ésimo problema como o número inteiro 
ci. Agora, quer montar um conjunto de problemas para um concurso, usando alguns dos problemas que criou.
O conjunto para o concurso deve ter pelo menos dois problemas. Você acha que a soma das dificuldades dos problemas escolhidos deve ser pelo menos l no máximor. Além disso, a diferença entre a dificuldade do problema mais fácil e do mais difícil do conjunto deve ser pelo menos x .
Descubra de quantas formas é possível escolher um conjunto de problemas que atenda a esses critérios.

Entrada
A primeira linha contém quatro inteiros 
n,l,r,x(1 ≤ n ≤ 15,1 ≤ l ≤ r ≤ 10ˆ9,1 ≤ x ≤ 10ˆ6) — respectivamente, o número de problemas que você tem, o valor mínimo e máximo da soma das dificuldades do conjunto e a diferença mínima entre a dificuldade do problema mais difícil e do mais fácil.A segunda linha contémninteiros 
c1, c2, ..., cn(1 ≤ ci≤ 10ˆ6) — as dificuldades de cada problema.

Saída
Imprima o número de maneiras de escolher um conjunto de problemas adequado para o concurso.

Nota
No primeiro exemplo, dois conjuntos são válidos: um com o segundo e o terceiro problema, e outro com os três problemas.No segundo exemplo, dois conjuntos são válidos — o conjunto com dificuldades 10 e 30, e o conjunto com dificuldades 20 e 30.No terceiro exemplo, qualquer conjunto com um problema de dificuldade 10 e outro de dificuldade 20 serve.

Exemplos
Exemplo 1:

Entrada:

3 5 6 1
1 2 3
Saída:

2
Exemplo 2:

Entrada:

4 40 50 10
10 20 30 25
Saída:

2
Exemplo 3:

Entrada:

5 25 35 10
10 10 20 10 20
Saída:

6


Gulosos

D. Máquina Estranha
Enunciado
Você tem n máquinas organizadas em círculo, onde n é no máximo 20. Cada máquina é do tipo A ou do tipo B. As máquinas são numeradas no sentido horário de 1 até n, e o tipo da máquina número i é indicado por si . Cada máquina recebe um inteiro x e o atualiza conforme seu tipo:

Tipo A: Diminui x em 1. Formalmente, atualiza x:=x−1.
Tipo B: Substitui x pelo piso da metade do seu valor. Formalmente, atualiza x := ⌊ x/2⌋, onde ⌊y⌋ é o piso de y, que é o maior inteiro menor ou igual a y.
Você recebe q consultas, cada uma com um único inteiro a. Em cada consulta, você começa na máquina 1 segurando o inteiro a. A cada segundo, as duas ações seguintes acontecem na ordem:
A máquina atual atualiza a conforme seu tipo.
Depois, você avança um passo no sentido horário para a próxima máquina. Formalmente: Se você estiver na máquina i, onde 1 ≤ i ≤ n − 1, vá para a máquina i + 1.Se estiver na máquina n, vá para a máquina 1.
Esse processo continua até que o inteiro a se torne 0. Para cada consulta, determine quantos segundos são necessários para que a chegue a 0.
Lembre-se: todas as consultas são independentes entre si.
Entrada
Cada teste contém vários casos de teste. A primeira linha contém um inteiro t (1 ≤ t ≤ 10) o número de casos de teste. A descrição dos casos segue.A primeira linha contém dois inteiros n e q (1 ≤ n ≤ 20, 1 ≤ q ≤ 10) a quantidade de máquinas e o número de consultas.A segunda linha contém uma string s, de tamanho n, composta apenas pelos caracteres A e B, representando os tipos das máquinas.A terceira linha contém q inteiros a, a, …, a_q (1 ≤ aᵢ ≤ 10) o valor inicial de cada consulta.Note que não há restrições sobre a soma de n em todos os casos.É garantido que a soma de q em todos os casos não ultrapassa 10.

Saída
Para cada caso de teste, imprima q inteiros representando as respostas para cada consulta.

Nota
No primeiro caso de teste, as consultas são as seguintes:

Consulta 1: a = 3
Começa na máquina 1.
A máquina 1 substitui a pelo piso da metade do seu valor: a = ⌊3 / 2⌋ = 1.
Em seguida, vai para a máquina 2.
A máquina 2 diminui a em 1: a = 1 − 1 = 0.
Portanto, são necessários 2 segundos para que a chegue a 0.

Consulta 2: a = 4
Começa na máquina 1.
A máquina 1 substitui a pelo piso da metade do seu valor: a = ⌊4 / 2⌋ = 2.
Vai para a máquina 2.
A máquina 2 diminui a em 1: a = 2 − 1 = 1.
Retorna à máquina 1.
A máquina 1 substitui a pelo piso da metade do seu valor: a = ⌊1 / 2⌋ = 0.
Portanto, são necessários 3 segundos para que a chegue a 0.

No segundo caso de teste, há apenas uma consulta:

Consulta a = 20
Começa na máquina 1. a = ⌊20 / 2⌋ = 10.
Permanece na máquina 1. a = ⌊10 / 2⌋ = 5.
Permanece na máquina 1. a = ⌊5 / 2⌋ = 2.
Permanece na máquina 1. a = ⌊2 / 2⌋ = 1.
Permanece na máquina 1. a = ⌊1 / 2⌋ = 0.
Portanto, são necessários 5 segundos para que a chegue a 0.
Exemplos
Exemplo 1:

Entrada:

3
2 2
BA
3 4
1 1
B
20
6 4
BAABBA
2 8 32 95
Saída:

2
3
5
2
5
8
11
