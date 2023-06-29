# work-with-files
Keep data locked in a file. View Data by entering a password. Working with file
/_________________________________________________________________________________/

#include <iostream>
#include <fstream>
using namespace std;

void object(char x) {
    struct person {
        string name;
        int age;
        double weight;
        string password;
        string Login;
    };
    person a;
    fstream Myfile;
    if (x == '1') {
        cout<<"\t Student file \n";
        Myfile.open("StudentNum1.txt", ios::app);
        cout<<"name = "; cin>>a.name;
        cout<<"age = "; cin>>a.age;
        cout<<"weight = "; cin>>a.weight;
        cout<<"Login password = "; cin>>a.Login;
        cout<<"enter the password = "; cin>>a.password;
        Myfile << "\n"<<a.Login << a.password << "\n"
            << a.name << " - name\n"
            << a.age << " - age\n"
            << a.weight << " - weight\n";
        Myfile.close();
    }
    else if(x == '2') {
        cout<<"\t Admin file \n";
        Myfile.open("AdminNum2.txt", ios::app);
        cout<<"name = "; cin>>a.name;
        cout<<"age = "; cin>>a.age;
        cout<<"weight = "; cin>>a.weight;
        cout<<"Login password = "; cin>>a.Login;
        cout<<"enter the password = "; cin>>a.password;
        Myfile << "\n"<<a.Login << a.password << "\n"
            << a.name << " - name\n"
            << a.age << " - age\n"
            << a.weight << " - weight\n";
        Myfile.close();
    }
    else if(x == '3') {
        cout<<"\t Teacher file \n";
        Myfile.open("TeacherNum3.txt", ios::app);
        cout<<"name = "; cin>>a.name;
        cout<<"age = "; cin>>a.age;
        cout<<"weight = "; cin>>a.weight;
        cout<<"Login password = "; cin>>a.Login;
        cout<<"enter the password = "; cin>>a.password;
        Myfile << "\n"<<a.Login << a.password << "\n"
            << a.name << " - namei\n"
            << a.age << " - agei\n"
            << a.weight << " - weight\n";
            Myfile.close();
    }
} void read (string x, string z) {
    string fileNames[] = {"StudentNum1.txt", "AdminNum2.txt", "TeacherNum3.txt"};
    for (int i = 0; i < 3; i++) {
     ifstream Myfile(fileNames[i]);
        string Line;
         while (getline(Myfile, Line)) {
            if (Line == x+z) {
                string line;
                int c = 0;
                while (getline(Myfile, line) && c!=4 ) {
                        c++;
                    cout << line << endl;
                }}
            }
         Myfile.close();
    }
}
int main(){
    char ch,x;
    cout<<"\n______________ PASSWORD ________________\n\n";
    cout<<"\t 1 - Sign up\n";
    cout<<"\t 2 - Login password\n";
    cin>>ch;
    if (ch == '1'){
        cout<<" 1 - Student \n 2 - Admin \n 3 - Teacher \n";
        cin>> x;
        object(x);
    } else if(ch == '2') {
        string login, pass;
        cout<< "Logini kiriting = "; cin>>login;
        cout<< "enter the password = "; cin>>pass;
        read (login, pass);
    } main();
    return 0;
}


/_________________________________________________________________________________/
