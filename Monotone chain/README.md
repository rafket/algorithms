# Monotone Chain

Ο αλγόριθμος Monotone Chain βρίσκει την κυρτή θήκη ενός συνόλου N σημείων σε O(NlogN). Η κυρτή θήκη ορίζεται ως το πολύγωνο με τη μικρότερη περίμετρο το οποίο περιέχει όλα τα σημεία.

## Περιγραφή του αλγορίθμου

Αρχικά ταξινομούμε τα σημεία ως προς την τετμημένη με αύξουσα σειρά. Παρατηρούμε ότι το αριστερότερο και το δεξιότερο σημείο (ή, σε περίπτωση περισσότερων από ένα σημείο, το αριστερότερο και κατώτερο, και δεξιότερο και ανώτερο) θα είναι αναγκαστικά σημεία της κυρτής θήκης. Μπορούμε να χωρίσουμε την κυρτή θήκη σε δύο "αλυσίδες", την ανώτερη αλυσίδα (upper chain), η οποία περιέχει τα σημεία που βρίσκονται δεξιόστροφα στη διαδρομή από το αριστερότερο σημείο προς το δεξιότερο, και την κατώτερη αλυσίδα (lower chain), η οποία περιέχει τα σημεία που βρίσκονται δεξιόστροφα στη διαδρομή από το δεξιότερο σημείο προς το αριστερότερο.Αρκεί λοιπόν να υπολογίσουμε τις δύο αυτές αλυσίδες. Θα χρησιμοποιήσουμε την συνάρτηση CCW (Counter-ClockWise), η οποία δέχεται τρία σημεία A,B,C, και επιστρέφει θετικό αριθμό αν το σημείο C βρίσκεται αριστερόστροφα της ημιευθείας που ξεκινάει από το A και περνάει από το B, μηδέν στην περίπτωση που είναι συνευθειακά, και αρνητικό αριθμό σε κάθε άλλη περίπτωση. Χρησιμοποιώντας την συνάρτηση αυτή, μπορούμε σε ένα πέρασμα του πίνακα των σημείων να δημιουργήσουμε το upper chain, εισάγοντας τα σημεία σε μία στοίβα (stack) με την ιδιότητα ότι τα τρία τελευταία στοιχεία της στοίβας έχουν αρνητικό CCW. Το ίδιο ακριβώς (απλώς με αντίστροφη σειρά προσθήκης σημείων) μπορούμε να κάνουμε για να δημιουργήσουμε το lower chain. Συνδυάζοντας αυτές τις δύο αλυσίδες, μπορούμε να βρούμε την απάντηση.