Il progetto si propone di affrontare un task di sentiment analysis utilizzando un modello di Linguaggio di Grandi Dimensioni (LLM), previa una fase di preprocessing dei dati.

Per la classificazione, è stato adottato il modello BERT-base-cased, scelto per la sua capacità di mantenere il contesto all'interno dei testi. La classificazione è stata eseguita tramite una rete BiLSTM collegata a una testa di classificazione, che riceve in input il token CLS di ogni tweet da analizzare.

Durante la fase di backpropagation, gli ultimi quattro layer di BERT sono stati ulteriormente finetunati, con l'obiettivo di migliorare gli embedding del token CLS, adattandoli in modo più efficace al compito di classificazione.

Il dataset, fornito in file di testo, è stato raccolto da Twitter e annotato in base alla polarità emotiva. Il task di classificazione è multi-classe, con l’obiettivo di prevedere l’emozione predominante in ogni messaggio tra le seguenti quattro categorie:
-  Rabbia (0)
-  Gioia (1)  
-  Ottimismo (2)
-  Tristezza (3)

Sono disponibili sia un set di addestramento etichettato che un set di validazione, mentre per il set di test sono fornite solo le informazioni testuali.

L'accuratezza del modello è valutata utilizzando la macro media dell'F1 score.

Le principali librerie utilizzate sono:

- Pandas e NumPy 
- Scikit-learn
- Torch 
- Transformers (Hugging Face)
- Matplotlib 
- NLTK 
- Re 
- Emot - per la conversione delle emoji ed emoticon in testo
- EasyNMT - per l'implementazione della backtranslation come tecnica di data augmentation
- Optuna - per l'ottimizzazione degli iperparametri del modello
