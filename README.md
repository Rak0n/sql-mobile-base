# sql-mobile-base
#  SQL Mobile Lab: Pirolisi Edition

Questo progetto è un mini-laboratorio SQL **completamente offline** e istantaneo, pensato per esercitarsi con le query SQL direttamente dallo smartphone, senza bisogno di server o installazioni.

È basato su **HTML puro, JavaScript e AlaSQL** (un motore SQL in-memory), il che lo rende leggerissimo e velocissimo.

##  Caratteristiche Principali

- **100% Offline:** Una volta caricato nel browser, non richiede connessione a internet. Perfetto per i viaggi in treno o in aereo.
    
- **Nessuna Installazione:** Gira interamente nel browser web (Safari, Chrome, ecc.).
    
- **Zero Server:** Usa `AlaSQL` per elaborare i dati direttamente nella memoria del telefono.
    
- **Database Mock Integrato:** Contiene un set di tabelle relazionali a tema "Pirolisi e Biomasse" pronte per essere interrogate.
    
- **Cheat Sheet Inclusa:** Una pratica guida SQL sempre a portata di mano nell'app.
    

##  Come usarlo (Installazione su iPhone/Android)

Il modo migliore per usare questo strumento è salvarlo come una **Web App** sulla schermata Home del tuo telefono, in modo che si comporti come un'app nativa.

**Metodo GitHub Pages (Consigliato):**

1. Carica il file `sql_lab_pirolisi.html` (rinominandolo preferibilmente in `index.html`) su un repository pubblico del tuo account **GitHub**.
    
2. Vai nelle **Impostazioni (Settings)** del repository e attiva **GitHub Pages** puntando al branch `main`.
    
3. Attendi qualche minuto e apri il link generato da GitHub Pages dal browser del tuo telefono (es. Safari su iPhone).
    
4. Tocca l'icona **Condividi** (il quadrato con la freccia in su su iOS) e seleziona **"Aggiungi alla schermata Home"**.
    
5. Apri l'app dalla nuova icona sulla tua Home. Ora sei pronto per usarla anche senza connessione!
    

## Schema del Database Mock

Il database contiene le seguenti tabelle per sperimentare con i `JOIN` e le aggregazioni:

- **`feedstocks`**: Dati generali sulle biomasse e catalizzatori.
    
- **`analisi_elementare_fs`**: Dati chimici delle biomasse (Carbonio, Ceneri).
    
- **`prove_pirolisi`**: Temperature e catalizzatori usati negli esperimenti.
    
- **`pirolisi_ricetta`**: Composizione percentuale dei feedstock per ogni prova.
    
- **`runs_pirolisi`**: Risultati degli esperimenti (resa in olio, char, gas).
    
- **`dati_gcms`**: Dettagli sui composti chimici rilevati.
    

## Esempio di Query

Prova a inserire questa query per vedere una combinazione di dati:

```
SELECT 
    p.id_prova, 
    p.temperatura, 
    r.resa_olio 
FROM prove_pirolisi p
JOIN runs_pirolisi r ON p.id_prova = r.id_prova
WHERE r.resa_olio > 40
ORDER BY r.resa_olio DESC;
```

_Progetto creato per facilitare lo studio e la pratica del linguaggio SQL in mobilità._
