# Event: {naam}

## Functioneel
Een functionele omschrijving van het event. Denk hierbij aan:
- Wanneer wordt het event getriggered?

## Kenmerken
De kenmerken van een event bericht worden vastgelegd aan de hand de attributen:

| Attribuut | Waarde                                                                                            |
| --------- | ------------------------------------------------------------------------------------------------- |
| type      | Identifier voor het soort event (bijv: "nl.gemeente.brp.persoon-overleden")                       |
| dataref   | Referentie naar de event data (bijv: "/api​/v1.3​/ingeschrevenpersonen​/{bsn}")                   |
| subject   | Waarde van het subject veld (meestal BSN). Maar kan verschillen per source, event type combinatie |
