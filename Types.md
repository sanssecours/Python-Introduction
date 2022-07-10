# Datentypen & Ausdrücke

## REPL

Bisher haben wir den meisten Code direkt im Powershell- oder Python-**Interpreter** (`python`) geschrieben. Dabei geben wir eine oder mehrere Zeilen von Code ein und führen diese – üblicherweise nach der Eingabe mittels Return <kbd>⏎</kbd> – aus. Diese Art der Eingabe-Oberfläche wird oft auch als sogenannte **[REPL](https://en.wikipedia.org/wiki/Read–eval–print_loop)** (Read-Eval-Print Loop) bezeichnet.

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

Um heraus zu finden welchen Typ ein bestimmter Ausdruck hat kann man die Funktion `type` verwenden:

```{python}
type(True)
type(1234)
type(12.34)
type("1234")
type('1234')
```

### Funktionen und Operatoren

Diverse Funtkionen wie z.B. `abs`, `min` und Operatoren wie z.B. `+`, `-` , `**` (Potzenz) können ebenfalls Teil eines Ausdrucks sein.

```{python}
1+2
"1" + "2"
2**3
abs(-123)
min(12.4, 12.3)
max(12.4, 12.3)
min(max(1,2,3), max(-1,-2,-3))
```

Wie man bei der Funktion `min` sieht werden die Argumente einer Funktion in Python durch Beistriche getrennt.

> - ❔ Warum unterscheidet sich das Ergebnis des ersten und des zweiten Ausdrucks?
>
> - ❔ Um welche mathematische Operation handelt es sich bei `**`?
> - ❔ Welchen Wert ermitteln die Funktionen `min`, `max` und `abs`?
>
> - ❔ Welche Typen haben die (Ergebnisse der) obigen Ausdrücke?

Operationen wie `+` oder `**` können ebenfalls als Funktion angesehen werden, die

- einen speziellen Namen (wie z.B. `+`, `-` , `*`) besitzen und
- meist **In**fix-Notation (Funktion/Operator zwischen Argumenten) statt **Post**fix-Notation (Argumente nach Operation/Funktion) verwenden.

So gibt es neben dem Operator `+` z.B. auch eine Funktion mit mehr oder weniger gleicher Funktionalität mit dem Namen `add`:

```{python, collapse=TRUE, comment='#'}
from operator import add # Funktion add importieren

add(1, 2) # Argumente nach Funktion (Postfix-Notation)
1 + 2 # Argumente vor und nach Funktion (Infix-Notation)
```

Neben den von Haus aus sichtbaren Funktionen/Operatoren, wie z.B. `abs` und `-`, gibt es noch viele andere Funktionen/Operatoren, die erst importiert werden müssen bevor man sie verwenden kann. Ein Beispiel dafür sehen wir in der ersten Zeile des obigen Codeblocks in dem die Funktion `add` aus dem Modul `operator` importiert wird.

Ein weitere Neuerung im obrigen Text sind Kommentare. Diese beginnen in Python mit dem Zeichen `#`. Der Text hinter diesem Zeichen (bis zum Zeilenende) wird vom Interpreter ignoriert. Kommentare dienen z.B. dazu zu **dokumentieren**,

- **warum** ein bestimmte Löung für ein Problem gewählt wurde,

- welche **Probleme** auftreten könnten oder
-  auch **wie** ein bestimmtes Problem gelöst wurde.

Dabei sollte man darauf achten **keine trivialen Kommentare** zu schreiben. Ein Kommentar wie z.B.

```python
1 + 2 # Die Ganzzahlen 1 und 2 werden addiert
```

ist höchstens für absolute Programmierneulinge interessant. Das soll natürlich keine Aufforderung sein keine Kommentare zu schreiben. **Kommentare** und andere Form der **Dokumentation** sind ein **essentieller Teil guter Software**.

#### Argumente (Input) und Rückgabewerte (Output)

Jede Funktion in Python übernimmt eine **bestimmte Anzahl von Argumenten** und returniert **einen Rückgabewert**. Dabei ist zu beachten, dass die Anzahl von Argumenten auch 0 sein kann. Eine Funktion kann auch `None` retunieren. Dieser Wert vom Typ `NoneType` steht im Endeffekt für „keinen Wert“. Schauen wir uns die Eingabewerte von Funktionen und Operatoren an Hand von ein paar Beispielen an.

```{python}
1 + 2
```

Die Operation `+` übernimmt hier **zwei Argumente** vom Typ `int` und gibt die Summe dieser Werte `3` (Typ `int`) zurück. Die Operation `+` ist auch auf andere Datentypen wie z.B. `float` und `str` definiert. Bei nachfolgendem Ausdruck:

```{python}
1 + 4.5
```

handelt es sich beim ersten Argumenten wiederum um eine **Ganzzahl** (`int`) und beim zweiten Argument um eine **Gleitkommazahl** (`float`). Beim Rückgabewert von `5.5` handelt es sich wiederum um eine **Gleitkommazahl**. Die Operation `+` ist auch auf Strings definiert, wobei hierbei die String aneinandergefügt werden:

```{python}
"Hello, " + "World"
```

Beim Rückgabewert handelt es sich wiederum um einen String:

```{python}
type("Hello, " + "World")
```

Manche Funktionen können auch eine beliebige Anzahl von Argumenten übernehmen. Eine dieser Funktionen ist `min`:

```{python}
min(1, -10)
min(1, -1, 0.5, -2)
```

Zum Schluss wollen wir uns noch die Funktion `print` ansehen, die wir schon verwendet haben um die Zeichenkette “Hello, World!” auf dem Bildschirm auszugeben. Diese kann wiederum eine beliebige Anzahl von Argumenten übernehmen und gibt diese auf dem “Standard Output” (`stdout`), also üblicherweise dem Bildschirm, getrennt durch Leerzeichen aus. Die Funktion gibt dabei aber keinen Wert zurück (`None`).

```{python}
print("Hello,", "World")
type(print("Hello,", "World"))
```

> - ❔ Warum gibt der Interpreter beim Aufruf des zweiten Ausdrucks sowohl den Typ des Ausdrucks (`<class 'NoneType'>`) als auch den Text “Hello, World” aus?

Die Funktion `print` kann auch ohne Argumente aufgerufen werden. Das sorgt dafür, dass ein leere Zeile (ein Zeilenvorschub) auf `stdout` ausgegeben wird.

```{python, results='hold'}
print("One")
print()
print("Two")
```

> - ❔ Wie lautet das Ergebnis der untenstehenden Ausdrücke?
>
> - ❔ Welchen Typ haben die ausgewerten Ausdrücke?
>
> - Falls die Ausdrücke Funktionen/Operatoren enthalten:
>   - ❔ Welchen Typ haben die Argumente der verwendeten Funktionen/Operatoren?
>
>   - ❔ Wie lautet der Typ des Rückgabewertes der ausgewerteten Funktionen/Operatoren? 
>
>
> Versuche die Aufgabe als erstes **im Kopf** zu lösen und gib diese danach im Python-Interpreter ein um dein Ergebnis zu überprüfen.
>
> Welche Aufgaben, die noch nicht besprochenen Funktionen (wie z.B. `float`) übernehmen, kannst du dabei feststellen indem du diese inklusive erster Klammer – also z.B. `float(` – in `ptpython` eingibst. Eine andere Möglichkeit ist in der [Python-Dokumentation](https://docs.python.org) nach der jeweiligen Funktion zu suchen.

```python
1
1.0
float(1)
int("1")
1+10 * 3.3
1.1
print(1+3)
str(1) + "10"
True
int(True)
int(False)
bool(1337)
```

### Vergleichsoperatoren

Eine, wie wir später noch sehen werden, in Programmiersprachen sehr wichtige Art Aufgabe übernehmen Vergleichsoperatoren. Diese Arten von Operatoren

- vergleichen **zwei Argumente** und

- geben ein **Ergebnis vom Typ `bool`**, also entweder `True` oder `False ` zurück.

Der häufigste Vergleichsoperator ist wohl `==` der seine zwei Argumente auf **Gleichheit** überprüft:

```{python}
1 == 2
"Hello" == 'Hello'
"hello" == "Hello"
None == None
```

Der genau entgegengesetzte Operator zu `==` ist `!=` und überprüft ob die Ausdrücken links und rechts **nicht gleich** (unterschiedlich) sind.

```{python}
1 != 1
1337 != 4
"Hello" != 'hello'
None != None
```

> - ❔ Wie lautet das Ergebnis der untenstehenden Ausdrücke?

```python
"1" == '1'
1 != 1
True == False
True != False
2 != 2.2
```

Neben Gleichheit kann man bestimmte Ausdrücke, wie z.b. Zahlen, auch mit

- `<` (kleiner) ,
- `<=` (kleiner gleich) ,
- `>` (größer), oder
- `>=` (größer gleich)

vergleichen.

```{python}
5 < 6
6 < 6
6 <= 6
2 >= 2
2.1 > 2.01
```

> - ❔ Wie lautet das Ergebnis der untenstehenden Ausdrücke?

```python
20 > 21
20 >= 21
1 >= 1
1 < 1
```

### Boolsche Operatoren

Boolsche Ausdrücke, also Ausdrücke die entweder den Wert `True` oder `False` annehmen sind ein wichtiger Bestandteil praktisch jedes Programms. Um boolsche Ausdrücke miteinander zu kombinieren kann man boolsche Operatoren verwenden. Hier wollen wir kurz auf die wichtigsten dieser Operatoren:

- `not`,
- `and`, und
- `or`

eingehen.

#### `not`

Der Operator `not` (nicht) wandelt **einen boolschen Ausdruck** in das **Gegenteil** um. Das heißt

- aus `not True` wird `False` und
- aus `not False` wird `True`.

Hierzu ein paar Beispiele:

```{python}
not False
not (1 >= 2)
not 1 >= 2
not not not True
```

Die Klammern `()` im zweiten Ausdruck können dabei auch wegelassen werden, da `>=` stärker bindet – also vorher ausgewertet wird – wie `not`. Eine Liste der Prioritäten der verschiedenen Operatoren in Python, also welche Operatoren früher oder später ausgeführt werden, findet sich z.B. [hier](https://docs.python.org/3/reference/expressions.html#operator-precedence).

#### `and`

Mittels des Operators `and` kann man zwei boolsche Ausdrücke miteinander verbinden. Dabei wird der kombinierte Ausdruck genau dann wahr (`True`) wenn der Ausdruck links und rechts (von `and`) wahr sind:

```{python}
False and False
True and False
False and True
True and True
(1 < 2) and (1 <= 2)
```
