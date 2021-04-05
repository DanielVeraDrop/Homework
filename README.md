# Homework
University Homework UCSP(CCOMP2-1)
//|Justin Daniel Vera Paco|
//|Ciencia de la Computación|
//|CCOMP2-1|UCSP
#include <iostream>
#include <string>
#include <stdio.h>
using namespace std;


void espacios(int espacio)//Imprime el espacio entre los "|__" y "__|".
{ 
	for(int i=0; i < espacio;++i){
		cout<<" ";
	}
}

void EscaleraDoble(int altura, int persona){ //Imprime la escalera y la persona en ella.
	int espacio=4, x;
	while(altura > 0){ //Se forma un bucle.
		x=8*(altura-1)+5;
    if(persona==-(altura)){ //Cuando la pesona esté a la derecha.
		  cout<<"|___";
		  espacios(x);
		  cout<<"_P_|";			
		}
		if(persona==altura){ //Cuando la pesona esté a la izquierda.
			cout<<"|_P_";
			espacios(x);
			cout<<"___|";				
		}
    if(persona!=altura&&persona!=-(altura)){ //Cuando la pesona esté en otro escalón.
			cout<<"|___";
			espacios(x);
			cout<<"___|";
		}
		altura--;
		cout<<"\n";
		espacios(espacio);
		espacio+=4;
	}
	if(persona==0){ //(if) Cuando la persona este en el centro y (else) cuando no.
		cout<<"|_P_|";
	}else{
		cout<<"|___|";
	}
}

int main(int argc, char *argv[]) {
	int altura,animacion,escalon;
	cout<<"Ingrese la altura: ";
  cin>>altura;//altura de la escalera.
  cout<<"En que escalon quiere que empiece la animación: ";
  cin>>escalon; //escalon en el que se empezará la animación.
	system("cls");
  animacion=1;
	while(animacion>0){ //crea la animación (si quiere controlar la cantidad de veces de la animación como el "trabajo extra" tiene esta referencia de abajo, pongala encima del system("cls") de la linea 54 sin los 2 slash y borre el "animación=1" para que funcione:D
  //cout<<"Cuantas veces quiere que la persona haga la animación: ";
  //cin>>animacion;
		for(int i=-(escalon) ; i >= -(altura); i--){ //Para subir o bajar escalones de la izquierda
			EscaleraDoble(altura,i);
			cout<<"\n";
			system("pause"); //Pausar la pantalla
			system("cls"); //Borrar la pantalla
		}
		for(int i=(-altura)+1 ; i <= altura; i++){ //Para subir o bajar escalones de la derecha
			EscaleraDoble(altura,i);
			cout<<"\n";
			system("pause");
			system("cls");
		}
		animacion--;
	}
	return 0;
}
//psdt lo hice en replit por lo que no se si el "cls" y el "pause" lo puse de manera correcta, si no es asi disculpe es que formatee mi pc :(.
