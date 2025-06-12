# 🎥 ScreenShare - Cross-Server Screen Share Plugin

**ScreenShare** è un plugin per **Minecraft 1.21.4 (Paper)** che permette di gestire uno screen share in modo sicuro, rapido e completamente automatizzato **tra server diversi** in una rete BungeeCord o Velocity.  
Tutto con un semplice comando: `/ss <giocatore>`.

---

## 🔧 Funzionalità principali

✅ Sposta automaticamente un giocatore nel **server dedicato allo screen share**  
✅ Salva **da quale server proviene** il giocatore  
✅ Esegue **comandi personalizzati** all’ingresso e all’uscita dallo screen share  
✅ Riporta il giocatore **al server originale** con `/ssend <giocatore>`  
✅ Completamente configurabile tramite `config.yml`  
✅ Compatibile con **BungeeCord** o **Velocity** (via Plugin Messaging Channel)  
✅ Codice ottimizzato, **nessuna dipendenza esterna**, tutto in un singolo `.jar`

---

## 📁 Configurazione

Alla prima accensione, verrà generato un file `config.yml` come questo:

```yaml
ss-server: "screenshare"
on-join-command: "ssmode %player%"
on-return-command: "pardon %player%"
```

- `ss-server`: il nome del server in cui eseguire lo screen share (come da `server.properties` o BungeeCord)
- `on-join-command`: comando eseguito **nel server SS** dopo il teleport (es. attivare una modalità)
- `on-return-command`: comando opzionale eseguito **prima** del ritorno al server originale (può essere vuoto)
- `%player%` sarà sostituito automaticamente con il nome del giocatore

---

## 💬 Comandi

| Comando | Descrizione | Permesso |
|--------|-------------|----------|
| `/ss <giocatore>` | Teleporta il player nel server SS e esegue il comando post-join | `screenshare.use` |
| `/ssend <giocatore>` | Riporta il player nel server originale e (opzionalmente) esegue il comando pre-return | `screenshare.end` |

---

## 🌐 Requisiti

- Server **Paper 1.21.4**
- Rete **BungeeCord** o **Velocity**
- Java 17+
- Plugin installato **su ogni server interessato** (almeno: main server + server SS)
- `BungeeCord` deve essere abilitato anche in `spigot.yml` (`bungeecord: true`)
- Plugin LuckPerms
---

## 🔒 Sicurezza consigliata

- Usa permessi per limitare l’uso dei comandi solo agli staff
- Non rendere accessibile il server SS ai player normali tramite altri comandi

---

## 🛠️ Compilazione

Il plugin è costruito con Maven. Esegui:

```bash
mvn clean package
```

Troverai il file `.jar` nella cartella `target/`.

---

## 💡 Idee future (facoltative)

- Integrazione con Discord per notifiche automatiche
- Timer AFK per auto-kick dal server SS
- Logging avanzato (MySQL/SQLite)

---

## 📃 Licenza

Questo plugin è open-source e può essere usato liberamente.  
Ricorda di citare l'autore originale se lo pubblichi altrove o lo modifichi.
