# ΙΟΝΙΟ ΠΑΝΕΠΙΣΤΗΜΙΟ, ΤΜΗΜΑ ΠΛΗΡΟΦΟΡΙΚΗΣ 
## ΜΑΘΗΜΑ
### Τεχνολογία λογισμικού 
Επιβλέπων καθηγητής: Χωριανόπουλος Κωνσταντίνος 

## Στοιχεία φοιτήτριας
### Μαρία Δήμα
### ΑΜ: Π2013029

## Συμμετοχικό περιεχόμενο
### Αποθετήριο σελίδας βιβλίου: https://github.com/p13dima/gr
### Url σελίδας βιβλίου: https://p13dima-gr.netlify.app/

#### Παραδοτέο Β. Νέο διαδραστικό παράδειγμα
##### Page scale descale menu effect: https://p13dima-gr.netlify.app/remix/page_scale_descale_menu_effect/

###### Πηγές
https://www.w3schools.com/css/css3_animations.asp

https://www.w3schools.com/jquery/event_on.asp

https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_menu_icon

## Ασκήσεις terminal
#### Άσκηση 1. Set-up continuous integration. Build and deploy your static site and your cv dynamically every time you make a small change in the source files.
##### asciinema: https://asciinema.org/a/MSENReT9thQV3cuTFSHaIlkl3
##### αποθετήριο σελίδας: https://github.com/p13dima/sw-askisi1
##### url σελίδας: https://p13dima-sw-askisi1.netlify.app/
Δγμιούργησα repository το οποίο έκανα clone στο σύστημα μου. Δημιούργησα τη σελίδα με τα απαραίτητα αρχεία index.html και style.css, έκανα commit και push τις αλλαγές. Χρησιμοποίησα το netlify για να κάνω deploy τη σελίδα μου.

###### Πηγές
https://app.netlify.com/

#### Άσκηση 2. Try different terminals and shells. Repeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs.
##### asciinema: https://asciinema.org/a/T1HJUUtOPl26AJS9uwcGiA5E1
Εγκατέστησα το zsh
```
sudo apt install zsh
```
Εγκατέστησα το oh-my-zsh
```
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Άλλαξα το theme του oh my zsh
```
git clone https://github.com/cviebrock/.oh-my-zsh-custom.git
```
Για να αλλάξω το theme στο .zshrc πρόσθεσα
```
ZSH_THEME="cviebrock"
ZSH_CUSTOM=$HOME/.oh-my-zsh-custom
```
Στη συνέχεια άλλαξα το command prompt του zsh με τον αμ μου, έκανα browse αρχείων και διάβασα το configuration file.

Για να ανοίξω το zsh αφού δεν τον όρισα ως default (ήθελε logout login)
```
zsh
```
###### Πηγές
https://github.com/cviebrock/.oh-my-zsh-custom

https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/

https://github.com/ohmyzsh/ohmyzsh

#### Άσκηση 3. Send notifications to your desktop-mobile. Send a notifcation when a big task completes, eg download, compiling, etc
##### asciinema: https://asciinema.org/a/2JhAF0QdO1PyctCYRkcEp0VBB
Εγκατέστησα το ntfy
```
sudo pip3 install ntfy
```
στη συνέχεια δημιούργησα ένα shell script που κάνει update στο σύστημα και στέλνει notification μόλις τελειώσει
```
#!/bin/bash

sudo apt-get update 
sudo apt-get upgrade

ntfy send "Update procces completed"
```

Έτρεξα το script αφού το έκανα executable
```
sudo chmod +x task.sh
./task.sh
```

Το notification
![notification](ntfy.jpg)

###### Πηγές
https://github.com/dschep/ntfy

https://vitux.com/how-to-write-a-shell-script-in-ubuntu/

#### Άσκηση 4. Use the terminal as an IDE. Edit your files (e.g., cv, website, code, etc) in vim or emacs and compile it in a different panel or use a plug-in
##### asciinema: https://asciinema.org/a/zKcaixOcO2jXTKicWeOYT6Ufl
εγκατέστησα τον vim και το curl
```
sudo apt install vim 
sudo apt install curl
```
Εγκατέστησα τον SpaceVim 
```
curl -sLf https://spacevim.org/install.sh | bash
```
O SpaceVim ανοίγει με τον vim και την πρώτη φορά που τρέχει γίνεται αυτοματα η εγκατάσταση των απαραίτητων plugin. Η χρήση του είναι πολύ απλή
```
spc <number> //πας στο αντιστοιχο παράθυρο
i //insert mode
Esc //exit insert mode
```
Επεξεργάστηκα τη σελίδα που δημιούργησα στην άσκηση 1 και εκανα commit και push τις αλλαγές.

###### Πηγές
https://spacevim.org/quick-start-guide/#online-tutor

https://spacevim.org/documentation/

#### Άσκηση 5. Try different operating systems in the emulator. Load at least two operating systems without a GUI (only CLI) and create a virtual local network
##### asciinema: https://asciinema.org/a/7qn17Tq8546ORFemPd27ua6Mg
Χρησιμοποίησα το Gentoo και το FreeBsd. Για να είναι δυνατή η επικοινωνία μεταξύ των δύο συστημάτων απο τις ρυθμίσεις του virtual box δημιουργησα ένα νέο δίκτυο στο οποίο ένταξα και τα δυο λειτουργικά. Η διαδικασία φαίνεται στις παρακάτω εικόνες.

Δημιουργία του δικτύου
![Δημιουργία του δικτύου](network.jpg)

Gentoo
![Gentoo nat](gentoo.jpg)

FreeBsd
![FreeBsd nat](freebsd-nat.jpg)

Άλλαξα το commanf prompt του Gentoo με τον αμ μου και εγκατέστησα το asciinema
```
sudo emerge -av asciinema
```
με την εντολή ifconfig είδα την ip και τον δύο συστημάτων

Ips
![ip addresses](ip.jpg)

Στη συνέχεια έκανα ping την ip του FreeBsd απο το Gentoo και επιβεβαίωσα τη μεταξύ τους επικοινωνία.
```
ping 192.168.100.5
```

###### Πηγές
https://asciinema.org/docs/installation

https://www.osboxes.org/gentoo/

https://www.osboxes.org/freebsd/

https://www.youtube.com/watch?v=vReAkOq-59I

#### Άσκηση 6. Set-up a system for python development. Install and configure in a user folder a python project that is not available through the package manager.
##### asciinema: https://asciinema.org/a/xxEU2SCxGdpXmLST257pwB67L
Για αυτη την άσκσηση έφτιαξα ένα δικό μου project, το chatta, ένα πάρα πολυ απλό chatbot το οποίο το έκανα deploy σε virtual enviroment που δημιούργησα.

###### Πηγές
https://docs.python-guide.org/dev/virtualenvs/

https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/

https://www.afternerd.com/blog/python-string-contains/

