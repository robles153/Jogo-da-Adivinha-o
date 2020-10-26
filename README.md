#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#define NUMERO_DE_TENTATIVAS 3

int main()
{
    setlocale(LC_ALL, "Portuguese");

    int chute;
    int numerosecreto=42;
    int tentativas =1;


    printf("\n\t\t\t\t************************************\n");
    printf("\t\t\t\t* Bem-Vindo ao jogo da Adivinhação *\n");
    printf("\t\t\t\t************************************\n");


    while(1)
{
    printf("Tentativa %d \n", tentativas);
       printf("\n\n\t\t\t\tQual é o seu  chute? ");
       scanf("%d", &chute);
       printf("\n\t\t\t\tSeu  chute foi %d!\n", chute);

       if(chute < 0)
	   { printf("\n\t\t\t\tVocê NÃO pode Chutar numeros NEGATIVOS\n");


	   continue; /* diz ao laço que ele deve ir direto para a próxima iteração,sem executar o restante de código que ainda
	   possa existir dentro do seu bloco de código*/

	   }

       int acertou = (chute ==numerosecreto);
       int maior = chute > numerosecreto;



       if(acertou){
            printf("\n\t\t\t\tParabens ! Você Acertou\n");
            printf("\t\t\t\tJogue de novo você é um bom jogador!\n\n");

            break;/* para o loop caso o jogador acertar o numero secreto*/
    }
    else if(maior){
            printf("\n\t\t\t\tSeu chute foi MAIOR que o Numero Secreto!\n");
        }

          else{
            printf("\n\t\t\t\tSeu Chute foi MENOR que o Numero Secreto!\n");
        }
        tentativas++;

      }


    printf("\n\n\t\t\t\tFIM DE JOGO!\n\n");
    printf("\n\t\t\t\tVoê Acertou em %dª tentativas!\n\n", tentativas);


    return 0;
}
