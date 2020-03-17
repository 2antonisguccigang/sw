# Μάθημα: Τεχνολογία Λογισμικού
#
## Προσωπικά Στοιχεία:
#### A.M.: Π2017203
#### Όνομα: Ανδρέας
#### Επώνυμο: Καγκελάρης
#
### Άσκηση 1
##### Τίτλος: performance monitoring
##### Ζητούμενα: monitor the performance of your python scripts and visualize them with colors and/or spark lines
#
##### Προαπαιτούμενα: 
##### α) Download hyperfine
###### wget https://github.com/sharkdp/hyperfine/releases/download/v1.9.0/hyperfine_1.9.0_amd64.deb
##### β) Εγκατάσταση hyperfine
###### sudo dpkg -i hyperfine_1.9.0_amd64.deb
##### γ) Δημιουργία python script το οποίο δημιουργεί αρχεία .txt με πλήθος αριθμών το οποίο και καθορίζεται με παράμετρο κατά την εκτέλεση του script. Το script είναι διαθέσιμο [εδώ](https://github.com/p17kagk/myfiles/blob/master/rand.py.tar.gz) (εκτέλεση με εντολή "python rand.py NUMBER_OF_FILES")
##### δ) Εκτέλεση του python script, ώστε να δημιουργήσουμε αρχεία με τυχαίους αριθμούς, πλήθους 100 και 1000 αντίστοιχα. Θα χρειαστούν στην συνέχεια για την εξαγωγή συμπερασμάτων.
###### python rand.py 100 && python rand.py 1000
##### ε) Δημιουργία 3 python scripts τα οποία θα διαβάζουν ένα .txt αρχείο με τυχαίους αριθμούς, και θα κάνουν ταξινόμηση με χρήση αλγορίθμου i)bubblesort ii)heapsort iii)mergesort. Τα 3 scripts είναι διαθέσιμα [εδώ](https://github.com/p17kagk/myfiles/blob/master/sorting_scripts.tar.gz)
##### στ) Εγκατάσταση asciinema, και δημιουργία λογαριασμού σε αυτό.
###### sudo apt-get install asciinema
##### ζ) Τροποποίηση του .bashrc έτσι ώστε το shell prompt να δείχνει τον Α.Μ. μας.
###### cd ~
###### vi .bashrc
###### export PS1='Π2017203:\w$ ' //add this line in the end of file
###### source .bashrc //execute this command so as to reload new .bashrc
#
##### Εκτέλεση Άσκησης:
##### α) Εκτέλεση του benchmark με 1 εντολή, αρχείο 100 αριθμών. 
###### hyperfine 'python heapsort.py 100'
##### β) Εκτέλεση του benchmark με 1 εντολή, αρχείο 100 αριθμών, αφού προηγουμένως κάνουμε warmup, ώστε τα δεδομένα να είναι φορτωμένα στην cashe memory πριν ξεκινήσει το test, και έτσι να μην επιρρεαστεί το αποτέλεσμα απο την ταχύτητα I/O του μέσου ανάγνωσης.
###### hyperfine --warmup 3 'python heapsort.py 100'
##### γ) Η προκαθορισμένη ρύθμιση του Hyperfine είναι να εκτελέσει την κάθε εντολή τουλάχιστον 10 φορές. Αν επιθυμούμε να το αλλάξουμε αυτό, πχ να έχουμε το αποτέλεσμα τουλάχιστον 8 εκτελέσεων αντί για 10, η εντολή που θα εκτελέσουμε είναι:
###### hyperfine -m 8 'python heapsort.py 100'
##### δ) Αντίστοιχα, για να εκτελεστεί η εντολή ακριβώς τις φορές που επιθυμούμε, η παράμετρος είναι "-r", και για να εκτελέστεί η εντολή το πολύ έναν αριθμό, η παράμετρος είναι "-R".
###### hyperfine -r 8 'python heapsort.py 100'
###### hyperfine -M 8 'python heapsort.py 100'
##### ε) Μπορούμε να κάνουμε export σε αρχείο τα αποτελέσματα, με την παράμετρο "--export-markdown FILENAME". Το αρχείο μπορούμε να το ανοίξουμε με έναν editor, πχ "more".
###### hyperfine --export-markdown export_file 'python heapsort.py 100'
###### more export_file
##### στ) Το export απο το βήμα 'ε' μπορεί να γίνει και σε .csv μορφή με την παράμετρο "--export-csv FILENAME". To αρχείο μπορούμε να το διαβάσουμε με την εντολή "column -s, -t < export_file_csv | less -#2 -N -S".
###### hyperfine --export-csv export_file_csv 'python heapsort.py 100'
###### column -s, -t < export_file_csv | less -#2 -N -S
##### ζ) Επίσης μπορεί να γίνει export σε αρχείο .json. To άνοιγμα του .json αρχείου μπορεί να γίνει με χρήση του προγράμματος "jq" για καλύτερη ανάγνωση.
###### hyperfine --export-json export_file_json 'python heapsort.py 100'
###### cat export_file_json | jq '.' | less
##### η) Τυχόν μηνύματα σφάλματος, μπορούν να μην εκτυπωθούν με την παράμετρο "-i".
###### hyperfine -i 'python heapsort.py 100'
##### θ) Εκτέλεση του benchmark με αρχείο 100 αριθμών, 3 φορές, μία για κάθε αλγόριθμο, ώστε να συγκρίνουμε την απόδοση των 3 διαφορετικών αλγορίθμων. Θα κάνουμε και εδώ χρήση του warmup.
###### hyperfine --warmup 3 'python heapsort.py 100' 'python mergesort.py 100' 'python bubblesort.py 100'
##### ι) Εκτελούμε ξανά το βήμα 'γ', αυτή την φορά χρησιμοποιώντας αρχεία 10.000 αριθμών.
###### hyperfine --warmup 3 'python heapsort.py 1000' 'python mergesort.py 1000' 'python bubblesort.py 1000'
##### κ) Σε περίπτωση που θέλουμε να δούμε αναλυτικά τα βήματα της εκτέλεσης, προσθέτουμε την παράμετρο --show-output. Αυτό είναι ιδιαίτερα χρήσιμο για την ανίχνευση σφαλμάτων.
###### hyperfine --show-output --warmup 3 'python heapsort.py 1000' 'python mergesort.py 1000' 'python bubblesort.py 1000'
#
#### Συμπεράσματα: 
##### Απο την εκτέλεση των βημάτων 'θ' και 'ι' διαπιστώνουμε οτι:
##### i) για μικρό πλήθος αριθμών (100), η ταξινόμηση με χρήση των αλγορίθμων mergesort και heapsort ήταν περίπου η ίδια (1.01 φορές πιο γρήγορος ο mergesort), ενώ η ταξινόμηση με τον αλγόριθμο bubblesort ήταν αρκετά πιο αργή (1.30 φορές πιο αργή απο τον mergesort).
##### ii) για μεγάλο πλήθος τυχαίων αριθμών (1000), ο mergesort ήταν και πάλι ο πιο γρήγορος αλγόριθμος, καθώς ολοκλήρωσε την ταξινόμηση 1.10 φορές πιο γρήγορα απο τον heapsort και 22.20 φορές πιο γρήγορα απο το bubblesort. Απο το τελευταίο μπορούμε να συμπεράνουμε οτι καθώς αυξάνετεται το πλήθος των αριθμών, η αποτελεσματικότητα του αλγορίθμου κατάταξης bubblesort μειώνεται κατά πολύ
###### Summary 
###### 'python mergesort.py 100' ran
###### 1.01 ± 0.01 times faster than 'python heapsort.py 100'
###### 1.30 ± 0.02 times faster than 'python bubblesort.py 100'
###### Summary
###### 'python mergesort.py 1000' ran
###### 1.10 ± 0.02 times faster than 'python heapsort.py 1000'
###### 22.20 ± 0.43 times faster than 'python bubblesort.py 1000'
##### Tests με μεγαλύτερο πλήθος δεν πραγματοποιήθηκε, καθώς ο χρόνος εκτέλεσης του bubblesort ξεπερνά τα διαθέσιμα χρονικά περιθώρια της παρουσίασης της άσκησης.
#
#### 2ος Τρόπος: Ένα εναλλακτικό λογισμικό είναι το py-spy.
##### Προαπαιτούμενα: 
##### α) Install py-spy
###### sudo pip install py-spy (απαιτείται η εγκατάσταση με δικαιώματα root)
##### Εκτέλεση:
##### α) εκτέλεση της εντολής py-spy record, όπου θα καταγράψει στο αρχείο filename.svg πληροφορίες σχετικά με την εκτέλεση του αρχείου και θα τις αναπάραστήσει με γραφικό τρόπο.
###### py-spy record -o filename.svg --pid PID (το PID θα το πάρουμε απο άλλο παράθυρο με την εντολή ps -ef | grep python)
##### β) Εναλλακτικά, μπορούμε να πετύχουμε το ίδιο αποτέλεσμα, με την παρακάτω εντολή, δίνοντας δηλαδή το όνομα του script αντί του PID.
###### py-spy record -o filename.svg -- python bubblesort.py 1000
##### γ) Μπορούμε να καθορίσουμε τον τύπο του αρχείου να είναι διαφορετικός απο τον default (.svg), όπως .raw ή .json.
###### py-spy record -f raw -o raw_image.raw -- python bubblesort.py 1000
###### py-spy record -f speedscope -o speedscope.json -- python bubblesort.py 1000
##### δ) Επίσης, μπορούμε να βλέπουμε σε αληθινό χρόνο το χρόνο που απαιτεί το κάθε functions του python script μου.
###### py-spy top -- python bubblesort.py 10000
##### ε) Τέλος, μπορούμε να δούμε το τρέχον call stack για το κάθε python thread μας.
###### py-spy dump --pid PID
#
##### Όλα τα παραπάνω βήματα, φαίνονται σε [αυτό](https://asciinema.org/a/310236) το link.
#
### Άσκηση 2
##### Τίτλος: try different terminals and shells
##### Ζητούμενα: repeat some of the previous exercises with a different terminal-shell and create a custom configuration that fits your needs
# 
##### 2.1 (st shell): Προαπαιτούμενα: Εγκατάσταση st
###### git clone https://github.com/LukeSmithxyz/st
###### cd st
###### sudo make install
#
##### Εκτέλεση:
##### from bash shell execute "st"
###### st
##### Εκτέλεση των παρακάτω εντολών:
###### pwd
###### ll
###### cd
###### lspci //display H/W
###### lshw //display S/W
###### cat config.h
##### /* from now on we'll demostrate some capabilities of this terminal */
###### scrollback with alt-↑/↓
###### scroll up/down in history with alt-k and alt-j
###### zoom/change font size shift + alt-j/k
###### copy text with alt-c, paste is alt-v
##### edit Xdefaults // change the following-xrdb FILE to make changes
###### st.font: Console-11;
###### *.background: #282828
###### *.foreground: white
###### *.cursorColor: white
#
##### 2.2 (zshell): Προαπαιτούμενα: Εγκατάσταση zsh
###### sudo apt install zsh
##### Εκτέλεση:
##### Verify Installation 
###### zsh --version
##### Εκτέλεση των παρακάτω εντολών:
###### pwd
###### ll
###### cd
###### lspci //display H/W
###### lshw //display S/W
##### Demostrate special capabilities
###### Automatic cd: Just type the name of the directory
###### Recursive path expansion: For example “/u/lo/b” expands to “/usr/local/bin”
###### echo Hello >a.txt >&1         # print Hello to both a.txt and stdout
###### echo Hello >a.txt >/dev/fd/0  # same
###### echo hello | tee a.txt        # same thing in bash
###### echo Hello >a.txt >b.txt      # print Hello to both a.txt and b.txt
##### change configuration
###### .zshrc
#
##### 2.3 (fish shell): Προαπαιτούμενα: Εγκατάσταση fish shell
###### sudo apt-add-repository ppa:fish-shell/release-3
###### sudo apt-get update
###### sudo apt-get install fish
##### Εκτέλεση:
###### pwd
###### ll
###### cd
###### lspci //display H/W
###### lshw //display S/W
##### Demostrate special capabilities
###### for i in foo bar baz; echo $i; end
###### math 5 +5 
###### random
###### begin
######    echo $xml_header
######    echo $html_header
######    if test -e $file
###### end
###### end > out.html
###### dirh
###### echo 'Hello World'
#
##### 2.4 (cshell): Προαπαιτούμενα: Εγκατάσταση csh
###### sudo apt-get install csh
##### Εκτέλεση:
###### pwd
###### ll
###### cd
###### lspci //display H/W
###### lshw //display S/W
##### Demostrate special capabilities
###### rm a\ b
###### echo 'Hello!'
##### set variables
###### set myvariable = word
###### set myvariable = "a string"
##### while command
###### while (1)
###### lpq
###### sleep 10
###### end
##### Parenthesis in the C shell
###### set i = ( a b c d e f g )
###### foreach i ( a b c d e f g )
###### echo $i
###### end
#
##### Όλα τα παραπάνω βήματα, φαίνονται σε [αυτό]() το link.
#
### Άσκηση 3
##### Τίτλος: set-up cloud services
##### Ζητούμενα: ssh to a remote machine and demonstrate your remote cli user land (e.g., email, editor, cv, code, etc)
##### Προαπαιτούμενα: Tα εργαλεία ssh,sftp,telnet είναι προεγκατεστημένα στις διανομές Ubuntu.
###### sudo apt install putty
###### sudo apt-get install openssh-server //on remote host
###### sudo apt-get install vsftpd //on remote host
##### Σε κάθε περίπτωση, το τερματικό στο οποίο θα συνδεόμαστε έχει την IP 192.168.2.51. Θα εκτελέσουμε εντολές editing, file explorer, file execution.
##### Εκτέλεση 3.1(ssh):
###### ssh andreas@192.168.2.51
##### Παράμετροι
###### ssh -E sshlog.txt andreas@192.168.2.51 //-E log_file Append debug logs to log_file instead of standard error.
###### ssh -4 andreas@192.168.2.51 //Force IPv4
###### ssh -6 andreas@192.168.2.51 //Force IPv6
###### ssh -C andreas@192.168.2.51 //Requests compression of all data
###### ssh -c aes128-cbc andreas@192.168.2.51 //Selects the cipher specification for encrypting the session
###### ssh -T andreas@192.168.2.51 //Disable pseudo-terminal allocation. 
###### ssh -V andreas@192.168.2.51 //Display the version number and exit. 
###### ssh -v andreas@192.168.2.51 //Verbose mode.
##### special commands
###### ~# //List forwarded connections.
##### Εκτέλεση εντολών:
###### cd Desktop
###### mkdir temp
###### cd temp
###### vi temp.txt
###### cat temp.txt
##### Εκτέλεση των python scripts της άσκησης 1
###### cat sshlog.txt
#
##### Εκτέλεση 3.2 (ftp/sftp)
###### ftp 192.168.2.51
###### passive
##### enable 'hash on' and get a file
###### get filename
##### Demonstrate FTP Server configuration
###### sudo ufw allow 20/tcp //open TCP ports
###### sudo ufw allow 21/tcp
###### sudo ufw status
###### sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.orig
###### sudo vi /etc/vsftpd.conf
##### Demonstrate other FTP commands
###### ?
##### Εκτέλεση των παραπάνω βημάτων με sftp
###### sftp andreas@192.168.2.51
##### Παράμετροι
###### sftp -Β 16000 andreas@192.168.2.51 //change buffer size
###### sftp -l 1600 andreas@192.168.2.51 //Limits the used bandwidth, specified in Kbit/s.
##### Demonstrate other FTP commands
###### ?
##### put/get a file
###### put
###### get
##### File Management
###### mkdir
###### vi
###### rm file
#
##### Εκτέλεση 3.3 (telnet)
###### telnet 192.168.2.51
##### Άλλος τρόπος
###### telnet
###### o 192.168.2.51
##### Εκτέλεση εντολών:
###### cd Desktop
###### mkdir temp
###### cd temp
###### vi temp.txt
###### cat temp.txt
##### Εκτέλεση των python scripts της άσκησης 1
#
##### Εκτέλεση 3.4 (putty)
###### putty 192.168.2.51
##### Έναρξη καταγραφής asciinema στο νέο παράθυρο
##### Εκτέλεση εντολών:
###### cd Desktop
###### mkdir temp
###### cd temp
###### vi temp.txt
###### cat temp.txt
##### Εκτέλεση των python scripts της άσκησης 1
##### Σύνδεση με ftp, get της καταγραφής, αναπαραγωγή καταγραφής
#
##### Όλα τα παραπάνω βήματα, φαίνονται σε [αυτό]() το link.
#
### Άσκηση 4
##### Τίτλος: send notifications to your desktop-mobile
##### Ζητούμενα: send a notifcation when a big task completes, eg download, compiling, etc
##### Προαπαιτούμενα:
##### Εγκατάσταση ntfy
###### sudo pip install ntfy
##### Εκτέλεση:
### Άσκηση 4
##### Τίτλος: choose your stack
##### Ζητούμενα: set-up a set of cli tools with minimal dependencies and a software licence that allows commercial use and selling
##### Προαπαιτούμενα:
##### Εγκατάσταση howdoi
###### pip install howdoi
##### Εγκατάσταση How2
###### npm install -g how-2
##### Εκτέλεση με howdoi:
###### printf '%(%Y-%m-%d)T\n' -1
###### howdoi print stack trace python
###### howdoi convert mp4 to animated gif
###### howdoi create tar archive
###### howdoi -h
###### howdoi find a file
###### sudo find / -name "rand.py.tar"
###### howdoi -a find a file
###### howdoi -l find a file
###### howdoi -c find a file
###### howdoi -C
###### howdoi -v
###### howdoi -e google find a file
###### howdoi -e bing find a file
###### howdoi -c make persistent usb
###### howdoi -c change time zone
###### howdoi -c delete a folder
###### howdoi -c delete a folder ubuntu
###### howdoi -c python create random numbers
##### Εναλλακτικό λογισμικό how2:
###### how2 unzip.gz 
###### how2 find a file 
###### how2 make a persistent usb ubuntu
###### how2 python random number
###### how2 -l python random number
###### how2 -l Cpp declare array 
###### how2 pull request github 
###### lynx https://unix.stackexchange.com/questions/16743/github-adding-a-repository-as-a-fork-from-an-existing-clone/16765#16765
#
##### Όλα τα παραπάνω βήματα, φαίνονται σε [αυτό]() το link.
#
### Άσκηση 5
##### Τίτλος: set-up a system for python development
##### Ζητούμενα: install and configure in a user folder a python project that is not available through the package manager
##### Προαπαιτούμενα:
##### python3 installed
##### pip installed
##### Εκτέλεση:
###### pip install --user pipenv
###### cd pipenv
###### pipenv install requests
###### vi main.py
###### pipenv run python main.py //run this script using pipenv run
###### pip install virtualenv
###### virtualenv --version //Test your installation
###### virtualenv venv //Create a virtual environment for a project
###### virtualenv -p /usr/bin/python2.7 venv //use the Python interpreter of your choice
###### export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python2.7 //change the interpreter globally with an env variable in ~/.bashrc
###### source venv/bin/activate //To begin using the virtual environment, it needs to be activated
###### pip install requests //Install packages using the pip command
###### deactivate //deactivate the virtual environment
###### pip freeze > requirements.txt //"freeze” the current state of the environment packages
###### pip install -r requirements.txt //install the same packages using the same versions
#
##### Όλα τα παραπάνω βήματα, φαίνονται σε [αυτό]() το link.
#






































  
































