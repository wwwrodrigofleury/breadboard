# 🔬 LogiBoard Studio · Simulador de Breadboard & Digital Trainer
### Laboratório Virtual de Montagem para Sistemas Lógicos (LEI / IPCB)

> **Criado especificamente de acordo com as aulas práticas e materiais do Prof. Nuno Roxo**
> Licenciatura em Engenharia Informática — Instituto Politécnico de Castelo Branco (IPCB)

---

## 🚀 Como Executar

O **LogiBoard Studio** é uma aplicação web moderna desenvolvida em HTML5, CSS3 e JavaScript ES Modules nativo, sem necessidade de build complexo.

### Opção 1: Abrir com qualquer servidor estático local (Recomendado)
No terminal, dentro da pasta do projeto (`c:\Users\Usuario\Downloads\breadBoard`):
```bash
npx serve . -l 3000
```
De seguida, abra no navegador:
👉 **`http://localhost:3000`**

*(Em alternativa, se usar a extensão **Live Server** do VS Code, clique com o botão direito em `index.html` e selecione **Open with Live Server**).*

---

## ⚡ Funcionalidades Principais

### 1. 🎛️ Digital Trainer IDL-800 Integrado
* **Interruptor Geral (POWER ON/OFF)** com LED indicador e **Voltímetro Digital DC** (5.00 V).
* **Botão de Auto-Alimentação da Breadboard**: interliga com 1 clique o +5V (VCC) e GND do trainer às calhas de alimentação da placa de ensaio.
* **8 Data Switches (SW1 a SW8)**: comutadores de nível lógico (0 e 1) com LEDs de estado e etiquetas A..H.
* **Gerador de Relógio (CLK)**:
  * **Modo Manual**: botão pulsador para enviar impulso individual de transição ascendente.
  * **Modo Automático**: oscilador contínuo com frequências selecionáveis (**0.5 Hz, 1 Hz, 2 Hz, 5 Hz**).
* **8 LEDs de Saída (LED1 a LED8)**: com iluminação suave, indicação HIGH/LOW e etiquetas de visualização.
* **Módulo de Display de 7 Segmentos**:
  * Display LED digital completo com terminais independentes (`a`, `b`, `c`, `d`, `e`, `f`, `g`).
  * Descodificação em tempo real do dígito hexadecimal/decimal exibido.
  * Suporte tanto para acionamento direto em cátodo comum como para descodificador **74LS47** (ânodo comum).

---

### 2. 🖲️ Placa de Ensaio (Breadboard de 60 Colunas)
* **Geometria Realista**:
  * Calhas de alimentação superior e inferior (`+` e `-`) ao longo de 60 colunas.
  * Barramentos de contactos verticais divididos pela calha central: bloco superior (linhas `j` a `f`) e bloco inferior (linhas `e` a `a`).
* **Auxiliares Visuais Inteligentes**:
  * Ao passar o cursor por qualquer orifício, a tira equipotencial inteira é destacada com um anel de brilho (halo verde).
  * Encaixe exato de circuitos integrados no formato DIP (Dual In-line Package) sobre a calha central.
  * Indicador da meia-lua / ranhura de orientação do pino 1.
  * Pontos luminosos nos pinos dos CIs indicando em tempo real o nível elétrico de cada pino (Vermelho = 1, Azul/Preto = 0, Cinzento = Z / flutuante).

---

### 3. 🔌 Gestor de Fios e Paleta de Cores do Laboratório
* **Ferramenta de Fio (Tecla `W`)**:
  * Clique no orifício de origem ou terminal do trainer e clique no destino para lançar o fio.
  * **Fios Curvos ou Retos**: botão na barra superior alterna entre curvas Bézier com gravidade natural e drop shadow ou linhas retas de engenharia.
* **Paleta de Cores com Convenção Oficial**:
  * `1` — 🔴 **Vermelho** (`#dc2626`): Alimentação (+5V / VCC)
  * `2` — ⚫ **Preto** (`#1e293b`): Massa (0V / GND)
  * `3` — 🟠 **Laranja** (`#f97316`): Variável de entrada **A** (SW1)
  * `4` — 🟡 **Amarelo** (`#eab308`): Variável de entrada **B** (SW2)
  * `5` — 🟢 **Verde** (`#22c55e`): Variável de entrada **C** (SW3)
  * `6` — 🔵 **Ciano** (`#06b6d4`): Variável de entrada **D** (SW4)
  * `7` — 🟦 **Azul** (`#3b82f6`): Sinais e interligações lógicas
  * `8` — 🟣 **Roxo** (`#a855f7`): Sinais e barramentos
  * `9` — 🌸 **Rosa** (`#ec4899`): Saídas para LEDs
  * `0` — ⚪ **Branco** (`#f8fafc`): Sinais de controlo / CLK
* **Ferramenta Tesoura (Tecla `D` ou `X`)**: clique em qualquer fio para o cortar e remover instantaneamente com som de corte.

---

### 4. 📍 Ponta de Prova Lógica (Tecla `P`)
* Inspirada nas pontas de prova de laboratório com ecrã digital e áudio Web Audio API.
* Ao clicar num orifício ou pino, indica:
  * 🔴 **Nível 1 (HIGH, 5.0 V)** com som agudo (880 Hz).
  * 🔵 **Nível 0 (LOW, 0.0 V)** com som grave (220 Hz).
  * ⚪ **Flutuante / Alta Impedância (Z)** com som neutro (440 Hz).
  * ⚠️ **Curto-Circuito / Conflito** com tom de aviso imediato.

---

### 5. 🧩 Catálogo Completo de Circuitos Integrados (74LS / HCT)
Todos os CIs do programa da disciplina com pinagem real, datasheet visual e simulação funcional:
1. **74LS04**: Hex Inverter (6 portas NOT)
2. **74LS08**: Quad 2-Input AND (4 portas AND)
3. **74LS32**: Quad 2-Input OR (4 portas OR)
4. **74LS86**: Quad 2-Input XOR (4 portas XOR)
5. **74LS11**: Triple 3-Input AND (3 portas AND de 3 entradas)
6. **74LS00**: Quad 2-Input NAND (4 portas NAND)
7. **74LS02**: Quad 2-Input NOR (4 portas NOR)
8. **74HCT253**: Dual 4-to-1 Multiplexer (2 MUX 4:1 com 3-state)
9. **74LS151**: 8-to-1 Line Multiplexer (1 MUX 8:1 com saídas Y e W)
10. **74LS175**: Quad D-Type Flip-Flop com Clear comum
11. **74LS109**: Dual J-K' Positive-Edge-Triggered Flip-Flop
12. **74LS47**: BCD-to-7-Segment Decoder/Driver (saídas ativas a 0)

---

### 6. 📚 Exercícios das Aulas Práticas & Testbench Automático
A aplicação inclui um painel dedicado com todos os exercícios dos slides:
* **Aula 3**: Função NOR com 74LS32 e 74LS04.
* **Aula 4**: Circuito de Votação de 3 Entradas com fatorização mínima: $f = A(B+C) + BC$ (74LS32 + 74LS11).
* **Aula 5**: Circuito Comparador de Palavras de 2 Bits $AB > CD$ (74LS04, 74LS11, 74LS32).
* **Aula 6**: Detetor de Palíndromos / Capicuas de 4 Bits com mapa em xadrez e portas XOR/XNOR (74LS86 + 74LS11).
* **Aula 7**: Detetor de Números de Fibonacci (4 bits) com Leis de De Morgan: $f = [ (A+B) \cdot (C + (B \oplus D)) ] \oplus 1$ (74LS86, 74LS32, 74LS11).
* **Aula 9**: Sistema de Alarme Residencial de 4 Modos com Multiplexer 8:1 (74LS151).
* **Aula 11**: Circuito Sequencial — Semáforo de Passadeira com Flip-Flop D (74LS175, 74LS08, 74LS32).
* **Aula 13**: Trabalho Final — Sequência de Fibonacci no Display de 7 Segmentos (0, 1, 1, 2, 3) controlada por botão e relógio.

#### Cada exercício dispõe de:
* Enunciado e objetivos práticos.
* Dicas de montagem e mapeamento de pinos do guião.
* **▶ Correr Testbench Automático**: testa todas as combinações da tabela de verdade em tempo real e apresenta uma tabela visual com as linhas verdes (**✓ OK**) ou vermelhas (**✗ Erro**).
* **⚡ Carregar Montagem Modelo**: monta automaticamente o circuito de referência 100% testado na breadboard para consulta e estudo.

---

### 7. 🔊 Efeitos Sonoros Web Audio
* Sons sintetizados em tempo real no navegador:
  * Clique dos interruptores basculantes (Toggle switches).
  * Clique de contacto de relés ao comutar a alimentação.
  * Som de estalido ao cortar fios (Scissors).
  * Apito de teste da Ponta de Prova.
  * Fanfarra de vitória quando o Testbench passa a 100%.
  * Buzzer de aviso em caso de erro elétrico.

---

### 8. 💾 Guardar e Partilhar Circuitos (JSON)
* **Guardar**: exporta toda a montagem (CIs colocados, posições e todas as ligações de fios) para um ficheiro `.json`.
* **Abrir**: permite aos estudantes carregar e continuar trabalhos de casa ou partilhar as suas montagens com colegas e docentes.

---

## ⌨️ Tabela de Atalhos de Teclado

| Tecla | Ação |
| :---: | :--- |
| `W` | Ativar Ferramenta de **Fio** |
| `S` | Ativar Modo de **Seleção / Cursor** |
| `P` | Ativar **Ponta de Prova Lógica** |
| `D` ou `X` | Ativar **Tesoura de Corte** |
| `Espaço` | Enviar **Impulso de Relógio (CLK)** |
| `1` a `9`, `0` | Selecionar cor de fio rápida (1=Vermelho, 2=Preto, etc.) |
| `Delete` / `Backspace` | Remover CI ou fio selecionado |

---

## 🧪 Testes Automatizados da Simulação
Para verificar a integridade da biblioteca lógica e de todos os modelos de circuito:
```bash
npm test
```
**Resultado esperado:**
```text
=== Testing Circuit Simulator Engine & Presets ===
Aula 3: 4/4 PASS
Aula 4: 8/8 PASS
Aula 5: 16/16 PASS
Aula 6: 16/16 PASS
Aula 7: 16/16 PASS
Aula 9: 16/16 PASS
Aula 11: 6/6 PASS
```
