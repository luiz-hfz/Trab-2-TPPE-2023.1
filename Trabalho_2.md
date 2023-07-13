# Trabalho 2

## Hisotrico de versões

| Versão | Data       | Descrição                             |
|--------|------------|---------------------------------------|
| 0.1    | 13/07/2023 | Criação do Documento e Adição topico de Simplicade   |


## Simplicidade

A simplicidade é uma característica fundamental de um código bem projetado, pois facilita a compreensão, reduz a complexidade e melhora a manutenibilidade do sistema. Um código simples é claro, coeso, com baixo acoplamento e estrutura bem definida.

## Efeitos no código:

- Estrutura: Um código simples possui uma estrutura clara e bem organizada. Os componentes e módulos são definidos de forma intuitiva e coesa, facilitando a compreensão e a navegação no código.
- Claridade: A simplicidade contribui para a clareza do código. Um código simples é fácil de entender, com nomes de variáveis e funções significativos, facilitando a leitura e a manutenção do código.
- Coesão: A simplicidade promove a coesão, ou seja, a capacidade dos componentes de um módulo estarem relacionados e funcionarem juntos de maneira lógica. Um código simples evita a proliferação de funcionalidades desnecessárias ou duplicadas, tornando o sistema mais coeso.
- Acoplamento: A simplicidade também influencia o acoplamento, que é o grau de interdependência entre os componentes do sistema. Um código simples reduz o acoplamento, evitando dependências desnecessárias e tornando o sistema mais flexível e modular.

## Relação com os maus cheiros de código definidos por Fowler:

- Código Duplicado: A simplicidade ajuda a evitar a duplicação de código, pois um código simples procura eliminar redundâncias e funcionalidades desnecessárias.

- Métodos Longos: Um código simples tende a ter métodos mais curtos e concisos, evitando a complexidade e a dificuldade de manutenção associadas a métodos longos e excessivamente complexos.

## Operação de refatoração relacionada:

- Extração de Método: Essa operação de refatoração pode ser usada para simplificar o código, dividindo um método complexo em métodos menores e mais claros. Ao extrair partes do código em métodos separados, podemos melhorar a legibilidade, a coesão e a reutilização do código.

## Exemplo em código:

``` python
def calculate_average(numbers):
    total = 0
    count = 0

    for number in numbers:
        total += number
        count += 1

    if count > 0:
        average = total / count
        return average
    else:
        return 0
```

Nesse exemplo, temos uma função `calculate_average` que recebe uma lista de números como entrada e calcula a média desses números. O código é simples e segue os princípios de simplicidade:

- Estrutura: O código possui uma estrutura clara, com a função `calculate_average` definida e uma lógica simples dentro dela.
- Claridade: Os nomes de variáveis são significativos, como `total`, `count` e `average`, tornando o código mais legível e compreensível.
- Coesão: O código é coeso, pois a função `calculate_average` tem uma única responsabilidade bem definida, que é calcular a média dos números.
- Acoplamento: O código tem baixo acoplamento, pois não depende de outros módulos ou funcionalidades complexas.

Esse exemplo ilustra como um código simples é mais fácil de entender, manter e modificar. Ao seguir os princípios de simplicidade, é possível evitar maus cheiros de código, como métodos longos, duplicação de código e complexidade desnecessária.





