---
type: lecture-cy
title: "NN5 - Multilayer Perzeptron"
menuTitle: "NN5 - MLP"
author: "Canan Yıldız (Türkisch-Deutsche Universität)"
weight: 5
outcomes:
  - k2: "Multi-Layer Perzeptron (MLP): Graphische Darstellung, Vorwärtslauf"
  - k2: "Aktivierungsfunktionen (insbesondere ReLU)"
  - k3: "Vorwärtslauf (forward pass) für ein gegebenes MLP"
  - k3: "Berechnung der einzelnen Aktivierungen"
# readings:
#   - key: "Russell2020"
#     comment: "Kapitel 2 und 3"
#   - key: "Ertel2017"
# quizzes:
#   - link: XYZ
#     name: "Testquizz (URL from 'Invite more Players')"
assignments:
    - topic: sheet08
youtube:
    - link: "https://youtu.be/7ltwa5WWuKI"
      name: "NN5.1 - MLP Forward Propagation"
attachments:
  - link: "https://github.com/KI-Vorlesung/Lecture/blob/master/markdown/nn/files/NN5-MLP.pdf"
    name: "NN5-MLP.pdf"
---


## Kurze Übersicht

### Multilayer Perzeptron (MLP)
*   Das Perzeptron kann nur linear separable Daten korrekt klassifizieren.
*   Durch das Zusammenschließen von mehreren Perzeptronen kann man ein mehrschichtiges Perzeptron (engl. Multilayer Perceptron) aufstellen, das komplexere Funktionen modellieren kann.
*   Ein MLP wird oft auch als **Feed Forward Neural Network** oder  als **Fully Connected Neural Network** bezeichnet.
*   Die "inneren" Schichten eines solchen Netzwerkes sind sogenannte **versteckte Schichten** (engl. hidden layer). Das sind alle Schichten ausgenommen die Eingangs- und Ausgangsschicht.

### Graphische Übersicht und Vorwärtslauf
*   Ein Multi-Layer Perzeptron
    ![](images/mlp.png)
    Ein Vorwärtslauf (forward pass):
    $$ a^{[1]} = ReLU \left( W^{[1]} \cdot \mathbb{x} + b^{[1]} \right) \tag{1}$$
    $$ \hat{y} := a^{[2]} = \sigma \left( W^{[2]} \cdot a^{[1]} + b^{[2]} \right) \tag{2}$$



