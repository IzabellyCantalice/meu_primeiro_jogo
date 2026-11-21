# 🚀 Coletor Espacial 2D

Bem-vindo à documentação oficial do projeto **Coletor Espacial 2D**! Este é um jogo casual em 2D desenvolvido para ser executado diretamente em navegadores web modernos, tanto em computadores quanto em dispositivos móveis (smartphones e tablets), empacotado em um arquivo único e autossuficiente (`index.html`).

---

## 📌 1. Visão Geral do Projeto

O objetivo do jogador é controlar uma pequena nave espacial na parte inferior da tela, desviando de meteoros incandescentes enquanto coleta esferas de energia cósmica para acumular pontos e avançar de fase.

### 🕹️ Principais Mecânicas e Funcionalidades
- **Nave Espacial:** Movimentação lateral rápida, responsiva e com feedback visual de propulsores de plasma.
- **Esferas de Energia (Verdes/Azuis):** Caem do topo e concedem **+10 pontos** a cada coleta com efeitos de partículas.
- **Meteoros Flamejantes (Vermelhos/Laranjas):** Rocha espacial com rastro de fogo. Reduz **1 coração de vida** caso colida com o jogador (o jogador inicia com 3 vidas).
- **Progressão de Dificuldade:** A cada 100 pontos acumulados, o jogador sobe de fase (*Fase 1, Fase 2, Fase 3...*), aumentando gradualmente a velocidade de queda e a frequência dos objetos.
- **Persistência de Recorde:** O recorde máximo de pontuação (High Score) é salvo automaticamente no navegador do usuário via `localStorage`.
- **Efeitos Sonoros Integrados:** Efeitos sonoros gerados dinamicamente via síntese de áudio, sem necessidade de arquivos externos de áudio (MP3/WAV).
- **Controles Híbridos:**
  - **Desktop:** Setas do teclado (`◀` e `▶`) ou teclas `A` e `D`.
  - **Mobile:** Botões de toque dedicados na tela OU controle por toque/arraste direto no Canvas.

---

## 💻 2. Tecnologias e Linguagens Utilizadas

O projeto foi construído utilizando os pilares clássicos da web moderna de forma leve e sem dependências pesadas de compilação:

| Tecnologia / Recurso | Tipo | Finalidade no Projeto |
| :--- | :--- | :--- |
| **HTML5** | Linguagem de Marcação | Estrutura semântica da aplicação, viewport responsivo e elemento `<canvas>` para a renderização gráfica 2D. |
| **JavaScript (ES6+)** | Linguagem de Programação | Motor do jogo (Game Loop), física simples, sistema de colisão (AABB), geração procedural de itens, partículas e persistência de dados. |
| **HTML5 Canvas API** | API Gráfica | Renderização vetorial em tempo real (60 FPS) da nave, meteoros, esferas de energia, partículas de explosão e estrelas cintilantes de fundo. |
| **Tailwind CSS (v3 via CDN)** | Framework CSS Utilitário | Estilização dos menus, painéis de HUD (placar, vidas, fase), botões com efeitos neon, sombras e design adaptável (mobile-first). |
| **Web Audio API** | API de Áudio Nativa | Síntese de frequências e osciladores em tempo real para os efeitos sonoros (moeda, impacto, fanfarra de fase e game over), funcionando 100% offline. |
| **LocalStorage Web API** | Armazenamento no Navegador | Salvamento e recuperação persistente do recorde de pontuação do jogador. |
| **Google Fonts (Fredoka)** | Tipografia Web | Fonte arredondada com estilo visual moderno e arcade para melhorar a legibilidade e identidade visual. |

---

## 🛠️ 3. Telas do Jogo

1. **Tela Inicial (Menu):**
   - Título estilizado em gradiente neon.
   - Ícone animado da nave espacial.
   - Resumo das regras e valor dos itens.
   - Exibição do Recorde Atual gravado.
   - Botão de ação em destaque: `JOGAR AGORA`.

2. **Interface Durante a Partida (HUD):**
   - Indicador de 3 Vidas (`❤️`).
   - Indicador da Fase atual (`Fase 1`, `Fase 2`, etc.).
   - Recorde no topo.
   - Marcador grande de Pontuação.
   - Meta dinâmica de pontuação para a próxima fase.
   - Banner comemorativo de transição de fase com animação e som.

3. **Tela de Fim de Jogo (Game Over):**
   - Notificação visual de nave destruída.
   - Resumo com Pontuação Final e Fase Alcançada.
   - Exibição do Recorde e selo especial animado `Novo Recorde Pessoal!` caso o recorde seja superado.
   - Botão de reinício rápido: `JOGAR DE NOVO`.

---

## 📋 4. Histórico de Mudanças e Atualizações (Changelog)

### [Versão 1.0.0] - Lançamento Inicial
- **Design e Fundo Espacial:**
  - Criação do fundo espacial escuro com nebulosas em gradiente radial.
  - Adição de 65 estrelas procedurais com velocidades e brilhos cintilantes independentes.
- **Entidade do Jogador:**
  - Criação da nave estilizada em degradê azul-ciano, cabine de vidro reflexiva, canhões e propulsor traseiro animado.
  - Implementação de limites de tela (evita sair das bordas).
  - Adição de sistema de invulnerabilidade temporária (efeito de piscar) após sofrer dano de meteoro.
- **Geração e Lógica de Itens:**
  - Implementação de Esferas de Energia (+10 pontos) com gradientes e efeito pulsar.
  - Implementação de Meteoros com detalhes de crateras e cauda de chamas.
  - Algoritmo de colisão retangular proporcional (AABB refinado).
- **Sistema de Fases e Balanceamento:**
  - Progressão a cada 100 pontos acumulados.
  - Aumento dinâmico da velocidade de queda dos objetos e frequência de surgimento.
  - Alerta animado central de `NOVA FASE! 🚀`.
- **Efeitos de Áudio (Web Audio API):**
  - Efeito sonoro de coleta de esfera (onda senoidal harmônica).
  - Efeito sonoro de colisão/dano (onda dente de serra de frequência descendente).
  - Fanfarra musical para transição de fases.
  - Efeito sonoro melancólico para Game Over.
- **Controles Multiplataforma:**
  - Suporte completo a teclado (`Setas` e `A/D`).
  - Botões touch na parte inferior (`ESQUERDA` / `DIREITA`) com suporte a toque contínuo.
  - Suporte a arraste com o dedo na tela do Canvas com interpolação suave de movimento.
- **Persistência de Dados:**
  - Integração com `localStorage` para manter o Recorde gravado entre recarregamentos de página.

---

## 🚀 5. Como Executar o Jogo

Não é necessária nenhuma instalação prévia de bibliotecas, compiladores ou servidores backend:

1. Baixe ou acesse o repositório do projeto.
2. Dê um duplo clique no arquivo [`index.html`](file:///c:/Users/izabe/Documents/GitHub/meu_primeiro_jogo/index.html) para executá-lo diretamente no seu navegador de preferência (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari, Opera, etc.).
3. Para jogar em dispositivos móveis, você pode hospedar o arquivo (por exemplo, no **GitHub Pages**) ou abrir o arquivo HTML diretamente no navegador do seu smartphone.

---

## 👩‍💻 Desenvolvedora

Projeto desenvolvido por **Izzy Soares / Izabelly Cantalice**.


