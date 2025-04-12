# Rigid Body-Attribute in Blender

Blender’s Rigid Body-System simuliert feste Objekte, die sich realistisch unter dem Einfluss von Kräften, Kollisionen und Einschränkungen verhalten. Mit den folgenden Modulen und deren Parametern kannst du das Verhalten deiner Objekte präzise steuern.

---

## 1. Rigid Body Typ
- **Beschreibung:**  
  Legt fest, ob ein Objekt aktiv (dynamisch) oder passiv (statisch) in der Simulation agiert.
- **Typen:**
  - **Aktiv:**  
    Das Objekt wird durch physikalische Kräfte beeinflusst, reagiert auf Kollisionen und bewegt sich dynamisch.
  - **Passiv:**  
    Das Objekt bleibt unbewegt und dient als unveränderliche Bühne oder Hindernis in der Szene.

---

## 2. Masse
- **Beschreibung:**  
  Bestimmt die Trägheit des Objekts. Eine höhere Masse führt zu einer stärkeren Beharrung, was bedeutet, dass das Objekt schwerfälliger auf externe Kräfte und Kollisionen reagiert.
- **Wertbedeutung:**  
  - **Niedrige Masse:** Schnelle, agile Bewegungen und eine leichte Reaktion auf Kräfte.
  - **Hohe Masse:** Langsamere Reaktionen, erhöhte Stabilität und eine dominantere Wirkung bei Zusammenstößen.

---

## 3. Dynamik-Optionen
- **Dynamic (Dynamisch):**  
  Aktiviert, ob das Objekt von den physikalischen Simulationen betroffen ist – bei deaktiviertem Dynamic bleibt es unbeeinflusst.
- **Animated (Animiert):**  
  Ermöglicht, dass keyframe-basierte Animationen mit der Simulation koexistieren. Das Objekt folgt den animierten Bewegungen, während gleichzeitig die physikalischen Effekte berücksichtigt werden.

---

## 4. Kollisions-Einstellungen
Diese Parameter regeln, wie das Objekt mit anderen Objekten in Kollision tritt und wie genau diese Berührungen berechnet werden.

### 4.1 Kollisionsform
- **Beschreibung:**  
  Bestimmt, welche Geometrie als Grundlage für Kollisionen genutzt wird.
- **Optionen:**
  - **Box:**  
    Umgibt das Objekt mit einer einfachen Würfelform, ideal für rechtwinklige Objekte.
  - **Kugel:**  
    Nutzt eine kugelförmige Hülle, bei der der größte Achsenwert als Radius dient.
  - **Kapsel:**  
    Eignet sich für längliche Objekte, die in ihrer Mitte dicker und an den Enden abgerundet sein können.
  - **Zylinder / Kegel:**  
    Für symmetrische, zylinderartige oder kegelförmige Objekte, wobei Höhe und Radius anhand der Bounding-Box ermittelt werden.
  - **Mesh-basierte Formen:**  
    - **Convex Hull:**  
      Bildet eine konvexe Umhüllung, die die äußeren Punkte des Objekts einschränkt – effizient, jedoch weniger präzise bei komplexen Formen.
    - **Mesh:**  
      Nutzt die exakte Geometrie des Objekts, was zu genauen Kollisionsberechnungen führt, jedoch rechenintensiver und potenziell instabil bei komplizierten Meshes.
  - **Mesh-Quelle:**  
    - **Base:**  
      Verwendet das Originalmesh, ohne Modifikationen.
    - **Deform:**  
      Berücksichtigt auch Deformationen durch Modifier oder Shape Keys, was eine realistischere Kollisionsgeometrie liefert.

### 4.2 Kollisionsrand (Collision Margin)
- **Beschreibung:**  
  Fügt der Kollisionsform einen kleinen Puffer hinzu, um zu verhindern, dass sich Objekte zu stark überschneiden.
- **Wertbedeutung:**  
  - **Niedrige Werte:** Präzisere Kollisionen, jedoch kann es zu abrupten Contact-Punkten kommen.
  - **Hohe Werte:** Erhöhen die Stabilität der Simulation, können aber sichtbare Abstandseffekte zwischen den Objekten verursachen.

---

## 5. Oberflächenreaktionen
Diese Parameter bestimmen, wie das Objekt auf physikalische Interaktionen wie Kollisionen reagiert.

### 5.1 Friction (Reibung)
- **Beschreibung:**  
  Reguliert den Widerstand, den das Objekt beim Gleiten über andere Oberflächen erfährt.
- **Wertbedeutung:**  
  - **Niedrige Werte:** Geringe Reibung, was zu leicht gleitenden Bewegungen führt.
  - **Hohe Werte:** Erhöhter Widerstand, wodurch das Objekt mehr Haftung zeigt und langsamer gleitet.

### 5.2 Bounciness (Bounciness / Restitution)
- **Beschreibung:**  
  Bestimmt die Elastizität bei Kollisionen.  
- **Wertbedeutung:**  
  - **Niedrige Werte:** Geringe Rückpralleffekte, das Objekt absorbiert den Aufprall.
  - **Hohe Werte:** Hohe Elastizität, die zu einem starken Abprallen und einer intensiveren Reaktion bei Kollisionen führt.

---

## 6. Dämpfung
- **Beschreibung:**  
  Dämpfung reduziert die kinetische Energie, sodass überschießende Bewegungen und Schwingungen schneller abgebaut werden.
- **Parameter:**
  - **Lineare Dämpfung:**  
    Verringert die translationalen Bewegungen (z. B. Geschwindigkeit), was als Luftwiderstand oder Reibungsverlust simuliert wird.
  - **Winkel-Dämpfung:**  
    Verringert die Drehgeschwindigkeit des Objekts, wodurch unkontrollierte Rotationen minimiert werden.
- **Wertbedeutung:**  
  - **Niedrige Werte:** Längere, dynamische Bewegungen und ein lebendigeres Verhalten.
  - **Hohe Werte:** Rasche Stabilisierung und ruhigere Bewegung, ideal um unerwünschte Überschwinger zu vermeiden.

---

## 7. Rigid Body Welt und Cache
- **Rigid Body Welt:**  
  Beinhaltet die globalen Einstellungen der gesamten Simulation, wie Solver-Iterationen und Zeitschrittlängen, welche die Genauigkeit und Stabilität der Berechnungen beeinflussen.
- **Cache:**  
  Ermöglicht das „Baking“ der Simulation, wodurch bereits berechnete Daten gespeichert werden. Das sorgt für eine schnellere und konsistente Wiedergabe, ohne dass die Physik jedes Mal neu berechnet werden muss.

---

## 8. Constraints (Einschränkungen) – Optional
- **Beschreibung:**  
  Constraints verbinden mehrere Rigid Body-Objekte miteinander und simulieren physikalische Bindungen wie Gelenke oder Scharniere.
- **Typen und Parameter:**  
  - **Fixed (Fest):**  
    Verbindet Objekte so, dass sie sich nicht relativ zueinander bewegen.
  - **Hinge (Drehgelenk):**  
    Erlaubt Rotationsbewegungen um eine definierte Achse.
  - **Slider und weitere Spezialformen:**  
    Ermöglichen es, bestimmte Bewegungsfreiheiten oder Limitierungen präzise zu steuern.
- **Anwendungsgebiet:**  
  Häufig verwendet bei der Simulation von Fahrzeugen, mechanischen Systemen oder zusammengesetzten Objekten, bei denen mehrere Teile synchron agieren sollen.

---