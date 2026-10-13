# docs/media/ — Afbeeldingen

De meeste bestanden in deze map zijn geëxtraheerd uit het officiële Word-brondocument:

    20250930 Handleiding Standaard datauitwisseling VB-PUO Release 2026 - rev02.docx

De originele bestandsnamen (image1..image23) komen uit de Word-interne `word/media/` structuur.
Hernoemde bestanden behouden hun oorspronkelijke inhoud.

## Hernoemingen (uit Word-brondocument)

| Huidig bestand                    | Oorspronkelijk | Inhoud                                       |
|-----------------------------------|----------------|----------------------------------------------|
| feedbackmessage_structure.svg     | image17.svg    | Hiërarchisch diagram feedbackbericht (§4.7)  |

## Vervangen door upstream bronbestand

| Huidig bestand                    | Bron                                                                                                              | Versie  | Inhoud                                      |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------|---------|---------------------------------------------|
| feedbackmessage_structure.svg     | github.com/Stichting-SIVI/VBPUOdsk — VBPUO_Feedback_Message/MessageStructureView/latest.svg (PlantUML, gegenereerd) | 2026-07-05 | Hiërarchisch diagram feedbackbericht (§4.7) |

## Conversies

De `.emf` bestanden (Windows Enhanced Metafile) zijn geconverteerd naar `.png` omdat browsers geen EMF ondersteunen. De oorspronkelijke `.emf` bestanden zijn bewaard als archief.

## Archief

De submap `archive/` bevat PNG-kopieën van bestanden die ook als SVG beschikbaar zijn.

## Revisieplaten hoofdstuk 4 (review-ronde augustus/september 2026)

Deze platen zijn niet uit Word afkomstig maar gegenereerd uit PlantUML-bron in deze map,
gerenderd via de Pummelaar (`http://192.168.1.195:5050`). De legenda is bij het ophalen
gestript (`/api/svg-clean?strip=legend`); de uitleg daaruit staat in de lopende tekst van
hoofdstuk 4.

| Huidig bestand   | PlantUML-bron            | Plaat op de Pummelaar                                       |
|------------------|--------------------------|--------------------------------------------------------------|
| `fpr-model.svg`  | `fpr-model.puml`         | `260831-1234-fpr-model` (tekstblok verwijderd; tekst staat in §4.2) |
| `image8.svg`     | `figuur8-revisie.puml`   | `260825-0858-…-figuur-8-…-revisie-2`                          |
| `image9.svg`     | `figuur9-revisie.puml`   | `260907-1747-…-figuur-9-…-revisie-3`                          |

Figuur 9 revisie 3 verschilt van revisie 2 doordat stap S (SIVI 13 voor de CVP in EUR) is
vervallen en de afzender van de cash-instructie CVP is vastgesteld: bij een switch de BA
(stap P), bij een complete sell de PUO/ZAF (stap O).
