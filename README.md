# Jogo-da-Adivinha-o
Jogo da adivinhação em construção utilizando linguagem C

#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int main()
{
    setlocale(LC_ALL, "Portuguese");

    int chute;
    int numerosecreto=42;


    printf("\n\t\t\t\t************************************\n");
    printf("\t\t\t\t* Bem-Vindo ao jogo da Adivinhação *\n");
    printf("\t\t\t\t************************************\n");


    printf("\n\n\t\t\t\tQual o seu chute? ");
    scanf("%d", &chute);
    printf("\n\t\t\t\tVocê chutou o numero %d!\n", chute);

    if(chute == numerosecreto){
        printf("\n\t\t\t\tParabens ! Você Acertou\n");
        printf("\t\t\t\tJogue de novo você é um bom jogador!\n\n");
    }
    else {

        if(chute > numerosecreto){
            printf("\n\t\t\t\tSeu chute foi MAIOR que o Numero Secreto!\n");
        }
        if(chute < numerosecreto){
            printf("\n\t\t\t\tSeu Chute foi MENOR que o Numero Secreto!\n");
        }
    }


    return 0;
}

