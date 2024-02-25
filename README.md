# Description


- import csv  
 importuje moduł csv, służący do czytania i zapisywania plików CSV.  


- def oblicz_wyniki_z_pliku(csv_path):  
definiuje nazwę funkcji, aby służyła konkretnemu celowi w skrypcie: oblicz_wyniki_z_pliku, przyjmuje ścieżkę do pliku CSV.  


- with open(csv_path, newline='') as csvfile:  
otwiera plik CSV, używając ścieżki przekazanej do funkcji. newline='' zapewnia odpowiednie traktowanie końców linii.  


- reader = csv.reader(csvfile, delimiter=';'):  
tworzy obiekt reader do iteracji po wierszach pliku, z średnikiem jako separatorem.  


- next(reader)  # Pomiń nagłówki  
używa next na reader, aby pominąć pierwszy wiersz, czyli nagłówki.


- suma_kolumny_f = 0  
wartosc_g_w_wierszu_2 = 0  
inicjalizuje zmienne do przechowywania sumy wartości z kolumny F i wartości z kolumny G w drugim wierszu.


- for i, row in enumerate(reader):  
rozpoczyna pętlę przez wiersze pliku, z numeracją wierszy dzięki enumerate.


- if i == 0:  # Zapisz wartość z kolumny G z drugiego wiersza  
wartosc_g_w_wierszu_2 = float(row[6].replace(',', '.'))  
jeśli jest to pierwszy wiersz danych, zapisuje wartość z kolumny G, konwertując na format zmiennoprzecinkowy.


- suma_kolumny_f += float(row[5].replace(',', '.'))  
dodaje do sumy wartości z kolumny F, konwertując na format zmiennoprzecinkowy.


- wartosc_h_w_wierszu_2 = suma_kolumny_f  
wartosc_i_w_wierszu_2 = wartosc_h_w_wierszu_2 + wartosc_g_w_wierszu_2  
oblicza wartości dla kolumn H i I na podstawie wcześniejszych obliczeń.


- return wartosc_h_w_wierszu_2, wartosc_i_w_wierszu_2  
zwraca obliczone wartości.
