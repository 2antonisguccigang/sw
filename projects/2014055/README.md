# ΙΟΝΙΟ ΠΑΝΕΠΙΣΤΗΜΙΟ, ΤΜΗΜΑ ΠΛΗΡΟΦΟΡΙΚΗΣ 
## ΜΑΘΗΜΑ Τεχνολογία Λογισμικού

## Στοιχεία φοιτητή  
### Παπακωστούλης Αντώνιος
### ΑΜ: Π2014055




### Άσκηση 1. Set-up continuous integration.build and deploy your static site and your cv dynamically every time you make a small change in the source files.

Για την παραπάνω άσκηση η σελίδα υλοποιήθηκε με το Github pages και χωρίς terminal επομένως δεν υπάρχει κάποιο asciinema url.


[CV](https://p14papa1.github.io/CV/)

[αποθετήριο κώδικα](https://github.com/p14papa1/CV)


### Άσκηση 2. Try different terminals and shells. Repeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs	

[asciinema url](https://asciinema.org/a/vdcpu4sMnC4F7ai02QP084MKB)

Για την παραπάνω άσκηση χρησιμοποίησα δύο καινούργια terminal το terminator και το xterm καθώς και το ranger για να επεξεργαστώ αρχεία κειμένου όπως ζητούσε μια άσκηση του μαθήματος Επικοινωνία Ανθρώπου υπολογιστή. Αρχικά για την εγκατάσταση

```bash
sudo apt-get install terminator
sudo apt-get install xterm
sudo apt-get install ranger
```

Ενώ για να ανοίξω το καθένα terminal έγραψα απλά τις εντολές


```bash 
xterm
terminal
ranger
```

![](xterm.png)

![](terminator.png)





### Άσκηση 3. Use the terminal as an IDE. Edit your files (e.g., cv, website, code, etc) in vim or emacs and compile it in a different panel or use a plug-in.

[asciinema url](https://asciinema.org/a/WQquskz7nLa40TdOSI95bPl44)

Για αυτή την άσκηση αποφάσισα να γράψω ένα απλό πρόγραμμα Hello World σε c με τον vi. Στην συνέχεια έγινε compile. Όλα έγιναν σε terminal. 




### Άσκηση 4. Send notifications to your desktop-mobile. Send a notifcation when a big task completes, eg download, compiling, etc	

[asciinema url](https://asciinema.org/a/IhO7bbcD78Dz6pKL6w83KFk7p)

Αρχικά για την άσκηση χρειάστηκε να εγκαταστήσω το ntfy.

```bash
sudo pip3 install ntfy
```

Στην συνέχεια έκανα ένα απλό update/upgrade και στην συνέχεια του είπα να μου στείλει notification όταν τελειώσει το upgrade. Τέλος το έκανα εκτελέσιμο και το έτρεξα.

```bash
sudo apt update
sudo apt upgrade
ntfy -t 'System' send "Upgrade Completed"
sudo chmod +x notification
./notification
```

![](Ntfy.png)













