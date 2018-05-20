# personaldata.h
#ifndef PERSONALDATA_H_INCLUDED
#define PERSONALDATA_H_INCLUDED

/*** Cabeceras del sistema ***/
#include <iostream>
#include <stdio.h>

/*** Cabeceras locales ***/
#include "name.h"
#include "address.h"
#include "economicdependent.h"
#include "listexception.h"

class PersonalData{
    private:
        Name name;                  ///Nombre completo
        Address address;            ///Domicilio
        std::string tel;            ///telefono
        std::string email;          ///Correo electrónico
        std::string status;         ///Estado civil
        std::string curp;           ///Curp
        EconomicDependent family[10];   ///Familiares dependientes económicos
        int cont;                       ///Conteo de familiares registrados

    public:
        PersonalData();         ///Constructor base

        /*** getters ***/
        Name getName();
        Address getAddress();
        std::string getTelphone();
        std::string getEmail();
        std::string getStatus();
        std::string getCurp();

        /*** setters ***/
        void setName(Name& );
        void setAddress (Address&);
        void setTelphone(std::string& );
        void setEmail(std::string& );
        void setStatus(std::string& );
        void setCurp(std::string& );

        std::string toStringData();

        /*** EconomicDependents ***/
        bool isEmpty();
        bool isFull();
        void insertData(int& ,Name&, int&);     ///Recibe (posición en el arreglo, Nombre, edad)
        void deleteData(int& );     ///Recibe (posción en el arreglo)

        int getLastPos();
        int getFirstPos();

        EconomicDependent retrieve(const int&);     ///Recibe (posición) - Retorna (objeto)
        bool findData(Name&);   ///Recibe(nombre) - retorna(bandera) [busca un dato]
        std::string toStringDependents();        ///Imprime lista
};


#endif // PERSONALDATA_H_INCLUDED
