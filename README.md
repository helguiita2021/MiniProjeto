# MiniProjeto

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

struct Candidato{  //criação de uma variavel estruturada
	
	char nome[200];
	int numero;
	char estado[10];
	int votos;
	char partidos[10];
	
};

struct Candidato candidatos[5]; // delimita a quantidade de pessoas cadastradas
int ultimoIndice = 0;


void imprimirMenu(){
	
	printf("-----------------------\t Menu do Projeto--------------------\n");
	printf("1->> Cadastro de Candidato: \n");
	printf("2->> Listagem de Candidatos Cadastrados \n");
	printf("3->> Listagem de Candidatos por Partido \n");
	printf("4->> Listagem de Candidatos por Estado \n");
	printf("5->> Voltar \n");
	printf("6->> Listagem de Candidatos por ordem, dos mais voltados para os menos voltados \n");
	printf("7->> Sair do Sistema \n");

}

	void CadastraCandidato(){
		
		printf(" Digite o Nome do Candidato: \n");
		scanf(" %s",candidatos[ultimoIndice].nome);
		fflush(stdin); //limpar baffer
		printf("Digite o numero do Candidato: \n");
		scanf("%d",&candidatos[ultimoIndice].numero);
		fflush(stdin);
		printf(" Digite o Estado do Candidato: \n");
		scanf("%s",candidatos[ultimoIndice].estado);
		fflush(stdin);
		printf(" Digite o nome do partido do Candidato");
		scanf("%s",candidatos[ultimoIndice].partidos);
		ultimoIndice++;
	}
	
	void ListagemCandidatosCadastrado(){
		int i;
		
		printf("Listar todos os candidatos cadastrado no sistema: \n\n");
		for(i=0;i<ultimoIndice;i++){
			
			printf("Nome do Candidato %s:\n",candidatos[i].nome);
			fflush(stdin);
			printf("Numero do Candidato %d:\n",candidatos[i].numero);
			fflush(stdin);
			printf("Estado do Candidato %s:\n",candidatos[i].estado);
			fflush(stdin);
			//printf("Quantidade de Votos Recebidos %d:\n",candidatos[i].votos);
		   	printf("Partid  dos Candidatos Cadastrado: \n",candidatos[i].partidos);
		   	
		   	
		}	
	}
	
	void ListagemCandidatosPartidos(){
		int i;
		char partidos[10];
		int cont=0;
		printf("digite o partido \n");
		scanf("%s",partidos);
		printf(" Listagem de candidatos por partidos \n\n");
		printf("Candidatos do partidos %s: \n",partidos);
		
		for(i=0;i<ultimoIndice;i++){	
		          if(strcmp(partidos,candidatos[i].partidos)==0){
				  printf("Nome do Candidato: %s",candidatos[i].nome);
                  cont++;		         	          
}
 
              }
              
        if(cont==0)	printf(" Não existe candidatos deste Partidos \n");
	}

	
    void ListagemCandidatosEstado(){
    	int i;
    	printf("\n Listagem de Candidato por Estado \n");
    	for(i=0;i<ultimoIndice;i++){
    		
    		printf("Nome do Candidato: %s",candidatos[i].nome);
    		printf(" Estado do Candidato: %s \n",candidatos[i].estado);
    	
    		
		}
    	
    	
    	
    	
	}





int main(void){
	
	printf("\n\t----------------PROJETO URNA:---------------\n\n\n");
	
	int opcao;
	
	do{
		
	
	imprimirMenu();
	
	printf(" \n\n Digite uma opcao: \n\n ");
	scanf("%d",&opcao);
	switch(opcao){
		
		case 1:
			CadastraCandidato();
			break;
		case 2:
		 ListagemCandidatosCadastrado();
		    break;
		case 3:
		   ListagemCandidatosPartidos();
		    break;       
		case 4:
		    ListagemCandidatosEstado();
			break;	
	
		
	}
	
} while(opcao !=7);
	
	
	
	
	
	

	

	
}
