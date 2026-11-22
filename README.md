# Wordle y teoría de la información de Shannon · Wordle and Shannon's Information Theory

**Integrantes / Authors:** Dayana Marcela Narváez · Ian Alejandro Hernández
**Curso / Course:** Comunicaciones Digitales · Universidad del Cauca (2026)

[Español](#español) · [English](#english)

---

## Español

Estrategia para resolver Wordle en inglés: en cada turno se juega la palabra que maximiza la información esperada I(X;Y), es decir, la entropía de los patrones de colores.

### Reglas y supuestos
- Palabra de 5 letras, 6 intentos, letras a–z sin tildes.
- **Respuestas:** 2.309 palabras (lista original publicada por 3Blue1Brown). Todas se consideran equiprobables: H(X) = log₂ 2.309 = 11,17 bits.
- **Intentos:** también se eligen entre esas 2.309 palabras. El juego real acepta ≈13.000.
- **Letras repetidas:** primero se marcan los verdes; luego cada amarillo gasta una copia libre de la letra.
- **Búsqueda:** con más de 60 candidatas solo se prueban candidatas. Con 60 o menos se prueban las 2.309 palabras. En caso de empate gana una candidata.

### Resultados (las 2.309 respuestas)
| Estrategia | Promedio de intentos | Resueltas en ≤ 6 | Máximo |
|---|---|---|---|
| Shannon (inicia con RAISE) | 3,51 | 100 % | 6 |
| CRANE + candidata al azar* | 3,88 ± 0,01 | 98,5 % | 10 |
| Candidata al azar* | 4,09 ± 0,02 | 98,1 % | 10 |

\*Promedio de 30 semillas (± desviación estándar). El máximo es el peor caso observado.

Mejores primeras palabras (bits esperados): RAISE 5,878 · SLATE 5,856 · CRATE 5,835 · IRATE 5,833 · TRACE 5,830.
Ejemplo (respuesta SHARD): RAISE (2.309 → 21) → SPLAT (21 → 5) → DUCHY (5 → 1) → SHARD.

### Cómo ejecutar
Abre `wordle_shannon.ipynb` en Google Colab y ejecuta todas las celdas. La lista de palabras se descarga de `github.com/3b1b/videos` (`_2022/wordle/data/possible_words.txt`). También se incluye una copia en `ans.txt`.

### Archivos
- `wordle_shannon.ipynb`: modelo, estrategia, ejemplo, simulaciones y gráfico.
- `ans.txt`: lista de 2.309 respuestas.
- `Trabajo final – Wordle (ES).pdf` / `(EN).pdf`: infografía entregada.

### Uso de IA
Usamos Claude (Anthropic) para hacer un borrador del texto, escribir el código de simulación y revisar, rediseñar y traducir la infografía. Las cifras se verificaron ejecutando el notebook.

---

## English

A strategy for solving English Wordle: each turn, play the word that maximizes the expected information I(X;Y), i.e. the entropy of the color patterns.

### Rules and assumptions
- 5-letter word, 6 guesses, letters a–z, no accents.
- **Answers:** 2,309 words (original list published by 3Blue1Brown), all assumed equally likely: H(X) = log₂ 2,309 = 11.17 bits.
- **Guesses:** also chosen from those 2,309 words. The real game accepts ≈13,000.
- **Repeated letters:** greens are marked first; then each yellow uses up one free copy of the letter.
- **Search:** with more than 60 candidates, only candidates are tested. With 60 or fewer, all 2,309 words are tested. Ties go to a candidate.

### Results (all 2,309 answers)
| Strategy | Average guesses | Solved in ≤ 6 | Max |
|---|---|---|---|
| Shannon (starts with RAISE) | 3.51 | 100% | 6 |
| CRANE + random candidate* | 3.88 ± 0.01 | 98.5% | 10 |
| Random candidate* | 4.09 ± 0.02 | 98.1% | 10 |

\*Mean over 30 seeds (± standard deviation). Max is the worst case observed.

Best first guesses (expected bits): RAISE 5.878 · SLATE 5.856 · CRATE 5.835 · IRATE 5.833 · TRACE 5.830.
Example (answer SHARD): RAISE (2,309 → 21) → SPLAT (21 → 5) → DUCHY (5 → 1) → SHARD.

### How to run
Open `wordle_shannon.ipynb` in Google Colab and run all cells. The word list is downloaded from `github.com/3b1b/videos` (`_2022/wordle/data/possible_words.txt`). A copy is also included as `ans.txt`.

### Files
- `wordle_shannon.ipynb`: model, strategy, example, simulations and chart.
- `ans.txt`: list of 2,309 answers.
- `Trabajo final – Wordle (ES).pdf` / `(EN).pdf`: submitted infographic.

### AI use
We used Claude (Anthropic) to draft the text, write the simulation code, and review, redesign and translate the infographic. All figures were verified by running the notebook.

### References
- Shannon, C. E. (1948). A Mathematical Theory of Communication. *Bell System Technical Journal, 27*, 379–423, 623–656.
- Cover, T. M., & Thomas, J. A. (2006). *Elements of Information Theory* (2nd ed.). Wiley.
- 3Blue1Brown (2022). *Solving Wordle using information theory* [Video]. YouTube.
