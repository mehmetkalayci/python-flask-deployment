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

# Python Flask application deployment on IIS

Setup wfastcgi and web.config

2. Setup wfastcgi and web.config:
Now that our app is ready to deploy, next we need to set up wfastcgi. Start with installing and activating CGI in your server. you can do this by opening your Server Manager. Click on add role and features


Keep clicking next to reach Server Roles then select
Web Server (IIS)>Web Server>Application Developement>CGI
then click next to install it.


Now go back to your command prompt and install wfastcgi using this command

pip install wfastcgi
then run the following command to enable it in the current environment.

wfastcgi-enable
the output should be something like this

https://mtuseeq.medium.com/how-to-deploy-flask-app-on-windows-server-using-fastcgi-and-iis-73d8139d5342

https://medium.com/@bilalbayasut/deploying-python-web-app-flask-in-windows-server-iis-using-fastcgi-6c1873ae0ad8

Sonra bakılacak
https://flask-httpauth.readthedocs.io/en/latest/#flask_httpauth.HTTPBasicAuth










