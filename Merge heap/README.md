# Merge heap

Η merge heap (ή αλλιώς meld heap) είναι μια randomized δομή δεδομένων. Είναι ιδιαίτερα εύκολη στην υλοποίηση, καθώς όλες οι πράξεις της heap υλοποιούνται με μία και μόνο συνάρτηση, την `merge`. Η υλοποίηση που παρέχουμε εδώ στο `source.cpp` κάνει heap sort χρησιμοποιώντας την merge heap.

## Περιγραφή του αλγορίθμου

Καθώς ο αλγόριθμος αποτελείται ουσιαστικά από μία και μόνο συνάρτηση, χρειάζεται να περιγράψουμε μόνο αυτήν. Για να ενώσουμε δύο heaps, αρκεί να επιλέξουμε τυχαία εάν η ρίζα της heap με τη μεγαλύτερη κορυφή θα καταλήξει στο αριστερό ή στο δεξί παιδί της heap με τη μικρότερη κορυφή. Αφού το αποφασίσουμε αυτό, απλά κάνουμε αναδρομικά merge την heap με την μεγαλύτερη κορυφή, με το αντίστοιχο παιδί της heap με την μικρότερη κορυφή. Αποδεικνύεται ότι με αυτόν τον τρόπο, η merge έχει πολυπλοκότητα O(log n).