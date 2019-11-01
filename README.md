# Kompilowanie

[https://pjreddie.com/darknet/install/](https://pjreddie.com/darknet/install/)

[Installing Darknet](https://pjreddie.com/darknet/install/)

## Uwagi

- Xavier ma proceosor ARM, więc trzeba osobno skompilować na xavierze i na PC! Na xavierze wszystkie zależności są już zainstalowane, więc make powinen udać się bez problemu. Binarka chyba też gdzieś jest (libdarknet.so)
- Jeżeli ktoś nie lubi kompilować to zapodaję linuksową binarki na X86-64. libdarknet.so dać do /usr/lib lub w tym samym folderze co darknet.py. 

[libka](libdarknet.so)

[darknet](darknet)

# Przygotowanie datasetu

### Instrukcja (dla Yolov2, ale dataset wygląda tak samo)

[How to train YOLOv2 to detect custom objects](https://medium.com/@manivannan_data/how-to-train-yolov2-to-detect-custom-objects-9010df784f36)

### Przykładowy dataset

Ścieżki w plikach są absolutne, więc trzeba pozmieniać na te we własnym komputerze. Możliwe że względne ścieżki też będą ok - ja miałem jakieś problemy

[dataset.zip](dataset-1cd5f842-407e-4cf4-bc59-afc9974e32a2.zip)

# Trenowanie

[How to train YOLOv3 to detect custom objects](https://medium.com/@manivannan_data/how-to-train-yolov3-to-detect-custom-objects-ccbcafeb13d2)

### One liner dla trenowania

    ./darknet detector train <plik.data> <plik.cfg> <opcjonalna_sciezka_do_poprzednich_wag>

### One liner dla testowania

    ./darknet detector demo <plik.data> <plik.cfg> <sciezka_do_wag> <sciezka_do_pliku_wideo>

# Używanie w pyhtonie

Oficjalnej dokumentacji nie ma, ale używanie w pythonie to po prostu bidngi do C. Kod źródłowy jest w pliku poniej na githubie. (Są lekkie modyfikacie w stosunku do orginalnego kodu z darkneta)

[https://github.com/DominikWasiolka/Xavier_ROV4/blob/robosub_2019/neural_networks/darknet.py](https://github.com/DominikWasiolka/Xavier_ROV4/blob/robosub_2019/neural_networks/darknet.py)

Najprościej będzie zobaczyć przykład użycia w implementacji na robosub_2019

[https://github.com/DominikWasiolka/Xavier_ROV4/blob/robosub_2019/neural_networks/YoloServer/DarknetYoloModel.py](https://github.com/DominikWasiolka/Xavier_ROV4/blob/robosub_2019/neural_networks/YoloServer/DarknetYoloModel.py)
