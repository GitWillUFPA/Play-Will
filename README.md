# Play-Will
Repositório criado para atividades de Programação II
Código em C++

```bash
#include <iostream>
#include <string>
#include <vector>

class Jogo {
private:
    std::string titulo;
    std::string genero;
    int classificacaoEtaria;
    const int constante = 10;
    static int contadorInstancias;
    static int contadorJogadas;
    static const std::vector<std::string> mensagens;

public:
    Jogo() : titulo(""), genero(""), classificacaoEtaria(0) {
        contadorInstancias++;
    }

    Jogo(const Jogo& outro) : titulo(outro.titulo), genero(outro.genero), classificacaoEtaria(outro.classificacaoEtaria) {
        contadorInstancias++;
    }

    Jogo(const std::string& titulo, const std::string& genero, int classificacaoEtaria)
        : titulo(titulo), genero(genero), classificacaoEtaria(classificacaoEtaria) {
        contadorInstancias++;
    }

    std::string getTitulo() const {
        return titulo;
    }

    void setTitulo(const std::string& novoTitulo) {
        titulo = novoTitulo;
    }

    std::string getGenero() const {
        return genero;
    }

    void setGenero(const std::string& novoGenero) {
        genero = novoGenero;
    }

    int getClassificacaoEtaria() const {
        return classificacaoEtaria;
    }

    void setClassificacaoEtaria(int novaClassificacaoEtaria) {
        classificacaoEtaria = novaClassificacaoEtaria;
    }

    void metodoNaoConst() {
        std::cout << "Método não constante chamado." << std::endl;
    }

    void metodoConst() const {
        std::cout << "Método constante chamado." << std::endl;
    }

    void mostrarInformacoes() const {
        std::cout << "Título: " << titulo << std::endl;
        std::cout << "Gênero: " << genero << std::endl;
        std::cout << "Classificação Etária: " << classificacaoEtaria << std::endl;
    }

    void jogar() {
        std::cout << "Jogando o jogo..." << std::endl;
        contadorJogadas++;
    }

    void metodoInLine() {
        std::cout << "Método inline chamado." << std::endl;
    }

    void loopFor() {
        std::cout << "Loop for de 0 a 10:" << std::endl;
        for (int i = 0; i < 10; i++) {
            std::cout << i << std::endl;
        }
    }

    void loopWhile() {
        std::cout << "Loop while de 0 a 10:" << std::endl;
        int i = 0;
        while (i < 10) {
            std::cout << i << std::endl;
            i++;
        }
    }

    static void mostrarMensagem() {
        std::cout << "Mensagem estática: " << mensagens[0] << std::endl;
    }
};

int Jogo::contadorInstancias = 0;
int Jogo::contadorJogadas = 0;
const std::vector<std::string> Jogo::mensagens = {"Bem-vindo ao jogo!"};

int main() {
    Jogo jogo1("Jogo A", "Ação", 12);
    jogo1.mostrarInformacoes();
    jogo1.jogar();

    Jogo::mostrarMensagem();

    jogo1.metodoNaoConst();
    jogo1.metodoConst();
    jogo1.loopFor();
    jogo1.loopWhile();
    jogo1.metodoInLine();

    std::cout << "Título atual: " << jogo1.getTitulo() << std::endl;
    jogo1.setTitulo("Novo Título");
    std::cout << "Novo título: " << jogo1.getTitulo() << std::endl;

    std::cout << "Gênero atual: " << jogo1.getGenero() << std::endl;
    jogo1.setGenero("RPG");
    std::cout << "Novo gênero: " << jogo1.getGenero() << std::endl;

    std::cout << "Classificação etária atual: " << jogo1.getClassificacaoEtaria() << std::endl;
    jogo1.setClassificacaoEtaria(15);
    std::cout << "Nova classificação etária: " << jogo1.getClassificacaoEtaria() << std::endl;

    return 0;
}
