Το πρόγραμμα περιέχει buffer overflow στην γραμμή strcpy(ifr.ifr_name, ifname);

Η μεταβλητή ifr_name είναι buffer μεγέθους IFNAMSIZ = 16 bytes

Το πρόγραμμα αντιγράφει το interface ifname στο buffer με την συνάρτηση strcpy

Η strcpy δεν ελέγχει το μέγεθος των δεδομένων οπότε αν δοθεί input μεγαλύτερο απο 16 bytes θα έχουμε buffet overflow 

Για το exploit δημιουργούμε script που παράγει ένα μεγάλο string

To script δημιουργεί συμβολοσειρά 200 χαρακτήρων και προκαλεί buffer overflow έτσι το πρόγραμμα επιστρέφει Segmentation fault 