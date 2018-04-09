# Bedingtes ausführen

[Zurück zum vierten Abschnitt](04Eingaben.md) | [Zurück zur ersten Seite](README.md)

Alle Programmiersprachen bieten die Möglichkeit, einen Befehl nur dann auszuführen, wenn eine bestimmte Bedingung eintritt.
In Python tritt eine Bedingung ein, wenn sie Wahr (`True`) ist - oder zu `True` ausgewertet wird.
Sie tritt nicht ein, wenn sie zu `False` ausgewertet wird.

Ein einfaches Beispiel ist somit:

```python
>>> if True:
...     print("wird angezeigt")
...
wird angezeigt
```

Das `if` in diesem Beispiel ist das Kommando, welches den bedingten Aufruf einleitet. Das `True` ist die Bedingung.
In diesem Fall also die Immer wahre Bedingung - man könnte stattdessen auch `1==1` schreiben.
Nun folgt ein **Doppelpunkt**. Die nächste Zeile wird eingerückt. Der `print`-Befehl gibt einfach das ihm zwischen Klammern übergebene aus. Ausgaben, also etwas was das Programm geschrieben hat, haben keine Punkte oder Pfeile am Anfang der Zeile.
Wird nun die Eingabe durch zweimaliges drücken von `Enter` bestätigt, erscheint, wie erwartet, der Text `wird angezeigt`.

> ### Übungen
> 1. Schreiben Sie ein `if`, welches eine wahre Bedingung hat und mit print `"Wahr"` ausgibt
> 2. Schreiben Sie ein `if`, welches eine unwahre Bedingung hat und mit print `"Unwahr"` ausgibt
> 
> Was gibt das erste, was gibt das zweite aus?

## Kurze Bemerkung zur **Einrückung**

Python verwendet verschieden starke Einrückungen, um die Zusammengehörigkeit von Befehlen zu markieren. Ist also zum Beispiel eine Zeile nach dem `if` Befehl mehr eingerückt als das `if` selbst, so gehört diese Zeile zu diesem `if`. Einrückungen sind immer notwendig nach einem Doppelpunkt und andersherum sind Doppelpunkte immer notwendig vor Einrückungen. Auch innerhalb eines eingerückten Bereiches kann wieder ein `if` vorkommen. Der Eingerückte teil des inneren `if`s muss dann noch weiter eingerückt werden.

> ### Merke
> Immer einrücken nach einem Doppelpunkt und immer wenn `Thonny` nicht automatisch einrückt, wo es eigentlich einrücken sollte, fehlt davor ein Doppelpunkt.

Beispiel:

```python
>>> if 1 == 1:
       if 5 == 6:
           print("fünfundsechs")
       print("einsundeins")

einsundeins
```

In einer grafischen Programmiersprache `scratch` wird der obere Code so dargestellt, dass deutlicher ist, was wie zusammen gehört.

![Geschachteltes If in Scratch](img/ifInScratch.png)

Das `if`, welches zu falls übersetzt wird, ist eine Klammer. Alles was innerhalb dieses `if`s ist, wird nur ausgeführt, wenn die Bedingung des `if`s zutrifft. Dieses "innerhalb" wird in Python durch "stärker eingerückt", also mehr Leerzeichen am Anfang der Zeile deutlich gemacht. Natürlich kann auch innerhalb eines `if`s ein zweites `if` stehen.

## Wenn → Dann → Ansonsten

Oft wird es benötigt, dass ein bestimmter Befehl ausgeführt wird, wenn eine Bedingung zutrifft, ansonsten ein anderer Befehl. Der Befehl hierzu ist `else`. Auch auf `else` folgt ein Doppelpunkt und weitere eingerückte Befehle.

> Notiz: Sowohl nach `if` als auch nach `else` muss mindestens ein eingerückter Befehl kommen. Also man kann  im folgenden Beispiel **keines** der beiden `print`s weglassen (man kann sie aber durch beliebige andere Befehle ersetzen).

```python
>>> if False:
...     print("wird nicht gezeigt")
... else:
...     print("wird gezeigt")
...
wird angezeigt
```
Logischerweise ist `else` nur nach einem fertigen `if` sinnvoll. Man sieht durch die `>>>`, das if beginnt den Befehl und alles weitere ist Teil dieses Befehls, was durch `...` gezeigt wird.

Alternativ kann man natürlich auch eine wahre Bedingung einstellen, welche dem Text in `print` widerspricht. Man sieht hier, dass dem Computer die Bedeutung der Worte völlig gleichgültig ist er folgt nur der Logik der Befehle:

```python
>>> if True:
...     print("wird nicht gezeigt")
... else:
...     print("wird gezeigt")
...
wird nicht angezeigt
```

> ### Aufgabe
> 1. Schreibe ein if, welches als Bedingung `True` hat und im Wahrheitsfall `"richtig so!"` ausgibt.
> 2. Schreibe ein if, welches als Bedingung `False` hat und im Sonstfall `"Sonstfall False"` ausgibt.

# Bedingungungen schreiben

Neben den normalen Rechenoperationen kann Python auch Vergleichsoperationen. Diese geben immer entweder wahr oder falsch zurück:

| Operator (Zeichen) | ist `True`(wahr) wenn... |
| `A == B` | A ist gleich wie B |
| `A < B` | A ist kleiner als B |
| `A > B` | A ist größer als B |
| `A != B` | A ist ungleich B |
| `A <= B` | A ist kleiner oder gleich B |
| `A >= B` | A ist größer oder gleich B |

Außerdem kann man noch zwei Wahrheitswerte mit den folgenden Befehlen kombinieren:

| Operator (Zeichen) | ist `True`(wahr) wenn... |
| `A and B` | ist wahr, wenn A und B wahr sind |
| `A or B` | ist wahr, wenn A oder B oder beide wahr sind |
| `not A` | ist wahr, wenn A unwahr (`False`) ist |

> ### Übung
> sind die folgenden Ausdrücke `True` oder `False`?
> 1. `5 < 6`
> 1. `5 != 6`
> 1. `5 <= 6`
> 1. `True and True`
> 1. `False or True`
> 1. `3 < 4 and 4 < 5`
> 1. `not (3 != 4)`
>
> Prüfen Sie die Ergebnisse, die Sie im Kopf herausgefunden haben mit Python nach.

# Kombinieren mit dem bisher gelernten

Natürlich kann dieses `if` mit allem zuvor gelernten und mit allem kommenden kombiniert werden. Die folgenden Beispiele kombinieren den `input`-Befehl mit den `if`-Abfragen.


# Beispiel: ein Grußprogramm

Ein Programm, das auf `hallo` und `tschüss` unterschiedlich reagiert:

```python
gru = input("Welcher gruß? ")
if gru == "hallo":
     print("Guten Tag")
elif gru == "tschüss":
     print("Auf Wiedersehen")
else:
     print("Ich habe Sie leider nicht verstanden")
```
In diesem Beispiel wird eine weitere Option der `if`-Ausdrücke verwendet: `elif`. Dieses steht für `else if` und bedeutet: Falls nicht die erste Bedingung dann vielleicht diese Bedingung also am ehesten zu übersetzen mit "oder wenn". Zwischen einem `if` und einem `else` können beliebig viele `elif` stehen, aber vorher muss immer ein `if` und stehen.

Wird dies in eine Datei `gru.py` gespeichert und diese dann (zweimal) ausgeführt, so entsteht folgende Ausgabe:

```bash
>>> %Run gru.py
Welcher gruß? hallo
Guten Tag
>>> %Run gru.py
Welcher gruß? tschüss
Auf Wiedersehen
>>> %Run gru.py
Welcher gruß? tschau
Ich habe Sie leider nicht verstanden
```

## Beispiel: ein "Passwortprogramm"

Die nun  gestellte Aufgabe ist es ein Passwort zu erraten, welches im Programm festgelegt wird. Zunächst speichern wir das zu erratende Passwort in einer Variablen.
```python
geheim = "Döner"
```
Es werden drei Versuche gegeben das Passwort zu erraten unter Verwendung des Eingabe-Befehls aus dem vorherigen Abschnitt:
```python
geheim = "Döner"

if geheim == input("Versuch1: "):
    print("geschaft")
elif geheim == input("Versuch2: "):
    print("geschaft")
elif geheim == input("Versuch2: "):
    print("geschaft")
else:
    print("nicht geschafft")
```

Beispiel:
```
Versuch1: hi
Versuch2: Döner
geschaft
```

Dieses Programm ist natürlich nicht so, wie der Computer ein Passwort abfragen würde, da das Passwort für jeden lesbar im Programm steht. Normalerweise wird das Passwort nur verschlüsselt abgespeichert.

> ### Übungen
> Schreiben Sie ein Programm, welches 3 Versuche gewährt eine Zahl zu erraten.
> 
> Vorsicht beim Vergleichen: der Buchstabe einer Zahl ist nicht gleich der Zahl. Zum Beispiel ist `"2" == 2` unwahr also `False`. Um diese beiden Werte sinnvoll zu vergleichen, muss der Buchstabe `"2"` zur Zahl `2` konvertiert werden ([mehr](03Variablen.md#umwandlung-von-datentypen)). 

[Weiter zum nächsten Abschnitt](06Zufall.md) |