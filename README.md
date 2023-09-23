# Cálculo de Pagamento com Descontos e Juros
## Introdução
Este algoritmo calcula o valor a ser pago por um produto com base no preço normal de etiqueta e na escolha da condição de pagamento. Ele utiliza códigos predefinidos para identificar a condição selecionada e aplicar os descontos ou juros correspondentes.

## Variáveis
preço: Representa o preço normal da etiqueta do produto. Neste exemplo, está definido como R$ 100.
formaDePagamento: Representa o código da condição de pagamento escolhida pelo cliente. Os códigos disponíveis estão listados a seguir:

    1: Débito, com 10% de desconto.

    2: À vista no Dinheiro ou PIX, com 15% de desconto.

    3: Pagamento em duas vezes, preço normal de etiqueta sem juros.

    4: Pagamento em mais de duas vezes, preço normal de etiqueta mais juros de 10%.

## Cálculo de Pagamento
O algoritmo utiliza estruturas condicionais `if` para determinar a condição de pagamento escolhida e calcular o valor final a ser pago com base nessa condição.

**Condição 1:** À Débito.
Se `formaDePagamento` for igual a 1, o código calcula o valor do desconto de 10% (debito) sobre o preço normal e subtrai esse desconto do preço original para obter o valorFinal.
~~~javascript 
  if (formaDePagamento === 1) {
     const debito = preco * 0.1;
     const valorFinal = preco - debito;
     console.log('R$: ' + valorFinal.toFixed(2));
    }
~~~

**Condição 2:** À vista no Dinheiro ou PIX.
Se a `formaDePagamento` for igual a 2, o código calcula o valor do desconto de 15% ( DinheiroPix) sobre o preço normal e subtrai esse desconto do preço original para obter o valorFinal.
~~~javascript 
    else if (formaDePagamento === 2) {
        const DinheiroPix = preco * 0.15;
        const valorFinal = preco - DinheiroPix;
        console.log('R$: ' + valorFinal.toFixed(2));
        }
~~~
**Condição 3:** Pagamento em Crédito. 
Se a `formaDePagamento` for igual a 3, o preço normal da etiqueta é mantido, pois não há desconto nem juros.
~~~javascript 
    else if (formaDePagamento === 3) {
        console.log('R$: ' + preco.toFixed(2));
    }
~~~
**Condição 4:** Pagamento parcelado.
Se `formaDePagamento` for igual a 4, o código calcula um juro de 10% `(parcelado)` sobre o preço normal e adiciona esse juros ao preço original para obter o valorFinal.
~~~javascript 
    else (formaDePagamento === 4) 
        const parcelado = preco * 0.1;
        const valorFinal = preco + parcelado;
        console.log('R$: ' + valorFinal.toFixed(2));
~~~
**Resultado**
O código exibe o valorFinal no formato com duas casas decimais usando `toFixed(2)` e imprime o resultado na forma de `"R$: [valor]"`.

## Conclusão
Este algoritmo permite calcular o valor a ser pago por um produto com base na condição de pagamento escolhida pelo cliente, aplicando descontos ou juros de acordo com os códigos pré-definidos. Ele fornece uma solução simples para lidar com diferentes cenários de pagamento e pode ser útil em sistemas de checkout ou aplicações de comércio eletrônico.
