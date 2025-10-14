

# T03: Seguretat Lògica: recuperant accés a sistemes

Marc Melendo   
2n b sistemes microinformàtics i xarxes

# Font d’informació: [modificar la contrasenya](https://waytoit.wordpress.com/2013/06/06/recuperando-password-en-ubuntu/) i [protegir el grub](https://waytoit.wordpress.com/2019/09/15/protegiendo-grub-en-ubuntu-server/)

# 

Un cop que hem iniciat la màquina i observem que té una contrasenya, haurem de reiniciar la màquina per poder accedir al menú de grub, fent shift \+ alguna lletra

![][image1]

Quan apareixi el menú seleccionem la segona opció per poder accedir al menú avançat de zorin

![][image2]

Un cop fet això escollim l'opció de recuperació

![][image3]

En el menú de recuperació, escollirem la versió de root

![][image4]

Un cop que tenim la terminal oberta amb permisos de root haurem de posar la següent comanda mount \-rw \-o remount / això per canviar els permisos per poder modificar la contrasenya de l'usuari

![][image5]

Abans de poder canviar la contrasenya hem de saber el nom d’usuari per poder canviar la contrasenya, en aquest cas com únicament hi ha un usuari si anem a la carpeta /home podrem veure el nom de l'usuari si fem un ls

![][image6]

Un cop fet això ja podrem canviar la contrasenya 

![][image7]

Per no tornar a olvidar la contrasenya en aquest cas he colocar Marc1234

Quan el client ha vist lo fácil que ha sigut canviar la seva contrasenya ha demanat un mètode per evitar que això ho pugui fer un tercer, per tant el que farem sera colocar una contrasenya en el grub, per poder fer-ho farem el següent:

 El primer pas serà ejecutar la terminal i elevar permisos amb sudo su

![][image8]

Despres executarem la segunt comanda **grub-mkpasswd-pbkdf2**. 

Aquesta comanda serveix per encriptar la contrasenya que volem fer servir pero en hash en aquest cas la contrasenya es Marc1234 i lo que surt a continuació és la contrasenya encriptada en hash

![][image9]

Això te un incovanient ja que no es comode, per tant farem servir la comanda tee per redirigir la sortida per defecta a un altre archiu per tant farem servir la següent comanda

![][image10]

Després haurem d’editar l’archiu amb 	sudo nano /etc/grub.d/40\_conf per poder afegir la autenticació, i també farem \-F per poder activar el minibufer per poder copiar el text quedant així la comanda

sudo nano \-F /etc/grub.d/40\_custom

Un cop obert farem CTRL+r i podrem afegir el nom del ficher d’origen en aquest cas és salida.txt i fem enter

![][image11]

Veurem com s’obre el fitxer salida.txt

![][image12]

El següent pas és copiar el hash, per poder fer això anirem a la linia i farem ALT+a per selecionar tota la linia i selecionarem unicament la part del hash amb el cursos o amb CTRL-e un cop fet farem ALT+6 per copiar el text, un cop fet això ja podrem tancar el fitxer amb CTRL \+x

![][image13]

Ara estem en el ficher /etc/grub.d/40\_custom i haurem d’afegit aquestes 2 linies

set superusers="nombre\_login"

password\_pbkdf2 nombre\_login 

Quedant algo com això

![][image14]

El **nombre\_login** és el nom d’usuari per identificar-se en el GRUB. Aquest nom no té perquè se el mateix nom d’usuari de la maquina

A la segona linia hem de colocar el user i la contrasenya que hem copiat avans per fer això farem CTRL+u un cop fet guardem i sortim

Ara ja únicament apliquem els canvis amb 

sudo grub-mkconfig \-o /boot/grub/grub.cfg

![][image15]

Reiniciem el sistema i comprovem que ens demana l’autentificació per accedir al grub















