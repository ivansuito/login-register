# login-register
Simple Register/Login verification with C++




CODE:


#include <iostream>
#include <fstream>
#include <string>
using namespace std;
bool IsLogged() 
{
    string username, password, us, pw;
    cout << "Nombre de usuario: "; cin >> username;
    cout << "Pasword: "; cin >> password;
    ifstream read("/**PATH**/" +  username + ".txt");
    getline(read, us);
    getline(read, pw);<
    if (us == username && pw == password){
        return true;
    } else {
        return false;
    }
}
int main() 
{
    int q1;
    cout << "1)Registrarse.\n2)Iniciar sesion.\nElige: "; cin >> q1;
    if (q1 == 1)
    {
        string username, password;
        cout << "Nombre de usuario: "; cin >> username;
        cout << "Password: "; cin >> password;
        ofstream file;
        file.open("/**PATH**/" + username + ".txt");
        file << username << endl << password; 
        file.close();
        main();
    }
    else if (q1 == 2)
    {
        bool status = IsLogged(); 
        if (!status)
        {
            cout << "No existe esta cuenta." << endl;
            system("PAUSE");
            return 0;
        } else 
        {
            cout << "Has iniciado sesion!" << endl;
            system("PAUSE");
            return 1;
        } 
    }   
}
