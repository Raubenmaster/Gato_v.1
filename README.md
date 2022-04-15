# Gato_v.1
juego de gato funcional // jugador v jugador


//Gato5.0
#include <iostream>
#include <stdio.h>
#include <stdlib.h>
using namespace std;

int tablero[3][3]={0,0,0,0,0,0,0,0,0};
int p1,p2,opcion,resultado,x,y;
int f1,f2,f3,c1,c2,c3,d1,d2;
int turno=1;
void instrucciones();
void jugar();
void jugador1();
void jugador2();
void opcionjugador();
void gato();
void multiplicar();
void formula1();
void formula2();
void ganador();


int main(){
	
	cout<<"Digite '1' para iniciar el juego"<<endl<<"Digite '2' para leer las instrucciones"<<endl<<"Digite '3' para salir del programa"<<endl<<"Press: ";cin>>opcion;
	
	switch(opcion){		
		case 1: 
		     cout<<"comienza el juego"<<endl;
		     jugar();
			 break; 
		case 2:
			 cout<<"--------------------instrucciones--------------------\n";
			 instrucciones();
			 break;
		case 3:
			 break;
			 return 0;
		default: 
		     system("cls");
		     cout<<"------------El numero elegido no esta en el rango chamaco tomtom------------"<<endl<<endl;		     
		     main();
			 break;		
	}	
	return 0;
}

void instrucciones(){	
	cout<<"Esta es la manera en la que esta previsto el tablero del gato...\n";
		cout<<"  7|8|9  "<<endl;
		cout<<"  4|5|6  "<<endl;
		cout<<"  1|2|3  "<<endl;
		cout<<"Para ingresar la posicion de tu ficha solo digita el numero correspondiente a esa posicion, el juego es para dos jugadores y es por turnos"<<endl;
		cout<<"-----------------------------------------------------"<<endl;
		main();
}
void jugar(){
	
	system("cls");
	gato();
	multiplicar();
	ganador();
	
	if(resultado==0){
	switch(turno){		
		case 1:			
			jugador1();
			break;			
		case 2:
			jugador2();		
    	}
    }
    if(resultado==1){   	
    	system("cls");
    	cout<<"-----------------el ganador es el jugador 1-----------------"<<endl<<endl;
        abort();
	}
    if(resultado==2){   	
    	system("cls");
    	cout<<"-----------------el ganador es el jugador 2-----------------"<<endl<<endl;
    	abort();
	}
	if(resultado==3){
		system("cls");
		cout<<"---------------------------------El juego termino en empate---------------------------------"<<endl<<endl;
		abort();
	}
	
}
void multiplicar(){	
	//filas
	f1=(tablero[0][0]*tablero[0][1]*tablero[0][2]);
	f2=(tablero[1][0]*tablero[1][1]*tablero[1][2]);
	f3=(tablero[2][0]*tablero[2][1]*tablero[2][2]);
	//columnas
	c1=(tablero[0][0]*tablero[1][0]*tablero[2][0]);
	c2=(tablero[0][1]*tablero[1][1]*tablero[2][1]);
	c3=(tablero[0][2]*tablero[1][2]*tablero[2][2]);
	//diagonales
	d1=(tablero[0][0]*tablero[1][1]*tablero[2][2]);
	d2=(tablero[0][2]*tablero[1][1]*tablero[2][0]);	
}
void gato(){	
	cout<<endl;
	cout<<"                   "<<tablero[2][0]<<"|"<<tablero[2][1]<<"|"<<tablero[2][2]<<endl;
	cout<<"                  --------"<<endl;
	cout<<"                   "<<tablero[1][0]<<"|"<<tablero[1][1]<<"|"<<tablero[1][2]<<endl;
	cout<<"                  --------"<<endl;
	cout<<"                   "<<tablero[0][0]<<"|"<<tablero[0][1]<<"|"<<tablero[0][2]<<endl<<endl;		
}
void jugador1(){
	
	cout<<"Jugador 1, Digite la posicion de su ficha: ";cin>>p1;
	opcionjugador();
	
	
}
void jugador2(){
	
	cout<<"Jugador 2, Digite la posicion de su ficha: ";cin>>p2;
	opcionjugador();	
	
}
void opcionjugador(){	
    switch(turno){
    	case 1:
    		switch(p1){
                	case 1:
                		x=0;
                		y=0;
                		formula1();
                		break;
    	            case 2:
                		x=0;
                		y=1;
                		formula1();
                		break;    	            	
    	            case 3:
                		x=0;
                		y=2;
                		formula1();
                		break;    	            	
    	            case 4:
                		x=1;
                		y=0;
                		formula1();
                		break;    	            	
    	            case 5:
                		x=1;
                		y=1;
                		formula1();
                		break;    	            	
                	case 6:
                		x=1;
                		y=2;
                		formula1();
                		break;                		
    	            case 7:
                		x=2;
                		y=0;
                		formula1();
                		break;    	            	
    	            case 8:
                		x=2;
                		y=1;
                		formula1();
                		break;    	            	
    	            case 9:	
                		x=2;
                		y=2;
                		formula1();
                		break;							
			}
    	case 2:
    		switch(p2){
                	case 1:
                		x=0;
                		y=0;
                		formula2();
                		break;
    	            case 2:
                		x=0;
                		y=1;
                		formula2();
                		break;    	            	
    	            case 3:
                		x=0;
                		y=2;
                		formula2();
                		break;    	            	
    	            case 4:
                		x=1;
                		y=0;
                		formula2();
                		break;    	            	
    	            case 5:
                		x=1;
                		y=1;
                		formula2();
                		break;    	            	
                	case 6:
                		x=1;
                		y=2;
                		formula2();
                		break;                		
    	            case 7:
                		x=2;
                		y=0;
                		formula2();
                		break;    	            	
    	            case 8:
                		x=2;
                		y=1;
                		formula2();
                		break;    	            	
    	            case 9:	
                		x=2;
                		y=2;
                		formula2();
                		break;							
			}			 
}
}
void formula1(){	
			if(tablero[x][y]==1||tablero[x][y]==2){
				system("cls");
				cout<<"--------------La casilla solicitada ya esta en uso--------------"<<endl<<endl;
				jugador1();
			}
			else{
                tablero[x][y]=1;
                turno=2;
                jugar();
			}		
}
void formula2(){

			if(tablero[x][y]==1||tablero[x][y]==2){
				system("cls");
				cout<<"--------------La casilla solicitada ya esta en uso--------------"<<endl<<endl;
				jugador2();
			}
			else{
                tablero[x][y]=2;
                turno=1;
                jugar();
			}			
}
void ganador(){
	if(f1==1 or f2==1 or f3==1 or c1==1 or c2==1 or c3==1 or d1==1 or d2==1){
		resultado=1;
	}
	if(f1==8 or f2==8 or f3==8 or c1==8 or c2==8 or c3==8 or d1==8 or d2==8){
		resultado=2;
	}
	if(f1!=0 and f2!=0 and f3!=0 and c1!=0 and c2!=0 and c3!=0 and d1!=0 and d2!=0){
		resultado=3;
	}
}
