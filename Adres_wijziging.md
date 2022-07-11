# Event: Adres wijziging

## Functioneel
Een adres wijziging van een persoon kan op meerdere manieren worden getriggered. Bijvoorbeeld:
- ingeschrevene
- technische wijziging i.v.m. BAG

Hierbij is een vraag wat er gedaan moet worden met verschillende soorten mutaties anders dan een verhuizing. Er is besloten een adres wijziging event te gebruiken ipv een verhuizing event. Een adres wijziging is een generiek concept en omslaat elke aanpassing van het adres. 

Hierbij is het aan het afnemende systeem om het event te verijken met informatie uit BRP  (inclusief het soort wijziging). Vervolgens kan het afnemend systeem waar nodig de niet relevante soorten adres wijzigingen negeren. 

Nuttig: in het veld "Omschrijving van de aangifte adreshouding" ([Zie pagina 314 van het Logisch ontwerp GBA 3.14](https://www.rvig.nl/binaries/rvig/documenten/publicaties/2022/01/02/logisch-ontwerp-gba-3.14/LO+GBA+3.14.pdf)) kan extra informatie worden opgehaald van de reden van de adres wijziging. 

## Kenmerken
De kenmerken van een event bericht worden vastgelegd aan de hand de attributen:

| Attribuut | Waarde                            |
| --------- | --------------------------------- |
| type      | "nl.gemeente.brp.wijziging-adres" |
| dataref   | Referentie naar haalcentraal: ??? |
| subject   | BSN                               |
