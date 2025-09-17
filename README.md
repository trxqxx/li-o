#include <iostream>
#include <vector>
#include <map>
#include <string>
using namespace std;

class ContaSalario {
public:
    string nome;
    string setor;
    double salario;

    ContaSalario(string n, string s, double sal) {
        nome = n;
        setor = s;
        salario = sal;
    }
};

int main() {
    // Criando lista de 15 objetos
    vector<ContaSalario> lista = {
        ContaSalario("Ana", "TI", 4500),
        ContaSalario("Bruno", "TI", 5200),
        ContaSalario("Carla", "RH", 3800),
        ContaSalario("Diego", "RH", 4000),
        ContaSalario("Eduardo", "Financeiro", 6000),
        ContaSalario("Fernanda", "Financeiro", 5500),
        ContaSalario("Gabriel", "TI", 4700),
        ContaSalario("Helena", "RH", 4100),
        ContaSalario("Igor", "Financeiro", 5900),
        ContaSalario("Joana", "TI", 4800),
        ContaSalario("Kleber", "Financeiro", 6200),
        ContaSalario("Larissa", "RH", 3900),
        ContaSalario("Marcos", "Financeiro", 6100),
        ContaSalario("Natália", "TI", 5300),
        ContaSalario("Otávio", "RH", 3700)
    };

    map<string, double> somaPorSetor;
    map<string, int> qtdPorSetor;
    double somaTotal = 0;

    // Processando dados
    for (auto &c : lista) {
        somaPorSetor[c.setor] += c.salario;
        qtdPorSetor[c.setor]++;
        somaTotal += c.salario;
    }

    // Exibir soma por setor
    cout << "Soma dos salários por setor:\n";
    for (auto &p : somaPorSetor) {
        cout << p.first << ": " << p.second << endl;
    }

    // Exibir média por setor
    cout << "\nMédia dos salários por setor:\n";
    for (auto &p : somaPorSetor) {
        double media = p.second / qtdPorSetor[p.first];
        cout << p.first << ": " << media << endl;
    }

    // Soma total
    cout << "\nSoma total de todos os salários: " << somaTotal << endl;

    return 0;
}
