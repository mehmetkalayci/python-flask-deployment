# Python Flask application deployment

Deployment İzlenecek Adımlar
1. Python kur
2. Virtual env kur
3. Gerekli kütüphaneleri kur
4. Deployment serveri ayarla
5. Deployment serveri başlat

1. Python 'ı kurarken PATH değişkenine ekle
2. C:\ocr_deployment klasörü oluştur
klasör içine gir
"python -m venv ocr_env" komutu ile env oluştur
"ocr_env\Scripts\activate" komutu ile env aktive et

3.
"pip install apiflask" komutu ile apiflask kütüphanesini kur
"pip freeze > requirements.txt" komutu ile kurulan kütüphaneleri requirements.txt dosyasına yaz.

4.
app.py dosyasını ocr_deployment klasörüne at.

main.py oluştur ve içine aşağıdaki satırları yaz.

from werkzeug.serving import run_simple
from api import app

appx = app
run_simple('localhost', 8080, appx, use_reloader=True)

5. 
python main.py komutu ile deployment serverı başlat


Kaynaklar
1. https://www.twilio.com/docs/usage/tutorials/how-to-set-up-your-python-and-flask-development-environment
2. https://werkzeug.palletsprojects.com/en/2.1.x/tutorial/
