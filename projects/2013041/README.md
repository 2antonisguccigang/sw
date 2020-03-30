# ΙΟΝΙΟ ΠΑΝΕΠΙΣΤΗΜΙΟ, ΤΜΗΜΑ ΠΛΗΡΟΦΟΡΙΚΗΣ 
## ΜΑΘΗΜΑ
### Τεχνολογία λογισμικού 
Επιβλέπων καθηγητής: Χωριανόπουλος Κωνσταντίνος 

## Στοιχεία φοιτητή  
### Φοίβος Αργυρίδης
### ΑΜ: Π2013041

## Συμμετοχικό περιεχόμενο
### url αποθετηρίου: https://github.com/fivosf/gr
### url σελιδας: https://fivos-gr.netlify.com/
### Παραδοτέο 1.Α
#### Eικόνα 1: Raspberry pi https://fivos-gr.netlify.com/gallery/f-raspberry-pi/
#### Εικόνα 2: Playstation https://fivos-gr.netlify.com/gallery/playstation/


### Άσκηση 1. Try different terminals and shells. Ρepeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs
#### asciinema: https://asciinema.org/a/e4dounmZh2PBkr2GbrtOIzn5u
Χρησιμοποίησα το zsh

```
sudo apt install zsh
```

To zsh terminal by default είναι το ίδιο με το bash. Όλες οι παραμετροποιήσεις γίνοντε απο το αρχείο .zshrc, Δημιουργησα το αρχείο και άλλαξα την μεταλητή PS1 με τον ΑΜ μου (Άσκηση 1 HCI), ενεργοποίησα τα χρώματα και το auto complete στις εντολες. Επίσης πατωντας 2 φορες το tab μπορω να δω όλα τα αρχεια (και dotfiles) με οποιαδήποτε εντολή. Τέλος έδειξα το configuration file μου .bashrc

```
nano .zshrc
```

#### Πηγές
https://www.youtube.com/watch?v=eLEo4OQ-cuQ

### Άσκηση 2. Set-up a system for python development. Install and configure in a user folder a python project that is not available through the package manager.
#### asciinema: https://asciinema.org/a/QolaktK9DbVgTEk2B9oZ38KGH
Για την άσκηση αυτή χρησιμοποίησα ένα δικό μου project το οποίο κάνει print τίτλους ειδήσεων απο www.euro2day.gr μέσω rss. Το μοναδικό dependency στο project είναι το feedparser.

```
pip install feedparser
```

Για να στήσω το virtual enviroment ακολούθησα τον οδηγό https://docs.python-guide.org/dev/virtualenvs/. Ο κώδικας του project είναι στο github. https://github.com/fivosf/mynews.

### Άσκηση 3. Send notifications to your desktop-mobile. Send a notifcation when a big task completes, eg download, compiling, etc
#### asciinema: https://asciinema.org/a/PorL9zTrycaOBRuGGDQ8JVXQt
Χρησιμοποίησα το ntfy

```
sudo pip install ntfy
```
Εφτιαξα ενα bash script (update.sh) το οποίο τρέχει update kai upgrade και στο τέλος στέλνει το notification στον χρήστη.

```
#!/bin/bash

sudo apt update
sudo apt upgrade -y

ntfy -t 'System' send "Upgrade Completed"
```

Παρακάτω φαίνεται το notification
![The notification](upgrade.jpg)

#### Πηγές
https://www.youtube.com/watch?v=bbdQXfReuG0

### Άσκηση 3. Try different operating systems in the emulator. Load at least two operating systems without a GUI (only CLI) and create a virtual local network.
#### asciinema: https://asciinema.org/a/7oCqxmiZQ21ATjk9DZzQ1WN8K
χρησιμοποίησα το ArchLinux και το FreeBsd με το virtual box σαν emulator. Για να δημιουργήσω το virtual local network απο τις ρυθμίσεις του virtual box δημιουργησα καινούργιο δίκτυο όπως φαίνεται στην παρακάτω εικόνα

![network creation](netcreate.jpg)

Στη συνέχεια απο τις ρυθμίσεις του κάθε συστήματος τα ένταξα στο καινούργιο δίκτυο που δημιουργησα

![assigning to network](netcreate2.jpg)

Στην παρακάτω εικόνα φαίνονται οι ip adresses των δύο συστημάτων

![ipaddress](ipaddress.jpg)

Για να δω την ip στο ArchLinux και στο FreeBsd χρησιμοποίησα τις εντολές αντίστοιχα

```
ip addr
ifconfig
```

Το asciinema εγκαταστάθηκε στο ArchLinux και το recording εγινε απο εκει.

```
sudo pip install asciinema
```

Για να τεκμηριώσω ότι υπάρχει επικοινωνία μεταξύ των δύο συστημάτων εκανα ping to freeBsd απο το ArchLinux

```
ping 192.168.100.5
```

#### Πηγές
https://www.youtube.com/watch?v=vReAkOq-59I





