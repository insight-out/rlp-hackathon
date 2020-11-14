## instapointment

Verteilte Terminfindung in der Gesundheitswirtschaft am Beispiel der COVID-19-Testzentren (UC09)

### Annahme

- Bei Verdacht auf COVID-19 findet Testung in Corona-Testzentrum (CT) statt
- Terminplanung (Tagestermine) durch das Gesundheitsamt (GA) in Absprache mit Patient und Testkapazität des CT
- tägliche Übermittlung der Termine von GA an CT
- CT nutzen übermittelte Termine zum Abgleich der Patienten vor Ort

### Probleme

Die meisten Patienten kommen direkt am Morgen des Testtermins.
**Überauslastung** zu Beginn - **Unterauslastung** zum Ende.

- Genervte Patienten
- Sinkende Akzeptanz
- Überarbeitete Fachkräfte
- Erhöhtes Infektionsrisiko

### Unser Ansatz

- Erhöhte Granularität bei der Terminplanung schafft gleichmäßigere Auslastung.
- Planung in 30-Minuten-Slots.
- Neue Termine und Änderungen sind im CT sofort sichtbar.
- Open Source
- Vollverschlüsselung der Patientendaten
- modernste Web-Technologien (Angular, React, Vue, Svelte, …)
    - → Verfügbarkeit auf allen Endgeräten

### Datenschutz

- Zentrale Datenhaltung durch Ämter oder RLP/Landes-IT
- Server in DE (ISO 27001)
- Accountvergabe über Gesundheitsämter/Landes-IT
- Kurze Speicherfristen für die Patientendaten
→ DSGV❤

### Roadmap

1. Fertigstellung Prototyp (MVP)
2. Parallel: Bewerbung um passende Ausschreibung BMG/BMWi
3. Gesundheitsamt und Testzentrum als Corporates für den MVP
4. Kontinuierliche Verbesserung über Feedback-Loop
5. Go-Live

### Ausblick

- Rückkanal CT → GA für live-Auslastung
- Automatische Analyse vergangener Testtage zu präventiven Kapazitätsverringerung hoch-frequentierter Zeitslots
- Erhöhung des Durchsatzes im CT durch Vorlagerung einzelner Elemente des Annahmeprozesses vor Ort.
- Erfassung E-Mail-Adresse/Telefonnummer
- QR-Code statt Perso/KVK


