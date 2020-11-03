jogo da Adivinhação usando linguagem C.



#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#define NUMERO_DE_TENTATIVAS 3

int main()
{
    setlocale(LC_ALL, "Portuguese");

    int chute;
    int acertou = 0;
    int tentativas =1;
    double pontos = 1000;
    int nivel;
    int totaldetentativas;
    

    srand(time(0));
    int numerosecreto = rand()% 100;


    printf("\n\t\t\t\t************************************\n");
    printf("\t\t\t\t* Bem-Vindo ao jogo da Adivinhação *\n");
    printf("\t\t\t\t************************************\n");

    printf("\n\t\t\t\tQual o Nivel de Difuculdade?");
    printf("\n\n\t\t\t\t(1) FACIL (2) MEDIO (3) DIFICIL\n");
    printf("\n\t\t\t\tEscolha: ");
    scanf("%d", &nivel);

    switch(nivel) {
    	case 1 :
    		totaldetentativas = 20;
    		break;
    	case 2 :
			totaldetentativas = 15;
			break;
		default:
			totaldetentativas = 6;
			break;
	}
	int i;
	
    for(i=1; i<= totaldetentativas; i++)
{
	printf("\n\t\t\t\tTentativa %d de %d!\n", i, totaldetentativas);
       printf("\n\n\t\t\t\tQual é o seu %dº.  chute? ", i  );
       scanf("%d", &chute);


       if(chute < 0)
	   { printf("\n\t\t\t\tVocê NÃO pode Chutar numeros NEGATIVOS\n");
	   i--;


	   continue; /* diz ao laço que ele deve ir direto para a próxima iteração,sem executar o restante de código que ainda
	   possa existir dentro do seu bloco de código*/

	   }
	   printf("\n\t\t\t\tSeu %dº. chute foi %d\n",i, chute);


       int acertou = (chute ==numerosecreto);
       

       if(acertou){
            printf("\n\t\t\t\tParabens ! Você Acertou\n");
            printf("\t\t\t\tJogue de novo você é um bom jogador!\n\n");

            break;/* para o loop caso o jogador acertar o numero secreto*/
    }
    else if(chute > numerosecreto){
            printf("\n\t\t\t\tSeu chute foi MAIOR que o Numero Secreto!\n");
        }

          else{
            printf("\n\t\t\t\tSeu Chute foi MENOR que o Numero Secreto!\n");
        }
        tentativas++;

         double pontosperdidos = abs(chute- numerosecreto ) / 2.0;
	     pontos = pontos - pontosperdidos;

      }



    printf("\n\n\t\t\t\tFIM DE JOGO!\n\n");
    if (acertou)
{
	   printf("\n\t\t\t\tVoê Acertou na %dª tentativas!\n\n", tentativas);
	   printf("\n\t\t\t\tVocê fez %.0f pontos!!!\n\n\n", pontos);
	  } else {
	   	
	   	printf("\n\t\t\t\tVOCÊ PERDEU!!!\n\n\n");
	   	printf("\n\t\t\t\tTENTE NOVAMENTE!!!\n\n\n");
	   }


    



    return 0;
}

