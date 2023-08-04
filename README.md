# -Checkpoint-01-SB-TSSR                                 
**Exercice 1 - Etude d'un réseau**   

   **1.1 Quizz**     
   
**1-** les différences entre le matériel A et le matériel B sont les suivantes :                                             
Le matériel A est désigné sous le nom "Ubuntu-2" et possède une interface "eth0" avec une adresse IP 10.0.0.1/24, une adresse Mac 00:50:79:66:68:01 et une passerelle de 10.10.0.254 . Tandis que, Le matériel B est désigné sous le nom "Ubuntu-1" et possède une interface "eth0" avec une adresse IP 10.0.1.1/26, une adresse Mac 00:50:79:66:68:00 il n'a pas de passerelle définie.   


**2-** em0, em1, em2 représentent les interfaces réseau de l'équipement pfSense-1 . Alors pfSense-1 possède trois interfaces réseau (em0, em1, em2).   

**3-** /26 est une notation CIDR qui indique le masque de sous-réseau. Dans ce cas (/26) signifie qu'il y a 26 bits d'adresse réseau et 6 bits d'adresse hôte. 

**4-** Dans le vocabulaire IP, Ubuntu est un système d'éxploitation basé sur Linux, et dans ce cas, Ubuntu-1 et Ubuntu-2 sont utilisés comme des noms pour désigner les machines du réseau.   

**5-** 

**6-** Non, d'après le schéma, Ubuntu-2 est connecté à l'équipement pfSense via un switch, et il n'est pas directement connecté à l'interface em1 de pfSense.                                                                

   **1.2 Etude théorique**   
   
**11-**                                                                
Réseau1 (10.0.1.1) :Le masque /26 signifie qu'il y a 26bits réservés pour le réseau et 32-26=6 bits réservés pour les hôtes(2^6=64)   
- Adresse de réseau : 10.0.1.0                                                       
- Adresse de diffusion : 10.0.1.63                                                               
- Plage d'adresses disponibles pour les hôtes : 10.0.1.1 à 10.0.1.62 (62 adresse)

Réseau2 (10.0.0.1) :Le masque /24 signifie qu'il y a 24 bits réservés pour le réseau et 32-24=8 bits réservés pour les hôtes (2^8=256)   
- Adresse de réseau : 10.0.0.0                                            
- Adresse de diffusion : 10.0.0.255
- Plage d'adresses disponibles pour les hôtes : 10.0.0.1 à 10.0.0.254 (254 adresses)

**12-** La machine Ubuntu-1 a une adresse IP de 10.0.1.1 et la machine Ubuntu-2 a une adresse IP de 10.0.0.1. Ces deux machines ne peuvent pas communiquer directement sans un routeur ou une passerelle.car elles appartiennent à deux réseaux différents.         

**13-** La machine Ubuntu-2 peut sortir du réseau car elle a une passerelle (10.10.0.254).

**14-** 

**1.3 Analyse de trames**    

**- Fichier1:**                         
**16-** Dans cette trame c'est l'adresse IP 10.10.4.1 qui initialise la communication.

**17-** la communication a réussi. L'appareil qui a l'adresse IP 10.10.4.2 a répondu a la question who has 10.10.4.2? avec son adresse MAC 00:50:79:66:68:03 en indiquant qu'il possède cette adresse IP.

**18-** Dans toute la trame, le request et le reply correspondent aux échanges entre les appareils du réseau.

​**19-**        

**-Fichier2:**                                               
**20-** c'est l'adresse IP 10.10.80.3 qui initialise la communication.                                               

**21-** La communication n'a pas réussi la trame indique que (no response found!) (pas de réponse trouvée). Cela signifie qu'après avoir envoyé la requête de (ping) à l'appareil qui a l'adresse IP 10.11.80.2, il n'a pas reçu de réponse.                                

**22-**                                                              

**-Fichier3:**                                                                
**23-** Dans cette trame, c'est l'appareil avec l'adresse MAC ca:01:da:d2:00:08 qui initialise la communication.                      

**24-**                                        
**25-**                                                 
**26-**                                                                            
