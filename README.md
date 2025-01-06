## Badanie pierwszości liczby i rozkład na czynniki pierwsze

Ten dokument zawiera opis algorytmów do badania pierwszości liczby oraz rozkładania liczby na czynniki pierwsze. Szczególną uwagę zwrócono na algorytmy o złożoności czasowej O(n)O(n

​). Dodatkowo omówiono dowód poprawności zastosowanych metod.
1. Badanie pierwszości liczby
Algorytm

Algorytm sprawdzający, czy liczba nn jest pierwsza, przebiega w następujących krokach:

    Obsługa przypadków szczególnych:
        Jeśli n≤1n≤1: liczba nie jest pierwsza.
        Jeśli n≤3n≤3: liczba jest pierwsza (dotyczy n=2,3n=2,3).
    Sprawdzenie podzielności przez 2 lub 3:
        Jeśli nn jest podzielne przez 2 lub 3, nie jest pierwsze.
    Iteracyjne sprawdzanie dzielników:
        Przejdź przez wszystkie liczby ii od 5 do nn

        ​ z krokiem 6 (tj. sprawdzając ii i i+2i+2):
            Jeśli nn jest podzielne przez ii lub i+2i+2, liczba nie jest pierwsza.
    Jeśli żaden dzielnik nie został znaleziony, nn jest liczbą pierwszą.

Złożoność czasowa

Złożoność czasowa algorytmu wynosi O(n)O(n
​), ponieważ przeszukujemy tylko dzielniki do nn

​, a sprawdzanie każdego dzielnika zajmuje stały czas.
Dowód poprawności

    Każda liczba nn większa niż 1 ma dzielnik pierwszorzędowy w zakresie od 2 do nn

​ (jeśli istnieje dzielnik większy niż nn
​, to drugi dzielnik musi być mniejszy niż nn

    ​).
    Sprawdzając liczby 2, 3, a następnie kolejne liczby w formacie 6k±16k±1, eliminujemy wszystkie możliwe dzielniki pierwsze.

2. Rozkład liczby na czynniki pierwsze
Algorytm

    Rozpocznij od najmniejszych dzielników:
        Sprawdzaj dzielniki od 2, dopóki nn jest podzielne przez 2.
        Następnie sprawdzaj dzielniki 3, 5, i kolejne liczby aż do nn

        ​.
    Dziel stopniowo:
        Jeśli nn jest podzielne przez dzielnik ii, zapisuj ii jako czynnik i kontynuuj dzielenie nn przez ii, aż nn nie będzie podzielne.
    Jeśli n>1n>1:
        Pozostała wartość nn jest liczbą pierwszą i należy ją uwzględnić w rozkładzie.

Złożoność czasowa

Złożoność algorytmu wynosi O(n)O(n
​), ponieważ przeszukujemy potencjalne dzielniki jedynie do nn
​.
