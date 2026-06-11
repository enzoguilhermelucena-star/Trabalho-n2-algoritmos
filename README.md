# Trabalho-n2-algoritmos

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

/* Simulação de um dia de vendas em uma loja */

int main() {
    /* Declaração de variáveis */
    float precos[200];
    float total_vendas = 0.0;
    int qtd_produtos = 0;
    int qtd_clientes = 0;
    int i = 0;
    int indice_produto = 0;

    /* Inicializa o gerador de números aleatórios */
    srand((unsigned int)time(NULL));

    /* Gera a quantidade de produtos (1 a 200) */
    qtd_produtos = (rand() % 200) + 1;

    /* Gera a quantidade de clientes (1 a 50) */
    qtd_clientes = (rand() % 50) + 1;

    /* Define os preços aleatórios para cada produto */
    for (i = 0; i < qtd_produtos; i++) {
        /* Preços entre R$ 5,00 e R$ 100,00 */
        precos[i] = 5.0f + ((rand() % 9501) / 100.0f);
    }

    /* Exibe o cabeçalho da simulação */
    printf("=== SIMULACAO DE VENDAS ===\n");
    printf("Total de produtos no estoque: %d\n", qtd_produtos);
    printf("Total de clientes que entraram: %d\n\n", qtd_clientes);
    printf("--- Resumo das Compras ---\n");

    /* Simula a compra de cada cliente */
    for (i = 0; i < qtd_clientes; i++) {
        /* Escolhe um produto aleatório do estoque */
        indice_produto = rand() % qtd_produtos;
        
        /* Acumula o valor no total do dia */
        total_vendas += precos[indice_produto];
        
        /* Exibe a compra do cliente atual */
        printf("Cliente %d comprou Produto %d por R$ %.2f\n", i + 1, indice_produto + 1, precos[indice_produto]);
    }

    /* Exibe o resultado financeiro final */
    printf("\n=================================\n");
    printf("Faturamento total do dia: R$ %.2f\n", total_vendas);
    printf("=================================\n");

    return 0;
}