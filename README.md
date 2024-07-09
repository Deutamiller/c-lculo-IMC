import java.time.format.TextStyle;
import java.util.Locale;
import java.time.LocalDate;
import java.time.LocalDateTime;

public class Main {


    public static void main(String[] args) {
        // variaveis de escrita
        String nome = "lets code";
        String bill = "amazing";
        System.out.println("Ola, " + nome + bill);

        // variaveis de numeros
        // int e usado para valores inteiros
        int a;
        int b = 2;
        a = 3;
        int soma = a + b;
        int subtracao = a - b;
        int multiplicacao = a * b;
        float divisao = (float) a / b;

        System.out.println(soma);
        System.out.println(subtracao);
        System.out.println(multiplicacao);
        System.out.println(divisao);

        // operadores booleanos e tabela verdade

//        boolean resultado = false;
//        System.out.println(resultado);


        // Algoritmo para ir pra praia com 2 condicoes: Fazer sol e fim de semana
        boolean fazerSol = false;
        boolean fimDeSemana = true;
        boolean vamosAPraia = fazerSol && fimDeSemana; //Usei essa linha para combinar as duas condicoes e ter o resultado, essa e uma operacao booleana

        // Tabela verdade
        // Operador && (and)
        // true && true= true (se os dois forem verdade, o resultado e verdade)
        // true && false= false
        // false && true = false (SO SAO VERDADEIROS QUANDO TODOS OS TEMOS SAO VERDADE)
        // false && false = false

        // Operador || (or)
        // true || true = true
        // true || false = true (TODAS SAO VERDADES QUANDO UM TERMO E VERDADE)
        // false ||true = true
        // false ||false = false (se os dois termos forem false, o resultado sera false)

        // Operador ? (alternario) Usado pra quando temos 2 comportamentos possiveis
        // 1 - E fim de semana
        // 2 - nao e fim de semana

        System.out.println(vamosAPraia);

        String mensagem = fazerSol ? "E fim de semana" : "Nao e fim de semana";
        System.out.println(mensagem);


        // Estruturas condicionais

        // if: Executa um bloco de código se uma condição for verdadeira.
        int nota = 100;

        if (nota >= 70) {
            System.out.println("Aprovado");
        }

        // if-else: Executa um bloco de código se uma condição for verdadeira, e outro bloco de código se a condição for falsa.
        if (nota >= 70) {
            System.out.println("Aprovado");
        } else {
            System.out.println("Reprovado");
        }

        // else if: Permite testar múltiplas condições, executando blocos de código diferentes para cada condição verdadeira.
        if (nota >= 90) {
            System.out.println("Excelente");
        } else if (nota >= 75) {
            System.out.println("Bom");
        } else if (nota >= 60) {
            System.out.println("Satisfatório");
        } else {
            System.out.println("Insatisfatório");
        }


//        switch: O switch é uma estrutura condicional que permite selecionar um bloco de código para ser executado dentre várias opções,
//         com base no valor de uma expressão. É uma alternativa ao uso de múltiplos if-else if-else
//         quando se está lidando com múltiplas condições que dependem do valor de uma única variável.
        int diaDaSemana = 7;

        switch (diaDaSemana) {
            case 1:
                System.out.println("Domingo");
                break;
            case 2:
                System.out.println("Segunda-feira");
                break;
            case 3:
                System.out.println("Terça-feira");
                break;
            case 4:
                System.out.println("Quarta-feira");
                break;
            case 5:
                System.out.println("Quinta-feira");
                break;
            case 6:
                System.out.println("Sexta-feira");
                break;
            case 7:
                System.out.println("Sábado");
                break;
            default:
                System.out.println("Dia inválido");
                break;

            //Explicação
            //switch (diaDaSemana): O valor da variável diaDaSemana é avaliado.
            //Casos (case 1, case 2, ..., case 7): Cada case compara o valor de diaDaSemana com um número.
            //Se diaDaSemana for 3, o código dentro do case 3 é executado e imprime "Terça-feira".
            //break: Após imprimir "Terça-feira", o break interrompe o switch, evitando que o código continue para os casos seguintes.
            //default: Se diaDaSemana não corresponder a nenhum dos casos (por exemplo, se for 0 ou 8), o bloco de código dentro do default será executado, imprimindo "Dia inválido".
        }



        // MANIPULAÇÃO DE ESTRINGS E DATAS - ANOTAÇÕES NO CADERNO

        // Quero fazer a seguinte linha:    Olá, (nome). Hoje é (dia da semana). BOM DIA.

        String name = "Tadeu";
//        System.out.println(name.toUpperCase()); // Esse comando é usado para colocar todas as palavras em maiúsculo.
//        System.out.println(name.toLowerCase()); //Esse comando é usado para colocar todas as palavras em minúsculo.
//        System.out.println(name.length()); //Esse comando é usado parar ver o tamanho da palavra.
//
//        //Para comparar duas strings usamos:
//
//        String nameOutro = "Tadeu";
//        System.out.println(name.equals(nameOutro)); // quando executado, aprenta o sinal verdadeiro (true)
        //String nameOutro = "tadeu";
//        System.out.println(name.equals(nameOutro)); o resultado seria false, pois o o valor da string é com t minúscolo ao invés de maiúsculo


//        Para usar a manipulação de datas, possuimos o ISO 8601, que é universal, sendo assim usamos o a variável LocalDate, mas ela é de uma classe de um outro pacote
//        Sendo assim eu preciso fazer o import desse arquivo == import java.time.LocalDate;
        LocalDate hoje = LocalDate.now(); //dessa forma eu consigo representar uma data com informações locais
        Locale brasil = new Locale("pt", "BR");
        System.out.println(hoje); //representa a data completa
        System.out.println(hoje.getDayOfWeek()); //me responde com o dia da semana
        System.out.println(hoje.getDayOfWeek().getDisplayName(TextStyle.FULL, brasil)); //isso para poder traduzir o código (Preciso de 2 parâmetros, o primeiro o estilo e o segundo a localidade (locale)
        String diaSemana = hoje.getDayOfWeek().getDisplayName(TextStyle.FULL, brasil);  // isso para ficar mais resumido e mais limpo ao invés de usar toda a linha de código acima
        String saudacao;
        LocalDateTime agora = LocalDateTime.now(); // essa linha me permite obter  a informação  de que horas são
        if (agora.getHour() >= 0 && agora.getHour() < 12) {
            saudacao = "bom dia!";
        } else if (agora.getHour() >= 12 && agora.getHour() < 18) {
            saudacao = "boa tarde";
        } else if (agora.getHour() >= 18 && agora.getHour() < 24) {
            saudacao = "boa noite";
        } else {
            saudacao = "Olá";
        }

        System.out.printf("Olá, %s. Hoje é %s, %s.%n", name, diaSemana, saudacao.toUpperCase());
        // printf é definir  o formato (%s) e depois definir os valores (as strings).
        // %s é para marcar os locais de cada  string
        // %n para fazer quebra de linha
    }
}
