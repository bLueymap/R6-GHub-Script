# Logitech G-Hub Recoil Script - Rainbow Six Siege

Este é um script de automação e compensação de recuo dinâmico desenvolvido em **Lua**, projetado especificamente para ser executado através do ecossistema de scripts do software **Logitech G-Hub**. 

O script foi estruturado de forma inteligente para separar os operadores entre **Atacantes** e **Defensores**, otimizando a interface no console e permitindo uma troca ágil de posições durante as rodadas.

---

## 🚀 Funcionalidades

* **Separação por Lados (Ataque/Defesa):** O painel do console filtra dinamicamente e exibe apenas os operadores do lado atual, reduzindo a poluição visual.
* **Troca Rápida de Lado:** Atalho dedicado que pula instantaneamente do Ataque para a Defesa (e vice-versa), redefinindo a seleção diretamente para o operador inicial do lado (`Sledge` no ataque / `Smoke` na defesa).
* **Interface de navegação:** O script conta com um painel visual no console do aplicativo que facilita a visualização de operadores marcando o selecionado com um `[✅]`, e o status do script (`[ ON ]` / `[ OFF ]`).
* **Recuo Dinâmico por Estágios:** Sistema avançado baseado em tempo que altera o comportamento do mouse dependendo de há quantos milissegundos o gatilho está pressionado e a possibilidade de se utilziar numeros decimais para ajustes fino.

---

## 🎮 Controles e Atalhos

Para navegar pelos operadores e ligar/desligar as funções, utilize as seguintes combinações no mouse e teclado:

### 🔄 Seleção de Operadores (Dentro do Lado Atual)
* `Right CTRL` + `Botão Avançar do Mouse (MB5)`: Seleciona o **Próximo** operador da lista.
* `Right CTRL` + `Botão Voltar do Mouse (MB4)`: Seleciona o operador **Anterior** da lista.
* `Right Shift` + `Botão Avançar do Mouse (MB5)`: Avança 6 operadores na lista, pulando para linha de baixo.
* `Right Shift` + `Botão Voltar do Mouse (MB4)`: Retrocede 6 operadores na, pulando para linha de cima.

### ⚙️ Sistema e Troca de Lados
* `Right ALT` + `Botão Avançar do Mouse (MB5)`: Liga / Desliga a execução do script.
* `Right ALT` + `Botão Voltar do Mouse (MB4)`: Altera entre **ATACANTES** ↔️ **DEFENSORES** (Pula direto para *Sledge* ou *Smoke*).

---

## 🛠️ Como Funcionam os Parâmetros de Eixo?

Cada operador possui uma linha de configuração detalhada para o comportamento do mouse. A estrutura funciona como uma linha do tempo em milissegundos (`ms`).

Exemplo de estrutura:
`{n="Nome", r=10, x1=0, tm1=0, x2=0, tm2=0, y1=0, tym1=0, y2=0, tym2=0}`

### 📐 Entendendo as Variáveis / Configurando o recoil:

* **`r` (Recoil Inicial):** A força vertical padrão. Assim que você **segura** o botão direito do mouse (mouse2 - mira) clica para atirar (mouse1), o mouse é empurrado para baixo com essa intensidade constante para anular o coice inicial do jogo.
* **Eixo Horizontal (Esquerda / Direita):**
    * `x1` e `x2`: Quantidade de pixels que o mouse se moverá horizontalmente. Valores **negativos** movem o mouse para a esquerda, valores **positivos** para a direita.
    * `tm1` e `tm2`: O tempo de atraso (em milissegundos) que o script espera após o clique inicial para começar a aplicar as forças `x1` e `x2`, respectivamente.
* **Eixo Vertical Dinâmico (Cima / Baixo):**
    * `y1` e `y2`: Força vertical adicional aplicada para armas cujo recuo aumenta ou diminui ao longo da rajada.
    * `tym1` e `tym2`: O tempo de disparo contínuo (em milissegundos) necessário para ativar as correções `y1` e `y2`.

> 💡 **Nota Prática:** Variáveis que começados com `tm` ou `tym` servem como **cronômetros (gatilhos de tempo)**, enquanto `r`, `x` e `y` definem a **força real de movimento** aplicada ao sensor do mouse para cima, baixo esquerda e direita.

---

## ⚙️ Como Configurar e Ajustar no Jogo

⚠️ **IMPORTANTE:** O script funciona com **qualquer** configuração de sensibilidade, DPI ou FOV que você utilize no jogo. Ele vem com valores *padrão* em todos os operadores, oque obviamente **não** vão funcionar perfeitamente na sua tela logo de início.
Para obter o recuo perfeito, você deve calibrar os eixos manualmente para cada operador *Apenas 1 arma por operador*. No meu perfil voce encontra o script para as duas armas, ele segue a mesma lógica deste porém a troca de armas é atribuida no clique do scroll do mouse, oque é algo incomum pra maioria dos jogadores.

### 🏋️‍♂️ Passo a Passo para Calibração:
1. Entre no **Campo de Tiro** do Rainbow Six Siege.
2. Escolha o operador que deseja ajustar.
3. Atire contra o alvo sem mover o mouse e observe o comportamento do tiro:
   * **Se a arma subir:** Aumente o valor de `r` (ou de `y1`/`y2`).
   * **Se a arma descer demais:** Diminua o valor de `r` (ou de `y1`/`y2`).
   * **Se a arma puxar para os lados:** Ajuste os valores de `x1`/`x2` e os gatilhos de tempo (`tm1`/`tm2`) conforme explicado na seção de eixos.
4. Alt-Tab para o G-Hub, altere os números na tabela do operador, salve (`Ctrl + S`) e teste novamente no jogo.

*Pode levar um tempinho para calibrar os seus operadores favoritos, mas uma vez ajustado para a sua sensibilidade, o recuo fica absolutamente perfeito!*

---

## 📦 Como Instalar

1. Abra o software **Logitech G-Hub** na aba superior clicque em **Perfis**.
2. Clique em **Adicionar Jogos e Aplicativos** e selecione o **Rainbow Six Siege**.
3. Em Perfis Cliquei nos 3 pontinhos do perfil **Padrão** e cliquei em **Criar Script LUA**.
4. Em seguinda na parte inferior clique em **Crie um novo Script de LUA**.
5. Apague o código pré escrito e cole o script baixado.
6. Na parte superior esquerda clique em **Script** e em seguida **Salvar e executar**.
7. Aumente o tamnho do console na parte inferior da tela para melhor visualização e pronto.

---
⚠️ *Aviso: Este script foi desenvolvido apenas para fins de estudo de automação de periféricos utilizando a API oficial da Logitech. Use com responsabilidade.*
