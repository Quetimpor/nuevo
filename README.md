#include<iostream>
#include<stdlib.h>
#include <math.h>
using namespace std;
char fin[1];
int i;
int main(){
	do{
			
		float ND, NDF, aux=0, real[50];
		int  contador=0, contadorR=0,  residuo[50];
		
	cout<<"\n\t    CONVERTIDOR \n";	
	
	//todo valor menor a 0 el programa no lo lee	
	cout<<"\n\t INGRESE NUMERO EN BASE DECIMAL";
	do{
		cout<<"\n\t -> ";cin>>ND;
		if(ND<0){cout<<"\n\t NUMERO INVALIDO...";}		
	}while(ND<0);	
	
	cout<<"\n\t Numero en base decimal: "<<ND;
	
	//para separar la parte entera de la fraccionaria
	NDF=ND-int(ND);			
	if(	NDF!=0){	
	
			//Parte entera		
			for( i=0; ND>=2; i++){				
			residuo[i]=fmod(ND,2);//uso fmod -> es el modulo de un num		
			ND=(int)(ND/2);			
			contador++;}
			
			//Parte real		
			for( i=0; aux!=1; i++){	
			real[contadorR]=(int)(NDF*2); //me quedo con la parte entera	
			aux=NDF*2;
			NDF=aux-int(aux); //obtengo el proximo a multiplicar		
			contadorR++;}
			
			//Resultado
			cout<<"\n\t Numero Binario: "; 
			cout<<ND;		
			for( i=contador-1; i>=0; i--){cout<<residuo[i];}			
			cout<<".";
			for(i=0; i<contadorR; i++){cout<<real[i];}
					
		}			
		else{
			
			//Parte entera		
			for( i=0; ND>=2; i++){
			residuo[i]=fmod(ND,2);//uso fmod -> es el modulo de un num
			ND=(int)(ND/2);
			contador++;}
			
			//Resultado		
			cout<<"\n\t Numero Binario: "; 
			cout<<ND; //lo que quedo
			for( i=contador-1; i>=0; i--){cout<<residuo[i];}	//el residuo reordenado							
		}	
		//Para probar mas veces
		cout<<endl<<"\n\tDesea continuar?...s/n: ";
		cin>>fin;
		strupr(fin);//Minusculas a mayusculas	
		system("pause>NULL");  
		system("cls");				
	}while (!(strcmp(fin,"S")));//Compara las cadenas
	
	cout<<endl<<"\n\tMuchas gracias por usar el programa :)";	
   	return 0;
  	
}
