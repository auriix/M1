# Sistemes RAID
* 1-Taula

Nivells | nº min. discs | nº máx. discs fallats  | Capacitat    | Lectura    | Escritura  |
------- | --------------| -----------------------| ------------ | -----------|------------|
RAID 0  | 2             | 0                      | 100%         | excelent   | excelent   |
RAID 1  | 2 (min i max) | 1                      | 50%          | very good  | good       |
RAID 5  | 3             | 1                      | (67%-94%)    | very good  | good       |
RAID 6  | 4             | 2                      | (50%-88%)    | good       | good       |
RAID 10 | 4             | 1/mirror               | 50%          | good       | good       |
RAID 50 | 6             | 1 per R5 set           | (67%-94%)    | very good  | very good  |
RAID 60 | 8             | 1 per R6 set           | (50%-88%)    | good       | good       |

* 2-Metodologia utilitzada a classe per a fer proves amb màquines virtuals.  
Primer hem creat una màquina virtual Fedora.  
Amb la bombeta afegim hardware: 3 DISCS vda (Virtio) de 200MB  
Entrem a la màquina i com a root executem aquesta comanda:  
  - **mdadm --create /dev/md0 --level=1 --raid-devices={nº de discs} {disc1} {disc2}**
  - El level indica el tipus de Raid
  - /dev/md0 (el nom del dispositiu)
Creem un sistema de fitxers al raid : **mkfs.ext4 /dev/md0**  
Amb **cat /proc/mdstat** podem veure el estat del raid.  
Montem /dev/md0 a /mnt: **mount /dev/md0 /mnt**  

Fiquem arxius dintre del directori /mnt, per simular que tenim fichers i borrem un disc desde la bombeta, per veure que passa, si s'han perdut les dades segons el tipus de Raid, i els discs que poden fallar.  
Anem afegint i borrant discs cambiant el tipus de Raid amb la primera comanda, així veiem els canvis que tè cadascún.

* 3-Crear RAID1  
**mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/vda /dev/vdb**  
El Raid 1 tè 2 discs (min i max).(/dev/vda /dev/vdb)
  - El level indica el tipus de Raid

* 4-Crear RAID5  
**mdadm --create /dev/md0 --level=5 --raid-devices=3 /dev/vda /dev/vdb /dev/vdc**  
El Raid 5 tè mínim 3 discs.(/dev/vda /dev/vdb /dev/vdc)
  - El level indica el tipus de Raid
  
* 5-Crear RAID6  
**mdadm --create /dev/md0 --level=6 --raid-devices=4 /dev/vda /dev/vdb /dev/vdc /dev/vdd**  
El Raid 6 tè mínim 4 discs.(/dev/vda /dev/vdb /dev/vdc /dev/vdd)
  - El level indica el tipus de Raid
  
* 6-Crear RAID10  
**mdadm --create /dev/md0 --level=10 --raid-devices=4 /dev/vda /dev/vdb /dev/vdc /dev/vdd**  
El Raid 10 tè mínim 4 discs.(/dev/vda /dev/vdb /dev/vdc /dev/vdd)
  - El level indica el tipus de Raid
  
