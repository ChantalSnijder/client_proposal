# Intern: urenraming en tariefberekening klant X

**Niet delen met klant X.** Dit document bevat het uurtarief. Het voorstel communiceert alleen tarieven per module of variant.

**Uurtarief:** €150 (excl. btw)
**Berekening:** tarief = uren × €150. Projectmanagement is in de uren van elk onderdeel verwerkt; er is geen aparte PM-regel.
**Nummering:** [nummer van de wens].[nummer van de module]

## Wens 1: Campagne-automatisering

| Module | Uren | Tarief |
|---|---|---|
| Module 1.1: As-is campagnes en triggerdefinities | 40 | €6.000 |
| Module 1.2a: Klantonderzoek informatiebehoeften per objecttype (excl. wervingskosten) | 120 | €18.000 |
| Module 1.2b: Campagnevoorstel per objecttype (alleen samen met 1.2a) | 40 | €6.000 |
| **Totaal wens 1** | **200** | **€30.000** |

Uren module 1.2a: opstellen 35, afnemen en afstemming met het bureau 50, analyseren en rapporteren 35.

## Wens 2: Journey Insight, van data naar actie

| Module | Uren variant A (begeleid) | Uren variant B (wij bouwen) | Tarief A | Tarief B |
|---|---|---|---|---|
| Module 2.1: Journey data model | 112 | 230 | €16.800 | €34.500 |
| Module 2.2: Klantonderzoek gaps (excl. wervingskosten) | 120 | 120 | €18.000 | €18.000 |
| Module 2.3: Knelpunten, kansen, oplossingen en instructies (alleen samen met 2.2) | 100 | 100 | €15.000 | €15.000 |
| Module 2.4: Conversational Analytics (alleen samen met 2.1) | 40 | 40 | €6.000 | €6.000 |
| **Totaal wens 2** | **372** | **490** | **€55.800** | **€73.500** |

### Urenopbouw per module

**Module 2.1 (journey data model)**

| Onderdeel | Uren variant A | Uren variant B |
|---|---|---|
| Technische verkenning (aanvulling op bestaande Databricks-inrichting, websitedata en calldata) | 8 | 8 |
| Identity layer | 16 | 16 |
| Event layer | 30 | 80 |
| Journey layer (incl. business ruling journey) | 30 | 70 |
| Semantic layer en nulmeting | 8 | 16 |
| Proof-of-concept journey-performance | 20 | 40 |
| **Totaal** | **112** | **230** |

Variant A: uren zijn begeleiding, review en overdracht. De bouw door het interne team van klant X zit niet in onze uren.
Variant B: uren zijn ontwerp en bouw door onze data engineers, inclusief overdracht voor beheer.

**Module 2.2 (klantonderzoek gaps):** opstellen 35, afnemen en afstemming met het bureau 50, analyseren en rapporteren 35.

**Module 2.3 (knelpunten, kansen, oplossingen en instructies):** customer journey map opzetten en maken 30, journey map-sessie met stakeholders 15, brainstorm met stakeholders 15, ideation 20, instructies voor development 20.

**Module 2.4 (Conversational Analytics):** vaststellen van de vragen 8, inrichten van de AI-laag op het journey data model en de semantische laag 12, dashboard of intuïtieve gebruikersinterface 12, testen van de kwaliteit van antwoorden en overdracht 8.

## Totaal opties

| Optie | Uren | Tarief |
|---|---|---|
| A: Wens 1 | 200 | €30.000 |
| B: Wens 1 + wens 2 variant A (2.1 t/m 2.4) | 572 | €85.800 |
| C: Wens 1 + wens 2 variant B (2.1 t/m 2.4) | 690 | €103.500 |

## Aannames bij de raming

- Alle uren zijn schattingen. De variant A-uren voor module 2.1 zijn mijn inschatting op basis van begeleiding en een bouwteam dat zelf kan bouwen; dat moet worden getoetst.
- Module 2.4 is in beide varianten gelijk en is een permanente voorziening. Wij doen ontwerp en opzet. Licentie- en gebruikskosten van de AI-omgeving en beheer na oplevering zitten niet in de raming; daar kan later een beheerraming bij komen.
- Module 1.1 (40 uur, één week) gaat uit van beschikbaarheid van de medewerkers die nu selecteren. De begeleiding van het bouwteam is in deze 40 uur beperkt.
- Module 1.2a (120 uur) en module 2.2 (120 uur) zijn verhoogd van 100 naar 120 uur. Dit blijft een grove inschatting: de onderzoeksopzet is nog niet bekend en de methode bepaalt de inspanning en de doorlooptijd. Interviews en surveys verschillen daarin sterk; een combinatie van methoden is vaak de beste oplossing, maar dat is pas definitief te bepalen als de onderzoeksopzet er ligt. Bevestig uren, tarief en doorlooptijd bij het akkoord op de onderzoeksopzet; een afwijking loopt via een change request.
- De twee onderzoeken zijn vergelijkbaar in opzet en gebruiken hetzelfde bureau. Er is een kans op dubbel werk. Overweeg ze te combineren, met aparte outcomes en tarieven per module.
- Wervingskosten zijn niet in de raming opgenomen. Digital Power selecteert het bureau, tenzij klant X dit zelf wil, en levert een voorstel voor de wervingskosten.
- De doorvoering van oplossingen is geen module meer. Die doet het interne team van klant X op basis van de instructies uit module 2.3. Als we die doorvoering later toch willen begeleiden, komt er een eigen raming bij.
- Discovery is teruggebracht naar 8 uur, omdat onze collega's de Databricks-omgeving al eerder hebben ingericht. Dit moet bij de start worden bevestigd; websitedata en calldata moeten nog wel worden gecontroleerd.
- De identity layer is in beide varianten teruggebracht naar 16 uur. De omvang hangt volledig af van de huidige setup: gebruiken de bronnen een overeenkomende ID, dan is de laag snel klaar; moeten ID's eerst in de bronsystemen worden afgevangen of afgeleid, dan kost het aanzienlijk meer. We gaan er nu vanuit dat de bronnen die we meenemen in het journey data model overeenkomende ID's gebruiken. Dit staat als randvoorwaarde in het voorstel en wordt in de technische verkenning van module 2.1 bevestigd; een afwijking loopt via een change request.
- Module 2.4 (40 uur) bevat ook het dashboard of de intuïtieve gebruikersinterface. Licentie- en gebruikskosten van de AI-omgeving en beheer na oplevering zitten niet in de raming.
- Doorlooptijden zijn schattingen: wens 1 circa 10 weken, wens 2 variant A circa 18 weken, variant B circa 16 weken (zie de tijdlijnberekening hieronder).
- Modules 2.2, 2.3 en 2.4 starten na afronding van module 2.1. Doorlooptijd wens 2 blijft gelijk: de bouw bepaalt de duur, en de variant bepaalt wie bouwt en de beschikbaarheid van developers.
- Module 2.2 blijft 100 uur, maar loopt over een langere periode door afstemming met het wervingsbureau en de planning. Module 2.3 wordt afgerond na module 2.2.
- Uren zijn exclusief btw.
- Bij de klantonderzoeken is het akkoord op de onderzoeksopzet, inclusief juridische basis en privacy-inrichting, een randvoorwaarde van klant X. Digital Power levert het wervingsvoorstel en het verwerkersakkoord wordt vóór de start afgesloten.

## Tijdlijn: onderbouwing (intern)

**Niet delen met klant X.** Het klantvoorstel toont alleen doorlooptijd in weken. Uren en de 32-urige werkweek staan hier, omdat ze samen met het tarief het uurtarief herleidbaar maken.

Basis: werkweek van 32 uur per persoon. Inzet in weken = uren / 32.

| Module | Uren | Inzet (wk) | Doorlooptijd (wk) | Waarom de doorlooptijd afwijkt |
|---|---|---|---|---|
| 1.1 As-is en triggerdefinities | 40 | 1,25 | 2 | Afhankelijk van de beschikbaarheid van de selectiemedewerkers |
| 1.2a Klantonderzoek informatiebehoeften | 120 | 3,75 | 8 | Werving en veldwerk door het externe bureau bepalen de doorlooptijd |
| 1.2b Campagnevoorstel per objecttype | 40 | 1,25 | 2 | Start na 1.2a |
| 2.1 Journey data model, variant A | 112 | 3,5 | 6 | Begeleiding loopt mee met de bouw door het interne team |
| 2.1 Journey data model, variant B | 230 | 7,2 | 4 | Met 2 data engineers (64 uur per week) |
| 2.2 Klantonderzoek gaps | 120 | 3,75 | 8 | Idem 1.2a |
| 2.3 Knelpunten, kansen, oplossingen | 100 | 3,1 | 4 | Inplannen van de sessies met stakeholders |
| 2.4 Conversational Analytics | 40 | 1,25 | 2 | Start na 2.1 |

**Parallelle planning optie B (getoond in het voorstel)**

| Module | Weken |
|---|---|
| 1.1 | 1–2 |
| 1.2a | 1–8 |
| 1.2b | 9–10 |
| 2.1 (variant A) | 1–6 |
| 2.4 | 7–8 |
| 2.2 | 7–14 |
| 2.3 | 15–18 |

- Totaal optie B: 572 uur over 18 weken, gemiddeld 32 uur per week, oftewel circa 1 fte gemiddeld. Pieken tot circa 1,5 à 2 fte in week 1–2 en week 7–10, dus daar zetten we twee mensen in.
- Sequentieel ("aan elkaar geplakt"): wens 1 10 weken + wens 2 18 weken = circa 28 weken, met grotendeels één persoon tegelijk.
- Optie C (variant B): 2.1 in 4 weken met 2 engineers, dan 2.2 week 5–12, 2.4 week 5–6, 2.3 week 13–16. Wens 2 komt daarmee op 16 weken, niet op de eerder genoemde 14.
- Alle doorlooptijden zijn indicatief. De grootste onzekerheid zit in de twee klantonderzoeken, omdat de onderzoeksopzet nog niet bekend is.
