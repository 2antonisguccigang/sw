# ***ΤΜΗΜΑ ΠΛΗΡΟΦΟΡΙΚΗΣ ΙΟΝΙΟΥ ΠΑΝΕΠΙΣΤΗΜΙΟΥ***
## ***Τεχνολογία Λογισμικού***
### ***Αναφορά***

### ***Στοιχεία φοιτητή:*** 

Όνομα: Φουτσιτζή Σοφρονία

AM: Π2017063

### ***Επιβλέπων καθηγητής: Χωριανόπουλος Κωνσταντίνος***

   
   ### ***Άσκηση 1 "Send notifications to your desktop-mobile"***
   
   #### [Link για την άσκηση](https://asciinema.org/a/wZhReoAb7YDQq6O8ZlLZVWfbw)
   
   Για την υλοποίηση της συγκεκριμένης εργασίας χρησιμοποιήσα το [ntfy](https://github.com/dschep/ntfy), με την χρήση του οποίου μπορούσα "μέσα" από το terminal (με την χρήση command-line εντολών), να στείλω ειδοποιήσεις στην επιφάνεια εργασίας του υπολογιστή μου. Παράλληλα, με την χρήση του συγκεκριμένου προγράμματος κάθε φορά που υλοποιούσα με διεργασία που διαρκούσε παραπάνω από 10sec (πχ να ακτεβάσω μία εφαρμογή ή να χρησιμοποιήσω μία εφαρμογή πχ το asciinema) μου εμφάνιζε, αυτομάτως, ειδοποίηση.

                                      1.Αλλαγή του τιτλού/Αποστολή ειδοποίησης
![image](https://github.com/fsofronia/sw/blob/P2017063/projects/2017063/screen03.jpg)


 
                                 2.Ειδοποίση/Επιτυχία διεργασίας/Χρόνος διεργασίας   
![image](https://github.com/fsofronia/sw/blob/P2017063/projects/2017063/screen04.jpg)
   
   
   
   
    
    
    
    
### ***Άσκηση 2 "try different terminals and shells"***
   #### ***repeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs***
   
   #### [Link για την άσκηση](https://asciinema.org/a/oTJZq0Fe6blPNT40QYy13irV8)
   
   Για την υλοποίηση της συγκεκριμένης εργασίας χρησιμοποιήσα το [the simple (suckless) terminal](https://github.com/LukeSmithxyz/st) και [Z shell](https://en.wikipedia.org/wiki/Z_shell). 
   
   Με την χρήση του συγκεκριμένου κελιού και τερματικού αλλά και με την χρήση του το [imagemagick](https://www.howtogeek.com/109369/how-to-quickly-resize-convert-modify-images-from-the-linux-terminal/), εργαλείο το οποίο χρησιμοποίησα για την επεξεργασία εικόνων, υλοποίησα μία από τις προηγούμενες εργασίες και συγκεκριμένα την εργασία "batch image conversion (convert your image files to different sizes and formats)" από τα Πολυμέσα αλλάζοντας το format των φωτογραφιών και απο .jpg σε .jpeg. Με τη χρήση της εντολής `convert *jpg *jpeg` δημιουργήθηκαν στον φάκελο  τέσσερις νέες φωτογραφίες αντίγραφα των προηγούμενων αλλά και σε .jpeg (στον φάκελο υπάρχουν και οι εικόνες σε .jpg).

   Έπειτα, με την εντολή `mv *jpeg /root/Downloads/New` μεταφέρθηκαν οι φωτογραφίες σε κατάληξη .jpeg σε έναν άλλο φάκελο όπου και επεξεργάστηκαν οι διαστάσεις τους, συγκεκριμένα υλοποιήθηκε αλλαγή στο μέγεθος των εικόνων κατά 20% με την χρήση της εντολής ` convert *.jpeg -resize 20% NewImage.jpeg`. Τέλος, με την εντολή `identify *.jpeg ` εμφανίστηκαν οι πληροφορίες για όλες τις φωτογραφίες σε .jpeg που όπως φαίνεται είναι, πλεόν, οι διπλάσιες, καθώς υπάρχουν οι αρχικές εικόνες αλλά και τα αντίγραφα τους με όνομα NewImage-().jpeg, στις οποίες οι διαστάσεις τους έχουν διαμορφωθεί αντίστοιχα.

   
 - Η εμφάνιση του ονόματος του κελιόυ-shell που χρησιμοποίησα γίνεται με τη χρήση της εντολής: (Output: zsh)
 
        $ echo $0
  
  - Η εμφάνιση του ονόματος του τερματικού-terminal που χρησιμοποίησα γίνεται με τη χρήση της εντολής: (Output: st-256color)
         
        $ echo $TERM 


