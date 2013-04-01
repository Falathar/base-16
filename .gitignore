#include <iostream>
#include <algorithm> // for std:find
#include <vector>
#include <stdlib.h>
#include <stdio.h>

#include <string.h>
#include <sstream>
#include <math.h>



// cas tests
// valeur hexa entree => valeur hexa attendue
// 0 => 0
// 1 => 1
// ..
// 5 => 5
// ..
// f => 15
// g => erreur
// F => 15

// OO => 0
// 01 => 1
// 1e => 30

//7ffffff => 2147483647(limte de int )
//80000000 => boucle le nombre devient negatif

using namespace std;

int main(int argc, const char * argv[])
{
    // parameters:
    std::string mystring;
    std::string lastchar="";
    int nb=0,k=0;
    char choix ='z';
    std::string hexa;
    
    // create vector:
std:vector<string> listHexaValues(16);
    listHexaValues[0]="0";
    listHexaValues[1]="1";
    listHexaValues[2]="2";
    listHexaValues[3]="3";
    listHexaValues[4]="4";
    listHexaValues[5]="5";
    listHexaValues[6]="6";
    listHexaValues[7]="7";
    listHexaValues[8]="8";
    listHexaValues[9]="9";
    listHexaValues[10]="a";
    listHexaValues[11]="b";
    listHexaValues[12]="c";
    listHexaValues[13]="d";
    listHexaValues[14]="e";
    listHexaValues[15]="f";
    
    printf("Bienvenue dans le convertisseur base 16 <-> base 10\n" );
    
    // loop until 'Q' or 'q' key pressed.
    while (choix != 'Q' && choix!= 'q')
    {
        cout<<" ****** Menu ******\n";
        cout<<" Veuillez effectuer l'un deux choix suivants:\n";
        cout<<" 1- Convertion d'un entier en hexadecimal\n";
        cout<<" 2- Convertion d'un hexadecimal en entier\n";
        cout<<" q- Appuyez sur 'q' ou 'Q' pour quitter\n";
        cout<<" ******************\n";
        
        // read user choice:
        std::cout <<"\nVotre choix : ";
        std::cin >> choix;
        
        if (choix == '1')
        { // user asked for choice 1 (base 10 -> base 16)
            hexa="" ; // clean hexa value.
            cout<<" Entrez un entier : ";
            cin>>nb;
            
            while (nb !=0)
            {
                // concat string
                hexa = listHexaValues[nb%16]+hexa ;
                
                // next :
                nb = nb/16;
            }
            if(hexa.length()==0)
            { // if hexa is empty
                hexa="0";
            }
            // display result:
            std::cout<<" convertion en hexa =  "<<hexa<<"\n\n";
        } // endif choice-1
        else if(choix=='2')
        {  // user asked for choice 2 (base 16 -> base 10)
            bool isOk = false;
            nb = 0;
            k=0;
            std::cout << " Entrez une valeur en hexadecimal:";
            std::cin >> mystring;
            while(mystring.length()>0)
            { // while char exists in mystring
                lastchar = mystring.substr(mystring.length()-1,1);
                mystring = mystring.substr(0,mystring.length()-1);
                
                // convert string (i.e. lastchar) to int value.
                int vallastchar=0;
                for(int index=0; index<listHexaValues.size();index++)
                {
                    if (strcasecmp(lastchar.c_str(),listHexaValues[index].c_str()) == 0)
                    {
                        vallastchar=index;
                        isOk = true;
                        break;
                    }
                }
                if(!isOk)
                {
                    std::cout << " Erreur caractere non reconnu :"+lastchar+"\n";
                    break;
                }
                
                nb=nb+vallastchar * pow (16,k);
                k=k+1;
            }// while (mystring.length()>0)
            if(isOk)
            { // only write convertion result if all char are valid.
                std::cout<<"\nConvertion en base 10 = "<<nb<<"\n";
            }
        } // endif choice-2
    } //  while (choix != 'Q' && choix!= 'q')
    
    
    return 0;
    
}
