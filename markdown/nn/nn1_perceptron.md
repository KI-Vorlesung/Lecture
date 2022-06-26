---
type: lecture-cy
title: "NN1 - Das Perzeptron"
menuTitle: "NN1 - Perzeptron"
author: "Canan Yıldız (Türkisch-Deutsche Universität)"
weight: 1
outcomes:
  - k2: "Arten des maschinellen Lernens"
  - k2: "Formalisierung eines ML-Problems, insbesondere Klassifizierung: Datensatz, Merkmalraum, Hyphotesenfunktion, Zielfunktion"
  - k2: "Perzeptron als linearer Klassifizierer"
  - k2: "Entscheidungsgrenze"
  - k3: "Berechnung der Entscheidungsgrenze"
  - k3: "Perzeptron Lernalgorithmus"
# readings:
#   - key: "Russell2020"
#     comment: "Kapitel 2 und 3"
#   - key: "Ertel2017"
# quizzes:
#   - link: XYZ
#     name: "Testquizz (URL from 'Invite more Players')"
assignments:
    - topic: sheet06
youtube:
    - link: "https://youtu.be/IJdiwITTC9Y"
      name: "NN1.1 - Einführung"
    - link: "https://youtu.be/oWcvFyLgqYc"
      name: "NN1.1 - Einführung"
    - link: "https://youtu.be/ZvWpI0Doocc"
      name: "NN1.3 - Das Perzeptron Modell"
    - link: "https://youtu.be/8Rdw2NBCCJk"
      name: "NN1.4 - Perzeptron Beispiel"
    - link: "https://youtu.be/JD8Qsg8_kQI"
      name: "NN1.5 - Der Perzeptron Lernalgorithmus"
attachments:
  - link: "https://github.com/KI-Vorlesung/Lecture/blob/master/markdown/nn/files/NN1-Das_Perzeptron.pdf"
    name: "NN1-Das_Perzeptron.pdf"
---


## Kurze Übersicht

### Definition "Maschinelles Lernen"
Fähigkeit zu lernen, ohne explizit programmiert zu werden. (Arthur Samuel, 1959)

### Arten des Lernens

*   Überwachtes Lernen (e.g. Klassifizierung, Regression)
*   Unüberwachtes Lernen (e.g. Clustering, Dimensionsreduktion)
*   Bestärkendes Lernen (e.g. Schach spielen)


### Formalisierung

*   Zielfunktion $f$
*   Merkmalraum (input space)
*   Ausgaberaum (output space)
*   Datensatz $ \mathcal{D} $
*   Hypothesenmenge $ \mathcal{H} $
*   Lernalgorithmus $ \mathcal{A} $


### Das Perzeptron
Ein einfaches Modell für die **binäre Klassifizierung**

*   Bilde gewichtete Summe (Linearkombination) der Merkmale
*   Vergleiche das Ergebnis mit einem Schwellenwert
    *   Positiv, falls über dem Schwellenwert
    *   Negativ, falls unter dem Schwellenwert
*   Gewichte und Schwellenwert sind unbekannte Parameter des Modells, die es zu lernen gilt > siehe **Perzeptron Lernalgorithmus**



