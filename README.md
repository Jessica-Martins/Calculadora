# Calculadora
Calculadora Desenvolvido em C++

#include <stdio.h> 
#include <stdlib.h> 
#include <math.h> 
#include <conio.h> 

/* run this program using the console pauser or add your own getch, system("pause") or input loop */ 

int main(int argc, char *argv[]) { 
	
	double v1, v2, res; 
	char op; 
	
	system ("title CALCULADORA"); 
	
	do 
	
	{
		system ("cls"); 
		printf ("\n"); 
		printf ("\n \t\t\t\t \xC9 \xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD \xBB"); 
		printf ("\n \t\t\t\t \xBA CALCULADORA \xBA"); 
		printf ("\n \t\t\t\t \xC8 \xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD\xCD \xBC"); 
		printf ("\n\n"); 
		
		printf ("\n\t INFORME O TIPO DE OPERACAO: \n\n"); 	

		printf("\t(+) - Soma\t\t\t(P) - Porcentagem\n"); 

   		printf("\t(-) - Subtracao\t\t\t(F) - Fatorial\n"); 

   		printf("\t(*) - Multiplicao\t\t(B) - Conversao Binario -> Decimal\n"); 

    	printf("\t(/) - Divisao\t\t\t(D) - Conversao Decimal -> Binario\n"); 

    	printf("\t(E) - Exponenciacao\t\t(S) - Sair\n"); 

    	printf("\t(R) - Raiz Quadrada\n"); 

		printf("\n\t Opcao: "); 
		scanf("%c", &op); 

 		switch (op) {
 			
		 	case '+': 
			{
			 	printf ("\n\n\t SOMA \n");
				printf ("\n Informe o primeiro valor: "); 
				scanf ("%lf", &v1); 	
				printf ("\n Informe o segundo valor: "); 
				scanf ("%lf", &v2); 
				res = v1 + v2; 
				printf ("\n\t %.2lf + %.2lf = %.2lf \n\n", v1, v2, res); 
				break; 
	        } 
	        
	        case '-': 
	        {
	        	printf ("\n\n\t SUBTRACAO \n"); 
				printf ("\n Informe o primeiro valor: "); 
				scanf ("%lf", &v1); 
				printf ("\n Informe o segundo valor: "); 
				scanf ("%lf", &v2); 
				res = v1 - v2; 
				
				printf ("\n \t %.2lf - %.2lf = %.2lf \n\n", v1, v2, res); 
				break; 
	        } 
	        
	        case '*': 
	        {
	        	printf ("\n\n\t MULTIPLICACAO \n"); 
				printf ("\n Informe o primeiro valor: "); 
				scanf ("%lf", &v1); 
				printf ("\n Informe o segundo valor: "); 
				scanf ("%lf", &v2); 
				res = v1 * v2; 
				printf ("\n \t %.2lf * %.2lf = %.2lf \n\n", v1, v2, res); 
				break; 
	        } 
	        
	        case '/':
	        {
	        	printf ("\n\n\t DIVISAO \n"); 
				printf ("\n Informe o primeiro valor: "); 
				scanf ("%lf", &v1); 
				printf ("\n Informe o segundo valor: "); 
				scanf ("%lf", &v2); 
				res = v1 / v2; 
				printf ("\n \t %.2lf / %.2lf = %.2lf \n\n", v1, v2, res); 
				break; 
	        } 
	        
	        case 'E':
			case 'e': 
			{
				printf ("\n\n\t EXPONENCIACAO \n"); 
				printf ("\n Informe a base: "); 
				scanf ("%lf", &v1); 
				printf ("\n Informe o expoente: "); 
				scanf ("%lf", &v2); 
				res = pow (v1, v2);
				printf ("\n \t %.2lf elevado %.2lf = %.2lf \n\n", v1, v2, res); 
				break; 
	        }
			
			case 'R': 
			case 'r': 
			{
				printf ("\n\n\t RAIZ QUADRADA \n"); 
				printf ("\n Informe o valor: "); 
				scanf ("%lf", &v1); 
				res = sqrt (v1); 
				printf ("\n \t Valor: %.2lf = %.2lf \n\n", v1, res); 
				break;
	        } 
	        
	        case 'P': 
	        case 'p':
			{
				printf ("\n\n\t PORCENTAGEM \n"); 
				printf ("\n Informe o valor: ");
				scanf ("%lf", &v1); 
				printf ("\n Informe a procentagem: "); 
				scanf ("%lf", &v2); 
				res = (v1/100)* v2; 
				printf ("\n\t %.2lf%% de %.2lf = %.2lf \n\n", v2, v1, res); 
				break;
			}
			case 'F':
			case 'f':
			{
				printf ("\n\n\t FATORIAL \n"); 
				printf("\n Informe o valor: ");
				scanf("%lf", &v1); 
				res = 1; 
				for (v2 = 2; v2 <= v1; v2 = v2 + 1) 
				res = res * v2; 
				printf("%.2lf = %.2lf \n\n", v1, res);
				break;
			}
			
			case 'D': 
			case 'd': 
			{ 
				printf ("\n\n\t CONVERSAO DE DECIMAL PARA BINARIO \n"); 
				int dec; 
				char bin[10]; 
				printf("\n Informe o valor em decimal: "); 
				scanf("%d",&dec); 
				itoa(dec,bin,2); 
				printf("\n O numero %d em binario e: %s \n\n",dec,bin); 
				break; 
			} 
			
			case 'B': 
			case 'b': 
			{
				printf ("\n\n\t CONVERSAO DE BINARIO PARA DECIMAL \n\n"); 
				int bin, d=1, dec = 0; 
				printf("\n Informe o valor em binario: "); 
				scanf("%d",&bin); 
				
				do 
				{					
					dec = dec+(bin%10)*d; 
					d = d*2; 
					bin = bin/10; 
				} while(bin !=0); 
				
				printf("\n Este valor em decimal eh %d \n\n",dec); 
				break; 
			} 
			
			case 'S': 
			case 's': 
			{ 
				printf ("\n\n\t PROGRAMA FINALIZADO \n"); 
				exit(1); 
			} 
			
			default: printf("\n Operacao impossivel de ser realizada! \n\n"); 
		} 
			
			printf ("\n Deseja fazer outra operacao? (S/N): "); 
			scanf ("%c", &op);
			
	} while (getche() == 's');
	printf ("\n\n");
	
	system ("pause"); 
	return 0; 
} 
