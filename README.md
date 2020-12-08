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
SSSSSSSSSSSSSSSSSSSSSSSSSSS
S..SSSSSSS...........P....S
S..@......................S
S..SSSSSS.......P.........S
S.......S.................S
SSSSSSSSSSSSSSSSSSSSSSSSSSS
