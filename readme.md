# InkTime - Smartwatch Project

## Descriere Generala
Acest proiect vizeaza designul si integrarea unui smartwatch bazat pe nRF52840, utilizand un display e-paper de 1.54 inch pentru eficienta energetica. Dispozitivul include circuite de management al alimentarii pentru o baterie Li-Po de 250mAh si un motor haptic pentru notificari.

---

## 1. Diagrama Bloc
Diagrama de mai jos ilustreaza interactiunea dintre unitatea centrala (MCU nRF52840) si perifericele integrate (Display, Haptic Driver, Senzori, Management Alimentare).

![Diagrama Bloc](https://github.com/user-attachments/assets/6885c55d-0675-49d7-9933-0034ffceac0e)

---

## 2. PCB Design & Layout

### Placement si Routing
* **Placement:** Componentele au fost grupate logic pentru a minimiza lungimea traseelor si a reduce interferentele electromagnetice, avand in vedere densitatea ridicata pe o suprafata de doar 46 x 35 mm.
* **Routing:** Din cauza complexitatii si a numarului mare de componente pe o placa de dimensiuni reduse, s-a utilizat o combinatie de rutare manuala pentru liniile critice si autorouter-ul din Fusion Autodesk pentru restul conexiunilor.

![PCB Layout Fata](https://github.com/user-attachments/assets/bb4ba7c8-f3bb-449f-8de8-f77c3becd22c)
![PCB Layout Spate](https://github.com/user-attachments/assets/df7f9451-2997-4e3e-9a60-74aae88e3079)

### Detalii de Fabricatie si Asamblare
PCB-ul este optimizat pentru productie industriala, respectand urmatoarele reguli de design:
* **Trasee de alimentare:** 0.3 mm.
* **Trasee de date/semnal:** 0.15 mm.
* **Integrare Mecanica:** Ansamblul a fost verificat prin modelare 3D, asigurand potrivirea perfecta a bateriei LP502030 si a display-ului in carcasa dedicata InkTime.

Toate fisierele necesare (Gerber, BOM, CPL) sunt disponibile in folderul `/Manufacturing`.

---

## 3. Alocarea pinilor Microcontroller-ului

| Componenta | Semnal | Pin nRF52840 |
| :--- | :--- | :--- |
| **Interfata E-Paper** | SCK | P0.31 |
| | DIN | P0.29 |
| | CS | P0.30 |
| | D/C | P1.13 |
| | RST | P0.02 (AIN0) |
| | BUSY | P0.03 (AIN1) |
| **Haptic Driver** | HAPTIC_EN | P1.12 |
| | SCL | P0.27 |
| | SDA | P0.26 |
| **Butoane (UI)** | Button 1 | P0.11 |
| | Button 2 | P0.12 |
| | Button 3 | P0.24 |

---

## Structura Repository
* **/Hardware**: Fisierele sursa Fusion 360 (.fsch, .fbrd).
* **/Mechanical**: Modelul 3D al ansamblului (.step).
* **/Manufacturing**: Arhiva Gerber, Bill of Materials (BOM) si Pick and Place (CPL).
