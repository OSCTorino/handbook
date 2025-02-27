# Il manuale dell'Open Science Community Torino

*This README is available in English [here](https://github.com/OSCTorino/handbook/tree/main/README.md)*

Benvenuti alla repository del manuale della Open Science Community Torino!
Questo manuale prova a compilare guide utili sull'applicazione dei principi di Open Science e di Data Management nella ricerca, e puo' essere utilizzata e modificata da chiunque nella comunita'.

**Per accedere al manuale, vai su [handbook.osc.to](https://handbook.osc.to/)!**

Se sei qui per contribuire al manuale, o per modificarlo, continua a leggere!

## Contribuire

Il manuale e' creato con [hugo](https://gohugo.io/) dai file di questa repository.
Per iniziare a contribuire, prima leggi la [guida su come contribuire alle repository su Github].

Il manuale e' automaticamente aggiornato dopo ogni commit attraverso [Github Actions](https://github.com/features/actions): appena qualche modifica e' aggiunta al branch `main`, viene rispecchiata dopo pochi minuti anche sul sito.

Tutte le pagine del manuale sono scritte in  [markdown](https://www.markdownguide.org/) come documenti nella cartella `handbook/content`, divisi in pagine italiane (`it`) e inglesi (`en`).

### Lingue
Ogni singola pagina, ad esempio `pagina.md`, puo' avere una versione in entrambe le lingue: basta creare due file con lo stesso nome sia nella cartella `en` che in quella `it`.
Per esempio, qui sotto la pagina `some_page.md` e' disponibile in entrambe le lingue:
```
handbook/
    it/
        some_page.md
    en/
        some_page.md
```

L'utente puo' selezionale la lingua preferita con un pulsante in basso a sinistra in ogni pagina.

Se una pagina e' disponibile in solo una lingua, comparira' in quella lingua in entrambe le versioni del sito, Inglese o Italiano.
Solo una pagina disponibile in entrambe le lingue cambiera' effettivamente la propria lingua dinamicamente.

### Tema
Il manuale usa il tema [Hextra](https://imfing.github.io/hextra/) che e' gia' sviluppato per guide e documentazione.
E' consigliato leggere il manuale del tema, e in particolare la sezione sugli [Hextra Shortcodes](https://imfing.github.io/hextra/docs/guide/shortcodes/).
Se non sai cosa sono gli shortcode, legge la [guida di Hugo agli shortcode](https://gohugo.io/content-management/shortcodes/).
La stessa pagina parla degli shortcode built-in di Hugo.

### Metadati di Pagina
Ogni pagina ha dei metadati in formato embedded, chiamati il *front-matter*.
Questi metadati raccolgono il titolo della pagina, la data di creazione, etc...

Puoi leggere la documentazione a riguardo di questi metadati [qui](https://gohugo.io/content-management/front-matter/).
Definisci i metadati in un blocco [YAML](https://yaml.org/) in cima alla pagina.
Nota che il front-matter **deve** necessariamente essere la prima cosa in una pagina, e deve essere delimitato da linee contenenti solo tre trattini: `---`.

Ad esempio:
```yaml
---
date: 2024-01-01
draft: false
params:
  author: James Bond
title: An example page
weigth: 10
---
```
La `date` e' la data in cui la pagina e' stata pubblicata.
`draf` (bozza) puo' essere vero (`true`) o falso (`false`) e contrassegna se la pagina deve essere pubblicata (`false`, non e' una bozza) o meno (`true`, e' una bozza).
Questa opzione e' utile se vuoi lavorare con dei collaboratori ad una pagina prima che essa sia disponibile al pubblico.
Il campo del titolo (`title`) e' il nome della pagina.
Oltre che alla cima della pagina', e' anche usato in altri punti, come ad esempio l'indice.

Tutti gli altri parametri (e ce ne sono molti) possono essere trovati sul [manuale di Hugo](https://gohugo.io/content-management/front-matter/).

### Contribuisci oggi!
Proto ad aiutare? Crea una pagina o modificane un'altra!

