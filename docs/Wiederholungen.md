# Wiederholungen

[Zurück zu Kapitel 8: Schildkröten](Turtle.md) |  [Inhaltsverzeichnis](README.md) |  [Weiter zu Kapitel 10: Mehrmaliges tun](Turtle-Wiederholungen.md) | 

Oftmals in einem Computerprogramm soll der Computer Dinge wiederholen. Eine Form der Wiederholung ist es etwas so lange zu wiederholen, bis eine Bedingung nicht mehr zutrifft. Die Bedingung wird dabei genauso geschrieben, wie dies bei `if` gemacht wurde.

## Der Befehl While
`while` wiederholt einen Programmteil so oft, bis die Bedingung nicht mehr zutrifft.

Ein abstraktes Beispiel:

```python
while <Bedingung>:
    print("ich werde wiederholt")
```

Der Aufbau des `while` ist identisch dem des `if` Befehls. Die Einleitung mit `while`, danach die Bedingung gefolgt von einem Doppelpunkt. In den nächsten Zeilen eingerückt die Befehle, die wiederholt werden sollen. Sollen mehrere Zeilen wiederholt werden, können auf das while mehrere eingerückte Zeilen folgen. Die Zugehörigkeit zu diesem while ist wie beim `if` durch die Einrückung definiert. Es kann auch innerhalb eines `while` noch ein `while` oder ein `if` vorkommen.

Ein konkretes Beispiel, welches immer wieder nach einer Eingabe fragt, bis `"ende"` eingegeben wurde:

```python
eingabe = input("Eingabe: ")
while not (eingabe == "ende"):
    print("Bei der Eingabe ", eingabe, "konnte ich kein ende finden")
    eingabe = input("Eingabe: ")
print("So, jetzt ist aber fertig.")
```

Hat je nach Eingaben folgende Ausgabe (das Programm wurde zwei mal gestartet):

```python
>>> %Run hallo.py
Eingabe: tut
Bei der Eingabe  tut konnte ich kein ende finden
Eingabe: Ende
Bei der Eingabe  Ende konnte ich kein ende finden
Eingabe: ende
So, jetzt ist aber fertig.
>>>
>>> %Run hallo.py
Eingabe: ende
So, jetzt ist aber fertig.
```

Es wird an diesem 2. Beispiel deutlich, dass die Wiederholung unter Umständen auch Null mal stattfindet. Es wird nämlich vor jedem Schleifenaufruf die Bedingung überprüft. Wird also schon beim ersten Mal eingeben `ende` eingegeben (der `input`-Befehl in der ersten Zeile im Beispiel), dann ist eingabe schon beim allerersten überprüfen gleich `ende` das heißt durch den Vergleich entsteht der Wahrheitswert `True` welcher durch den "nicht"-Befehl `not` zu `False` umgekehrt wird. Solange aus der Bedingung `True` entsteht werden die enthaltenen Befehle wiederholt. Da schon am Anfang `False` entsteht, wird das `print` und das zweite `input` kein einziges Mal ausgeführt, sondern einfach übersprungen und das letzte `print` zeigt seine Ausgabe. Dieses letzte `print` hat weniger Leerzeilen am anfang der Zeile und gehört damit nicht mehr zu dem `while`, wird also nicht mehr wiederholt.

> ### Übungen
> Kleine Beispiel in die Datei `solang.py`:
>
> 1. Schreiben Sie eine `while`-Schleife, die immer fragt "warum soll ich?" erst bei der Eingabe "schluss jetzt!" beendet sich die Schleife.
> 1. Schreiben Sie eine Schleife, die wiederholt solange man "weiter" eingibt.

## Der Befehl for

For ist der Befehl, der "für jedes" wiederholt. Also zum Beispiel für jeden Buchstaben, oder für jede Zahl in einer Liste `[1,2,3,4,5]`.

```python
for i in "hallo":
    print(i * 5)
```

Produziert die folgende Ausgabe:

```
>>> %Run forletter.py
hhhhh
aaaaa
lllll
lllll
ooooo
```

Wie man am Ergebnis sehen kann speichert das `for` den ersten Buchstaben von `"hallo"` in die Variable `i` und führt dann damit das `print` aus. Es wird also fünf mal `h` ausgegeben.

Im nächsten Durchgang speichert das `for` in die selbe Variable `i` den zweiten Buchstaben von `"hallo"` und führt damit das `print` aus. Es erscheint `aaaaa`. Und so weiter.

Ziemlich gleich funktioniert das mit Zahlenlisten:

```python
for i in [1,2,3,4,5,6,7,8,9,524]:
    print(i * 5)
```

Ergibt die Ausgabe:

```
>>> %Run forletter.py
5
10
15
20
25
30
35
40
45
2620
```