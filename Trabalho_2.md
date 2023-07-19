# Trabalho 2

## Hisotrico de versões

| Versão | Data       | Descrição                             |
|--------|------------|---------------------------------------|
| 0.1    | 13/07/2023 | Criação do Documento e Adição topico de Simplicade   |
| 0.2    | 19/07/2023 | Adição do tópico de Portabilidade |
| 0.3    | 19/07/2023 | Adição do tópico de Boa Documentação |
| 0.4    | 19/07/2023 | Adição do tópico de Elegância |


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

# Boa Documentação

A boa documentação em um projeto de software refere-se à prática de criar e manter uma documentação clara, completa e atualizada, que descreve o funcionamento interno do código, a arquitetura, os componentes, as interfaces, as decisões de design e outras informações relevantes. Isso inclui tanto a documentação direta do código (como comentários) quanto documentação externa (como manuais do usuário ou documentos técnicos).

## Efeitos no código:

 Estrutura: A boa documentação ajuda a estabelecer uma estrutura coerente no código, permitindo que os desenvolvedores entendam como os diferentes componentes se relacionam e interagem entre si.
 Claridade: Com uma documentação adequada, o código se torna mais claro e legível, facilitando a compreensão tanto para o desenvolvedor que escreveu o código originalmente quanto para outros que precisam mantê-lo ou colaborar no projeto.
 Coesão: A documentação ajuda a explicar a responsabilidade de cada módulo ou função, garantindo que eles sejam coesos, ou seja, que mantenham uma única responsabilidade bem definida.
 Acoplamento: Uma boa documentação pode ajudar a identificar os pontos de acoplamento entre diferentes partes do código, permitindo que os desenvolvedores entendam as dependências e as interfaces.
 Manutenibilidade: Com uma documentação adequada, a manutenção do código se torna mais fácil, pois novos desenvolvedores ou membros da equipe podem se familiarizar rapidamente com o código existente.
Relação com os maus-cheiros de código definidos por Fowler:
A falta de documentação ou documentação inadequada pode levar a alguns maus-cheiros de código definidos por Martin Fowler, como:

Comentários Desnecessários: Comentários confusos ou redundantes que não fornecem informações úteis podem poluir o código e torná-lo menos legível.
Código Duplicado: Sem documentação adequada, os desenvolvedores podem não perceber que um trecho de código já foi implementado em outro lugar, levando a duplicações desnecessárias.
Métodos/Funções Gigantes: Sem documentação clara sobre a funcionalidade de cada método ou função, os desenvolvedores podem hesitar em dividir blocos de código longos em unidades menores e mais gerenciáveis.
Classe/Módulo com Responsabilidade Excessiva: A falta de documentação pode resultar em classes ou módulos que acumulam várias responsabilidades, tornando o código mais difícil de manter e entender.
Operação de refatoração para atingir a característica - Boa Documentação:
Para alcançar a característica de boa documentação, pode-se seguir as seguintes práticas de refatoração:

Adicionar Comentários Significativos: Revisar o código existente e adicionar comentários significativos para explicar o propósito de cada classe, método, função ou trecho de código complexo. Os comentários devem esclarecer o "porquê" das decisões de design, não apenas o "o que" o código está fazendo.

Criar Documentação Externa: Criar ou atualizar manuais do usuário, documentação técnica e/ou wiki do projeto para descrever a arquitetura geral, fluxos de trabalho, configurações e outras informações relevantes para desenvolvedores e usuários.

Usar Padrões de Documentação: Padronizar a forma como os comentários são escritos e apresentar diretrizes claras para a documentação do código. Isso torna mais fácil para todos os membros da equipe seguirem o mesmo formato e estilo.

Atualizar a Documentação Regularmente: Garantir que a documentação seja revisada e atualizada conforme o código é alterado ou evolui. Documentação desatualizada pode levar a confusões e erros.

Ferramentas de Automação: Utilizar ferramentas de geração de documentação automática, como Doxygen ou Javadoc, para extrair automaticamente comentários do código e criar documentação estruturada.

Lembre-se de que uma boa documentação é um elemento essencial para o sucesso de um projeto de software, pois contribui para a compreensão, manutenção e colaboração eficazes entre os membros da equipe. Se precisar de mais informações específicas ou tiver alguma dúvida adicional, sinta-se à vontade para perguntar!

# Elegância

A elegância é uma característica que engloba os aspectos estéticos do design do código, muitas vezes caminhando lado a lado com a simplicidade. Um código elegante é aquele que não se complica sem necessidade, um código que não se perde em sua complexidade e que resolve os problemas de maneira sucinta e direta.

## Efeitos no código:

- Estrutura: A elegância trás uma noção de complementação, cada parte complementa a anterior, gerando assim uma estrutura de fácil acopanhamento.
- Claridade: Seguindo a ideia de complementação, uim código elegante possui um fluxo direto e claro, não sendo repleto de casos especiais.
- Coesão: A elegância também associa  coisas parecidas, evitando assim a ploriferação de duplicidade e código desnecessário, assim, aumentando a coesão do código.
- Acoplamento: Um código elegante também favorece acoplamento, visto que uma característica importante da elegância é poder mudar uma parte do código sem afetar todo o resto do sistema. Además, a elegância também trás um funcionamento mais local, sem precisar passar por muitos métodos e módulos diferentes. 

## Relação com os maus cheiros de código definidos por Fowler:

- Código Duplicado: Seguindo com os aspectos de simplicidade, a elegância também ajuda na diminuição de duplicidade de código, proncipalmente por conta da associação de aspectos similares como a localidade de mudança.

- Cirurgia com rifle: Por conta do aspecto da localidade de mudança, o códgio elegante também faz com que mudanças feitas no código não efetem uma área muito grande, assim evitando muitas mudanças em lugares diferentes do código.

## Operação de refatoração relacionada:

- Incorporar classe: Ao juntar o conjunto de conportamentos em uma só estrutura, o código se torna mais coeso e direto, que por sua vez ajuda com o problema de Cirurgia com rifle, visto que uma mudança que afeta tais métodos ou campos estará concentrado em uma mesma estrutua.


## Exemplo em código:

Levemos em conta as seguintes classe.

``` java
public class Pessoa{
    private String nome;
    private String cpf;
    private String rg;

    ...
}

public class Empresa{
    private String titulo;
    private String cnpj;

    ...
}
```

Nesse exemplo, temos alguns documentos que podem ser validados, e esses métodos podem ser feitos cada um em uma classe diferente, por exemplo poderia existir o `PessoaService.java` e um `EmpresaService.java` e nela ter a validação deles.

Mas ao invés disso, se for criado uma classe `DocumentoValidation.java` e nele ser colocado todos os métodos de validação, se alguma mudança for feita, por exemplo em uma biblioteca de validação, todas as mudanças seriam feitas em `DocumentoValidation.java` e não nos dois arquivos.

Isso se caracteriza como uma operação de "Incorporar classe", que por sua vez aumenta a elegância do código, visto que associa aspectos iguais do código e diminui a localidade de mudanças.
