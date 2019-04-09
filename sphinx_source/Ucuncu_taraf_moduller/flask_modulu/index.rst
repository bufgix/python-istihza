.. meta::
   :description: Bu bölümde Flask Mikroframeworkünü tanıyıp, küçük bir merhaba dünya uygulaması yazacağız
   :keywords: python, flask

.. highlight:: python3

******
Flask
******
Bu bölümde Flask **mikroframeworkünü** tanıyıp, basit bir `merhaba dünya` uygulaması yaparak Flask'ı anlamaya çalışacağız. 

Flask Nedir?
*************
Flask, Python ile çalışan basit ve bir o kadar güçlü bir web mikroframeworktür. Flask ile hem basit hem de komplike uygulamalar geliştirebilirsiniz. Bunu yaparken karmaşık konfigirasyonlar ve katı proje yapısı ile karşılaşmazsınız.

Flask Kurulumu
***************
Flask'ı `pip` ile kolay bir şekilde yükleyebilirsiniz::

    pip install Flask


Şimdi hızlıca bir `merhaba dünya` uygulaması yapalım. 
Proje dizinimizde herhangi bir isimde bir Python dosyası oluşturalım. Ben `app.py` koydum ismini.

`app.py`::

    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def index():
        return 'Merhaba dünya. Merhaba Flask'

    if __name__ == '__main__':
        app.run()

Görüldüğü gibi 1. satırda `flask` paketi içinden `Flask` sınıfını içe aktardık. Ardından bu sınıftan bir örnek oluşturmamız gerek. `Flask` sınıfı argüman olarak uygulamanın veya modulün adıdır.
Bu örnekte olduğu gibi tek modül kullanıyorsanız, `__name__` kullanmanız gerekir. Diğer satırda `route()` bezeyicisini kullanarak Flask'a hangi URL'nin fonksyonumuzu tetiklemsini gerektiğini söylüyoruz.
Bezeyici için bir fonksyon yazıyoruz. İsmini sizin için anlamlı olduğu sürece istediğinizi koyabilirsiniz. Bu fonksyon işlemini bitirdikten sonra mutlaka geriye bir değer döndürmelidir. Bu örnekte
basit bir `string` döndürdük.
Alt satırda ise `app` nesnesinin `run()` fonksyonunu kullanarak uygulamamızı başlatıyoruz.

Bu dosyayı çalıştırdığınızda şuna benzer bir çıktı göreceksiniz::

    $ python app.py

    * Serving Flask app "run" (lazy loading)
    * Environment: production
    * Debug mode: off
    * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

Görüldüğü gibi sunucunuzu `http://127.0.0.1:5000/` adresinde başlattı. İnternet tarayıcınızdan `http://127.0.0.1:5000/` giderseniz::
    
    Merhaba dünya. Merhaba Flask

göreceksiniz. Tebrikler ilk Flask uygulamanızı oluşturdunuz.