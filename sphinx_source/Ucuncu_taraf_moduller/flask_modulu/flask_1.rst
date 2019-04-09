Flask Proje Yapısı
*******************
Flask'ın sizi sabit bir proje yapısına zorlamaz. Ama genelikle aşağıda verilen proje yapısı kullanılır::

    proje_dizini
    |   run.py
    |   
    \---flask_app
        |   app.py
        |   __init__.py
        |   
        +---static
        |   +---css
        |   +---img
        |   \---js
        \---templates
                base.html
                index.html
            


Dikkat ettiyseniz `flask_app` adlı dizin içinde `__init__.py` dosyası var. Bu demek oluyor ki yapacağımız uyglamayı bir paket şekline yazacağız. Şimdi bu dosya ve dizilerin ne işe yaradığını açıklayalım.

run.py
=======
Bu dosya ilerde göreceğimiz Flask uygulamasının çalıştırma yeridir. 