---
title: "Löpande genomsnittlig självkostnad"
description: "Lagerstängningsprocessen i kvittar utleveranstransaktioner mot inleveranstransaktioner utifrån lagervärderingsmetoden som väljs i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet löpande genomsnittliga självkostnaden används ofta bokförs utleveranstransaktioner."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Löpande genomsnittlig självkostnad

Lagerstängningsprocessen i kvittar utleveranstransaktioner mot inleveranstransaktioner utifrån lagervärderingsmetoden som väljs i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet löpande genomsnittliga självkostnaden används ofta bokförs utleveranstransaktioner.

Systemet beräknar det löpande genomsnittliga självkostnaden för en artikel med hjälp av följande formel: Uppskattat pris = (fysiskt belopp + ekonomiskt belopp) / (fysisk kvantitet + ekonomisk kvantitet)

## <a name="using-the-running-average-cost-price"></a>Använda löpande genomsnittlig självkostnad
I följande tabell visas när systemet bokför lagertransaktioner med den löpande genomsnittliga självkostnaden och när den självkostnad som definierats i artikelns huvudpost i stället.

| Villkor                                               | Den uppskattade löpande genomsnittliga självkostnaden används | Självkostnad som definierats i artikelns huvudpost används |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Både täljaren\* nämnare och\*\* är positiva.  | Ja                                                      | Ingen                                                                |
| Täljaren\*, nämnare\*\*, eller båda är negativa. | Ingen                                                       | Ja                                                               |
| Nämnare\*\* är 0 (noll).                        | Ingen                                                       | Ja                                                               |

\*Täljare = (fysiskt belopp + ekonomiskt belopp) \*\*nämnare = (fysisk kvantitet + ekonomisk kvantitet) **notering:** om de **inkludera fysiskt värde** för en artikel inte alternativet är markerat, används 0 (noll) för både fysiskt belopp och fysisk kvantitet. Information om det här alternativet finns i [Inkludera fysiskt värde](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Undvika prissättningsförstärkning
I sällsynta fall kommer flera uttag prissätts innan det finns tillräckligt många inleveranser att basera priset på. I det här scenariot kan uppskattningarna av genomsnittlig självkostnad blåsas upp alltför mycket. Det finns dock steg du kan vidta för att undvika prissättningsförstärkning eller begränsa dess effekter när det inträffar. **Scenario** Följande transaktioner görs för en artikel som du har valt **Inkludera fysiskt värde** för:

1.  Du får ekonomiskt en kvantitet av 100 om vardera 1 000,00 kronor.
2.  Du utlevererar ekonomiskt en kvantitet på 200.
3.  Du tar fysiskt emot en kvantitet av 101 om vardera 2 020,00 kronor.

När du undersöker den uppskattade löpande genomsnittliga självkostnaden för artikeln, räknar du med en självkostnad på 15,1 kronor vardera. I stället kan du hitta förväntas löpande medelvärde eller USD 102.00 som baseras på följande formel: Uppskattat pris = \[202 + (-100)\] / \[101 + (-100)\] = 102 / 1 = 102 prissättningsförstärkning detta pris beror på att när 200 artiklar utlevereras ekonomiskt i steg 2 100 objekt måste uppdatering av systemet innan det finns motsvarande inleveranser. Situationen orsakar negativt lager. Systemet beräknar sedan enhetspriset för USD 1.00, som förväntat. När motsvarande 100 inleveranser ankommer har de enhetspriset 20,00 kronor vardera. **Obs!** Trots att utleveranserna leder till ett negativt lager, är lagret positivt när utleveranspriset beräknas. Därför används den löpande genomsnittliga självkostnaden istället för priset i artikelns huvudpost. Systemet har nu en lagervärdesförskjutning i USD 100.00. Även om förskjutningen bygger på 100 enheter, där det finns en enhetsförskjutning på 10,00 kronor vardera, har vi nu bara en enhet i lagret. Därför tilldelas förskjutningen på 1 000,00 kr till denna enda enhet. Resultatet blir den alltför uppblåsta uppskattade självkostnaden. **Obs!** För en jämförelse, observera att om steg 2 och 3 byter plats i scenariot ovan kommer 200 artiklar att utlevereras till enhetspriset 15,10 kr och en enhet finns kvar med enhetspriset 15,10 kr. Eftersom detta scenario för prissättningsförstärkning kan inträffa när negativt lager är involverat, är det svårt att undvika i följande fall:

-   Du måste uppskatta utleveranspriser på värdet och kvantiteten av lagerbehållningen.
-   Du måste justera värdet och kvantiteten av lagerbehållningen för ut- och inleveranser.
-   Din affärsmodell tillåter utsändning, eller prissättning av fler enheter än du har.
-   Du måste acceptera alla värden och kvantiteter för inleverans som skickas till dig.

Om din affärsmodell tillåter det kan följande metoder hjälpa dig att undvika de negativa kvantiteter som gör scenariot för prissättningsförstärkning möjligt:

-   Om du väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Fysiskt negativt lager** på sidan **Artikelmodellgrupper**.
-   Om du *inte* väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Ekonomiskt negativt lager** på sidan **Artikelmodellgrupper**.

Tänk även på att den maximala förskjutningen av ditt fysiska lagervärde begränsas av antalet fysiska transaktioner och differensen mellan fysiska och ekonomiska priser. Så länge som alla fysiska transaktioner uppdateras ekonomiskt kan det fysiska värdet inte stiga till extrema nivåer. Dessutom minskar förstärkningseffekten betydligt när den ackumulerade förskjutningen sprids ut på ett flertal tillgängliga enheter istället för bara på en enda enhet.

