# DakiPraKi - Tradutor Online

Um serviço de tradução simultânea entre **Português (Moçambique)** e **Xichangana (Moçambique)**. Funciona integralmente no navegador, utilizando a *Web Speech API* para _Live Caption_ e Text-To-Speech.

## 🚀 Como Executar Localmente

### Pré-requisitos
Para abrir a plataforma corretamente (devido aos módulos ES6 no JavaScript e às APIs do navegador), o painel deve ser aberto através de um **Servidor Local (Localhost)** e não diretamente pelo protocolo `file://`.

**Formas fáceis de correr:**
1. **VS Code**: Instale a extensão "Live Server" e clique em "Go Live".
2. **Node.js**: Corra o comando `npx serve` no terminal desta pasta.
3. **Python**: Corra o comando `python -m http.server 8000` no terminal desta pasta.

## 📂 Estrutura do Projeto

Nesta reformulação, a base de código foi dividida em vários ficheiros escaláveis:

- `index.html` → Marcação principal, NavBar e interface lado-a-lado.
- `css/style.css` → Todos os estilos e temas (*Apple Inspired Liquid Glass*).
- `js/dictionary.js` → Apenas o motor de dados (a base de palavras e a função de serialização do mapa).
- `js/app.js` → A classe JavaScript principal (`DakiPraKiApp`) que contém:
  - Lógica de _Live Caption_ (microfone).
  - Lógica de tradução ao-vivo.
  - Lógica Text-to-Speech (Altifalante).

## 🛠 Como Contribuir (Adicionar Traduções)

Para um programador ou tradutor adicionar palavras ou frases ao sistema, siga este passo:

1. Abra o ficheiro `/js/dictionary.js`.
2. Localize a array `DICT` no topo do ficheiro.
3. Insira o par de tradução usando o formato:
   ```js
   { ch: "palavra em xichangana", pt: "palavra em portugues" }
   ```
4. **Nota:** Letras minúsculas e maiúsculas não importam, o motor no `app.js` normaliza as palavras e deteta correspondências longas (frases) de forma "gulosa".

## 🚀 Como Atualizar / Partilhar via GitHub

1. Faça Git add, commit e push da sua `main` origin:
```bash
git add .
git commit -m "Nova melhoria do DakiPraKi"
git push origin main
```
2. Recomenda-se acionar o **GitHub Pages** (Settings > Pages > Branch: Main) para o seu repositório criar o link partilhável de forma automática (Ex: `https://[seu-user].github.io/dakipraki`).

Desenvolvido orgulhosamente pela **thynkOS**.
