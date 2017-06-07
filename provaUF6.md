# Prova pràctica UF6

- Comandes per instal.lar el servidor web
       
       dnf install nginx
        
- Comandes per activar el servei web

        systemctl start nginx 
        
- Comandes per activar el tallafocs firewalld

        systemctl start firewalld.service 
        
-  Comandes per donar accés remot al servidor web.

        firewall-cmd --permanent --zone=public --add-port=80/tcp
