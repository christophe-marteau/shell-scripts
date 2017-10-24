# Scripts bash

## grepMAC

Outil qui permet essaye de reconnaitre une adresse MAC dans un filtre grep, pour l'étendre aux différents
formats d'adresse MAC pour effectuer une recherche dans un fichier. Le script prend en charge les formats
d'adresse MAC suivants :

  - xx:xx:xx:xx:xx:xx
  - xx-xx-xx-xx-xx-xx
  - xxxxxx-xxxxxx
  - xxxxxxxxxxxx

Le script est insensible à la case de l'adresse MAC

Usage :

  ```
  grepMAC <filtre> <file>
  ```

Exemple :
  
  ```
  grepMAC 84248D872DC4 /var/log/syslog
  ```

L'équivalent grep de cet exemple est : `/bin/grep -iE "84248d872dc4|84:24:8d:87:2d:c4|84-24-8d-87-2d-c4|84248d-872dc4" "/var/log/syslog"`

  ```
  grepMAC 'blabla|84248D872DC4|plicploc|84:24:8d:87:2d:a4|213.234.45.46' /var/log/syslog
  ```

L'équivalent grep de cet exemple est : `/bin/grep -iE "blabla|84248d872dc4|84:24:8d:87:2d:c4|84-24-8d-87-2d-c4|84248d-872dc4|plicploc|84248d872da4|84:24:8d:87:2d:a4|84-24-8d-87-2d-a4|84248d-872da4|213.234.45.46" "/var/log/syslog"`

