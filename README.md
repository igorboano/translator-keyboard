# Translator Keyboard — Guida al progetto

## Come aprire in Android Studio

1. Apri Android Studio
2. File → Open → seleziona la cartella `TranslatorKeyboard`
3. Attendi il sync Gradle (scarica le dipendenze automaticamente)
4. Collega un telefono Android (o avvia un emulatore)
5. Premi Run (▶)

## Struttura del progetto

```
app/src/main/java/com/translatekeyboard/
├── keyboard/
│   ├── TranslatorKeyboardService.kt  ← Servizio IME principale
│   ├── KeyboardView.kt               ← Tastiera disegnata su Canvas
│   ├── KeyboardLayout.kt             ← QWERTY / AZERTY / QWERTZ / Numeri
│   └── EmojiPanel.kt                 ← Pannello emoji con categorie
├── translation/
│   └── TranslationManager.kt         ← Chiamate API MyMemory (gratuita)
├── data/
│   ├── TranslationEntity.kt          ← Struttura record DB
│   ├── TranslationDao.kt             ← Query Room
│   ├── TranslationDatabase.kt        ← Istanza DB locale
│   ├── TranslationRepository.kt      ← Accesso dati
│   └── AutoDeleteWorker.kt           ← Worker auto-cancellazione
└── settings/
    ├── SettingsManager.kt             ← Tutte le preferenze (SharedPreferences)
    ├── SettingsActivity.kt            ← Schermata impostazioni
    └── SetupActivity.kt               ← Schermata iniziale (launcher)
```

## Funzionalità implementate

- Tastiera QWERTY / AZERTY / QWERTZ
- Layout numeri e simboli
- Dimensione tasti: Piccoli / Medi / Grandi
- Pannello emoji con 6 categorie + recenti
- Traduzione in uscita via API MyMemory (gratuita, 30 lingue)
- Traduzione in entrata via clipboard (opzionale, a scelta utente)
- Database locale (Room) — nessun dato su server
- Auto-delete traduzioni configurabile (1h / 6h / 12h / 24h / 48h / 7gg)
- Cancellazione manuale a fine conversazione
- Impostazioni complete con anteprima lingua

## Come installare la tastiera sul telefono

1. Installa l'app
2. Apri l'app → segui i 2 passi guidati
3. Nelle impostazioni Android: Lingua e immissione → Gestisci tastiere → attiva "Translator Keyboard"
4. Tieni premuto il campo testo in qualsiasi app → cambia tastiera → seleziona "Translator Keyboard"

## Aggiungere l'email per aumentare il limite API

Nelle impostazioni app inserisci la tua email → il limite giornaliero passa da 5.000 a 50.000 caratteri/giorno (gratuito, nessun account necessario).

## Costi di esercizio

| Voce | Costo |
|---|---|
| API traduzione (MyMemory) | €0 |
| Database locale (Room) | €0 |
| Backend | Nessun backend |
| Server | Nessun server |
| **Totale** | **€0** |
