# Grundlagen

Wie bei jedem Handwerk gibt es auch beim Programmieren gewisse Werkzeuge die man benötigt um eine Applikation zu erstellen. Das erste Werkzeug, dass ein angehender Programmierer verwendet ist wahrscheinlich ein **Text-Editor**. In diesem Programm schreibt man dann wie schon der Name andeutet Text, so-genannten **Code**, in einer bestimmten **Programmiersprache**. Je nach Programmiersprache beschreibt der Code entweder

1. welche Schritte ein Computer ausführen soll (imperativ), oder
2. das Problem selber (deklarativ).

> Ein Programmiersprache ist wesentlich einfacher aufgebaut als eine menschliche Sprache. Das mag zu dem Gedanken verleiten, dass es einfacher ist einem Computer beizubringen wie er ein bestimmtes Problem aussieht (deklarative Programmierung) oder wie es zu lösen ist (imperative Programmierung) als z.B. einer Person. Das ist aber ein Trugschluss. Im Endeffekt benötigt der Computer (durch die Einfachheit der Programmiersprache) eine wesentlich genauere Beschreibung als ein Mensch, führt diese aber dafür (im Normalfall) fehlerfrei und äußerst schnell durch.

Der „fertige“ Code wird entweder

1. von einem **Compiler** in Maschinen-Befehle übersetzt (**kompiliert**) und dann vom Computer ausgeführt, oder
2. direkt vom einem **Interpreter** ausgeführt (**interpretiert**).

Üblicherweise findet, zur Optimierung der Geschwindigkeit eines Programms, auch bei der Interpreter-Variant eine Übersetzung in maschinen-nahen Code statt. Als Programmierer muss man sich dabei aber – im Gegensatz zur Compiler-Variante – üblicherweise keine Gedanken machen.

```{r, fig.align="center", echo=FALSE}
knitr::include_graphics("Pictures/Programming-Process.svg", auto_pdf = TRUE)
```

## Die Werkzeuge

### Editor

Wie schon in einführenden Teil beschrieben ist ein Text-Editor oder auch kurz Editor eines der wesentlichen Werkzeuge eines Programmierers. Von einer Textverarbeitung (wie z.B. “Word”, “LibreOffice” oder “Google Docs”) unterscheidet sich ein Texteditor, dadurch, dass man damit wirklich nur Text schreiben kann. Eine Formatierung oder das Einfügen von Bildern ist nicht möglich.

Als essentielles Werkzeug ist ein Texteditor praktisch Teil der Standard-Installation von vielen Betriebssystemen:

- Linux :z.B. [gedit][], [Kate][], [Vim][], [Emacs][], [ed][]
- macOS: [TextEdit][], [Vim][], [Emacs][], [ed][]
- Windows [Notepad][]

[ed]: https://www.gnu.org/fun/jokes/ed-msg.html
[emacs]: https://en.wikipedia.org/wiki/Emacs
[gedit]: https://en.wikipedia.org/wiki/Gedit
[kate]: https://en.wikipedia.org/wiki/Kate_(text_editor)
[notepad]: https://en.wikipedia.org/wiki/Windows_Notepad
[textedit]: https://en.wikipedia.org/wiki/TextEdit
[vim]: https://en.wikipedia.org/wiki/Vim_(text_editor)

Theoretisch wäre es also möglich z.B. einfach Notepad zu verwenden und darin zukünftige Programmier-Projekte zu verwirklichen.

![](Pictures/Notepad.png)

In der Praxis verwendet man aber üblicherweise einen speziell für die Programmierung angepassten Texteditor (manchmal auch Code-Editor genannt).

### Command Line

Während man heutzutage als Anwender meist eine grafische Benutzeroberfläche (GUI: Graphical User Interface) verwendet ist es als Programmierer üblich für viele Aufgaben in einer text-basierten Oberfläche (CLI: Command Line Interface) zu erledigen. Diese hat den Vorteil, dass man hier (wesentlich leichter als in einem GUI) Schritte (wiederum mittels Programmierung) automatisieren kann.

Um eine kleine Einführung in eine text-basierte Oberfläche zu geben schauen wir uns hier einmal an wie man unter Windows einen Texteditor mittels CLI installiert. Dazu installieren wir als erstes [„Windows Terminal“](https://github.com/microsoft/terminal) in der Powershell (einem Interpreter für die Programmiersprache PowerShell).

1. Das Programm PowerShell öffnen
2. Den folgenden Text (Code) in das PowerShell-Fenster einfügen

   ```sh
   winget install --id=Microsoft.WindowsTerminal -e
   ```

   und dann mittels <kbd>⏎</kbd> (Return) ausführen.

   - Bei `winget` handelt es sich hierbei um ein Programm (**Befehl**) zum Suchen und Installieren von Software, die in diesem Zusammenhang auch als **Paket** bezeichnet wird.
   - Mit dem **(Sub-)Befehl** (Argument) `install` teilt man `winget` mit, dass es ein Paket installieren soll.
   - Der Name des Pakets wird mit der (Long-)**Option** (`--`) `id` mit dem **Argument** `Microsoft.WindowsTerminal` spezifiziert
   - Die (Short-)**Option** (`-`) `e` wiederum gibt an, dass das das genau (exakt) das Paket `Microsoft.WindowsTerminal` installiert werden soll

3. Zeit zum auf die Schulter klopfen, nachdem du im 2. Schritt (wahrscheinlich) dein erstes PowerShell-„Programm“ geschrieben hast

Um zu sehen ob die Installation von „Windows Terminal“ funktioniert hat suchen wird nach dem Programm Windows Terminal (einem mehr oder weniger modernerer Ersatz des Programms PowerShell) und führen es aus.

![](Pictures/Windows%20Terminal.png)

Nun wollen wir in einem zweiten Schritt einen Code-Editor installieren. Ein beliebtest Programm ist dabei [Visual Studio Code](https://github.com/microsoft/vscode) von Microsoft.

1. Da wir nicht genau wissen wie das Paket für Visual Studio heißt suchen wir mit dem Befehl Kommando/Argument `search` nach dem Paket

   ```sh
   winget search 'Visual Studio Code'
   ```

   Die Gänsefüßchen (Single Quotes) sorgen dabei dafür, dass der Text als als Ganzes interpretiert wird und nicht als die 3 Argumente `Visual`, `Studio` und `Code`.

2. Die Ausgabe des obigen Befehls/Code sollte nun die gefunden Pakete/Software anzeigen

### Interpreter/Compiler

### IDE
