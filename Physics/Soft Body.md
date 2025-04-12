# Soft-Body-Attribute in Blender

In Blender ermöglicht das Soft-Body-System die Simulation von Objekten, die sich realistisch verformen und flexibel auf äußere Kräfte reagieren. Die folgenden Module und deren Parameter lassen sich individuell anpassen:

---

## 1. Masse
- **Beschreibung:**  
  Die Masse bestimmt das Gewicht jedes Einzelpunkts (Vertex) im Soft-Body und beeinflusst, wie stark das Objekt auf äußere Kräfte reagiert. Eine höhere Masse führt typischerweise zu mehr Trägheit.
- **Wertbedeutung:**  
  - **Niedrige Werte:** Leichtere und reaktionsschnellere Objekte.  
  - **Hohe Werte:** Schwerere Objekte, die träge auf Bewegungen reagieren.

---

## 2. Reibung (Friction)
- **Beschreibung:**  
  Dieser Parameter regelt, wie stark Bewegungen gedämpft werden, basierend auf der Wechselwirkung mit der Umgebung (z. B. Luft oder andere beteiligte Oberflächen).  
- **Wertbedeutung:**  
  - **Niedrig:** Wenig Widerstand, das Objekt gleitet nahezu ohne Verzögerung.  
  - **Hoch:** Deutlicher Dämpfungseffekt, wodurch das Objekt schneller langsamer wird.

---

## 3. Ziel (Goal)
- **Beschreibung:**  
  Der Zielparameter definiert, wie stark einzelne Punkte an ihrer animierten oder ursprungsdefinierten Position „festgehalten“ werden. Dies dient als eine Art Rückholkraft, damit das Objekt seine Form behält, auch wenn externe Kräfte wirken.
- **Wertbedeutung:**  
  - **0:** Die Punkte folgen vollständig der dynamischen Simulation.  
  - **1:** Die Punkte bleiben an der ursprünglichen Position nahezu fest verankert.

---

## 4. Kanten (Edges)
Die Kanten-Attribute simulieren die Federn, die die Vertices eines Meshs miteinander verbinden. Dadurch wird das interne Spannungsverhalten modelliert, was essenziell für Dehnung, Kompression und Biegung ist. Die wichtigsten Unterparameter sind:

### 4.1 Pull
- **Beschreibung:**  
  Bestimmt die Federsteifigkeit in Längsrichtung der Kante, also wie weit sich die Kante dehnen darf.
- **Wertbedeutung:**  
  - **Niedrig:** Sehr weiche, elastische Materialien (z. B. Gummi).  
  - **Hoch:** Steifere Verbindungen, die weniger dehnbar sind.

### 4.2 Push
- **Beschreibung:**  
  Regelt den Widerstand der Kante gegen das Zusammenziehen bzw. Komprimieren.
- **Wertbedeutung:**  
  - **Niedrig:** Erlaubt ein einfaches Zusammenrutschen der Kanten.  
  - **Hoch:** Verhindert ein zu starkes Zusammendrücken, was vor allem bei steifen oder aufgeblasenen Objekten wichtig ist.

### 4.3 Damp (Dämpfung)
- **Beschreibung:**  
  Reduziert Schwingungen, die durch die wechselwirkenden Kräfte beim Dehnen und Stauchen der Kanten entstehen.
- **Wertbedeutung:**  
  - **Höhere Werte:** Sorgen für eine stabilere Bewegung ohne übermäßiges Nachschwingen.

### 4.4 Plasticity (Plastizität)
- **Beschreibung:**  
  Ermöglicht dauerhafte Deformationen nach Überbeanspruchung oder Kollisionen.  
- **Wertbedeutung:**  
  - **0:** Das Objekt kehrt in seine ursprüngliche Form zurück.  
  - **Höhere Werte:** Das Objekt behält die veränderte Form bei.

### 4.5 Bending
- **Beschreibung:**  
  Führt zusätzliche virtuelle Verbindungen (z. B. diagonale Kanten) ein, um das Biegen oder Verformen des Materials zu kontrollieren.
- **Wertbedeutung:**  
  - Erhöhte Werte stabilisieren die Struktur und verhindern ein übermäßiges Zusammenbrechen bei seitlicher Krafteinwirkung.

### 4.6 Length
- **Beschreibung:**  
  Bestimmt, in welchem Umfang sich die Länge der Kanten verändern darf, wenn Kräfte darauf wirken.
- **Wertbedeutung:**  
  - **0 %:** Keine Längenänderung erlaubt.  
  - **Bis 100 %:** Volle Anpassung, sodass das Objekt schrumpfen oder sich ausdehnen kann.

### 4.7 Collision
- **Beschreibung:**  
  Legt fest, wie Kollisionen innerhalb des Soft-Body-Meshs und mit anderen Objekten erkannt und behandelt werden.
- **Wertbedeutung:**  
  - **Edge-Modus:** Prüft primär die Kanten auf Kollisionen mit zusätzlichen Dämpfungseffekten.  
  - **Face-Modus:** Nutzt Flächentests für eine genauere, wenn auch rechenintensivere Kollisionsabfrage.

### 4.8 Aerodynamics
- **Beschreibung:**  
  Simuliert den Einfluss von Luft- oder Fluidströmungen, die als Drag (Widerstand) oder Lift (Auftrieb) wirken können.
- **Wertbedeutung:**  
  - **Simple:** Erzeugt einen grundlegenden Luftwiderstandseffekt.  
  - **Lift Force:** Integriert einen Auftriebseffekt, der durch einen multiplikativen Faktor (typisch um 30) bestimmt wird.

### 4.9 Stiffness (bei Quad-Faces)
- **Beschreibung:**  
  Bei viereckigen Flächen wirken diagonale Kanten als Verstärkungsfedern, die verhindern, dass die Fläche unter Krafteinwirkung zusammenbricht.
- **Wertbedeutung:**  
  - Höhere Werte erhöhen die strukturelle Integrität der Flächen.

### 4.10 Shear
- **Beschreibung:**  
  Bestimmt die Scherfestigkeit der internen Federn in Quad-Faces, um seitliche Verformungen zu minimieren.
- **Wertbedeutung:**  
  - Höhere Werte verringern die Möglichkeit, dass das Mesh bei seitlichen Kräften verzerrt wird.

---

## 5. Dämpfung (Damping)
- **Beschreibung:**  
  Neben der spezifischen Dämpfung in den Kanten sorgt die globale Dämpfung für ein ruhigeres Gesamtverhalten des Soft-Body-Objekts. Sie reduziert allgemein Schwingungen und hilft, das System schneller zur Ruhe kommen zu lassen.
- **Wertbedeutung:**  
  - **Niedrige Werte:** Mehr dynamisches, freies Schwingen.  
  - **Höhere Werte:** Schnellere Stabilisierung und weniger Oszillation.

---

## 6. Kollisionen (Collisions)
- **Beschreibung:**  
  Aktiviert und steuert die Abfrage von Kollisionen des Soft-Body-Objekts, sowohl intern (Selbstkollision) als auch extern mit anderen Objekten.
- **Wertbedeutung:**  
  - Eine höhere Kollisionspräzision führt zu realistischeren Simulationen, kann jedoch rechenintensiver sein.  
  - Weitere Einstellungen, wie z. B. Kollisionsabstand oder -präzision, helfen, das Gleichgewicht zwischen Performance und Realismus zu finden.

---

## 7. Cache
- **Beschreibung:**  
  Der Cache speichert bereits berechnete Simulationsergebnisse, sodass beim Wiedergeben der Animation die Physik nicht jedes Mal neu simuliert werden muss.
- **Wertbedeutung:**  
  - Das "Baking" der Simulation ermöglicht schnelles Vorspulen und eine konsistente Wiedergabe der physikalischen Effekte.

---