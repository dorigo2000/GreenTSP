## 🔋 TSP con ricarica
Questo progetto affronta una variante del problema del **Traveling Salesman Problem (TSP)** in cui un veicolo elettrico con autonomia limitata deve visitare *n* clienti, partendo e tornando dal deposito. Se necessario, tra due clienti il veicolo può fermarsi presso una stazione di ricarica per eseguire una ricarica completa.

### ⚙️ Descrizione del problema
- Il **veicolo** ha un'autonomia massima di *K* km
- Il grafo include: **deposito** (nodi di partenza/arrivo), **clienti** e **stazioni di ricarica**
- Sono noti i **tempi di percorrenza** tra ogni coppia di nodi
- Si assume una **curva di ricarica lineare nel tempo**

#### ⏱️ Tempi considerati
- **Tempo di percorrenza** degli archi
- **Tempo per la ricarica** alle stazioni (proporzionale alla quantità di energia da ricaricare)
- **Check sull'autonomia**

🎯 L'obiettivo è **determinare il tour di durata minima** che visita tutti i clienti e rispetta i vincoli energetici.

---

### 🧠 Euristiche utilizzate
Per risolvere il problema sono state adottate le seguenti **euristiche**:
- **Nearest Neighbour**: per ottenere una prima soluzione rapida e grezza
- **2-opt**: per migliorare localmente il percorso iniziale
- **Simulated Annealing**: per l'ottimizzazione globale

#### 🔬 Tuning con Optuna
I **parametri** dell'algoritmo **Simulated Annealing** sono stati ottimizzati tramite **Optuna**, una potente libreria di *hyperparameter tuning* basata su *ottimizzazione bayesiana*.
