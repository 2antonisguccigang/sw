# Τεχνολογία Λογισμικού
**Όνομα:** Αλεξάνδρα  
**Επώνυμο:** Παραμύθα  
**ΑΜ:** Π2017001  
**Προσωπικό Αποθετήριο:** https://github.com/lextale/sw/tree/2017001/projects/2017001  

___

## Εργασία 1: try different terminals and shells
**references:** zsh  
**deliverables:** repeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs  
**asciinema:** https://asciinema.org/a/7Vc9CCpHoDG56NLKevLTwD53D  
**asciinema file in repo:** https://github.com/lextale/sw/blob/2017001/projects/2017001/zsh/zsh.cast  


#### Περιγραφή
Εγκατέστησα το zsh shell με την εντολή:
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Στη συνέχεια "πειράζοντας το .zshrc αρχείο που βρίσκονται τα configurations του shell άλλαξα το θέμα, ώστε κάθε φορά που κάνει launch να επιλέγεται ένα τυχαίο θέμα.
```
<span style="background-color:lightblue;border: 1px lightblue;border-radius: 25px;padding:10px;"><code>nano /home/p2017001/.zshrc</code></span>
```
Τέλος, δοκίμασα να ανοίξω διάφορα shells και να τρέξω κάποια εντολή σε ένα από αυτά.  
  
<br>  
<p  align="center">
    <em>Asciinema: zsh</em>
    <br>
    <a href="https://asciinema.org/a/7Vc9CCpHoDG56NLKevLTwD53D?autoplay=1"><img src="https://asciinema.org/a/7Vc9CCpHoDG56NLKevLTwD53D.png" height="500" width="500"/></a>
</p>

___

## Εργασία 2: use the terminal as an IDE
**references:** https://www.latex-project.org/  
**deliverables**: edit your files (e.g., cv, website, code, etc) in vim or emacs and compile it in a different panel or use a plug-in  
**asciinema:** https://asciinema.org/a/nbqWuP9mjPOrNq9FLMyHJW76B  
**asciinema file in repo: https://github.com/lextale/sw/blob/2017001/projects/2017001/LaTex/latex.cast  

#### Περιγραφή
Άνοιξα ένα tex αρχείο στο texstudio και το επεξεργάστηκα
```
texstudio sampletex.tex
```
<p align="center">
  <img src="https://github.com/lextale/sw/blob/2017001/projects/2017001/LaTex/latex.gif" height="500 width="550>
</p>

Το έκανα compile σε μορφή pdf με την εντολή:
```
pdftex sampletex.tex
```
<p align="center">
  <img src="https://github.com/lextale/sw/blob/2017001/projects/2017001/LaTex/pdftex.gif" height="500 width="550>
</p>
<br>  
<p  align="center">
    <em>Asciinema: Latex</em>
    <br>
    <a href="https://asciinema.org/a/nbqWuP9mjPOrNq9FLMyHJW76B?autoplay=1"><img src="https://asciinema.org/a/nbqWuP9mjPOrNq9FLMyHJW76B.png" height="500" width="500"/></a>
</p>

___

## Εργασία 3: set-up a system for python development
**references:** https://docs.python-guide.org/dev/virtualenvs/  
**deliverables:** install and configure in a user folder a python project that is not available through the package manager  
**asciinema:** https://asciinema.org/a/tvHgXHSCaXPJn6AXuSrbfA7HP  
**asciinema file in repo:** https://github.com/lextale/sw/blob/2017001/projects/2017001/Python-Visual-Enviroments/python-visual-env.cast  

#### Περιγραφή
Εγκατέστησα τον dependency magager _Pipenv_
```
pip install --user pipenv
```
Μέσα στον φάκελο του python project μου εγκατέστησα μέσω του pipenv την library _requests_ που θα χρησιμεύσει για το πρόγραμμά μου
```
pipenv install requests
```
Δημιούργησα ένα πρόγραμμα και το έτρεξα με την εντολή
```
pipenv run python main.py
```
Εγκατέστησα το _virtualenv_
```
pip3 install virtualenv
```
Δημιούργησα το δικό μου enviroment
```
virtualenv mypyenv
```
Ενεργοποιήθηκε ως εξής:
```
source mypyenv/bin/activate
```
Και απενεργοποιήθηκε αναλόγα:
```
deactivate
```
<br>  
<p  align="center">
    <em>Asciinema: Virtual Enviroments</em>
    <br>
    <a href="https://asciinema.org/a/tvHgXHSCaXPJn6AXuSrbfA7HP?autoplay=1"><img src="https://asciinema.org/a/tvHgXHSCaXPJn6AXuSrbfA7HP.png" height="500" width="500"/></a>
</p>
___
## Εργασία 4: send notifications to your desktop-mobile
**references:** https://github.com/dschep/ntfy  
**deliverables:** send a notifcation when a big task completes, eg download, compiling, etc  
**asciinema:** https://asciinema.org/a/xdm8CJCTdbTF1zCZikx6HKxLm  
**asciinema file in repo:** https://github.com/lextale/sw/blob/2017001/projects/2017001/ntfy/ntfy.cast

#### Περιγραφή
Στάλθηκε μια ειδοποίηση όταν κατέβηκε ένα αρχείο:
```
ntfy -t "Download Complete" done youtube-dl --extract-audio --audio-format mp3 https://www.youtube.com/watch?v=gs-MtItyOFc
```
<p align="center">
  <img src="https://github.com/lextale/sw/blob/2017001/projects/2017001/ntfy/ntfy.gif" height="500 width="550>
</p>

<br>  
<p  align="center">
    <em>Asciinema: Ntfy</em>
    <br>
    <a href="https://asciinema.org/a/xdm8CJCTdbTF1zCZikx6HKxLm?autoplay=1"><img src="https://asciinema.org/a/xdm8CJCTdbTF1zCZikx6HKxLm.png" height="500" width="500"/></a>
</p>
___


