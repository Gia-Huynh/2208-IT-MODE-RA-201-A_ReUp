# Sas2flash_shenanigans
(I will spam Gigabyte RA-201-A in this post, a lot, since I coudln't find any information regarding flashing this card, so that other people with the same Gigabyte RA-201-A can find this post)  
I wasted 5 days trying to flash my Gigabyte RA-201-A (rev 2.0) to IT mode using Sas2flash, but all I can get was "No LSI SAS adapters found!" no matter what i tried.  
Using the clue from https://www.truenas.com/community/threads/ibm-serveraid-m1015-and-no-lsi-sas-adapters-found.27445/,  
I desperately tried flashing the LSI 9207's sbr file to the card from this link: https://forums.servethehome.com/index.php?threads/the-complete-lsi-avago-broadcom-sbr-download-megathread.33607/  
which somehow makes sas2flash finally able to recognize my card, the commmand was  
megarec -writesbr 0 empty512.sbr (I flashed the 512 bytes file since the original sbr on this card has 512 sbr file size, and flashing the 256 bytes empty sbr doesn't fully  wiped out the card)  
megarec -writesbr 9207SBR.bin  
dunno if I did megarec -cleanflash 0 or not.  
No other guide on the internet tells you about this, which is kinda weird lol.  
Gigabyte RA-201-A No LSI SAS adapters found sas2flash.  
If somehow you fucked up then this link will guide you to recover the card: https://forums.servethehome.com/index.php?threads/is-there-a-way-to-restore-an-lsi-2208-after-firmware-update-failure.13237/  
