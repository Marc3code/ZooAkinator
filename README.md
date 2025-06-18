# ZooAkinator
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
    git clone https://github.com/seu-usuario/seu-repositorio.git
    ```
2.  Navegue até a pasta do projeto:
    ```bash
    cd seu-repositorio
    ```
3.  Abra o arquivo `index.html` diretamente em seu navegador de preferência.

## 🔮 Atualizações Futuras e Roteiro de Evolução

O objetivo é transformar este projeto de uma experiência local e individual para uma plataforma web colaborativa e inteligente.

### 1. Disponibilização Online e Banco de Dados Centralizado

A próxima grande etapa é mover a base de conhecimento de `localStorage` para um banco de dados na nuvem. Isso permitirá que o conhecimento adquirido por um jogador beneficie todos os outros, criando uma **inteligência coletiva** que cresce com o tempo.

* **Plano de Ação:**
    1.  **Deploy da Aplicação:** Hospedar o front-end em uma plataforma como **Vercel**, **Netlify** ou **GitHub Pages**.
    2.  **Criação de uma API Backend:** Desenvolver um backend simples (ex: com Node.js e Express) que servirá como intermediário entre o front-end e o banco de dados.
    3.  **Migração para Banco de Dados Online:**
        * **Tecnologia Recomendada:** Um banco de dados NoSQL como o **MongoDB** (utilizando o serviço em nuvem **MongoDB Atlas**) é a escolha ideal para este caso. Sua natureza baseada em documentos permite armazenar a estrutura aninhada da árvore de conhecimento (JSON) de forma nativa e eficiente, facilitando a leitura e a atualização de ramos específicos.

### 2. Moderação de Conteúdo com LLMs

Com um banco de dados público e colaborativo, surge o desafio de garantir a qualidade e a integridade dos dados inseridos pelos usuários. Respostas inadequadas, ofensivas ou sem sentido poderiam corromper a base de conhecimento.

* **Plano de Ação:**
    1.  **Implementação de um Gateway de Validação:** Antes que uma nova pergunta ou animal seja salvo no banco de dados, a API de backend enviará os dados para um modelo de linguagem grande (LLM) para validação.
    2.  **Modelo a Ser Utilizado:** A API do **Google Gemini** ou do **OpenAI (GPT)** pode ser integrada para realizar as seguintes verificações automáticas:
        * **Análise de Coerência:** O LLM verificará se a pergunta e a resposta são lógicas dentro do contexto de um jogo sobre animais. (Ex: A pergunta "Ele tem um chifre no nariz?" para o animal "Rinoceronte" é coerente).
        * **Verificação Ética e de Segurança:** O modelo analisará o texto para identificar e bloquear conteúdo impróprio, ofensivo, discurso de ódio ou qualquer informação que viole as diretrizes de segurança.

A implementação dessas duas atualizações transformará o projeto em uma aplicação web robusta, escalável e segura, onde uma comunidade de usuários pode, de forma colaborativa, "ensinar" uma IA de maneira divertida e construtiva.

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
