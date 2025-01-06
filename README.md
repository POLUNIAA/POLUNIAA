## Badanie pierwszości liczby i rozkład na czynniki pierwsze

### 1. Liczby pierwsze
Liczba pierwsza to taka liczba naturalna większa od 1, która dzieli się wyłącznie przez 1 oraz samą siebie. Przykłady to `2,3,5,7,11`. 

**Liczby pierwsze** są fundamentalne w matematyce, ponieważ każda liczba naturalna większa od 1 może być przedstawiona jako iloczyn liczb pierwszych, co nazywamy rozłożeniem na czynniki pierwsze.

### Zastosowania w praktyce

Liczby pierwsze i ich rozkład na czynniki mają kluczowe znaczenie w kryptografii (np. w algorytmie RSA), kompresji danych. Na przykład, duże liczby pierwsze są wykorzystywane w szyfrowaniu danych, gdzie trudność w rozłożeniu na czynniki pierwsze zapewnia bezpieczeństwo.

---

### 2. Badanie pierwszości liczby
Na czym polega badanie pierwszości?

Celem jest określenie, czy dana liczba `n > 1` jest pierwsza. Kluczowe założenie algorytmu o złożoności **O(√n)** to fakt, że jeśli liczba n ma dzielnik większy od 1 i mniejszy od n, to co najmniej jeden z tych dzielników jest mniejszy lub równy √n.

Przykład:

Liczba n=36.

	- Pierwiastek kwadratowy wynosi √36=6.
 
	- Dzielniki 36 to `1,2,3,4,6,9,12,18,36`
 
	- Wystarczy sprawdzić dzielniki do 66, aby wykryć, że liczba jest złożona.
 
### Algorytm krok po kroku
	Jeśli n ≤ 1, to liczba nie jest pierwsza.
 
	Jeśli n = 2 lub n = 3, to liczba jest pierwsza (są to najmniejsze liczby pierwsze).
 
	Sprawdzamy, czy n jest podzielne przez 2 lub 3. Jeśli tak, to liczba nie jest pierwsza.
 
	Dla liczb większych od 3 iterujemy przez potencjalne dzielniki od 5 do √n, sprawdzając liczby w postaci `6k ± 1 (np. 5,7,11,13)`. 
	Liczby w tej postaci to jedyne możliwe kandydaty na dzielniki, ponieważ wszystkie inne są podzielne przez 2 lub 3.
 
Przykład działania algorytmu:

Dla liczby n = 97:
	Liczba 97 > 1, nie jest podzielna przez 2 ani 3.
	Pierwiastek 97 ≈ 9.8. Sprawdzamy dzielniki 5, 7.
	97 nie dzieli się przez żadną z tych liczb, więc jest pierwsza.

### 3. Rozkład na czynniki pierwsze

Na czym polega rozkład na czynniki pierwsze?

Rozkład liczby na czynniki pierwsze polega na znalezieniu takich liczb pierwszych, których iloczyn daje początkową liczbę nn. Proces ten jest iteracyjny: dzielimy liczbę przez jej najmniejszy dzielnik pierwszy, aż do uzyskania wyniku 1.
Przykład:
Dla n=84n = 84:
	Najmniejszy dzielnik to 22, dzielimy 84/2 = 42.
	Ponownie dzielimy przez 22, otrzymując 42/2 = 21.
	Następny dzielnik to 33, dzielimy 21/3 = 7.
	Pozostaje liczba 77, która jest pierwsza. Rozkład: 2×2×3×7 

### Algorytm krok po kroku
	Sprawdzamy, czy liczba n jest podzielna przez 2. Jeśli tak, zapisujemy 2 jako czynnik i dzielimy n przez 2, aż n przestanie być podzielne przez 2.
	Następnie iterujemy przez liczby pierwsze od 3 do √n, zapisując każdy dzielnik jako czynnik i dzieląc n przez niego, aż n przestanie być podzielne.
	Jeśli po zakończeniu iteracji n > 1, oznacza to, że pozostała liczba n jest pierwsza.
Przykład działania algorytmu:
Dla liczby n= 100:
	Dzielimy przez 2: 100 / 2 = 50, 50 / 2 = 25.
	Przechodzimy do kolejnego dzielnika 5: 25 / 5 = 5, 5 / 5 = 1.
	Wynik: 2 × 2 × 5 × 5

### 4. Złożoność algorytmu

O(√n)

Wzorcowa złożoność algorytmu jest 
`O(√(n))`
gdzie n to rozkładana liczba. Rozłożenie liczby na czynniki pierwsze, inaczej faktoryzacja tej liczby, polega na przedstawieniu jej w postaci iloczynu liczb pierwszych. Idea algorytmu jest prosta.
	Najmniejszy możliwy czynnik pierwszy to liczba 2, ponieważ jest to najmniejsza liczba pierwsza i taką wartość początkową ustawiamy dla zmiennej czynnik (*),
	algorytm wykonujemy tak długo, jak długo `czynnik * czynnik <= liczba`


	Jeśli liczba n ma dzielnik większy od 1, to co najmniej jeden z dzielników d spełnia d ≤ √n. Dzięki temu wystarczy sprawdzić dzielniki tylko do √n, zamiast wszystkich do n − 1.
	Dla rozkładu na czynniki pierwsze, za każdym razem redukujemy n, co również ogranicza liczbę operacji.
 
Przykład porównania:

Dla n = 10^6:
	Sprawdzanie wszystkich dzielników O(n): wymaga miliona operacji.
Sprawdzanie dzielników do √n(O(√n)): wymaga około tysiąca operacji.

### 5. Dowód poprawności

Jeśli liczba n ma dzielniki inne niż 1 i n, to:
	Dla każdego dzielnika d_1  istnieje d_2  taki że d_(1 )× d_2 = n.
	Jeśli d_(1 )> √n, to d_2< √n. Dlatego wystarczy sprawdzić dzielniki do √n.

### 6. Podsumowanie
Opisane algorytmy są efektywne, proste w implementacji i mają szerokie zastosowanie w praktyce. Ich złożoność O(√n) czyni je idealnymi dla większości przypadków użycia, gdzie liczba n jest relatywnie niewielka. Dla dużych liczb, np. w kryptografii, stosuje się bardziej zaawansowane metody, takie jak testy probabilistyczne i algorytmy faktoryzacji.

