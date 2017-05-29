### Tallafocs
* Què es un sistema tallafocs? Quina és la seva finalitat? 
  - És un element de hardware o software utilitzat en una xarxa d'equips informàtics, la seva finalitat es controlar les comunuicacions, permetent-les o prohibint-les segons les polítiques de xarxa que hagi definit l'organització responsable de la xarxa. 

* Quines generacions de tallafocs hi ha hagut i què millorava cadascun?
  - Primera generació: Filtratge de paquets  
Permetia analitzar cada paquet i els comparava per decidir si bloquejarlos o acceptava.
  
  - Segona generació: Filtres d'estat  
Aquesta segona generació ademés tè en conta la colocació de cada paquet individual dintre d'una serie de paquets, aquesta tencología és capaç de determinar si un paquet inidica l'inici de la conexió, de si es part d'una conexió existent o paquet erroni.
  
  - Tercera generació: Capa d'aplicació  
Actúa sobre la capa de aplicació OSI, pot entendre diferents protocols i aplicacions i permet detectar si algún protocol no desitjat s'ha colat a través d'un port no estándar o si estàn utilitzant algún protocol per saltar-se el firewall.
  
  
* Quines capes té el model OSI?
  - Aplicació
  - Presentació
  - Sessió
  - Transport
  - Xarxa
  - Enllaç
  - Físic
  
* Quines capes té el model TCP/IP? En aquest cas feu una breu descripció de les funcionalitats de cada capa.
  - Aplicació: incorpora aplicacions de xarxa estándar (Telnet, SMTP, FTP, etc.). 
  - Transport: brinda les dades d'enrutament, juntament amb els mecanismes que peremeten conèixer l'estat de la transmissió.
  - Internet: responsable de proporcionar el paquet de dades (datagrama). 
  - Accés a xarxa: especifica la forma en la que les dades han de enrutarse, sigui quin siguiel tipus de xarxa utilitzada.
  
* A quina capa/capes sol treballar tradicionalment un tallafocs?
  - Sol treballar des de la capa de Transport (3) fins la d'Aplicació (4), en el model TCP/IP.
        
### Tallafocs Linux
* Busqueu quins són els tradicionals sistemes de tallafocs incorporats en linux i anomeneu-los
  - firewalld i iptables.
* Quins dels anteriors tallafocs estan instal.lats al fedora de classe? Com ho comproveu?
  - Els dos estan instal·lats.

        # systemctl status firewalld.service          
        # systemctl status iptables 
  
* Algun dels anteriors tallafocs es troba activat?
  - Els dos es troben inactius.
* Instal.leu el servidor web httpd o nginx i activeu-ne el servei (dnf installl ...  ; systemctl ....). Indiqueu les comandes i comproveu que des d'una altra màquina podeu accedir via web a la vostra IP (digueu-li a un company). Hauria de sortir la plana per defecte.

        # dnf install nginx
        # systemctl status nginx  
        # systemctl start nginx         
        
  - Cuan el meu company es conecta via navegador surt la plana per defecte de nginx.
* Activeu el servei firewalld. Indiqueu com ho feu.

        # systemctl start firewalld.service    
        
* Comproveu si ara es pot seguir accedint.
  - Ja no pot accedir.
 
### Win7
* Porta aquest SO algun tallafocs incorporat?
  - Porta el "Firewall de Windows".
* Arrenqueu una màquina win7 a isard.escoladeltreball.org
* Indiqueu com arribar al tallafocs (passos i pantalles)
  - Primer obrim el Inici  
  - Busquem el Panel de control  
  - Click a Sistema y seguridad
  - Click a Firewall de Windows.
* Es troba activat en aquest windows?
  - Si, està activat per defecte.
* Busqueu un altre tallafocs per windows. Indiqueu la plana web i les prestacions que ens dona. Intenteu que NOMÉS sigui tallafocs.

  - Comodo Personal Firewall
      - Prestacions:
        - Et manté al corrent de tots els arxius sospitosos.
        - Denegar per defecte Protection ™ de manera que només els arxius segurs executing.
        - Les actualitzacions automàtiques per a la protecció més actualitzada.
