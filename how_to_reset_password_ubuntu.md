## How to reset forgotten root password in Ubuntu
In this article, you will learn how to reset the forgotten root password on Ubuntu 18.04 LTS and Ubuntu 20.04 LTS.
Firstly, you need to either power on or reboot your Ubuntu system. You should get a grub menu as shown below. If you are running your system on VirtualBox, press the ‘SHIFT’ key on the keyboard to bring up the boot menu.

+ Ubuntu Grub Menu
![Ubuntu Grub menu](/pictures/ubuntu/ubuntu_gub.png)
Next, press the 'e' key to edit the grub parameters. This should display a screen as shown below.

+ Grub Boot Parameters
![Grub ubuntu](/pictures/ubuntu/grub_boot.png)
Scroll down until you get to the line that begins with 'linux /boot/vmlinuz' the entire line is highlighted below.

+ Find Grub Boot Parameter
![Grub ubuntu](/pictures/ubuntu/grub_boot_1.png)
Narrow down to a section that reads "ro quiet splash $vt_handoff".

+ Locate Grub Boot Parameter
![Grub ubuntu](/pictures/ubuntu/grub_boot_2.png)
Replace "ro quiet splash $vt_handoff" with rw init=/bin/bash as shown. The aim is to set the root file system with read and write commands denoted by the rw prefix.

+ Enable Root Filesystem
![Grub ubuntu](/pictures/ubuntu/grub_boot_3.png)
Thereafter, press ctrl + x or F10 to reboot your system. Your system will boot into a root shell screen as shown below. You can confirm that the root filesystem had read and write access rights by running the command.
```bash
# mount | grep -w /
```
The output in the screenshot below confirms read and write access rights denoted by rw.

+ Confirm Root Filesytem Permissions
![File Systems](/pictures/ubuntu/file_system.png)
To reset the root password execute the command.
```bash
# passwd
``` 
Provide a new password and confirm it. Thereafter, you will get a ‘password updated successfully’ notification.

+ Reset Root Password in Ubuntu
![Reset Password](/pictures/ubuntu/change_password.png)
With the root password successfully changed, reboot into your Ubuntu system by running the command.
```bash
# exec /sbin/init
```
----------------------------------------------------------------------------------------------------------------------------------------
## Comment réinitialiser le mot de passe root oublié dans Ubuntu
Dans cet article, vous apprendrez comment réinitialiser le mot de passe root oublié sur Ubuntu 18.04 LTS et Ubuntu 20.04 LTS.
Tout d’abord, vous devez allumer ou redémarrer votre système Ubuntu. Vous devriez obtenir un menu de grub comme indiqué ci-dessous. Si vous exécutez votre système sur VirtualBox, appuyez sur la touche 'SHIFT' du clavier pour afficher le menu de démarrage.

+ Menu Ubuntu Grub
! [Menu Ubuntu Grub](/pictures/ubuntu/ubuntu_gub.png)
Ensuite, appuyez sur la touche 'e' pour modifier les paramètres grub. Cela devrait afficher un écran comme indiqué ci-dessous.

+ Paramètres de démarrage Grub
! [Grub ubuntu](/pictures/ubuntu/grub_boot.png)
Faites défiler vers le bas jusqu’à ce que vous arriviez à la ligne qui commence par 'linux /boot/vmlinuz', la ligne entière est mise en surbrillance ci-dessous.

+ Trouver le paramètre de démarrage Grub
! [Grub ubuntu](/pictures/ubuntu/grub_boot_1.png)
Réduisez à une section qui se lit « ro quiet splash $vt_handoff ».

+ Localiser le paramètre de démarrage Grub
! [Grub ubuntu](/pictures/ubuntu/grub_boot_2.png)
Remplacez « ro quiet splash $vt_handoff » par rw init=/bin/bash comme indiqué. L’objectif est de définir le système de fichiers racine avec des commandes de lecture et d’écriture indiquées par le préfixe rw.

+ Activer le système de fichiers racine
! [Grub ubuntu](/pictures/ubuntu/grub_boot_3.png)
Ensuite, appuyez sur ctrl + x ou F10 pour redémarrer votre système. Votre système démarrera dans un écran de shell racine comme indiqué ci-dessous. Vous pouvez confirmer que le système de fichiers racine disposait de droits d’accès en lecture et en écriture en exécutant la commande.
'''bash
# montage | grep -w /
```
La sortie dans la capture d’écran ci-dessous confirme les droits d’accès en lecture et en écriture indiqués par rw.

+ Confirmer les autorisations de Root Filesytem
! [Systèmes de fichiers](/pictures/ubuntu/file_system.png)
Pour réinitialiser le mot de passe root, exécutez la commande.
'''bash
# passwd
``` 
Fournissez un nouveau mot de passe et confirmez-le. Par la suite, vous recevrez une notification « mot de passe mis à jour avec succès ».

+ Réinitialiser le mot de passe root dans Ubuntu
! [Réinitialiser le mot de passe](/pictures/ubuntu/change_password.png)
Une fois le mot de passe root modifié avec succès, redémarrez dans votre système Ubuntu en exécutant la commande.
'''bash
# exec /sbin/init
```


Link:
+ [Youtube](https://www.youtube.com/watch?v=n0EiH5LJyrY)
+ [Tecmint](https://www.tecmint.com/install-virtualbox-in-debian-and-ubuntu/)