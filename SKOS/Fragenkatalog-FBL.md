# Fragenkatalog Systematik FBL

## Workflow

1. Wer aktualisiert und modifiziert die Systematik?
2. Wie ist der Workflow zur Aktualisierung der Systematik?
3. Muss die Systematik zwingend im Wiki gepeflegt werden?
4. Kann die Systematik in eine einzige gemeinsam pflegbare Tabelle überführt werden?
5. Wäre es denkbar einen Issue-basierten Workflow über unser Git-Repositorium für die Lokalsystematiken zu etablieren?
6. Wäre es denkbar, dass die Systematik direkt im SKOS-Code bearbeitet wird, wenn die Syntax und die Eintragsstruktur bekannt sind?
7. Wie können handschriftliche Anmerkungen in einem Ausdruck wieder in die digitale Version zurückfließen?
8. Können wir bei der Erstellung einer SKOS-Version der Systematik über den Issue-Tracker unseres Repositoriums für die Lokalsystematiken arbeiten?
9. Welche Anwendungen sollen durch die digitalisierte Version der Systematik (weiterhin/ erstmals) bedient werden können?

## Rückfragen zu den Tabellen im Wiki

- Die Systematik hat insgesamt vier Level (siehe unten)?
- Warum haben manche Systemstellen einen Kommentar über mehrere Tabellenzeilen?
- Ist es korrekt, dass die Ziffer für die Systemstellen auf unterschiedlichen Ebenen/Leveln der Systematik vorkommen kann (z.B. CD 740 Formale Grammatik und CD 740 Allgemeines)?
- Bezieht sich ein "siehe auch"-Kommentar in einer Kategroeie auf die nächsthöhere Systemstelle oder auf ein noch höheres Level? (z.B. CD 770: beziehen sich die auf diese Zeile folgenden Kommentare auf CD 770, auf CD 740 oder auf CD? --> Bezug auf CD insgesamt scheint mir am passendsten)
- Ist die Bezugnahme solcher Hinweise einheitlich geregelt oder kann sich dies von Systemstelle zu Systemstelle unterscheiden?
- Welche Bedeutung hat der Fettdruck in den Tabellen? Wir er konsequent angewendet oder gibt es Stellen, wo dies vergessen wurde? Wie ist das Verhältnis von z.B. CD 10 (kein Fetdruck) und CD 50 (Fettdruck)?  Wie das Verhältnis zwischen EM 300 (Fettdruck) und EM 500 (kein Fettdruck)?
- Gibt es weitere potentielle Stellen mit Missverständnispotential?

## Interpretation/ Strukturvorschlag

Die nachfolgende Interpretation der Systematik basiert auf der Version im TIB-Wiki und ist ggf. fehlerhaft.

|Systemstelle (L1)|Systemstelle (L2) | Systemstelle (L3) |Systemstelle (L4)|Inhalt|Hinweis|
|----|----|----|----|----|----|
| A ||||Informations- und bibliographischer Apparat, Buch- und Bibliothekswesen Hochschule, Studium, Beruf||
|A|AA|||Informationsapparat|||
|A|AA|100||Allgemein-Enzyklopädien||
|A|AA|100|110|Deutschsprachige Enzyklopädien||
|B||||Wörterbücher||
|B|BB|||Wörterbücher||
|B|BB|100||Deutsch||
|B|BB|100|120|Neuhochdeutsch, Frühneuhochdeutsch||
|C||||Allgemeine Sprach- und Literaturwissenschaft|
|C|CB|||Allgemeines zur Allgemeinen Sprachwissenschaft||
|C|CB|40||Gesamtdarstellungen|Festschriften siehe unter CZ 200|
|C|CD|||Geschichte der Allgemeinen Sprachwissenschaft||
|C|CD|740||Formale Grammatik|
|C|CD|740|740|Allgemeines||
|C|CD|740|770|Sonstige|Computerlinguistik siehe unter CK 600\|Geschichte der Rhetorik siehe unter CK 305\|Geschichte der Soziolinguistik siehe unter CJ 220|
|E||||
|E|EM|||Alt- und Mittelenglische Literatur|
|E|EM|10||Handbücher|
|E|EM|100||Literaturgeschichte|
|E|EM|300||Einzelne Gattungen
|E|EM|300|300|Allgemeines. Gattungsübergreifendes|
|E|EM|300|400|Lyrik|
|E|EM|900||Einzelne Autoren. Primär- und Sekundärliteratur
|E|EM|950||Anthologien. Textsammlungen|

## SKOS-Modelleriung - Vorschlag

```turtle
<https://www.example.com/2567485456> a skos:Concept ;
    skos:notation "A" ;
    skos:prefLabel "Informations- und bibliographischer Apparat, Buch- und Bibliothekswesen Hochschule, Studium, Beruf"@de ;
    skos:narrower <https://www.example.com/1548645456> .

<https://www.example.com/1548645456>  a skos:Concept ;
    skos:notation "AA" ;
    skos:prefLabel "Informationsapparat"@de ;
    skos:narrower <https://www.example.com/12415452312> .

etc.

```
