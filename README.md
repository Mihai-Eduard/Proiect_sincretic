# Cerința proiectului

Se va realiza un sistem de conducere pe bază de microcontroller care va efectua următoarele funcții:

- Încălzirea sistemului până la o temperatură setată **TSET** într-un timp **t_incalzire**
- Menținerea acestei temperaturi pentru o perioadă de timp **t_mentinere**
- Răcirea sistemului treptat într-o perioadă de timp **t_racire**

## Interfața cu utilizatorul

- Sistemul va dispune de un LCD 16x2 pe care va fi afișat meniul, iar în timpul rulării se vor afișa temperatura setată, temperatura curentă și timpul rămas din etapa actuală (t_incalzire, t_mentinere, t_racire).
- Meniul sistemului va permite modificarea următorilor parametri: **TSET, t_incalzire, t_mentinere, t_racire, KP, KI, KD**.
- Parametrii vor fi salvați în memoria nevolatilă. Repornirea sistemului nu va afecta parametrii salvați.
- Navigarea prin meniul echipamentului se va face prin patru butoane: "OK", "Cancel", "+", "-".
- Opțional, se poate crea o interfață pe PC pentru afișarea unui grafic al temperaturii.

## Reglarea temperaturii

- Controlul temperaturii va fi asigurat de un regulator de tip **PID**.
- Senzorul de temperatură folosit va fi unul de tip **LM35** sau echivalent.
- Elementul de execuție al sistemului ce va asigura încălzirea senzorului va fi un bec incandescent c.c. de putere >= 5W ce va putea ajunge la o temperatură de minim 50°C.
- Se va folosi un releu sau un tranzistor pentru a comanda pornirea/oprirea alimentării acestui bec de către microcontroller.

## Perturbații

- Se va implementa un generator de numere random (PRNG sau TRNG).
- Sistemul va dispune de un generator de perturbații care va afecta circuitul de măsurare a temperaturii cu valori aleatorii folosind modulul PRNG/TRNG implementat anterior.
- Apăsarea butonului "OK" în timpul rulării unui program de reglare a temperaturii va porni modulul de perturbații, iar apăsarea din nou a aceluiași buton o va opri.
