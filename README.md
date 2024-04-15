# Play-Will
Repositório criado para atividades de Programação II
Código C++

#include <iostream>
#include <string>

class Jogo {
private:
    std::string titulo, genero;
    int classificacaoEtaria;
    const int constante = 10;
    static int contadorInstancias, contadorJogadas;
    static const std::string mensagens[];

public:
    Jogo() : titulo("Desconhecido"), genero("Desconhecido"), classificacaoEtaria(0) { contadorInstancias++; }
    Jogo(const Jogo& other) : titulo(other.titulo), genero(other.genero), classificacaoEtaria(other.classificacaoEtaria) { contadorInstancias++; }
    Jogo(const std::string& t, const std::string& g, int c) : titulo(t), genero(g), classificacaoEtaria(c) { contadorInstancias++; }
    
    void mostrarInformacoes() const { std::cout << "Titulo: " << titulo << "\nGenero: " << genero << "\nClassificacao Etaria: " << classificacaoEtaria << std::endl; }
    void jogar() { contadorJogadas++; }
    
    std::string getTitulo() const { return titulo; }
    std::string getGenero() const { return genero; }
    int getClassificacaoEtaria() const { return classificacaoEtaria; }
    static int getContadorInstancias() { return contadorInstancias; }
    static int getContadorJogadas() { return contadorJogadas; }

    void setTitulo(const std::string& novoTitulo) { titulo = novoTitulo; }
    void setGenero(const std::string& novoGenero) { genero = novoGenero; }
    void setClassificacaoEtaria(int novaClassificacaoEtaria) { classificacaoEtaria = novaClassificacaoEtaria; }
    
    static void mostrarMensagens() { for (const auto& msg : mensagens) std::cout << msg << std::endl; }
};

int Jogo::contadorInstancias = 0;
int Jogo::contadorJogadas = 0;
const std::string Jogo::mensagens[] = {"Bem-vindo ao jogo!", "Boa sorte!"};

int main() {
    Jogo jogo1;
    jogo1.mostrarInformacoes();
    Jogo jogo2("Aventura", "RPG", 12);
    jogo2.mostrarInformacoes();
    std::cout << "Contador de instâncias: " << Jogo::getContadorInstancias() << "\nContador de jogadas: " << Jogo::getContadorJogadas() << std::endl;
    
    Jogo::mostrarMensagens();

    return 0;
}

