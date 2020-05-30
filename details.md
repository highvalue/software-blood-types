# Weiterführende Gedanken zu Software-Bluttypen 


Rhesus-Faktor:

```
+ = Logik
- = keine Logik
```

Antigene:
```
D = Domäne
A = Adapter (Ap=Provider, Ag=Gate)
T = Technik
U = Utility
I = Integration
```

Sichtbar in einer Softwarezelle sind erstmal nur D und A.

Da es zwischen den Modulen aber keine funktionalen Abhängigkeiten gibt, müssen sie zusammengehalten werden. Das machen I Module. Das sind Application und Message Handling.
A Module sind per definitionem techniknah. Sie verbergen die Kommunikation mit der Umwelt, für die Technik nötig ist. Solange der Technikaufwand gering ist, reicht ein Modul. Wenn er größer wird, muss vom A Modul ein T Modul abgespalten werden. Dann entsteht eine Abstraktionshierarchie, die schrittweise technische Daten in Domänendaten wandelt u umgekehrt. Das sind sozusagen OSI Layer. Typischerweise besteht ein Adapter dann aus:

- Validation - das hat mit D zu tun
- Mapping - das kann man als U ansehen
- API-Ansteuerung - hier steckt das T

Ein Adapter ist also eine Mischung. Das ist auch natürlich, denn er stellt ja eine Grenze da. Adapter konstituieren die Membran der Softwarezelle.

Auf hoher Flughöhe reicht es, von A zu sprechen. Wenn man näher kommt, kann mann D, U, T unterscheiden.

Am Ende löst sich also A auf. Es gibt kein A, sondern nur D,T,U,I

Die Domäne zerfällt gern in Domänenservices (Ds. haben Daten) und Domänendaten (Dd, sind Daten; von Entität u Aggregat sprechen erstmal nicht).

Wo immer Verschiedenes zusammenspielen soll, braucht es I. Die großen Brocken, die pauschal in der Softwarezelle zu sehen sind, werden von den großen Interationen zusammengehalten: App und MH.

Aber wann immer irgendein Belang zerlegt wird, entsteht wieder die Notwendigkeit für Integration! Das macht die Fraktalität aus.

Wenn A in D,U,T zerfällt, dann braucht es I, um die Teile zusammenzuhalten. Nur so können Abstraktionsebenen entstehen:

```
Level0: technischer I/O
Level1: mapped I/O
Level2: validated I/O
Module haben jeweils nur einen Fokus, was R+ u R- angeht. 
```

Aber bei Funktionen ist das Ziel, reine Integrationen `f-` bzw. Operationen `f+` herzustellen. Hybride sind zu vermeiden (`f+-`).

Bei einem I Modul ist der Fokus natürlich Integration. `I-` zu schreiben, ist überflüssig. Aber bei Domänenmodulen kann es nützlich sein, den Rhesus-Faktor zu anzugeben: `D+` ist ein Domänenservice. Aber `D-` ist zb eine Domänenklasse, die integriert Vllt verbindet sie zwei `D+` Klassen.
