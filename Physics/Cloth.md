# Cloth-Physik-Attribute in Blender

Die Cloth-Physik in Blender simuliert realistische Stoffbewegungen, indem sie ein Netz von virtuellen Federn und Dämpfungskräften verwendet. Anhand der folgenden Kategorien kannst du die Materialeigenschaften, das Innenleben und den Einfluss äußerer Kräfte präzise steuern.

---

## 1. Physical Properties (Physikalische Eigenschaften)

Diese Einstellungen definieren die grundlegenden Materialeigenschaften deines Stoffes.

- **Vertex Mass (Punktmasse)**  
  *Beschreibung:* Bestimmt das Gewicht jedes einzelnen Vertices (Stoffpunkt).  
  *Wertbedeutung:*  
  - Niedrige Werte bewirken einen leichten, luftigen Stoff.  
  - Hohe Werte resultieren in einem schweren, träge reagierenden Material.

- **Air Viscosity (Luftviskosität)**  
  *Beschreibung:* Simuliert den Widerstand, den der Stoff in einer "dicken" Luft oder Flüssigkeitsumgebung erfährt.  
  *Wertbedeutung:*  
  - Ein höherer Wert verlangsamt das Fallen des Stoffes, indem er die Bewegung dämpft.

- **Bending Model (Biegungsmodell)**  
  *Beschreibung:* Legt fest, wie das Biegen des Stoffes berechnet wird.  
  *Optionen:*  
  - **Linear:** Nutzt lineare Federn zwischen den Punkten – traditionell und weniger rechenintensiv.  
  - **Angular:** Berücksichtigt Winkelabweichungen zwischen den Flächennormalen – führt zu realistischeren Falten und Biegungen.

- **Stiffness & Damping (Steifigkeit & Dämpfung)**  
  Diese Parameter bestimmen, wie widerstandsfähig der Stoff gegen verschiedene Deformationen ist und wie schnell überschüssige Schwingungen abgebaut werden:
  
  - **Tension (Zugsteifigkeit):**  
    *Beschreibung:* Regelt, wie stark der Stoff sich gegen das Strecken wehrt.  
    *Wertbedeutung:*  
    - Niedrig: Stoff dehnt sich leicht.  
    - Hoch: Stoff behält eher seine ursprüngliche Länge.

  - **Compression (Kompressionssteifigkeit):**  
    *Beschreibung:* Bestimmt, wie sehr der Stoff gegen das Zusammendrücken schützt.  
    *Wertbedeutung:*  
    - Niedrig: Leicht zusammengedrückt, was weiche Materialien simuliert.  
    - Hoch: Hält den Stoff flach und widerstandsfähig gegen Stöße.

  - **Structural (Gesamtsteifigkeit):**  
    *Beschreibung:* Eine übergreifende Einstellung, die das allgemeine Verhalten des Stoffes in Bezug auf interne Spannungen beeinflusst.

  - **Shear (Scherverformungswiderstand):**  
    *Beschreibung:* Bestimmt, wie stark der Stoff seitliche Verzerrungen widersteht.  
    *Wertbedeutung:*  
    - Niedrig: Leicht verschiebbare Stofffäden.  
    - Hoch: Verhindert das zerlaufen der Struktur.

  - **Bending (Biege-Steifigkeit & Wrinkle Coefficient):**  
    *Beschreibung:* Reguliert, wie stark der Stoff gegen Biegung und das Entstehen von Falten  resistiert.  
    *Wertbedeutung:*  
    - Niedrig: Leicht faltender, verformbarer Stoff.  
    - Hoch: Stabilere, weniger verformbare Flächen.

  - **Damping-Werte (Dämpfung beim Strecken, Komprimieren etc.):**  
    *Beschreibung:* Reduziert überschießende Schwingungen in den jeweiligen Deformationsmodi (Tension, Compression, Shear, Bending).  
    *Wertbedeutung:*  
    - Höhere Dämpfung bewirkt, dass Bewegungen ruhiger und weniger nachhallend ablaufen.

---

## 2. Internal Springs (Interne Federn)

Diese Einstellungen aktivieren und konfigurieren zusätzliche interne Verbindungen zwischen den Mesh-Vertices, um das Verhalten bei 3D-Deformationen anzupassen.

- **Aktivierung der internen Federn:**  
  *Beschreibung:* Schaltet den Einsatz interner Federn ein, um den Stoff bei inneren Belastungen ähnlich wie ein Soft Body zu verhalten.

- **Max Spring Creation Length (Maximale Federnlänge):**  
  *Beschreibung:* Legt fest, wie weit zwei Punkte maximal voneinander entfernt sein dürfen, um noch einen Federanschluss zu bilden.  
  *Wertbedeutung:* Ein Wert von 0 deaktiviert ggf. die Längenbegrenzung.

- **Max Creation Diversion (Maximale Abweichung):**  
  *Beschreibung:* Bestimmt den zulässigen Winkel, um vom Vertex-Normal abzuweichen, wenn Federn erstellt werden.  
  *Wertbedeutung:* Größere Winkel erlauben flexiblere Federnetzwerke.

- **Check Surface Normals (Oberflächennormalen prüfen):**  
  *Beschreibung:* Erzwingt, dass die verbundenen Punkte entgegengesetzte Normalrichtungen haben, was zu realistischeren internen Kräften führt.

- **Tension & Compression (bei internen Federn):**  
  *Beschreibung:* Analog zu den externen Einstellungen wirken diese Parameter lokal auf die internen Federn, um deren Verhalten beim Strecken und Komprimieren zu steuern.  
  *Wertbedeutung:* Kann zusätzlich per Vertex Group variiert werden, um gezielte Bereiche weicher oder steifer zu machen.

---

## 3. Pressure (Innendruck)

Diese Parameter ermöglichen die Simulation von weichen, druckgefüllten Objekten wie Ballons oder aufblasbaren Kissen.

- **Pressure (Druck):**  
  *Beschreibung:* Ein einheitlicher Druck, der kontinuierlich auf die Stoffoberfläche wirkt.  
  *Wertbedeutung:*  
  - Positive Werte bewirken eine Aufblähung des Stoffes.  
  - Negative Werte können zu einem Einfallen führen.

- **Pressure Scale (Druckskalierung):**  
  *Beschreibung:* Skaliert den Einfluss des angewendeten Drucks, um subtile oder dramatische Effekte zu erzielen.

*Hinweis:* Bei nicht-manifold Meshes kann der Druck "entweichen", weshalb oft der Einsatz von Vertex Groups hilfreich ist, um unerwünschte Bereiche auszuschließen.

---

## 4. Collisions (Kollisionen)

Diese Einstellungen optimieren die Interaktion des Stoffes mit sich selbst und anderen Objekten in der Szene.

- **Self-Collision (Selbstkollision):**  
  *Beschreibung:* Sorgt dafür, dass sich die Stoffteile nicht in die Quere kommen und unnatürliche Überlappungen vermieden werden.

- **Collision Distance (Kollisionsabstand):**  
  *Beschreibung:* Definiert einen minimalen Abstand zwischen Stoffpunkten, um das Eindringen zu verhindern.  
  *Wertbedeutung:*  
  - Niedrige Werte ermöglichen detailliertere Kollisionen, erfordern aber mehr Rechenleistung.  
  - Höhere Werte erhöhen die Stabilität auf Kosten feinerer Kollisionseffekte.

- **Collision Friction (Kollisions-Reibung):**  
  *Beschreibung:* Bestimmt, wie stark Reibungseffekte zwischen kollidierenden Flächen auftreten.  
  *Wertbedeutung:*  
  - Höhere Werte führen zu geringerer Gleiteigenschaft und mehr "Haftung" beim Zusammenstoßen.

---

## 5. Cache

Hier werden die Simulationsergebnisse gespeichert, sodass Blender die Berechnungen nicht in jedem Frame neu durchführen muss.

- **Baking/Cache:**  
  *Beschreibung:* Speichert die berechnete Simulation (Frames) – ideal für die Vorschau und den finalen Render.  
  *Wertbedeutung:*  
  - Durch "Baking" wird die Simulation konsistent wiedergegeben und Rechenleistung bei Wiederholungen gespart.

- **Quality Steps & Speed Multiplier:**  
  *Beschreibung:* Parameter, die definieren, wie viele Sub-Steps pro Frame berechnet werden und wie schnell die Simulation ablaufen soll.  
  *Wertbedeutung:*  
  - Mehr Quality Steps bedeuten genauere Simulationen, erhöhen jedoch die Renderzeit.

---

## 6. Shape

Dieser Bereich steuert, wie der ursprüngliche Mesh-Zustand in die Simulation einfließt bzw. welchen Einfluss dieser Zustand als "Referenz" behält.

- **Vertex Pinning (Über Vertex Groups):**  
  *Beschreibung:* Ermöglicht es, bestimmte Bereiche des Stoffes an ihrer Ausgangsposition zu verankern.  
  *Wertbedeutung:*  
  - Mit höheren Pinning-Werten bleiben die markierten Bereiche fester und beeinflussen das Gesamtdynamikverhalten.

- **Shape Matching/Stiffness:**  
  *Beschreibung:* Steuert, wie sehr der Stoff versucht, zu seiner ursprünglichen Form zurückzukehren, obwohl äußere Kräfte wirken.

---

## 7. Property Weights

Mit diesen Einstellungen kannst du die physikalischen Eigenschaften über Vertex Groups differenziert auf einzelne Bereiche des Stoffes anwenden.

- **Mass, Structural, Shear, Bending usw.:**  
  *Beschreibung:* Jeweilige Gewichte erlauben es, z. B. Bereiche mit höherer oder geringerer Steifigkeit, Dämpfung oder Masse zu versehen.  
  *Wertbedeutung:*  
  - Ermöglicht lokal differenziertes Materialverhalten – ideal, wenn der Stoff an bestimmten Stellen mehr Flexibilität oder Stabilität aufweisen soll.

---

## 8. Field Weights

Diese Werte regulieren den Einfluss von externen Kraftfeldern (wie Wind, Turbulenzen oder Gravitation) auf die Stoffsimulation.

- **Field Weight Multipliers:**  
  *Beschreibung:* Numerische Multiplikatoren, die bestimmen, wie stark externe Felder (z. B. Wind, Magnetfelder oder Vortex-Effekte) den Stoff beeinflussen.  
  *Wertbedeutung:*  
  - Höhere Werte führen zu einer stärkeren Reaktion auf externe Kräfte, während niedrigere Werte den Einfluss dämpfen.

---