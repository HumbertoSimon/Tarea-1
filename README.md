# Tarea-1
Ejercicio introductorio de nodos
 
 # Codigo
 
 public class mainclass 
 {

    public static void main(String[] args) {
       ArbolBinario arbolito = new ArbolBinario();
       ArbolBinario arbolitot = new ArbolBinario();
       
       arbolito.agregarNodo(20, "");
       arbolito.agregarNodo(19, "");
       arbolito.agregarNodo(23, "");
       arbolito.agregarNodo(57, "");
       arbolito.agregarNodo(67, "");
       arbolito.agregarNodo(99, "");
       
       
       arbolitot.agregarNodo(20, "");
       arbolitot.agregarNodo(23, "");
       arbolitot.agregarNodo(57, "");
       
     arbolito.inOrden(arbolito.raiz);
      System.out.println("------------");
     arbolitot.inOrden(arbolitot.raiz);
    }
      
}


public class NodoArbol 
{
    int dato;
    NodoArbol hijoIzquierdo, hijoDerecho;
    String nombre;
    
    public NodoArbol(int d, String nom){
        this.dato=d;
        this.nombre=nom;
        this.hijoDerecho=null;
        this.hijoIzquierdo=null;
    }
   
}

public class ArbolBinario 
{
  NodoArbol raiz;
public ArbolBinario(){
      raiz=null;
}  

public void agregarNodo (int d, String nom){
NodoArbol nuevo = new NodoArbol(d, nom);
if(raiz==null){
raiz=nuevo;
}else{
NodoArbol auxiliar=raiz;
NodoArbol padre;
while(true){
padre=auxiliar;
if(d<auxiliar.dato){
auxiliar=auxiliar.hijoIzquierdo;
if(auxiliar==null){
    padre.hijoIzquierdo=nuevo;
    return;
}
}else{
   auxiliar=auxiliar.hijoDerecho;
   if(auxiliar==null){
       padre.hijoDerecho=nuevo;
       return;
       }
    }
}
}    
}
public void inOrden(NodoArbol r){
    if(r!=null){
    inOrden(r.hijoIzquierdo);
    System.out.println(r.dato);
    inOrden(r.hijoDerecho);
    }
}

}
