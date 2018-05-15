# personaldata.h
///cabecera de la clase para datos personales
#ifndef PERSONALDATA_H_INCLUDED
#define PERSONALDATA_H_INCLUDED

/*** Cabeceras del sistema ***/

/*** Cabeceras locales ***/
#include "name.h"
#include "address.h"
#include "economicdependent.h"

class PersonalData{
    private:
        Name name;                  ///Nombre completo
        Address address;            ///Domicilio
        std::string tel;            ///telefono
        std::string email;          ///Correo electrónico
        std::string status;         ///Estado civil
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
        int getCont();

        /*** setters ***/
        void setName(Name& );
        void setAddress (Address&);
        void setTelphone(std::string& );
        void setEmail(std::string& );
        void setStatus(std::string& );
        void setCont(int& );
};


#endif // PERSONALDATA_H_INCLUDED
