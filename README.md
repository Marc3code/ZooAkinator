# ZooAkinator

Grupo: 

Marcos Bernardino de Sousa Terceiro

João Marcelo Nunes de Souza

Igor Dias Anisio

João Augusto Silva Nolasco

Erica Kathlen de Andrade dos Santos

Marlos Emanuel da Silveira Fontes

-----------------------------------------------------------------------------

Um jogo de adivinhação de animais com uma IA simples que aprende com o jogador. Quando erra, o sistema pede a resposta correta e uma nova pergunta para expandir sua base de conhecimento, que fica salva no navegador.

# 🌳 Jogo de Adivinhação de Animais com IA de Autoaprendizagem

Este projeto é uma aplicação web interativa de um "gênio" que tenta adivinhar o animal em que o usuário está pensando. A sua principal característica é a capacidade de **aprender com os próprios erros**, utilizando uma árvore de decisão binária como base de conhecimento que se expande a cada rodada perdida.

Quando a IA falha em sua adivinhação, ela solicita ao usuário o animal correto e uma nova pergunta que diferencie esse animal do palpite errado. Com essa informação, a IA reestrutura sua árvore de conhecimento, tornando-se mais inteligente e robusta.

## ✨ Recursos Atuais

* **IA com Autoaprendizagem:** O jogo expande sua base de conhecimento dinamicamente. Cada vez que perde, ele aprende um novo animal e uma nova característica.
* **Árvore de Decisão Dinâmica:** A lógica central é baseada em uma estrutura de árvore de perguntas e respostas. A IA navega por essa árvore para chegar a uma conclusão.
* **Persistência de Dados Local:** O conhecimento adquirido é salvo no `localStorage` do navegador. Isso garante que o progresso da IA não seja perdido ao fechar e reabrir a página.
* **Interface Responsiva e Moderna:** A interface foi criada com foco na experiência do usuário, utilizando CSS moderno para se adaptar a diferentes tamanhos de tela.
* **Base de Conhecimento Inicial:** O jogo já começa com uma árvore de conhecimento considerável, tornando a experiência inicial rica e desafiadora.
* **Zero Dependências:** O projeto é construído inteiramente com **HTML, CSS e JavaScript puros (vanilla)**, sem a necessidade de frameworks ou bibliotecas externas.

## ⚙️ Como a Lógica Funciona

1.  A IA percorre a árvore de conhecimento fazendo perguntas de "sim" ou "não".
2.  Com base nas respostas do usuário, ela navega para o próximo nó da árvore.
3.  Este processo continua até que a IA chegue a um nó final (uma folha), que representa um palpite de animal.
4.  **Se o palpite estiver correto**, a IA vence a rodada.
5.  **Se o palpite estiver errado**, o processo de aprendizagem é ativado:
    a.  A IA pergunta: "Qual animal você pensou?".
    b.  Em seguida, ela pergunta: "O que um(a) `[animal do usuário]` tem que um(a) `[palpite errado da IA]` não tem?".
    c.  Com base na nova pergunta e no novo animal, a IA substitui o nó do palpite errado por um novo nó de pergunta, reorganizando a árvore para incluir o novo conhecimento.
6.  A árvore de conhecimento atualizada é salva no `localStorage`, pronta para futuras partidas.

## 💻 Tecnologias Utilizadas

* **HTML5:** Estrutura semântica da página.
* **CSS3:** Estilização, responsividade e design.
* **JavaScript (ES6+):** Lógica do jogo, manipulação do DOM e interação com o `localStorage`.

## 🚀 Como Executar Localmente

Como este é um projeto front-end autocontido, não há necessidade de instalação ou build.

1.  Clone este repositório:
    ```bash
    git clone https://github.com/Marc3code/ZooAkinator.git
    ```
2.  Navegue até a pasta do projeto:
    ```bash
    cd ZooAkinator
    ```
3.  Abra o arquivo `index.html` diretamente em seu navegador de preferência.

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
