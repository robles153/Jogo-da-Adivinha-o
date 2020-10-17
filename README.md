# Jogo-da-Adivinha-o
Jogo da adivinhação em construção utilizando linguagem C

#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#define NUMERO_DE_TENTATIVAS 3

int main()
{
    setlocale(LC_ALL, "Portuguese");

    int chute;
    int numerosecreto=42;


    printf("\n\t\t\t\t************************************\n");
    printf("\t\t\t\t* Bem-Vindo ao jogo da Adivinhação *\n");
    printf("\t\t\t\t************************************\n");

for(int i = 1; i <=NUMERO_DE_TENTATIVAS; i++){
       printf("\n\n\t\t\t\tQual é o seu %dº chute? ", i);
       scanf("%d", &chute);
       printf("\n\t\t\t\tSeu %dº chute foi %d!\n",i, chute);

       int acertou = chute ==numerosecreto;
    // imprimirá 0 quando a condição for falsa,
    // e 1 quando ela for verdadeira.

       printf("\n\t\t\t\tAcertou: %d\n", acertou);


       if(acertou){
            printf("\n\t\t\t\tParabens ! Você Acertou\n");
            printf("\t\t\t\tJogue de novo você é um bom jogador!\n\n");
            break;
    }
    else {

          int maior = chute > numerosecreto;
          if(maior){
            printf("\n\t\t\t\tSeu chute foi MAIOR que o Numero Secreto!\n");
        }
          if(chute < numerosecreto){
            printf("\n\t\t\t\tSeu Chute foi MENOR que o Numero Secreto!\n");
        }
      }
    }

    printf("\n\n\t\t\t\tFIM DE JOGO!\n\n");


    return 0;
}


