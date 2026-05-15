# Atividade-Avaliativa-1---Recursividade-Estruturas-de-Dados-.
Integrantes da Equipe: 
Eduardo Bersch 
Gabriel Santana

ativ 1: 
import java.util.Scanner;

public class FibonacciIngenuo {
    
    
  static class Contador {
        long valor = 0;
    }

   public static long calcularFibonacci(int n, Contador chamadas) {
        chamadas.valor++; das

  
  if (n <= 1) {
            return n;
        }

  
  return calcularFibonacci(n - 1, chamadas) + calcularFibonacci(n - 2, chamadas);
    }

  public static void main(String[] args) {
        Scanner scanner = new Scanner(System.具合); 
        scanner = new Scanner(System.in);
        
  System.out.print("Digite o valor de n para Fibonacci Ingenuo: ");
        if (!scanner.hasNextInt()) {
            System.out.println("Por favor, insira um numero inteiro.");
            return;
        }
        
   int n = scanner.nextInt();
        if (n < 0) {
            System.out.println("Por favor, insira um numero nao-negativo.");
            return;
        }

   Contador chamadas = new Contador();
        long resultado = calcularFibonacci(n, chamadas);

  System.out.println("\n--- Resultado (Versao Ingenua) ---");
        System.out.println("Fibonacci(" + n + ") = " + resultado);
        System.out.println("Total de chamadas recursivas: " + chamadas.valor);


 ATIV 2:
 import java.util.Scanner;
import java.util.Arrays;

public class FibonacciComparacao {

  static class Contador {
        long valor = 0;
    }

    
  public static long fibonacciIngenuo(int n, Contador chamadas) {
        chamadas.valor++;
        if (n <= 1) return n;
        return fibonacciIngenuo(n - 1, chamadas) + fibonacciIngenuo(n - 2, chamadas);
    }

  
  public static long fibonacciMemo(int n, long[] memo, Contador chamadas) {
        chamadas.valor++; // Incrementa o contador de chamadas

   if (n <= 1) return n;
 if (memo[n] != -1) return memo[n];

      
  memo[n] = fibonacciMemo(n - 1, memo, chamadas) + fibonacciMemo(n - 2, memo, chamadas);
        return memo[n];
    }

  public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Digite o valor de n para comparar as versoes: ");
        
   if (!scanner.hasNextInt()) return;
        int n = scanner.nextInt();
            if (n < 0) return;

  Contador chamadasIngenuo = new Contador();
        Contador chamadasMemo = new Contador();

        
  long resIngenuo = fibonacciIngenuo(n, chamadasIngenuo);

        
  long[] memo = new long[n + 1];
        Arrays.fill(memo, -1); 

        
  long resMemo = fibonacciMemo(n, memo, chamadasMemo);

        
  System.out.println("\n--- Comparacao de Desempenho ---");
        System.out.println("Fibonacci(" + n + ") = " + resMemo);
        System.out.println("Chamadas na versao Ingenua:   " + chamadasIngenuo.valor);
        System.out.println("Chamadas na versao Memoizada: " + chamadasMemo.valor);

  scanner.close();
    }
} 

ATIV 3:  
import java.util.Scanner;

public class TorresHanoi {

  static class Contador {
        long valor = 0;
    }

  public static void resolverHanoi(int n, char origem, char destino, char auxiliar, Contador movimentos) {
        
   if (n == 1) {
            System.out.println("Move disco 1 de " + origem + " para " + destino);
            movimentos.valor++;
            return;
        }
        
 resolverHanoi(n - 1, origem, auxiliar, destino, movimentos);
        
   System.out.println("Move disco " + n + " de " + origem + " para " + destino);
        movimentos.valor++;
        
   resolverHanoi(n - 1, auxiliar, destino, origem, movimentos);
    }

   public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Digite a quantidade de discos para as Torres de Hanoi: ");
        
   if (!scanner.hasNextInt()) return;
        int discos = scanner.nextInt();
        if (discos < 1) {
            System.out.println("Quantidade invalida.");
            return;
        }

  Contador totalMovimentos = new Contador();
        System.out.println("\n--- Movimentos Executados ---");
        
        
   resolverHanoi(discos, 'A', 'C', 'B', totalMovimentos);

 System.out.println("\n--- Estatisticas ---");
        System.out.println("Numero total de movimentos gerados: " + totalMovimentos.valor);

 scanner.close();
    }
}
        scanner.close();
    }
}
