# SA-LOPR 
algoritmo "semnome"

var
produtos : vetor[1..3] de caractere
gasto : vetor[1..3] de inteiro
quantidade : vetor[1..3] de inteiro
quantidade_v : vetor[1..3] de inteiro
valor : vetor[1..3] de inteiro
ganhos : vetor[1..4] de inteiro
despesa : vetor[1..4] de inteiro
i, lucro_final : inteiro

inicio

escreval("vamos calcular todas as despesas e ganhos desse mês,")
escreval("quanto vendemos e quanto gatamos.")
escreval("quantas peças fabricamos esse mês")
para i de 1 ate 3 faca
   escreval("digite um produto fabricado")
   leia(produtos[i])
fimpara
para i de 1 ate 3 faca
   escreval("quanto custa a fabricação de um / uma ", produtos[i] )
   leia(gasto[i])
   escreval("quantas unidades de um / uma ", produtos[i] , " foram feitos ? ")
   leia(quantidade[i])
fimpara
para i de 1 ate 3 faca
   despesa[i] <- gasto[i]*quantidade[i]
   escreval("as despeasas de fabricação de" , quantidade[i] , " " , produtos[i] , " foi" , despesa[i])
fimpara
despesa[4] <- despesa[1] + despesa[2] + despesa[3]
escreval("o gasto total das despesas foi de" , despesa[4])

para i de 0 ate 50 faca
   escreval("")
fimpara

escreval("agora vamos ver quanto nós vendemos")
para i de 1 ate 3 faca
   escreval("qual a quantiedade de vendas de ", produtos[i] , "(max de" , quantidade[i], ")")
   leia(quantidade_v[i])
   se quantidade[i] >= quantidade_v[i] entao
      escreval("e qual a valor de um /uma ", produtos[i])
      leia(valor[i])
      ganhos[i] <- quantidade_v[i] * valor[i]
      escreval("o valor total que ganhamos na venda de " ,quantidade_v[i], " " , produtos[i] ," foi de " , ganhos[i])
   senao
      escreval("IMPOSSIVEL")
      i <- i - 1
   fimse
fimpara
ganhos[4] <- ganhos[1] + ganhos[2] + ganhos[3]
escreval("o junção de todos os ganhos foi de ", ganhos[4])

para i de 0 ate 50 faca
   escreval("")
fimpara

lucro_final <- ganhos[4] - despesa[4]
escreval(" o valor total de lucro com despesas deu " ,lucro_final)

fimalgoritmo
