# Trabalho 2

## Hisotrico de versões

| Versão | Data       | Descrição                             |
|--------|------------|---------------------------------------|
| 0.1    | 13/07/2023 | Criação do Documento e Adição topico de Simplicade   |
| 0.2    | 19/07/2023 | Adição do tópico de Portabilidade |


# Simplicidade

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

# Portabilidade
A portabilidade em um projeto de software refere-se à capacidade do código ser facilmente adaptado e executado em diferentes plataformas ou ambientes, como sistemas operacionais, dispositivos e arquiteturas. Um código portável é aquele que não possui dependências específicas da plataforma e pode ser reutilizado em diferentes contextos sem grandes modificações.

## Efeitos no código:
- Estrutura: O código portável deve evitar o uso de bibliotecas ou recursos específicos de uma plataforma e preferir soluções universais.
- Claridade: Um código portável tende a ser mais claro, pois evita complexidades desnecessárias relacionadas à plataforma.
- Coesão: A coesão do código é favorecida, pois as funcionalidades são implementadas de forma independente das particularidades da plataforma.
- Acoplamento: O acoplamento é reduzido ao mínimo, uma vez que o código portável evita depender de recursos específicos de uma plataforma.

## Relação com os maus cheiros de código definidos por Fowler:
- Maus-cheiros de dependência: Código altamente dependente de recursos específicos de uma plataforma pode torná-lo menos portável e mais difícil de adaptar a outras plataformas.
- Maus-cheiros de código duplicado: Repetição de código específico de uma plataforma pode levar a problemas de portabilidade, pois será necessário refazer essas partes para outras plataformas.

## Operação de refatoração relacionada:
Uma operação de refatoração que pode ajudar a alcançar a portabilidade em um projeto de software é a "Substituição de Funções ou Bibliotecas Específicas da Plataforma". Ela pode ser feita da seguinte forma:

- Identifique funções, bibliotecas ou APIs específicas da plataforma que estão sendo utilizadas em seu código. Em seguida, crie wrappers ou interfaces genéricas para essas funcionalidades específicas da plataforma e implemente versões alternativas dessas wrappers para cada plataforma de destino.

## Exemplo em código:
Suponha que você esteja desenvolvendo um aplicativo que precise usar funcionalidades de acesso ao sistema de arquivos. Em uma plataforma, você está usando a API específica da plataforma (por exemplo, java.io no Android) para realizar operações de leitura e escrita de arquivos. No entanto, para tornar o código mais portável, você pode criar uma interface FileHandler e implementá-la para cada plataforma de destino.

``` Java
// Interface genérica para manipulação de arquivos
public interface FileHandler {
    void readFile(String fileName);
    void writeFile(String fileName, String content);
}

// Implementação para a plataforma Android
public class AndroidFileHandler implements FileHandler {
    @Override
    public void readFile(String fileName) {
        // Implementação específica para ler arquivos no Android
        // Usando java.io e outras APIs da plataforma
    }

    @Override
    public void writeFile(String fileName, String content) {
        // Implementação específica para escrever arquivos no Android
    }
}

// Implementação para outra plataforma (iOS, por exemplo)
public class iOSFileHandler implements FileHandler {
    @Override
    public void readFile(String fileName) {
        // Implementação específica para ler arquivos no iOS
        // Usando as APIs específicas da plataforma iOS
    }

    @Override
    public void writeFile(String fileName, String content) {
        // Implementação específica para escrever arquivos no iOS
    }
}
``` 

Dessa forma, o restante do código pode usar a interface FileHandler sem se preocupar com as particularidades de cada plataforma. Em tempo de execução, você pode instanciar a implementação adequada dependendo da plataforma em que o aplicativo está sendo executado.
