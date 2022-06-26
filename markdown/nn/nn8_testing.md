---
type: lecture-cy
title: "NN8 - Performanzanalyse"
menuTitle: "NN8 - Performanzanalyse"
author: "Canan Yıldız (Türkisch-Deutsche Universität)"
weight: 8
outcomes:
  - k2: "Performanzmetriken für die Evaluierung von Klassifizierungsmodellen"
  - k2: "Wahrheitsmatrix (engl. Confusion Matrix)"
  - k2: "Treffergenauigkeit (engl. Accuracy)"
  - k2: "Precision (engl. Precision)"
  - k2: "Recall"
  - k2: "$F_1$-Score (Harmonisches Mittel)"
  - k3: "Berechnung und Deutung von Precision und Recall"
  - k3: "Berechnung und Deutung des $F_1$-Scores"
  - k3: "Einsatz bei Evaluierung und Auswahl von Modellen"
# readings:
#   - key: "Russell2020"
#     comment: "Kapitel 2 und 3"
#   - key: "Ertel2017"
# quizzes:
#   - link: XYZ
#     name: "Testquizz (URL from 'Invite more Players')"
youtube:
    - link: "https://youtu.be/T-WYL28iwdU"
      name: "NN8.1 - Confusion Matrix"
    - link: "https://youtu.be/fpsNzn4Moow"
      name: "NN8.2 - Precision und Recall"
    - link: "https://youtu.be/Wx_HAuIXTAQ"
      name: "NN8.3 - Precision Recall Trade-off"
    - link: "https://youtu.be/UAV7EpdIe6Q"
      name: "NN8.4 - F1-Score"
    - link: "https://youtu.be/vsmoYiArtrA"
      name: "NN8.5 - Harmonisches Mittel- Intuition"
attachments:
  - link: "https://github.com/KI-Vorlesung/Lecture/blob/master/markdown/nn/files/NN8-Performanzanalyse.pdf"
    name: "NN8-Performanzanalyse.pdf"
---


## Kurze Übersicht

### Performanzmetriken für Klassifizierungsprobleme

#### Wahrheitsmatrix (engl. Confusion Matrix)
*   Gibt eine Übersicht über die Anzahl von richtig und falsch klassifizierten Datenpunkten (bei binärer Klassifizierung)
    *   $TP = $ # True Positives $ = $ Anzahl richtiger 1-Vorhersagen
    *   $FP = $ # False Positives $ = $ Anzahl falscher 1-Vorhersagen
    *   $FN = $ # False Negatives $ = $ Anzahl falscher 0-Vorhersagen
    *   $TN = $ # True Negatives $ = $ Anzahl richtiger 0-Vorhersagen
*   Bei Klassifizierungsproblemen mit $N$ Klassen hat man eine $N \times N$ Matrix, die in Position $(i,j)$ die Anzahl der Klasse-$j$-Beispiele enthält, die als Klasse-$i$ vorhergesagt wurden.

![Abbildung 1 - Wahrheitsmatrix bei binärer Klassifizierung](images/nn8-1.png)

#### Treffergenauigkeit (engl. Accuracy)
*   Anzahl richtig klassifizierter Datenpunkte, Erfolgsrate (engl. correct rate)
    $$ Accuracy = \frac{TP+TN}{TP+TN+FP+FN} $$

*   Accuracy vermittelt ein falsches Bild des Erfolges bei unausgewogenen Datensätzen \
    Beispiel:
    *   Klasse 1 hat 10, Klasse 0 hat 990 Beispiele.
    *   Ein Modell, das immer 0 ausgibt, hat $990/1000 = 0.99$ Treffergenauigkeit, ist aber offensichtlich kein gutes Modell!

#### Precision

*   Positive Predictive Value (PPV)
*   Antwort auf: Von allen **positiven Vorhersagen**, wie viele sind richtig?
    $$ Precision = \frac{TP}{TP + FP} $$
*   Wahrscheinlichkeit, dass ein positiv klassifiziertes Beispiel auch tatsächlich positiv ist.
*   Je näher an 1, desto besser.
*   Accuracy of **positive predictions**.

#### Recall

*   True Positive Rate, auch Sensitivität (engl. Sensitivity)
*   Antwort auf: Von allen **positiven Beispielen**, wie viele wurden richtig klassifiziert?
    $$ Recall = \frac{TP}{TP + FN} $$
*   Wahrscheinlichkeit, dass ein positives Beispiel tatsächlich als solches erkannt wird.
*   Je näher an 1, desto besser.
*   Accuracy of **positive examples**.

#### Precision-Recall Trade-off
*   Ein gutes Modell sollte hohe Precision und zugleich hohes Recall haben.
*   Man kann die Precision eines Modells beliebig erhöhen (durch das Vergrößern des Schwellenwertes bei der Klassifizierung), jedoch wird dabei der Recall abnehmen.
*   Genau so kann man den Recall eines Modells beliebig erhöhen (durch das Verkleinern des Schwellenwertes bei der Klassifizierung), jedoch wird dabei die Precision abnehmen.
*   Es gilt ein gutes Trade-off zu finden.
*   Eine Zwei-Zahlen-Metrik erschwert den Entscheidungsprozess bei Evaluierung und Modellauswahl.

#### $F_1$-Score (Harmonisches Mittel)

*   Fasst Precision (P) und Recall (R) in einer Metrik zusammen (Harmonisches Mittel von P und R):
    $$ F_1-Score = \frac{2}{\frac{1}{P} + \frac{1}{R}} = 2 \cdot \frac{PR}{P + R} $$
*   Der $F_1$-Score wird nur dann hoch sein, wenn P und R beide hoch sind.
*   Je näher an 1, desto besser.
*   Sehr kleine P und R Werte ziehen den $F_1$-Score sehr stark herunter. In dieser Hinsicht gibt diese Metrik ein akkurates Bild über den Erfolg eines Modells.
