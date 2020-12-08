# Obiektowe
## 1. Gra przygodowa
### Opis
Prosta gra w konsoli - dwuwymiarowa plansza z graczem, potworami i ścianami. Gracz może chodzić po mapie (ale nie przechodzić przez ściany), odpoczywać lub atakować potwory. Potwory są obdarzone prostą sztuczną inteligencją i polują na gracza.

### Sterowanie
Postacią sterujemy za pomocą konsoli, wprowadzając odpowiednie znaki (np. WASD, R). Próba przejścia na kratkę z potworem oznacza zaatakowanie tego potwora.

### Rozgrywka
Gra jest turowa i każda akcja gracza (atak, odpoczynek lub krok) powoduje start następnej tury.
Gracz i potwory (istoty) mają swoje własne punkty życia i atrybuty - siła, szybkość i maksymalna liczba punktów życia. 
Siła mówi nam, jak wiele punktów życia dana istota odbiera przeciwnikowi przy ataku.
Szybkość mówi, ile kratek dana istota może przejść w trakcie jednej tury (gracz ma szybkość 1). Jeśli szybkość ma część ułamkową, to gra losuje, czy istota zatrzyma się w miejscu, czy przejdzie jeszcze 1 kratkę.

Na jednym polu na mapie może znajdować się albo ściana albo gracz albo potwór.

### Potwory
Potwory wyczuwają gracza i jeśli jest w określonej odległości, to zaczynają go gonić (idą w jego stronę).
Jeśli potwory sąsiadują z graczem (są na sąsiednim polu), to będą go atakować.
Na końcu tury potwór może albo zaatakować gracza (jeśli z nim sąsiaduje), podejść do niego lub - jeśli nie wyczuwa gracza - czekać.

### Gracz
Jeśli gracz odpocznie w danej turze, to zregeneruje jeden punkt życia.
Gracz umiera, gdy skończą mu się punkty życia. Po śmierci gracza zaczynamy grę od nowa.

### Mapa
Mapa jest losowo generowana. Powinna istnieć ścieżka pomiędzy dowolnymi dwoma polami na mapie (poza ścianami). Przykład:
<code>

SSSSSSSSSSSSSSSSSSSSSSSSSSS
  
S..SSSSSSS...........P....S

S..@......................S

S..SSSSSS.......P.........S

S.......S.................S

SSSSSSSSSSSSSSSSSSSSSSSSSSS

</code>

## 2. Kooperacja
### Opis
Symulujemy zachowanie zróżnicowanej grupy ludzi. Gdy dwoje ludzi się spotka mogą podjąć decyzję o kooperacji lub oszustwie.

### Kooperacja lub oszustwo
Gdy obie osoby kooperują, obie dostają +1 punkt.
Gdy jedna osoba kooperuje, a druga oszuka, to oszust dostaje +3 punkty, a ofiara traci 3 punkty.
Jeśli obie oszukają, to tracą po jednym punkcie.

### Rozgrywka
Na początku tworzymy N postaci, każda z własną osobowością, losowym imieniem (ciąg znaków), wiekiem i płcią. W trakcie gry postacie losowo wchodzą ze sobą w interakcję i podejmują decyzję o kooperacji lub oszustwie.
Każda osoba ma 5% szansy na pomyłkę przy interakcji (robi odwrotnie niż powinna).
Ich interakcję widzi losowa grupa osób i na tej podstawie może wyrobić sobie o nich opinię. Postacie pamiętają wszystkie interakcje, w których brały udział, i których były świadkami.

### Osobowość
Osobowość mówi o tym, czy i kogo dana osoba oszuka.
Typy osobowości:
	W interakcji z drugą osobą A
	1. Zawsze oszukuje A (5% POPULACJI)
	2. Zawsze kooperuje z A (5% POPULACJI)
	3. Kooperuje z A, o ile nigdy nie widziała, że A oszukuje (10% POPULACJI)
	4. Kooperuje z A, o ile widziała, że A kooperuje w 90% przypadków (lub nigdy jej nie widziała) (40% POPULACJI)
	5. Kooperuje z A, o ile widziała, że A kooperuje w 67% przypadków (lub nigdy jej nie widziała) (40% POPULACJI)

### Ranking
Po zapauzowaniu gry możemy zobaczyć ranking, który pokazuje liczbę przebytych tur oraz osoby z największą liczbą punktów i ich osobowości.

**Liczba tur: 13**

|     POZYCJA    	|     IMIĘ       	|     PŁEĆ    	|     WIEK    	|     WYNIK    	|     OSOBOWOŚĆ    	|
|----------------	|----------------	|-------------	|-------------	|--------------	|------------------	|
|     1.         	|     TRTIKJD    	|     K       	|     18      	|     30p.     	|     1            	|
|     2.         	|     WEWEWEW    	|     M       	|     32      	|     13p.     	|     4            	|
|     3.         	|     ILJ        	|     K       	|     54      	|     10p.     	|     5            	|
|     4.         	|     WRRWM      	|     M       	|     23      	|     4p.      	|     3            	|
|     5.         	|     WIPI       	|     M       	|     56      	|     -2p.     	|     2            	|



