---
title: Löpande genomsnittlig självkostnad
description: Lagerstängningsprocessen kvittar utleveranstransaktioner mot inleveranstransaktioner baserat på den lagervärderingsmetod som har valts i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet en löpande genomsnittlig självkostnad som i de flesta fall används för bokföring av utleveranstransaktioner.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75dfd2f23034bbd222e020b532027e60ef215241
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830277"
---
# <a name="running-average-cost-price"></a>Löpande genomsnittlig självkostnad

[!include [banner](../includes/banner.md)]

Lagerstängningsprocessen kvittar utleveranstransaktioner mot inleveranstransaktioner baserat på den lagervärderingsmetod som har valts i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet en löpande genomsnittlig självkostnad som i de flesta fall används för bokföring av utleveranstransaktioner.

Systemet beräknar den löpande genomsnittliga självkostnaden för en artikel med följande formel: 

Uppskattat pris = (fysiskt belopp + ekonomiskt belopp) / (fysisk kvantitet + ekonomisk kvantitet)

## <a name="using-the-running-average-cost-price"></a>Använda löpande genomsnittlig självkostnad
Följande tabell visar när systemet bokför lagertransaktioner med den löpande genomsnittliga självkostnaden och när den självkostnad som definierats i artikelns huvudpost används istället.

| Villkor                                               | Systemet använder den uppskattade löpande genomsnittliga självkostnaden | Systemet använder självkostnaden som definieras i artikelns huvudpost |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Både täljaren\* och nämnaren\*\* är positiva.  | Ja                                                      | Ingen                                                                |
| Täljaren\*, nämnaren\*\* eller båda är negativa. | Ingen                                                       | Ja                                                               |
| Nämnaren\*\* är 0 (noll).                        | Ingen                                                       | Ja                                                               |

\* Täljare = (fysiskt belopp + ekonomiskt belopp) \*\* nämnare = (fysisk kvantitet + ekonomisk kvantitet) 

**Obs!** Om alternativet **Inkludera fysiskt värde** inte markeras för en artikel använder systemet 0 (noll) för både fysiskt belopp och den fysiska kvantiteten. Information om det här alternativet finns i [Inkludera fysiskt värde](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Undvika prissättningsförstärkning
Vid sällsynta tillfällen prissätter systemet flera uttag innan det finns tillräckligt många inleveranser att basera ett pris på. I det här scenariot kan uppskattningarna av genomsnittlig självkostnad blåsas upp alltför mycket. Det finns dock steg du kan vidta för att undvika prissättningsförstärkning eller begränsa dess effekter när det inträffar. **Scenario** Följande transaktioner görs för en artikel som du har valt **Inkludera fysiskt värde** för:

1.  Du får ekonomiskt en kvantitet av 100 om vardera 1 000,00 kronor.
2.  Du utlevererar ekonomiskt en kvantitet på 200.
3.  Du tar fysiskt emot en kvantitet av 101 om vardera 2 020,00 kronor.

När du undersöker den uppskattade löpande genomsnittliga självkostnaden för artikeln, räknar du med en självkostnad på 15,1 kronor vardera. I stället upptäcker du en uppskattade löpande genomsnittskostnad på 1 020,00 kronor, baserat på följande formel: Beräknat pris = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 Den här prissättningsförstärkningen inträffar eftersom när 200 artiklar utlevereras ekonomiskt i steg 2, måste systemet prissätta 100 av artiklarna, innan den har några motsvarande inleveransen. Situationen orsakar negativt lager. Systemet beräknar sedan enhetspriset 10,00 kronor, som vi kan förvänta. När motsvarande 100 inleveranser ankommer har de enhetspriset 20,00 kronor vardera. 

**Obs!** Trots att utleveranserna leder till ett negativt lager, är lagret positivt när utleveranspriset beräknas. Därför används den löpande genomsnittliga självkostnaden istället för priset i artikelns huvudpost. I det här läget har systemet en lagervärdesförskjutning på 1 000,00 SEK. Även om förskjutningen bygger på 100 enheter, där det finns en enhetsförskjutning på 10,00 kronor vardera, har vi nu bara en enhet i lagret. Därför tilldelas förskjutningen på 1 000,00 kr till denna enda enhet. Resultatet blir den alltför uppblåsta uppskattade självkostnaden. 

**Obs!** För en jämförelse, observera att om steg 2 och 3 byter plats i scenariot ovan kommer 200 artiklar att utlevereras till enhetspriset 15,10 kr och en enhet finns kvar med enhetspriset 15,10 kr. Eftersom detta scenario för prissättningsförstärkning kan inträffa när negativt lager är involverat, är det svårt att undvika i följande fall:

-   Du måste uppskatta utleveranspriser på värdet och kvantiteten av lagerbehållningen.
-   Du måste justera värdet och kvantiteten av lagerbehållningen för ut- och inleveranser.
-   Din affärsmodell tillåter utsändning, eller prissättning av fler enheter än du har.
-   Du måste acceptera alla värden och kvantiteter för inleverans som skickas till dig.

Om din affärsmodell tillåter det kan följande metoder hjälpa dig att undvika de negativa kvantiteter som gör scenariot för prissättningsförstärkning möjligt:

-   Om du väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Fysiskt negativt lager** på sidan **Artikelmodellgrupper**.
-   Om du *inte* väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Ekonomiskt negativt lager** på sidan **Artikelmodellgrupper**.

Tänk även på att den maximala förskjutningen av ditt fysiska lagervärde begränsas av antalet fysiska transaktioner och differensen mellan fysiska och ekonomiska priser. Så länge som alla fysiska transaktioner uppdateras ekonomiskt kan det fysiska värdet inte stiga till extrema nivåer. Dessutom minskar förstärkningseffekten betydligt när den ackumulerade förskjutningen sprids ut på ett flertal tillgängliga enheter istället för bara på en enda enhet.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]