# Explorador e Gerador de QR Code

Um projeto educacional desenvolvido para entender como os QR Codes funcionam por dentro, desde a teoria matemática dos módulos e correção de erros até a implementação prática de uma aplicação web interativa, sem depender de APIs externas.

Feito para um trabalho da matéria de Sistemas Web, do curso de Ciência da Computação

## Acesse a Aplicação Online
Você pode testar a ferramenta direto no navegador usando o [GitHub Pages](https://github.com/matheuscjustinog/QRCode)

---

## Como o QR Code Funciona? (O que aprendi construindo isso)

Um QR Code não é apenas um desenho, ele é uma matriz bidimensional estruturada com regras rígidas:
1. **Padrões de Detecção (Finder Patterns):** Os três quadrados nos cantos que dizem à câmera a orientação do código.
2. **Padrões de Temporização (Timing Patterns):** Linhas que calibram o tamanho dos módulos (pixels).
3. **Modo de Dados e Codificação:** Como o link ou texto é transformado em blocos de bits (Modo Byte / Alfanumérico).
4. **Correção de Erros (Reed-Solomon):** O algoritmo matemático que adiciona redundância, permitindo que o QR Code seja lido mesmo com até 30% de danos ou rasuras.

---

## Tecnologias Utilizadas
* **HTML5 / CSS3:** Interface moderna, responsiva e estilizada com Tailwind CSS.
* **JavaScript (Vanilla):** Lógica de manipulação de eventos e renderização.
* **Biblioteca Cliente (ex: qrcode.js / nativa):** Executada 100% no navegador do usuário (Client-Side), garantindo privacidade total (nenhum dado é enviado para servidores de terceiros).

---

## Desafios Enfrentados e Soluções

Durante o desenvolvimento do projeto sem o uso de APIs externas, surgiram alguns desafios técnicos no entendimento e na implementação dos QR Codes. Abaixo estão os principais problemas encontrados e como foram solucionados:

### 1. Lógica e Matemática
* **Problema:** A matemática e a lógica utilizadas para a conversão de links em binário e posteriormente de binário para uma imagem é extensa e complexa.
* **Solução:** Implementamos a biblioteca `qrcode.js` via JavaScript, permitindo a renderização da matriz do QR Code no elemento HTML `<canvas>` sem nenhuma chamada de rede ou necessidade de criar a lógica de conversão do zero.

### 2. Redimensionamento e Download sem perda de qualidade
* **Problema:** Exportar o QR Code gerado em telas de alta resolução (Retina/4K) poderia deixar a imagem borrada se gerada apenas como um elemento sintético.
* **Solução:** Utilizamos o método nativo `toDataURL('image/png')` extraído diretamente da matriz do Canvas com dimensões dinâmicas, garantindo um arquivo PNG nítido e pronto para uso em impressões ou telas.

---

## Como Executar o Projeto Localmente

Não é necessário instalar gerenciadores de pacotes como `npm` ou servidores como `node` para rodar este projeto básico.

1. **Clone o repositório:**
   `git clone [https://github.com/matheuscjustinog/QRCode.git](https://github.com/matheuscjustinog/QRCode.git)`

2. **Acesse a pasta do projeto:**
   `cd QRCode`

3. **Abra a aplicação:**
   * Basta dar dois cliques no arquivo `index.html` para abrir diretamente no seu navegador de preferência.

---

## Contribuições

Contribuições são super bem-vindas! Se você quiser adicionar visualizadores interativos da matriz do QR Code, novos temas ou otimizações no código:

1. Faça um **Fork** do projeto.
2. Crie uma Branch para sua funcionalidade (`git checkout -b feature/NovaFuncionalidade`).
3. Faça o **Commit** de suas alterações (`git commit -m 'feat: adiciona nova funcionalidade'`).
4. Faça o **Push** para a Branch (`git push origin feature/NovaFuncionalidade`).
5. Abra um **Pull Request**.

---

## Licença

Este projeto está sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
