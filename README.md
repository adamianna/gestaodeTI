# gestaodeTI
#include <stdio.h>
#include <string.h>

// Definição da estrutura da carta
typedef struct {
    char estado[3];
    char codigo[5];
    char nome[50];
    unsigned long int populacao;
    float area;
    double pib; // Usando double para valores maiores
    int pontos_turisticos;
    float densidade_populacional;
    double pib_per_capita;
} Cidade;

int main() {
    Cidade c;

    printf("--- Cadastro de Carta: Cidades de São Paulo ---\n\n");

    // Entrada de Dados
    printf("Estado (ex: SP): ");
    scanf("%2s", c.estado);

    printf("Código da Carta (ex: A01): ");
    scanf("%4s", c.codigo);

    printf("Nome da Cidade: ");
    scanf(" %[^\n]s", c.nome); // Lê a string incluindo espaços

    printf("População: ");
    scanf("%lu", &c.populacao);

    printf("Área (em km²): ");
    scanf("%f", &c.area);

    printf("PIB (em bilhões): ");
    scanf("%lf", &c.pib);

    printf("Número de pontos turísticos: ");
    scanf("%d", &c.pontos_turisticos);

    // --- Cálculos das Propriedades Derivadas ---
    // Densidade Populacional = População / Área
    c.densidade_populacional = (float)c.populacao / c.area;

    // PIB per Capita = (PIB * 1.000.000.000) / População 
    // (Considerando que o PIB foi inserido em bilhões)
    c.pib_per_capita = (c.pib * 1000000000.0) / c.populacao;

    // Exibição dos Dados
    printf("\n------------------------------------------\n");
    printf("DADOS DA CARTA REGISTRADA:\n");
    printf("------------------------------------------\n");
    printf("Estado: %s\n", c.estado);
    printf("Código: %s\n", c.codigo);
    printf("Cidade: %s\n", c.nome);
    printf("População: %lu habitantes\n", c.populacao);
    printf("Área: %.2f km²\n", c.area);
    printf("PIB: R$ %.2f bilhões\n", c.pib);
    printf("Pontos Turísticos: %d\n", c.pontos_turisticos);
    
    // Resultados calculados
    printf("Densidade Populacional: %.2f hab/km²\n", c.densidade_populacional);
    printf("PIB per Capita: R$ %.2f\n", c.pib_per_capita);
    printf("------------------------------------------\n");

    return 0;
}
