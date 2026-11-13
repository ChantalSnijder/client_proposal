# Voorstel: Campagne-automatisering en Insight-driven optimisation voor klant X

**Klant:** Klant X (glasvezelaanleg)
**Opgesteld door:** Digital Power, Customer Experience
**Status:** Concept v0.6, ter bespreking
**Geldig tot:** [datum]

---

## 1. Samenvatting

Klant X communiceert in 2027 naar verwachting met ongeveer 150.000 adressen. Dit bestaat uit adressen die vanuit 2026 worden meegenomen in herinneringscampagnes, en nieuwe adressen uit 2027. De communicatie loopt via ongeveer 20 campagnes in één project. De campagnes worden nu in de bestaande campagnetool handmatig geselecteerd en per stroom geaccordeerd. Dat werkt voor grote campagnemomenten, maar niet voor de fijnmazige, adresgerichte journey die klant X wil bereiken.

Dit voorstel bestaat uit twee wensen. Modules worden genummerd als [nummer van de wens].[nummer van de module]. Een module heeft één doel, één outcome en één tarief.

- **Wens 1: Campagne-automatisering.** Campagnes worden event-gedreven getriggerd, zonder handmatige selectie. Wens 1 bestaat uit drie modules: module 1.1 (triggerdefinities en vertaling naar het bouwteam), module 1.2a (klantonderzoek naar informatiebehoeften per objecttype) en module 1.2b (campagnevoorstel per objecttype).
- **Wens 2: Insight-driven optimisation: van data naar actie.** Het doel is een betere klantreis: hogere tevredenheid bij de consument en hogere conversie, waarbij conversie betekent dat een afspraak wordt gemaakt of een toestemming wordt gegeven. Het journey data model is het middel. Het automatiseert de inzichten over de journeys en sluit AI aan, zodat optimalisatie wordt versneld. Wens 2 bestaat uit vier modules: module 2.1 (journey data model), module 2.2 (klantonderzoek naar gaps in de journey), module 2.3 (knelpunten, kansen, oplossingen en instructies) en module 2.4 (Conversational Analytics).

Elke wens heeft een eigen business ruling. Wens 1 bepaalt wanneer een campagne wordt getriggerd. Wens 2 bepaalt hoe events worden gegroepeerd tot een journey en in welke journey een klant zich bevindt. De twee wensen komen samen in de eventcatalogus.

Onze rol is adviserend en aansturend, of uitvoerend, afhankelijk van de gekozen variant. Het interne team van klant X bouwt de campagnetool.

---

## 2. Aanleiding

- De communicatie heeft een call-to-action (CTA). De gewenste reactie is een toestemming of het inplannen van een afspraak. Deze reactie is de kern-KPI.
- Campagnes zijn er in twee soorten: **CTA-campagnes** (vragen om een actie) en **update-campagnes** (informeren over de voortgang van het project).
- De campagnetool en het verzendhuis draaien al. De selectie-intelligentie zit nu bij medewerkers, niet in het systeem.
- Er is weinig journey-inzicht beschikbaar. Klant X wil van campagnes naar een gestuurde klantreis per adres.
- Klant X wil zelf inhouse bouwen.

---

## 3. Huidige situatie en bekende onbekenden

**Wat we weten**
- Naar verwachting circa 150.000 adressen in 2027 (meegenomen adressen uit 2026 met herinneringen, plus nieuwe adressen uit 2027)
- Één project met circa 20 campagnes, inclusief herinneringen
- Per adres is bekend om welk objecttype het gaat
- Handmatige selectie en goedkeuring per DM- en eDM-stroom
- Een werkende campagnetool met koppeling naar het verzendhuis
- Een intern development team dat de campagnetool bouwt
- Een Databricks-omgeving, met data engineers die bekend zijn met deze omgeving

**Wat we nog niet weten**
- De huidige respons op CTA's en de nulmeting
- De exacte inrichting van de Databricks-omgeving (Unity Catalog, bestaande pipelines, bronsystemen). Dit wordt in module 2.1 vastgesteld.
- **Hoeveel websitedata beschikbaar is.** Deze data is voor het journey data model belangrijk en wordt in module 2.1 vastgesteld.
- **Hoeveel calldata beschikbaar is.** Ook deze data is belangrijk voor het journey data model en wordt in dezelfde verkenning vastgesteld.
- Het budget en de gewenste doorlooptijd

---

## 4. Doelstellingen en outcomes

| Doelstelling | Outcome | Meting |
|---|---|---|
| Minder handmatig werk | Campagnes draaien event-gedreven, handmatig alleen bij uitzondering | Aandeel campagnes zonder handmatige selectie |
| Hogere conversie | Meer afspraken en toestemmingen per adres | Conversie per CTA-type, responstijd |
| Hogere tevredenheid consument | Minder knelpunten in de klantreis, betere aansluiting op de informatiebehoefte | Tevredenheidsmeting na doorvoering, bezwaar- en opt-outpercentage |
| Inzicht in de journey | Journey-performance per objecttype is geautomatiseerd inzichtelijk | Beschikbaarheid van dashboards en KPI's |
| Versnelde optimalisatie | AI signaleert optimalisatiekansen en geeft oplossingskansen op basis van de journey-context | Doorlooptijd van inzicht tot doorgevoerde oplossing |

*Streefwaarden bepalen we samen na de nulmeting.*

---

## 5. Wens 1: Campagne-automatisering

### 5.1 Doel
Vervang de handmatige selectie en goedkeuring door event-gedreven campagnes. Wens 1 levert de triggerdefinities, het onderzoek naar informatiebehoeften per objecttype en een campagnevoorstel per objecttype. Het interne team bouwt de oplossing.

### 5.2 Modules

Elke module heeft één doel, één outcome en één tarief.

**Module 1.1: As-is campagnes en triggerdefinities**
- *Doel:* De huidige handmatige selectie vervangen door vastgelegde triggerdefinities, en die vertalen naar specificaties voor het campagnetool-bouwteam.
- *Werkzaamheden:*
  - Inventariseren van de 20 huidige campagnes, inclusief herinneringen
  - Vastleggen van de selectielogica die nu bij medewerkers zit
  - Per campagne een triggerdefinitie: welk event (plandatum, toestemming, schouw, geen reactie) en welke voorwaarden
  - Vertalen naar beslistabellen en functionele specificaties
  - Validatie met de selectiemedewerkers
  - Begeleiding van het bouwteam tijdens de bouw, beperkt tot de uren van deze module
- *Outcome:* Alle 20 campagnes (incl. herinneringen) hebben een gevalideerde triggerdefinitie. Het bouwteam kan ze bouwen zonder aanvullende uitleg.
- *Tarief:* **€6.000** (excl. btw)
- *Afhankelijkheden:* geen. Module 1.1 kan zelfstandig worden afgenomen.

**Module 1.2a: Klantonderzoek informatiebehoeften per objecttype**
- *Doel:* Inzicht in de informatiebehoeften van consumenten per objecttype.
- *Werkzaamheden:*
  - Opstellen van het onderzoek: onderzoeksvragen, objecttypes en kenmerken (in samenspraak met klant X), methode en vragenlijst
  - Werving van consumenten, uitgevoerd door een extern onderzoeksbureau
  - Afnemen van het onderzoek, in samenwerking met het bureau
  - Analyseren van de resultaten en opstellen van het behoeftenprofiel per objecttype
- *Outcome:* Per objecttype is vastgesteld welke informatie consumenten nodig hebben, vastgelegd in een onderzoeksrapport met een behoeftenprofiel per objecttype.
- *Tarief:* **€18.000** (excl. btw)
- *Grove inschatting:* de onderzoeksopzet is nog niet bekend. Interviews en surveys verschillen sterk in doorlooptijd en in de manier van afnemen; een combinatie is vaak de beste oplossing, maar dat stellen we pas definitief vast als de onderzoeksopzet er ligt. Tarief en doorlooptijd bevestigen we bij het akkoord op de onderzoeksopzet; een afwijking loopt via een change request.
- *Niet in het tarief:* de **wervingskosten** van het externe onderzoeksbureau (respondentwerving, incentives en eventuele panelkosten). Digital Power selecteert het bureau, tenzij klant X dit zelf wil, en levert een voorstel voor de wervingskosten. Deze kosten worden apart begroot en door klant X gedragen.
- *Randvoorwaarde:* Klant X geeft akkoord op de onderzoeksopzet, inclusief de juridische basis en de privacy-inrichting, vóór de start (zie hoofdstuk 9).
- *Afhankelijkheden:* geen. Module 1.2a kan zelfstandig worden afgenomen.

**Module 1.2b: Campagnevoorstel per objecttype**
- *Doel:* De huidige campagnes splitsen per objecttype, op basis van de informatiebehoeften uit module 1.2a.
- *Werkzaamheden:*
  - Toewijzen van de bestaande campagnes aan de objecttypes
  - Per objecttype een voorstel voor de campagnestructuur: stappen, kanalen, timing en CTA
  - Herinneringen en escalatie binnen het project, om overbelasting van een adres te voorkomen
- *Outcome:* Per objecttype is een campagnevoorstel opgesteld en de bestaande campagnes zijn aan de objecttypes toegewezen.
- *Tarief:* **€6.000** (excl. btw)
- *Afhankelijkheden:* Module 1.2b is alleen af te nemen samen met module 1.2a, omdat het campagnevoorstel is gebaseerd op het klantonderzoek. Module 1.1 is niet verplicht, maar de triggerdefinities uit module 1.1 maken het voorstel direct bouwbaar.
- *Let op:* Het campagnevoorstel is gebaseerd op het klantonderzoek uit module 1.2a en is nog niet gevalideerd met consumenten. Die validatie valt buiten deze module en kan als vervolgstap worden toegevoegd.

### 5.3 Samenstelling en tarieven

| Samenstelling | Tarief (excl. btw) |
|---|---|
| Module 1.1 | €6.000 |
| Module 1.2a (excl. wervingskosten) | €18.000 |
| Module 1.1 + 1.2a | €24.000 |
| Module 1.2a + 1.2b | €24.000 |
| **Alle drie modules (wens 1 volledig, excl. wervingskosten)** | **€30.000** |

- Module 1.2b is alleen af te nemen samen met module 1.2a.
- **Doorlooptijd wens 1 (alle modules):** circa 7 weken. Module 1.1 duurt circa 2 weken, mits de medewerkers beschikbaar zijn. Module 1.2a duurt circa 5 weken, inclusief werving; dat is strak en vraagt een bureau met een panel op de plank. Module 1.2b start na afronding van module 1.2a en duurt circa 2 weken.

### 5.4 Deliverables
- Triggerdefinities per campagne, met beslistabellen en functionele specificaties (module 1.1)
- Onderzoeksrapport met behoeftenprofiel per objecttype (module 1.2a)
- Campagnevoorstel per objecttype, met toewijzing van de bestaande campagnes (module 1.2b)

### 5.5 Outcome (waarop we afrekenen)
- Per module de outcome zoals beschreven bij de module
- Het interne team kan de specificaties zonder aanvullende uitleg in de campagnetool bouwen
- Een nieuw objecttype kan met de vastgelegde logica worden toegevoegd

---

## 6. Wens 2: Insight-driven optimisation: van data naar actie

### 6.1 Doel
Een betere klantreis, met hogere tevredenheid bij de consument en hogere conversie: afspraken en toestemmingen. Het journey data model is het middel. Het automatiseert de inzichten over de journeys en sluit AI aan, zodat de optimalisatie van de journey wordt versneld. Doordat het datamodel de context van de journey vastlegt, kan AI gerichter inzichten en oplossingskansen leveren.

### 6.2 Modules

Elke module heeft één doel, één outcome en één tarief.

**Module 2.1: Journey data model**
- *Doel:* De klantreis per adres vastleggen in een schaalbaar datamodel, als basis voor geautomatiseerd inzicht en voor AI.
- *Werkzaamheden:*
  - Technische verkenning, beperkt tot de aanvulling op de Databricks-omgeving die onze collega's eerder hebben ingericht, en de beschikbaarheid van websitedata en calldata
  - Identity layer: koppeling van bronnen via ID's (adres- en objectsleutel, contactsleutel, toestemmingssleutel) en de koppelregels
  - Event layer: verzamelen van de datapunten uit de bronnen in één dataset of omgeving
  - Journey layer: groeperen van events tot journeys per adres, met de business ruling die bepaalt in welke journey een klant zit, per objecttype
  - Semantic layer: definities van data, KPI's en metrics, zodat dashboards en AI dezelfde betekenis gebruiken, en de nulmeting van conversie en tevredenheid
  - Proof-of-concept van de journey-performance voor één objecttype
- *Outcome:* Het datamodel is opgeleverd, gereviewd en gedocumenteerd. KPI's en de nulmeting zijn door klant X goedgekeurd. De proof-of-concept toont journey-performance voor één objecttype.
- *Tarief:* **€16.800** in variant A (begeleid bouwen) en **€34.500** in variant B (wij bouwen), excl. btw
- *Aanname bij de identity layer:* de omvang hangt af van de huidige setup. Gebruiken de bronnen een overeenkomende ID, dan is de laag snel klaar; moeten ID's eerst in de bronsystemen worden afgevangen of afgeleid, dan kost het meer tijd. Het tarief gaat uit van overeenkomende ID's in de bronnen die we meenemen (zie hoofdstuk 9).
- *Afhankelijkheden:* geen. Module 2.1 is de basis voor module 2.4.

**Module 2.2: Klantonderzoek naar gaps in de journey**
- *Doel:* Vaststellen waar consumenten in de klantreis vastlopen.
- *Werkzaamheden:*
  - Opstellen van het onderzoek, gericht op de gaps in de journey
  - Werving van consumenten, uitgevoerd door een extern onderzoeksbureau
  - Afnemen van het onderzoek, in samenwerking met het bureau
  - Analyseren en rapporteren van de resultaten
- *Outcome:* De gaps in de journey zijn vastgelegd in een onderzoeksrapport.
- *Tarief:* **€18.000** (excl. btw)
- *Grove inschatting:* dezelfde kanttekening als bij module 1.2a. De onderzoeksopzet is nog niet bekend en de methode bepaalt de inspanning en de doorlooptijd.
- *Niet in het tarief:* de **wervingskosten** van het externe onderzoeksbureau. Digital Power selecteert het bureau, tenzij klant X dit zelf wil, en levert een voorstel voor de wervingskosten. Deze kosten worden apart begroot en door klant X gedragen.
- *Randvoorwaarde:* Klant X geeft akkoord op de onderzoeksopzet, inclusief de juridische basis en de privacy-inrichting, vóór de start (zie hoofdstuk 9).
- *Afhankelijkheden:* start na afronding van module 2.1. Module 2.3 bouwt hierop voort.
- *Let op:* De uren van deze module blijven gelijk, maar de module loopt over een langere periode door afstemming met het wervingsbureau en de planning van de werving.

**Module 2.3: Knelpunten, kansen, oplossingen en instructies**
- *Doel:* Eenmalig de knelpunten, kansen en oplossingen in de journey vaststellen, en instructies opleveren waarmee klant X de oplossingen kan doorvoeren.
- *Werkzaamheden:*
  - Opzetten en maken van een customer journey map
  - Journey map-sessie met stakeholders
  - Brainstorm met stakeholders
  - Ideation van oplossingen
  - Instructies voor development, waarmee het interne team de oplossingen kan doorvoeren
- *Outcome:* Geprioriteerde knelpunten, kansen en oplossingen zijn vastgesteld, en er zijn instructies voor doorvoering opgeleverd.
- *Tarief:* **€15.000** (excl. btw)
- *Afhankelijkheden:* Module 2.3 is alleen af te nemen samen met module 2.2, omdat de knelpunten op het klantonderzoek zijn gebaseerd. Module 2.3 start na afronding van module 2.1, en de data uit module 2.1 maakt de knelpunten beter onderbouwd.
- *Let op:* De doorvoering zelf wordt uitgevoerd door het interne team van klant X op basis van de instructies.

**Module 2.4: Conversational Analytics**
- *Doel:* AI toevoegen aan het journey data model, zodat medewerkers in gewone taal vragen kunnen stellen over de journeys en direct inzichten en oplossingskansen krijgen. Dit is een permanente voorziening, geen eenmalige analyse, zodat optimalisatiekansen structureel en versneld worden gevonden.
- *Werkzaamheden:*
  - Vaststellen welke vragen Conversational Analytics moet kunnen beantwoorden, bijvoorbeeld: welke klantvragen komen binnen via calls, hoe lossen medewerkers die klantvragen op, waar lopen klanten online tegenaan waarna ze bellen, en hoe kan een call worden voorkomen met een online oplossing
  - Inrichten van de AI-laag op het journey data model en de semantische laag, zodat de antwoorden de journey-context gebruiken
  - Bouwen van een dashboard of intuïtieve gebruikersinterface, waarin medewerkers de vragen stellen en de antwoorden zien
  - Testen van de kwaliteit van de antwoorden en de oplossingskansen
  - Inrichten van de toegang voor gebruikers en overdracht van de werkwijze aan klant X
- *Outcome:* Conversational Analytics is beschikbaar op het journey data model. Gebruikers kunnen de vastgestelde vragen beantwoorden en krijgen onderbouwde oplossingskansen. De werkwijze en het beheer zijn overgedragen.
- *Tarief:* **€6.000** (excl. btw)
- *Afhankelijkheden:* Module 2.4 is alleen af te nemen samen met module 2.1 en start na afronding van module 2.1.
- *Let op:* Het ontwerp en de opzet doen wij in beide varianten. Licentie- en gebruikskosten van de AI-omgeving en het beheer na oplevering vallen buiten deze module.

### 6.3 Uitvoeringsvarianten

De variant bepaalt wie de journey data model-lagen in module 2.1 bouwt. Module 2.2, 2.3 en 2.4 zijn in beide varianten gelijk.

**Variant A: Begeleid bouwen door het development team van klant X**
- Wij ontwerpen de architectuur en het datamodel en begeleiden het eigen development team van klant X tijdens de bouw van module 2.1.
- Wij voeren reviews uit en dragen de kennis over.
- Klant X bouwt zelf. De kosten van het interne team vallen buiten ons tarief.

**Variant B: Wij bouwen de lagen**
- Onze data engineers, die bekend zijn met de Databricks-omgeving van klant X, ontwerpen en bouwen de lagen van module 2.1.
- Klant X beoordeelt en accepteert het resultaat en neemt het over voor beheer.
- Het interne team hoeft niet mee te bouwen; het beheer en de doorontwikkeling blijven bij klant X.

### 6.3b Visualisatie: journey map van de klant

Ter visualisatie van de aanpak van wens 2 is een eerste journey map gemaakt van de klantreis van glasvezelaanleg: van toestemming geven, via schouw en HAS-aansluiting, tot het kiezen van een provider met glasvezelabonnement. Per fase staan de touchpoints, acties, gedachten, behoeften, pijnpunten en kansen voor de campagne. Zie `klant_x_journey_map.pdf`.

- De map is volledig hypothetisch. Ook het organisatieproces van klant X is bij ons onbekend. Fases, behoeften, pijnpunten en gedachten worden getoetst in module 2.2 en definitief gemaakt in module 2.3.
- De stemmingscurve is een hypothese per stap en geen gemeten waarde.

**Voordelen van een journey map voor campagnes en conversie**
- Per stap zie je waar de conversie wegvalt, zodat je gericht optimaliseert.
- Het juiste bericht past bij de stap waarin de klant zit, niet bij een vaste verzenddatum.
- Eén beeld van wat een adres al heeft ontvangen voorkomt dubbele of irrelevante berichten.
- Pijnpunten die nu tot bellen leiden, los je online op.
- Per stap kun je een kanaal, bericht of timing testen.

### 6.4 Tarieven en doorlooptijd wens 2

| Module | Variant A (begeleid) | Variant B (wij bouwen) |
|---|---|---|
| 2.1 Journey data model | €16.800 | €34.500 |
| 2.2 Klantonderzoek gaps (excl. wervingskosten) | €18.000 | €18.000 |
| 2.3 Knelpunten, kansen, oplossingen en instructies | €15.000 | €15.000 |
| 2.4 Conversational Analytics | €6.000 | €6.000 |
| **Totaal wens 2** | **€55.800** | **€73.500** |

- **Doorlooptijd wens 2:** circa 15 weken in variant A en circa 13 weken in variant B. Module 2.2, 2.3 en 2.4 starten na afronding van module 2.1. Module 2.2 kan langer duren door afstemming met het wervingsbureau en de planning van de werving. Module 2.3 wordt afgerond na module 2.2.

---

## 7. Opties en afweging

We adviseren optie B. Onderstaand de afwegingen per optie.

**Optie A: Wens 1 volledig, €30.000 excl. wervingskosten**
- *Voordelen:* Snel zichtbaar resultaat in de campagnes; lagere investering; directe vermindering van handmatig werk
- *Nadelen:* Geen inzicht in de journey-performance; succes is alleen op campagnelevel meetbaar; geen zicht op knelpunten bij de consument

**Optie B: Wens 1 volledig en wens 2 variant A (alle vier modules), €85.800 excl. wervingskosten**
- *Voordelen:* Klant X bouwt zelf en houdt de kennis en het eigenaarschap; wens 1 levert direct waarde, wens 2 maakt die waarde meetbaar en stuurbaar; AI versnelt de optimalisatie; lagere investering dan variant B
- *Nadelen:* Het interne team moet voldoende capaciteit hebben om module 2.1 te bouwen; de doorlooptijd van wens 2 hangt af van die capaciteit

**Optie C: Wens 1 volledig en wens 2 variant B (alle vier modules), €103.500 excl. wervingskosten**
- *Voordelen:* Snelle oplevering van het datamodel door onze data engineers, die de Databricks-omgeving al kennen; minder belasting op het interne team
- *Nadelen:* Hogere investering; het eigenaarschap en de kennis blijven minder snel bij klant X, dus het beheer moet goed worden overgedragen

*Alternatief:* Afname van een deel van wens 2. Module 2.2 en 2.3 samen zijn een zelfstandig pakket voor het vaststellen van de knelpunten. Module 2.4 vraagt module 2.1.

---

## 8. Risico's

| Risico | Impact | Beperking |
|---|---|---|
| Selectie-intelligentie zit bij medewerkers | Triggerdefinities zijn incompleet of worden later herzien | Vastleggen en validatie in module 1.1 |
| Beschikbaarheid van het interne development team (variant A) of de medewerkers die nu selecteren (wens 1) | Bouw of validatie loopt vertraging op | Vastgestelde capaciteit als randvoorwaarde; planning in overleg |
| Hoeveelheid websitedata en calldata is onbekend | Journey-inzichten zijn onvolledig, vooral voor online interactie en het contact met klant X | Vaststellen in module 2.1; bij beperkte beschikbaarheid aanpassing van de scope via change request |
| Kwaliteit van adres- en objectdata | Koppelingen tussen bronnen falen of geven dubbele records | Kwaliteitscheck in de identity layer van module 2.1 |
| Bronnen gebruiken geen overeenkomende ID | De identity layer kost aanzienlijk meer tijd dan geraamd | Aanname vastgelegd als randvoorwaarde en bevestigd in de technische verkenning van module 2.1; bij afwijking een change request |

---

## 9. Randvoorwaarden

Om de planning en het outcome te halen, vragen wij het volgende van klant X:

1. **Toegang** tot de campagnetool, de campagnedata en de bestaande campagnedocumentatie. Voor wens 2 ook tot de Databricks-omgeving (ontwikkel- of testomgeving), de websitedata en de calldata.
2. **Beschikbaarheid** van de medewerkers die nu selecteren: circa één week voor module 1.1, en sessies voor validatie (circa [X] sessies van [X] uur)
3. **Beschikbaarheid** van het development team van klant X: [X] uur per week gedurende module 2.1 in variant A. In variant B is dit beperkt tot beoordeling en overname.
4. **Beschikbaarheid** van stakeholders voor de journey map-sessies en brainstorms in module 2.3 (circa [X] sessies van [X] uur)
5. **Overeenkomende ID's in de bronnen.** We gaan ervan uit dat de bronnen die we meenemen in het journey data model een overeenkomende ID gebruiken, zodat de identity layer snel is in te richten. Moeten ID's eerst in de bronsystemen worden afgevangen of afgeleid, dan kost die laag aanzienlijk meer tijd. We bevestigen dit in de technische verkenning van module 2.1; een afwijking loopt via een change request.
6. **Eén opdrachtgever** met mandaat om beslissingen te nemen over triggerdefinities, business rulings, de vragen voor Conversational Analytics en scope
7. **Akkoord op de onderzoeksopzet** voor de klantonderzoeken (module 1.2a en module 2.2), inclusief de juridische basis en de privacy-inrichting. Klant X geeft dit akkoord vóór de start.
   - Digital Power selecteert het externe wervingsbureau, tenzij klant X dit zelf wil.
   - Digital Power levert een voorstel voor de wervingskosten. Klant X draagt deze kosten; ze zijn niet in het tarief opgenomen.
   - Het verwerkersakkoord met het gekozen bureau wordt vóór de start afgesloten.
8. **Besluitvorming** over dit voorstel vóór [datum], zodat de planning kan starten
9. **Scope-wijzigingen** lopen via een change request met impact op tarief en doorlooptijd

---

## 10. Uitsluitingen

Het volgende maakt geen onderdeel uit van dit voorstel:

- Vaststellen van de juridische basis voor communicatie en de DPIA's van bestaande processen (al geregeld)
- Juridische beoordeling van de klantonderzoeken; die ligt bij klant X (zie hoofdstuk 9)
- Wervingskosten voor de klantonderzoeken: respondentwerving, incentives en panelkosten van het externe bureau (zie module 1.2a en module 2.2)
- Doorvoering van de oplossingen in de campagnes en de journey; dit doet het interne team van klant X op basis van de instructies uit module 2.3
- Licentie- en gebruikskosten van de AI-omgeving en beheer van Conversational Analytics na oplevering (module 2.4)
- Goedkeuringsprocessen (four-eyes, compliance) en het inrichten daarvan
- Bouw van de campagnetool en de functionele implementatie in de campagnetool (door het interne team)
- In variant A: de bouwkosten van het interne development team van klant X
- Beheer en onderhoud na oplevering

---

## 11. Tarieven en doorlooptijd

| Onderdeel | Tarief (excl. btw) | Doorlooptijd |
|---|---|---|
| Wens 1: Campagne-automatisering (modules 1.1, 1.2a, 1.2b) | €30.000 | circa 7 weken |
| Wens 2 variant A: begeleid bouwen (modules 2.1 t/m 2.4) | €55.800 | circa 15 weken |
| Wens 2 variant B: wij bouwen (modules 2.1 t/m 2.4) | €73.500 | circa 13 weken |
| **Optie B (wens 1 + wens 2 variant A)** | **€85.800** | circa 15 weken |
| **Optie C (wens 1 + wens 2 variant B)** | **€103.500** | circa 13 weken |

- Alle bedragen zijn excl. btw en excl. wervingskosten van het externe onderzoeksbureau (modules 1.2a en 2.2). Die kosten worden apart begroot.
- Tarieven zijn outcome-gebaseerd: de vaste prijs geldt voor het beschreven resultaat per module of variant.
- Betaling in mijlpalen, gekoppeld aan de outcomes.
- Prijzen zijn geldig tot [datum].

---

## 12. Volgende stappen

1. Bespreking van dit voorstel met de contactpersoon van klant X
2. Toelichting aan de manager met de onderbouwing van opties, modules, varianten en randvoorwaarden
3. Besluit over de samenstelling van wens 1 en wens 2, en over optie A, B of C
4. Bij akkoord: startgesprek, planning en toegang tot de benodigde omgevingen
