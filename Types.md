# Datentypen & Ausdrücke

## REPL

Bisher haben wir den meisten Code direkt im Powershell- oder Python-**Interpreter** (`python`) geschrieben. Dabei geben wir eine oder mehrere Zeilen von Code direkt ein und führen diese – üblicherweise nach der Eingabe mittels Return <kbd>⏎</kbd> – aus. Diese Art der Eingabe-Oberfläche wird oft auch als sogenannte **[REPL](https://en.wikipedia.org/wiki/Read–eval–print_loop)** (Read-Eval-Print Loop) bezeichnet.

Wie bei vielen anderen interpretierten Sprachen existieren auch bei Python alternative REPLs, die das Arbeiten mit Code nochmals vereinfachen können. Eine solche REPL mit dem Namen [`ptpython`](https://github.com/prompt-toolkit/ptpython) wollen wir nun installieren. Dazu verwenden wir [`pip`](https://pypi.org/project/pip/), einen Package-Manager für Python. Ähnlich wie [`winget`](https://docs.microsoft.com/en-us/windows/package-manager/winget/) (und viele andere Package-Manager) kann man das Sub-Kommando `install` dazu verwenden Software zu installieren:

```sh
pip install ptpython
```

Nach der Installation können wir `ptpython` mittels Eingabe des Befehls

```sh
ptpython
```

verwenden und uns mit der Bedienung davon ein wenig vertraut machen. Wie wir im Verlauf noch sehen werden bietet `ptpython` in Vergleich zur Standard-REPL (`python`) Funktionen wie **Autovervollständigung** und **Syntax-Highlighting**.

## Ausdrücke

Bei einem Ausdruck (`Expression`) handelt es sich um ein (üblicherweise relativ kurzes) Stück Code, dass ausgewertet werden kann und dann ein bestimmtes Ergebnis eines bestimmten Datentyps liefert.

### Konstanten

Einer der einfachsten Varianten von Ausdrücken sind Konstanten. Diese kennt man eventuell auch schon aus dem Mathematik-Unterricht. Hier mal ein paar Beispiele:

| Konstante/Ausdruck | Datentyp                 |
| ------------------ | ------------------------ |
| `True`             | `bool` (Boolscher Wert)  |
| `1234`             | `int` (Ganzzahl)         |
| `12.34`            | `float` (Gleitkommazahl) |
| `"1234"`           | `str` (Zeichenkette)     |
| `'1234'`           | `str` (Zeichenkette)     |

Um heraus zu finden welchen Typ ein bestimmter Ausdruck hat kann man die Funktion type verwenden:

```{python}
type(True)
type(1234)
type(12.34)
type("1234")
type('1234')
```
