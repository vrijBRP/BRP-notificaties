# Event bericht

De berichten die uit BRP worden verstuurd zullen berichten zijn die voldoen aan de [CloudEvent standaard](https://github.com/cloudevents/spec/blob/v1.0.2/cloudevents/spec.md) en het [NL GOV profile for CloudEvents](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents).

Dit document definieerd de event berichten in een context van BRP, event berichten uit andere contexten kunnen anders vormgegeven worden.

Er is gekozen voor een event met minimale event gegevens. TODO: aanvullen waarom.

## Event definitie
Volgens het NL GOV profiel voor CloudEvents bestaat een event bericht uit JSON. Hieronder wordt beschreven welke velden verplicht zijn en hoe hier invulling aan wordt gegeven. Daarnaast zijn er enkele optionele attributen toegevoegd aan het event bericht deze worden tevens toegelicht.

### Verplichte velden
- [specversion](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#specversion) 
    - Moet altijd "1.0" zijn
- [type](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#type)
    - Moet reverse domain name notation zijn en zou geen organisatie namen moeten bevatten. In de context van berichten uit BRP is de prefix "nl.gemeente.brp."
- [source](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#source)
    - SHOULD be URN notation, SHOULD contain organisation en het source system, SHOULD use OIN for Gov organizations. In de context van BRP zal dit volgens de vorm "urn:nld:oin:{oin}:systeem:BRP-{component}" zijn.
    - Uitzoeken of sub-oin tot problemen kan leiden...
- [id](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#id)
    - uuid4

### Extra velden
- [subject](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#subject)
    - BSN
- [time](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#time)
    - Het moment van het aanmaken van een event in UTC, RFC 3339. 
- [dataref](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/#dataref)
    - Data referentie attribut naar de API waar de event data te vinden is.

## Voorbeeld event
Hieronder is een voorbeeld event zoals overeengekomen opgenomen. Dit voorbeeld beschrijft het event [persoon overleden](./Persoon_overleden.md).
```json
{
    "specversion": "1.0",
    "type": "nl.gemeente.brp.persoon-overleden",
    "source": "urn:nld:oin:00000001823288444000:systeem:VrijBRP",
    "id": "935ba316-6932-41c4-8a28-00309f515d5d",
    "subject": "999992806",
    "time": "2022-06-20T11:15:00Z",
    "dataref": "https://gemeente.vrijbrp.nl/haal-centraal/api​/v1.3​/ingeschrevenpersonen​/999992806"
}
```
