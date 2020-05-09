# Τμήμα Πληροφορικής Ιονίου Πανεπιστημίου
### Μάθημα: Τεχνολογίες Λογισμικού
* Σύνδεσμος Αποθετηρίου: https://github.com/mmits/sw

#### Στοιχεία Φοιτητή
* Ονοματεπώνυμο: Ελένη Μαρία Μητσοπούλου
* ΑΜ: Π2017018

#### Επιβλέπων Καθηγητής
* Χωριανόπουλος Κωνσταντίνος

---

## Άσκηση 1:
**Τίτλος:** Use the terminal as an IDE<br>
**Περιγραφή:** Edit your files (e.g., cv, website, code, etc) in vim or emacs and compile it in a different panel or use a plug-in<br>
**Asciinema link:** https://asciinema.org/a/gZHBJVEWIjmmnLhfNecxSHq7U

Χρησιμοποίησα το [SpaceVim](https://spacevim.org/), μια επέκταση του text editor Vim η οποία διαθέτει εργαλεία για την ανάπτυξη κώδικα με διάφορες γλώσσες προγραμματισμού και πολλά άλλα.
![1](SC1.png)

Μετά την εγκατάσταση του SpaceVim, αλλάζω και προσθέτω νέες παραμέτρους στο config file του προγράμματος, ώστε να υποστηρίζει error checking, autocompletion και compiling της γλώσσας Python.<br>
![2](SC2.png)
Το κομμάτι κώδικα που προσέθεσα είναι το παρακάτω:<br>
```
[[layers]]
name = 'lang#python
auto-completion-return-key-behavior = "complete"
auto-completion-tab-key-behavior = "cycle"
```

Ύστερα, μπορώ να γράψω ένα πρόγραμμα, το οποίο μετά το SpaceVim εκτελέι μέσα από το δικό του shell.
![2](SC4.png)

## Άσκηση 2:
**Τίτλος:** Send notifications to you desktop-mobile<br>
**Περιγραφή:** Send a notifcation when a big task completes, eg download, compiling, etc

Χρησιμοποίησα το [ntfy](https://github.com/dschep/ntfy), μια python-based εφαρμογή η οποία στέλνει notifications στο περιβάλλον του υπολογιστή μου.

Σε περιβάλλοντα Linux απαιτείται η εντολή `eval "$(ntfy shell-integration)"` στο config file του bash του συστήματος για να στέλνεται ειδοποίηση κάθε φορά που τερματίζεται μια διεργασία.

Λόγω της λειτουργίας της εφαρμογής μόνο στο περιβάλλον του υπολογιστή και όχι στο terminal, αντί για asciicast έφτιαξα ένα gif που δείχνει λειτουργία του ntfy
![1](ntfy.gif)

Επίσης, με τη χρήση του intergration με την υπηρεσία αποστολής μηνυμάτων Pushbullet, έστειλα μια ειδοποίηση από το terminal στο κινητό μου.
![2](pushbullet.png)

Μόνη απαίτηση ήταν να προσθέσω ένα κομμάτι κειμένου στο config αρχείο του ntfy, το οποίο περιέχει το access token που μου δίνει το Pushbullet.

## Άσκηση 3:
**Τίτλος:** Create an agent for news<br>
**Περιγραφή:** The demo should display the new content added on a news web site

## Άσκηση 4:
**Τίτλος:** Create your own static site and blog generator<br>
**Περιγραφή:** The generator should consider posts, pages, and templates

Χρησιμοποίησα το [Hugo](https://gohugo.io/). 

Μετά την εγκατάσταση του Hugo, εγκατέστησα το θέμα της ιστοσελίδας στο οποίο θέλω να αλλάξω τη σελίδα μου, το [Notepadium](https://themes.gohugo.io/hugo-notepadium/). και μετά έγραψα ένα νέο post, όπως φαίνεται παρακάτω.
![1](SC11.png)

## Άσκηση 5:
**Τίτλος:** Performance monitoring<br>
**Περιγραφή:** Monitor the performance of your python scripts and visualize them with colors and/or spark lines
**Asciinema link:** https://asciinema.org/a/dZMJ2XSyOhdkNAAn8ZWo69ZjS

## Άσκηση 6:

**Asciinema link:** https://asciinema.org/a/9zIhVI2nlGBIstHsjKex9ZQTj
