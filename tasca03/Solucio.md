

# T03: Seguretat Lògica: recuperant accés a sistemes

Marc Melendo   
2n b sistemes microinformàtics i xarxes

Link al [docs](https://docs.google.com/document/d/1HB_-Vpcaq0nlhv4iNWEHdD1XMobPg66Q/edit?usp=sharing&ouid=117080756775083118180&rtpof=true&sd=true)

# Font d’informació: [modificar la contrasenya](https://waytoit.wordpress.com/2013/06/06/recuperando-password-en-ubuntu/) i [protegir el grub](https://waytoit.wordpress.com/2019/09/15/protegiendo-grub-en-ubuntu-server/)

# 

Un cop que hem iniciat la màquina i observem que té una contrasenya, haurem de reiniciar la màquina per poder accedir al menú de grub, fent shift \+ alguna lletra

![Podem veure el perfil de Miquel Valls per posar la contrasenya](/tasca03/img/1.png)

Quan apareixi el menú seleccionem la segona opció per poder accedir al menú avançat de zorin

![vallem el menu d'arranque de zorin](/tasca03/img/2.png)

Un cop fet això escollim l'opció de recuperació

![selecionem advanced options for zorin](/tasca03/img/3.png)

En el menú de recuperació, escollirem la versió de root

![escollim la opcio de root en el menú de recuperació](/tasca03/img/4.png)

Un cop que tenim la terminal oberta amb permisos de root haurem de posar la següent comanda mount \-rw \-o remount / això per canviar els permisos per poder modificar la contrasenya de l'usuari

![comanda per canviar els permisos](/tasca03/img/5.png)

Abans de poder canviar la contrasenya hem de saber el nom d’usuari per poder canviar la contrasenya, en aquest cas com únicament hi ha un usuari si anem a la carpeta /home podrem veure el nom de l'usuari si fem un ls

![comanda per veure el nom](/tasca03/img/6.png)

Un cop fet això ja podrem canviar la contrasenya 

![comanda per canviar la contrasenya](/tasca03/img/7.png)

Per no tornar a olvidar la contrasenya en aquest cas he colocar Marc1234

Quan el client ha vist lo fácil que ha sigut canviar la seva contrasenya ha demanat un mètode per evitar que això ho pugui fer un tercer, per tant el que farem sera colocar una contrasenya en el grub, per poder fer-ho farem el següent:

 El primer pas serà ejecutar la terminal i elevar permisos amb sudo su

![ejecutar la terminal i elevar permisos amb sudo su](/tasca03/img/8.png)

Despres executarem la segunt comanda **grub-mkpasswd-pbkdf2**. 

Aquesta comanda serveix per encriptar la contrasenya que volem fer servir pero en hash en aquest cas la contrasenya es Marc1234 i lo que surt a continuació és la contrasenya encriptada en hash

![Encriptem la contrasenya](/tasca03/img/9.png)

Això te un incovanient ja que no es comode, per tant farem servir la comanda tee per redirigir la sortida per defecta a un altre archiu per tant farem servir la següent comanda

![fem servir la comanda tee per redirigir la sortida](/tasca03/img/10.png)

Després haurem d’editar l’archiu amb 	sudo nano /etc/grub.d/40\_conf per poder afegir la autenticació, i també farem \-F per poder activar el minibufer per poder copiar el text quedant així la comanda

sudo nano \-F /etc/grub.d/40\_custom

Un cop obert farem CTRL+r i podrem afegir el nom del ficher d’origen en aquest cas és salida.txt i fem enter

![farem CTRL+r i escribim salida.txt](/tasca03/img/11.png)

Veurem com s’obre el fitxer salida.txt

![Veurem com s’obre el fitxer salida.txt](/tasca03/img/12.png)

El següent pas és copiar el hash, per poder fer això anirem a la linia i farem ALT+a per selecionar tota la linia i selecionarem unicament la part del hash amb el cursos o amb CTRL-e un cop fet farem ALT+6 per copiar el text, un cop fet això ja podrem tancar el fitxer amb CTRL \+x

![copiar el hash](/tasca03/img/13.png)

Ara estem en el ficher /etc/grub.d/40\_custom i haurem d’afegit aquestes 2 linies

set superusers="nombre\_login"

password\_pbkdf2 nombre\_login 

Quedant algo com això

![Vellem el resultat de la comanda explicada anteriorment](/tasca03/img/14.png)

El **nombre\_login** és el nom d’usuari per identificar-se en el GRUB. Aquest nom no té perquè se el mateix nom d’usuari de la maquina

A la segona linia hem de colocar el user i la contrasenya que hem copiat avans per fer això farem CTRL+u un cop fet guardem i sortim

Ara ja únicament apliquem els canvis amb 

sudo grub-mkconfig \-o /boot/grub/grub.cfg

![vellem el resultat de la comanda](/tasca03/img/15.png)

Reiniciem el sistema i comprovem que ens demana l’autentificació per accedir al grub

![vellem el menu per escriure l'usuari i contrasenya](/tasca03/img/16.png)















