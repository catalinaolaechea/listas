# listas
#include <iostream>

using namespace std;
/*Realice un procedimiento o función que al recibir dos listas como parámetro, devuelva
una tercer lista que concatene las mismas.*/
struct nodoListas
{
    int info;
    nodoListas*sig;

};
void agregarDelante(nodoListas*&Lista,int dato)
{
    nodoListas*nuevo=new nodoListas();
    nuevo->info=dato;
    nuevo->sig=Lista;
    Lista=nuevo;
}
void recorrerLista(nodoListas*Lista1)
{
    nodoListas*aux;
    aux=Lista1;
    while(aux!= NULL)
    {
        cout<<aux->info<<endl;
        aux=aux->sig;
    }
}
void juntarListas(nodoListas*&Lista3,nodoListas*Lista)
{
    int dato;
    nodoListas*aux;
    aux=Lista;
    while(aux!=NULL)
    {
        dato=aux->info;
        agregarDelante(Lista3,dato);
        aux=aux->sig;
    }
}
int main()
{
    nodoListas*Lista1=NULL;
    nodoListas*Lista2=NULL;
    nodoListas*Lista3=NULL;
    agregarDelante(Lista1,5);
    agregarDelante(Lista1,6);
    agregarDelante(Lista1,99);
    agregarDelante(Lista2,3);
    agregarDelante(Lista2,7);
    agregarDelante(Lista2,44);
    cout<<"unificar listas"<<endl;
    juntarListas(Lista3,Lista2);
    juntarListas(Lista3,Lista1);
    recorrerLista(Lista3);
    return 0;
}
