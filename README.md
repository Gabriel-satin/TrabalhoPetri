#TrabalhoJava
# TrabalhoJava
# TrabalhoPetri
Boa noite professor

package com.company;


import java.util.Scanner;

public class EstoqueDeTenis {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int tamanhoEstoque = 5;
        String[] modelos = new String[tamanhoEstoque];
        int[] tamanhos = new int[tamanhoEstoque];
        double[] valores = new double[tamanhoEstoque];
        int[] quantidades = new int[tamanhoEstoque];

        modelos[0] = "Air Force";
        tamanhos[0] = 40;
        valores[0] = 299.99;
        quantidades[0] = 10;

        modelos[1] = "Puma Disk";
        tamanhos[1] = 38;
        valores[1] = 199.99;
        quantidades[1] = 5;

        modelos[2] = "Fila";
        tamanhos[2] = 42;
        valores[2] = 249.99;
        quantidades[2] = 3;

        System.out.println("Informe os dados do novo tênis:");
        modelos[3] = scanner.nextLine();
        tamanhos[3] = scanner.nextInt();
        valores[3] = scanner.nextDouble();
        quantidades[3] = scanner.nextInt();
        scanner.nextLine();

        System.out.print("Informe o modelo do tênis a ser removido: ");
        String modeloRemover = scanner.nextLine();
        int indiceRemover = -1;
        for (int i = 0; i < tamanhoEstoque; i++) {
            if (modelos[i] != null && modelos[i].equalsIgnoreCase(modeloRemover)) {
                indiceRemover = i;
                break;
            }
        }
        if (indiceRemover != -1) {
            modelos[indiceRemover] = null;
            tamanhos[indiceRemover] = 0;
            valores[indiceRemover] = 0.0;
            quantidades[indiceRemover] = 0;
            System.out.println("Tênis removido do estoque.");
        } else {
            System.out.println("Tênis não encontrado no estoque.");
        }
        System.out.println("\nEstoque de Tênis:");
        for (int i = 0; i < tamanhoEstoque; i++) {
            if (modelos[i] != null) {
                System.out.println("Modelo: " + modelos[i]);
                System.out.println("Tamanho: " + tamanhos[i]);
                System.out.println("Valor: R$" + valores[i]);
                System.out.println("Quantidade: " + quantidades[i]);
                System.out.println("-------------------");
            }
        }
        double total = 0.0;
        for (int i = 0; i < tamanhoEstoque; i++) {
            if (modelos[i] != null) {
                total += valores[i] * quantidades[i];
            }
        }
        System.out.println("Total do dinheiro em estoque: R$" + total);
    }
}
