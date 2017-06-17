OOP Basics
===========

De ce OOP?
----------

- Cod mai usor de dezvoltat
- Usor de modificat cand vrem sa adaugam un nou feature
- Pentru modularitate
- Pentru proprietati ca mosternirea si polimorfismul care permit reutilizarea codului
- Pentru specificatorii de acces care limiteaza utilizarea anumitor metode si variabile 
- Paradigma moderna de programare, folosita worldwide

Clase vs Instante
-----------------

Clasele sunt scheletele care contin modelarea si comportamentul care va fi preluat de catre instante.

Instantele (numite si obiecte) sunt niste variabile care au comportamentul definit in clasa respectiva.

Exemplu de clasa:

public class Test {
    public int x;
    public int y;

}

Exemplu de instanta:

Test obiect_1 = new Test();

Functii vs Metode
-----------------

Functiile actioneaza la fel ca cele din alte limbaje. In programarea orientata pe obiecte notiunea de functie
a fost "inlocuita" cu cea de metoda. Asadar, o metoda este o functie care se afla in interiorul unei clase si lucreaza cu datele specificate de utilizator.

Exemplu:

public class Test {

    public void printText {
        System.out.println("Printeaza acest text"); // Echivalentul a "cout" din C++ 
 
   }

}

Aici printText este o metoda deoarece se afla in interiorul clasei Test

Constructor 
-----------

Constructorul este o metoda care se apeleaza la instantierea unui obiect (la apelarea keywordului new). Daca nu definim noi unul, compilatorul ne va face unul default, care in Java initializeaza toate campurile cu valorile lor default (pentru int/float este 0, pentru String este 'null', etc).

Pentru a defini un constructor, nu ii vom pune tip de return si acesta va avea numele clasei:

public class Test {
    public Test {
         System.out.println("Instantiem un nou obiect");
    
    }

}

La crearea unui obiect al clasei Test in main, output-ul ar fi:
"Instantiem un nou obiect".

Practic, in interiorul unui constructor ne putem stabili niste valori sau un comportament initial.

Keyword-ul "this"
-----------------

Keywordul "this" este o referinta la instanta curenta. Cu alte cuvinte, daca am avea si un camp "x" in clasa, si un parametru "x" in metoda:

public class Test {
    private int x;
    
    public void printX(int x) {

         System.out.println(x); // afiseaza pe "x" parametrul metodei printX 
         System.out.println(this->x); // afiseaza pe "x" dinauntrul clasei
    
    }

}

Nota: Keyword-ul "this" poate accesa si variabilele private ale clasei.

Metoda main
-----------

Pentru a rula codul, in Java efectiv rulam o clasa (click-dreapta pe un fisier si apoi Run) si acesta va apela metoda main din interiorul clasei sale. Doar clasele cu metoda main definita pot fi rulate.

Semnatura este: public static void main(String[] args) {}. 

Un cod complet cu noile notiuni ar fi:

public class Test {
    private int x; private int y;

    public Test(int x, int y) {
        this.x = x; 
        this.y = y; // setam x si y din clasa sa fie cei dati ca parametru 
   
    }

    public void showXY() {
        System.out.println("x este: " + this.x + ", iar y: " + this.y); // "+" concateneaza doua stringuri
    
    }

    public static void main(String[] args) {
        Test a = new Test(5, 7);
        a.showXY(); // "x este: 5, iar y: 7"
    
    }

}

Reguli de sintaxa si coding style in Java:

- Fiecare clasa va fi creata in fisier separat altfel programul nu va compila
- Numele clase incepe cu litera mare (se recomanda a fi un substantiv)
- Numele metodei incepe cu literea mica iar daca este format din mai multe cuvinte restul incep cu litera mare
- Variabilele respecta aceleasi reguli ca metodele
- Numele constantelor se scrie cu majuscule
