# Event: persoon overleden

## Functioneel
Het event persoon overleden is een eenduidig.

Event wordt gekeken naar de mutaties van de persoonslijst (in tegenstelling tot de zaak). 
Dit is wenselijk omdat de persoon nog in leven kan zijn in brp op het moment dat de zaak wordt ingeschoten.

## Kenmerken
De kenmerken van een event bericht worden vastgelegd aan de hand de attributen:

| Attribuut | Waarde                                                                  |
| --------- | ----------------------------------------------------------------------- |
| type      | "nl.gemeente.brp.persoon-overleden"                                     |
| dataref   | Referentie naar haalcentraal: "/api​/v1.3​/ingeschrevenpersonen​/{bsn}" |
| subject   | BSN                                                                     |
