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

* 1-Metodologia utilitzada a classe per a fer proves amb màquines virtuals.
  - Primer hem creat una màquina virtual Fedora.
  - Amb la bombeta afegim hardware: 3 DISCS vda (Virtio) de 200MB 
  - Entrem a la màquina i com a root executem aquesta comanda: mdadm --create /dev/md0 --level=1 --raid-devices={nº de discs} {disc1} {disc2}
