# CHIFFREMENT ET DECHIFFREMENT DE CESAR 

#include <iostream>
#include <string>
using namespace std;

string chiffrementCesar(string message, int decalage) {
    string messageChiffre = "";
    for (int i = 0; i < message.length(); i++) {
        if (isalpha(message[i])) {
            char lettre = isupper(message[i]) ? 'A' : 'a';
            messageChiffre += (message[i] - lettre + decalage) % 26 + lettre;
        } else {
            messageChiffre += message[i];
        }
    }
    return messageChiffre;
}

int main() {
    string message;
    int decalage;
    
    cout << "Entrez le message à chiffrer : ";
    getline(cin, message);
    
    cout << "Entrez le décalage : ";
    cin >> decalage;
    
    string messageChiffre = chiffrementCesar(message, decalage);
    cout << "Message chiffré : " << messageChiffre << endl;
    
    return 0;
}
