
## Diagram związków encji
![Diagram](https://user-images.githubusercontent.com/51990837/59754114-bf578380-9285-11e9-826f-b9237c12b722.PNG)

## Opis funkcjonalności
W ramach pracy inżynierskiej powstała obiektowo – relacyjna baza danych, która skupia w sobie tabele dotyczące użytkowników, zgłoszeń oraz archiwum. Po zainstalowaniu wtyczki PostGIS można było zacząć tworzenie tabel. Na początku powstała tabela przechowująca dane do logowania użytkowników. Składa się z trzech kolumn: login, hasło oraz email. Został w niej nadany klucz główny w kolumnie ,,login”, dzięki któremu powstała relacja z tabelą ,,zgłoszenia”, aby przenieść kolumnę do tej tabeli. Tabela ,,zgłoszenia” odpowiadająca za gromadzenie danych związanych ze zgłoszeniami użytkowników składa się z kolumn: gid (klucz główny), typ, opis, data, geom oraz użytkownik. Do tej tabeli został przypisany wyzwalacz oraz funkcja.

## Wyzwalacz tworzący archiwum
![Trigger](https://user-images.githubusercontent.com/51990837/59754675-d9459600-9286-11e9-8699-e3071b9b5ce2.PNG)

Dzięki funkcji create_archiwum oraz wyzwalaczowi zgłoszenia_archiwum w przypadku kiedy użytkownik usunie swoje zgłoszenie, w tabeli ,,zgłoszenia” ono zniknie ale w tabeli ,,archiwum” zostanie ono zarchiwizowane, umożliwiając jednocześnie przechowywanie historii aktywności użytkownika.
