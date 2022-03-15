# About

Nämä muistiinpanot on tehty kurssin viimeisen kerran arvioitavaa laboratorioharjoitusta varten, jotta aivan kaikkia peruskomentoja ei tarvitse etsiä omista julkaisuista muistiinpanoista ja joiden arvelevan olevan hyödyllisiä. Labraharjoituksessa saa käyttää julkisia materiaaleja joten sen takia julkaisen tämän. Olen varma, että oli vielä enemmän tärkeitä komentoja ja vinkkejä, joita kannattaisi olla tässä, mutta en nyt muistanut enempää.

# Virtuaalikoneen asennuksen jälkeen, tee ensimmäiseksi

(Sivulta: https://terokarvinen.com/2021/install-debian-on-virtualbox/)

* Tee päivitykset (päivän) aluksi ja aina ennen uusien ohjelmien asentamista

> sudo apt-get update

> sudo apt-get -y dist-upgrade

* Palomuurin asennus

> sudo apt-get -y install ufw

> sudo ufw enable

# Hyödyllisiä perusohjelmia

* Tekstieditori micro

> sudo apt-get install micro

* Elämänlaadun parannus, bash-completion

> sudo apt-get -y install bash-completion

* Micron asetus default-editoriksi

> export EDITOR=micro

* Haku verkko-osoitteesta, wget

> sudo apt install wget

# Apachen asennus

(Sivuilta: https://terokarvinen.com/2008/install-apache-web-server-on-ubuntu-4/ ja https://terokarvinen.com/2022/deploy-django/)

* Asennus

> sudo apt-get install apache2

Käynnistys

> sudo systemctl start apache2

* Testaa se verkkoselaimessa ("http://localhost")

* Testisivun korvaus sudona vain tämän kerran

> echo "See you at TeroKarvinen.com"|sudo tee /var/www/html/index.html

* Käyttäjäkansioiden salliminen

> sudo a2enmod userdir

* Jonka jälkeen tarvitsee uudelleenkäynnistää

> sudo systemctl restart apache2

* Tehdään kansio kotihakemistoon omalle nimelle

> mkdir public_html

* Jonne luodaan tiedosto

> micro index.html

* Esimerkkisisältö:

        <!doctype html>
        <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>blah</title>
        </head>
        <body>
            <p>I'm the content</p>
        </body>
        </html>

* Tarkista selaimesta "http://localhost/~nimi"

* Muista asentaa Apachelle palomuuri myös!

* Palvelimen pysäytys

> sudo service apache2 stop

# Tärkeitä kansioita Linuxissa

(Sivulta https://terokarvinen.com/2020/command-line-basics-revisited/ kopioitu.)

"
    **Dir**  	    **: Explanation** <br>
    / 	        : Root directory, the top of the filesystem. There are no drive letters in Linux, everything is under /.<br>
    /home/ 	    : Contains home directories for all users.<br>
    /home/tero/ : Home directory of user "tero". The only place where user "tero" can permanently store data.<br>
    /etc/ 	    : All system wide settings. They are in human readable, plain text files.<br>
    /media/ 	: Removable media, such as /media/cdrom/ or /media/usbdisk/<br>
    /var/log/ 	: System wide logs, such as /var/log/syslog, /var/log/auth.log and /var/log/apache2/error.log
"
