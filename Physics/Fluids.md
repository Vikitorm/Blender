# Fluid-Physik-Attribute in Blender

Die Fluid-Physik in Blender ermöglicht die Simulation von Flüssigkeiten und Gasen, einschließlich Wasser, Rauch und Feuer. Die folgenden Attribute und Einstellungen helfen dir, die Simulation präzise zu steuern.

---

## 1. Domain (Simulationsbereich)
- **Beschreibung:**  
  Der Domain definiert den Raum, in dem die Fluid-Simulation stattfindet. Alle Berechnungen und Interaktionen sind auf diesen Bereich beschränkt.
- **Wichtige Parameter:**  
  - **Resolution Divisions:**  
    Bestimmt die Detailgenauigkeit der Simulation. Höhere Werte erzeugen feinere Details, erhöhen jedoch die Rechenzeit.  
  - **Time Scale:**  
    Regelt die Geschwindigkeit der Simulation. Niedrige Werte verlangsamen die Bewegung, während höhere Werte sie beschleunigen.  
  - **Border Collisions:**  
    Legt fest, wie die Fluidbewegung an den Rändern der Domain behandelt wird (z. B. freie Bewegung oder Begrenzung).

---

## 2. Flow (Flüssigkeitsquelle)
- **Beschreibung:**  
  Flow-Objekte sind die Quellen, aus denen Flüssigkeit oder Gas emittiert wird.
- **Wichtige Parameter:**  
  - **Flow Type:**  
    Wähle zwischen Flüssigkeit, Rauch, Feuer oder einer Kombination.  
  - **Initial Velocity:**  
    Gibt der emittierten Flüssigkeit eine Anfangsgeschwindigkeit, um dynamische Bewegungen zu erzeugen.  
  - **Density:**  
    Bestimmt die Dichte des emittierten Materials, was sich auf die Interaktion mit anderen Objekten auswirkt.

---

## 3. Effector (Interaktionsobjekte)
- **Beschreibung:**  
  Effector-Objekte beeinflussen die Fluidbewegung, indem sie Hindernisse oder Kräfte erzeugen.
- **Wichtige Parameter:**  
  - **Collision Type:**  
    Legt fest, ob das Fluid reflektiert, absorbiert oder durch das Objekt hindurchfließt.  
  - **Friction:**  
    Beeinflusst, wie stark das Fluid durch das Objekt abgebremst wird.  
  - **Stickiness:**  
    Bestimmt, wie stark das Fluid an der Oberfläche des Objekts haftet.

---

## 4. Viscosity (Viskosität)
- **Beschreibung:**  
  Die Viskosität regelt die Fließfähigkeit des Fluids.  
- **Wichtige Parameter:**  
  - **Low Viscosity:**  
    Simuliert dünne Flüssigkeiten wie Wasser.  
  - **High Viscosity:**  
    Simuliert dicke Flüssigkeiten wie Honig oder Lava.

---

## 5. Buoyancy (Auftrieb)
- **Beschreibung:**  
  Regelt, wie stark das Fluid durch Schwerkraft und Dichteunterschiede beeinflusst wird.  
- **Wichtige Parameter:**  
  - **Buoyancy Density:**  
    Höhere Werte bewirken, dass leichteres Material schneller aufsteigt.  
  - **Heat Buoyancy:**  
    Simuliert den Auftrieb durch Temperaturunterschiede, z. B. bei Rauch oder Feuer.

---

## 6. Surface Tension (Oberflächenspannung)
- **Beschreibung:**  
  Bestimmt, wie stark das Fluid dazu neigt, sich zusammenzuziehen und glatte Oberflächen zu bilden.  
- **Wichtige Parameter:**  
  - **High Tension:**  
    Erzeugt runde Tropfen und stabile Formen.  
  - **Low Tension:**  
    Führt zu unregelmäßigen und dynamischen Bewegungen.

---

## 7. Interaction Radius (Interaktionsradius)
- **Beschreibung:**  
  Legt fest, wie weit Fluidpartikel voneinander entfernt sein können, um miteinander zu interagieren.  
- **Wichtige Parameter:**  
  - **Small Radius:**  
    Erzeugt detaillierte, eng verbundene Simulationen.  
  - **Large Radius:**  
    Führt zu groberen, weniger präzisen Bewegungen.

---

## 8. Advanced Settings (Erweiterte Einstellungen)
- **Beschreibung:**  
  Zusätzliche Optionen für komplexe Simulationen.  
- **Wichtige Parameter:**  
  - **Variable Viscosity:**  
    Ermöglicht unterschiedliche Viskositäten innerhalb der Simulation, z. B. für Mischungen aus Wasser und Öl.  
  - **Adaptive Domain:**  
    Passt die Größe der Domain dynamisch an, um Rechenressourcen zu sparen.  
  - **Mesh Generation:**  
    Erstellt ein Mesh aus der Fluidoberfläche für realistische Renderings.

---

## 9. Cache
- **Beschreibung:**  
  Speichert die Simulationsergebnisse, um die Wiedergabe zu beschleunigen.  
- **Wichtige Parameter:**  
  - **Bake:**  
    Berechnet die Simulation und speichert sie für die Vorschau und den finalen Render.  
  - **Compression:**  
    Reduziert die Dateigröße des Caches, um Speicherplatz zu sparen.

---

## 10. Field Weights (Kraftfelder)
- **Beschreibung:**  
  Regelt den Einfluss von externen Kräften wie Wind, Magnetfeldern oder Gravitation auf das Fluid.  
- **Wichtige Parameter:**  
  - **Gravity:**  
    Bestimmt, wie stark die Schwerkraft das Fluid beeinflusst.  
  - **Wind:**  
    Simuliert den Einfluss von Luftströmungen auf Rauch oder Flüssigkeit.