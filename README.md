# Tema GRUB "Fermi Salò"


Questo repository contiene un tema grafico personalizzato per GRUB, il bootloader che appare quando accendi il computer e ti permette di scegliere quale sistema operativo avviare (ad esempio Linux, Windows, ecc.).

**Cos'è un tema GRUB?**
Un tema GRUB cambia l'aspetto del menu di avvio: puoi avere sfondi, icone, colori e font diversi, rendendo il menu più bello, leggibile e riconoscibile. Questo tema è stato creato apposta per il Liceo Scientifico Statale "Enrico Fermi" di Salò (BS), con grafiche dedicate e icone per tante distribuzioni Linux.

**Perché personalizzare GRUB?**
- Per rendere il menu di avvio più chiaro e gradevole.
- Per dare un tocco personale (o scolastico!) al computer.
- Per riconoscere subito le varie opzioni di avvio grazie alle icone.

Se segui questa guida, potrai installare il tema anche se non hai mai toccato GRUB prima!

---



## Guida all'installazione con interfaccia grafica (Grub Customizer)

> **Questa guida è pensata per Linux Mint e Ubuntu.**

### 1. Scarica il tema

Prima di tutto, devi scaricare il tema sul tuo computer. Apri il terminale e digita:

```bash
# Scarica la cartella del tema dal sito GitHub
git clone https://github.com/diozrios/fermi-salo-grub-theme.git
```

Se non hai git, puoi anche scaricare il file ZIP dalla pagina GitHub e poi estrarlo. L'importante è avere la cartella `fermi-grub-boot`.

**Perché?** Così avrai tutti i file del tema pronti da copiare nella posizione giusta.

### 2. Installa Grub Customizer

Grub Customizer è un programma che ti permette di cambiare facilmente l'aspetto di GRUB senza usare solo il terminale.

Installa Grub Customizer con questi comandi:

```bash
# Aggiorna la lista dei programmi disponibili
sudo apt update

# Aggiunge il repository da cui scaricare Grub Customizer
sudo add-apt-repository ppa:danielrichter2007/grub-customizer

# Aggiorna di nuovo la lista, ora che c'è il nuovo repository
sudo apt update

# Installa il programma Grub Customizer
sudo apt install grub-customizer
```

### 3. Copia il tema nella cartella corretta

Ora dobbiamo mettere la cartella del tema dove GRUB può trovarla. Digita:

```bash
# Crea la cartella dei temi se non esiste già
sudo mkdir -p /boot/grub/themes

# Copia la cartella del tema nella posizione giusta
sudo cp -r fermi-grub-boot /boot/grub/themes/
```

**Perché?** GRUB cerca i temi in `/boot/grub/themes/`, quindi dobbiamo copiare lì la cartella.

### 4. Seleziona il tema con Grub Customizer

1. Avvia Grub Customizer (cercalo nel menu o scrivi `grub-customizer` nel terminale).
2. Vai nella scheda "Aspetto" o "Appearance".
3. Scegli il tema "fermi-grub-boot" dalla cartella `/boot/grub/themes/`.
4. Salva le modifiche.

**Perché?** Così GRUB userà il nuovo tema ogni volta che accendi il PC.

### 5. Aggiorna GRUB (consigliato)

Per rendere effettive le modifiche, aggiorna GRUB:

```bash
sudo update-grub
```

**Perché?** Questo comando dice a GRUB di rileggere la configurazione e applicare il nuovo tema.



## Guida all'installazione via terminale (passo-passo, a prova di liceale)


> **Questa guida funziona su tutte le distribuzioni Linux che usano GRUB 2.**


### 1. Scarica il tema

Per prima cosa, scarica il tema sul tuo computer. Apri il terminale e digita:

```bash
git clone https://github.com/diozrios/fermi-salo-grub-theme.git
```

Se non hai git, puoi anche scaricare il file ZIP dalla pagina GitHub e poi estrarlo. L'importante è avere la cartella `fermi-grub-boot`.

**Perché?** Così avrai tutti i file del tema pronti da copiare nella posizione giusta.

### 2. Permessi di amministratore

Tutti i comandi vanno eseguiti con `sudo` davanti, per ottenere i permessi di amministratore.

**Perché?** Solo l'amministratore può modificare i file di sistema come quelli di GRUB.

### 3. Copia la cartella del tema

Copiamo la cartella del tema dove GRUB può trovarla. Digita:

```bash
# Crea la cartella dei temi se non esiste già
sudo mkdir -p /boot/grub/themes

# Copia la cartella del tema nella posizione giusta
sudo cp -r fermi-grub-boot /boot/grub/themes/
```

**Perché?** GRUB cerca i temi in `/boot/grub/themes/`, quindi dobbiamo copiare lì la cartella.

### 4. Modifica la configurazione di GRUB

Ora dobbiamo dire a GRUB di usare il nuovo tema. Apri il file di configurazione con:

```bash
# Apre il file di configurazione di GRUB con l'editor di testo
sudo nano /etc/default/grub
```

Poi aggiungi o modifica questa riga (se non c'è, aggiungila in fondo):

Aggiungi o modifica la riga seguente (inseriscila se non c'è):


```bash
GRUB_THEME="/boot/grub/themes/fermi-grub-boot/theme.txt"
```

**Perché?** Così GRUB saprà dove trovare il tema e lo userà all'avvio.

Salva e chiudi l'editor (`Ctrl+O`, `Invio`, poi `Ctrl+X` per nano).


### 5. Aggiorna GRUB

Esegui il comando per aggiornare la configurazione di GRUB:

**Su Ubuntu/Debian:**
```bash
# Aggiorna la configurazione di GRUB
sudo update-grub
```

**Su Arch/Manjaro:**
```bash
# Aggiorna la configurazione di GRUB su Arch/Manjaro
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

**Perché?** Questo comando aggiorna la configurazione di GRUB e applica il nuovo tema.

### 6. Riavvia il computer

Ora puoi riavviare il computer per vedere il nuovo tema in azione:

```bash
# Riavvia il computer
sudo reboot
```

**Perché?** Solo riavviando il PC potrai vedere il nuovo tema GRUB all'avvio.


## Note

- Se qualcosa va storto, puoi sempre rimuovere la riga `GRUB_THEME` da `/etc/default/grub` e aggiornare di nuovo GRUB.
- Il tema è stato testato su Ubuntu e Arch Linux, ma dovrebbe funzionare su tutte le distribuzioni che usano GRUB 2.

---

## Disclaimer e Crediti

Questo tema deriva da "distro-grub-themes" di AdisonCavani, rilasciato sotto GNU GPL v3.

**Autore originale:** AdisonCavani (GNU GPL v3)

**Modifiche apportate da:** Filip Jofce – a.s. 2024/2025

---

## Licenza

Questo tema è distribuito sotto licenza GNU GPL v3. Vedi il file LICENSE per dettagli.
