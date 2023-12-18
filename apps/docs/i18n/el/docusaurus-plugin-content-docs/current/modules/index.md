# Βασικά Αρθρώματα

`Αυτό το έγγραφο έχει μεταφραστεί αυτόματα και μπορεί να περιέχει λάθη. Μη διστάσετε να ανοίξετε ένα Pull Request για να προτείνετε αλλαγές.`

Το LlamaIndex.TS προσφέρει αρκετά βασικά αρθρώματα, χωρισμένα σε υψηλού επιπέδου αρθρώματα για γρήγορη εκκίνηση και χαμηλού επιπέδου αρθρώματα για την προσαρμογή των βασικών στοιχείων όπως χρειάζεστε.

## Ενότητες Υψηλού Επιπέδου

- [**Έγγραφο**](./high_level/documents_and_nodes.md): Ένα έγγραφο αναπαριστά ένα αρχείο κειμένου, αρχείο PDF ή άλλα συνεχή δεδομένα.

- [**Κόμβος**](./high_level/documents_and_nodes.md): Το βασικό δομικό στοιχείο δεδομένων. Συνήθως, αυτά είναι μέρη του εγγράφου που χωρίζονται σε διαχειρίσιμα κομμάτια που είναι αρκετά μικρά για να τροφοδοτηθούν σε ένα μοντέλο ενσωμάτωσης και LLM.

- [**Αναγνώστης/Φορτωτής**](./high_level/data_loader.md): Ένας αναγνώστης ή φορτωτής είναι κάτι που παίρνει ένα έγγραφο στον πραγματικό κόσμο και το μετατρέπει σε μια κλάση έγγραφου που μπορείτε να χρησιμοποιήσετε στον Δείκτη σας και στις ερωτήσεις σας. Αυτή τη στιγμή υποστηρίζουμε αρχεία απλού κειμένου και PDF με πολλές ακόμα επιλογές που θα έρθουν.

- [**Δείκτες**](./high_level/data_index.md): Οι δείκτες αποθηκεύουν τους κόμβους και τις ενσωματώσεις αυτών των κόμβων.

- [**Μηχανή Ερωτήσεων**](./high_level/query_engine.md): Οι μηχανές ερωτήσεων είναι αυτές που δημιουργούν την ερώτηση που εισάγετε και σας δίνουν το αποτέλεσμα. Οι μηχανές ερωτήσεων συνδυάζουν συνήθως ένα προκαθορισμένο προτροπή με επιλεγμένους κόμβους από τον Δείκτη σας για να δώσουν στο LLM το πλαίσιο που χρειάζεται για να απαντήσει στην ερώτησή σας.

- [**Μηχανή Συνομιλίας**](./high_level/chat_engine.md): Μια μηχανή συνομιλίας σας βοηθά να δημιουργήσετε ένα chatbot που θα αλληλεπιδρά με τους Δείκτες σας.

## Αρθρώματα Χαμηλού Επιπέδου

- [**LLM**](./low_level/llm.md): Η κλάση LLM είναι μια ενοποιημένη διεπαφή πάνω από έναν μεγάλο πάροχο μοντέλου γλώσσας όπως το OpenAI GPT-4, το Anthropic Claude ή το Meta LLaMA. Μπορείτε να την υποκλάσετε για να γράψετε ένα συνδετικό για το δικό σας μεγάλο μοντέλο γλώσσας.

- [**Ενσωμάτωση**](./low_level/embedding.md): Μια ενσωμάτωση αναπαρίσταται ως ένα διάνυσμα από αριθμούς κινητής υποδιαστολής. Το προεπιλεγμένο μοντέλο ενσωμάτωσης της OpenAI με το όνομα text-embedding-ada-002 αποτελείται από 1.536 αριθμούς κινητής υποδιαστολής. Ένα άλλο δημοφιλές μοντέλο ενσωμάτωσης είναι το BERT, το οποίο χρησιμοποιεί 768 αριθμούς κινητής υποδιαστολής για να αναπαραστήσει κάθε κόμβο. Παρέχουμε μια σειρά από εργαλεία για την εργασία με ενσωματώσεις, συμπεριλαμβανομένων 3 επιλογών υπολογισμού ομοιότητας και της μεγαλύτερης αποκλειστικής σχέσης.

- [**TextSplitter/NodeParser**](./low_level/node_parser.md): Οι στρατηγικές διαίρεσης κειμένου είναι απίστευτα σημαντικές για τη συνολική αποτελεσματικότητα της αναζήτησης ενσωματώσεων. Αυτή τη στιγμή, παρόλο που έχουμε μια προεπιλεγμένη λύση, δεν υπάρχει μια μέγεθος που να ταιριάζει σε όλους λύση. Ανάλογα με τα αρχεία πηγής, μπορεί να θέλετε να χρησιμοποιήσετε διαφορετικά μεγέθη και στρατηγικές διαίρεσης. Αυτή τη στιγμή υποστηρίζουμε τη διαίρεση με βάση το σταθερό μέγεθος, τη διαίρεση με βάση το σταθερό μέγεθος με επικαλυπτόμενα τμήματα, τη διαίρεση ανά πρόταση και τη διαίρεση ανά παράγραφο. Ο διαχωριστής κειμένου χρησιμοποιείται από τον NodeParser κατά τη διαίρεση των `Εγγράφων` σε `Κόμβους`.

- [**Retriever**](./low_level/retriever.md): Ο Retriever είναι αυτός που πραγματοποιεί την επιλογή των Κόμβων που θα ανακτηθούν από τον δείκτη. Εδώ, μπορείτε να δοκιμάσετε να ανακτήσετε περισσότερους ή λιγότερους Κόμβους ανά ερώτημα, να αλλάξετε τη συνάρτηση ομοιότητας ή να δημιουργήσετε τον δικό σας retriever για κάθε ξεχωριστή περίπτωση χρήσης στην εφαρμογή σας. Για παράδειγμα, μπορείτε να έχετε έναν ξεχωριστό retriever για περιεχόμενο κώδικα έναντι περιεχομένου κειμένου.

- [**ResponseSynthesizer**](./low_level/response_synthesizer.md): Ο ResponseSynthesizer είναι υπεύθυνος για τη λήψη μιας συμβολοσειράς ερωτήματος και τη χρήση μιας λίστας `Κόμβων` για τη δημιουργία μιας απάντησης. Αυτό μπορεί να πάρει πολλές μορφές, όπως η επανάληψη όλου του περιεχομένου και η καλλιέργεια μιας απάντησης ή η δημιουργία ενός δέντρου περιλήψεων και η επιστροφή της ρίζας.

- [**Αποθήκευση**](./low_level/storage.md): Σε κάποιο σημείο θα θέλετε να αποθηκεύσετε τους δείκτες, τα δεδομένα και τα διανύσματά σας αντί να εκτελείτε τα μοντέλα ενσωμάτωσης κάθε φορά. Οι IndexStore, DocStore, VectorStore και KVStore είναι αφαιρέσεις που σας επιτρέπουν να το κάνετε αυτό. Συνδυασμένα, σχηματίζουν το StorageContext. Αυτή τη στιγμή, σας επιτρέπουμε να διατηρήσετε τις ενσωματώσεις σας σε αρχεία στο σύστημα αρχείων (ή ένα εικονικό σύστημα αρχείων στη μνήμη), αλλά προσθέτουμε επίσης ενεργά ενσωματώσεις σε Βάσεις Δεδομένων Διανυσμάτων.