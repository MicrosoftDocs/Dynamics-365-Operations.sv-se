---
title: Löpande genomsnittlig självkostnad
description: Lagerstängningsprocessen kvittar utleveranstransaktioner mot inleveranstransaktioner baserat på den lagervärderingsmetod som har valts i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet en löpande genomsnittlig självkostnad som i de flesta fall används för bokföring av utleveranstransaktioner.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d324324312ce9e47b07de8e3de952b8d7c53647
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672190"
---
# <a name="running-average-cost-price"></a>Löpande genomsnittlig självkostnad

[!include [banner](../includes/banner.md)]

Lagerstängningsprocessen kvittar utleveranstransaktioner mot inleveranstransaktioner baserat på den lagervärderingsmetod som har valts i artikelns artikelmodellgrupp. Innan en lagerstängning körs beräknar systemet en löpande genomsnittlig självkostnad som i de flesta fall används för bokföring av utleveranstransaktioner.

Systemet beräknar den löpande genomsnittliga självkostnaden för en artikel med följande formel:

Uppskattat pris = (fysiskt belopp + ekonomiskt belopp) / (fysisk kvantitet + ekonomisk kvantitet)

## <a name="default-item-cost"></a>Standardartikelkostnad

Standardartikelkostnaden för en frisläppt produkt kan konfigureras på ett av två sätt på sidan **Information om frisläppt produkt**:

- Skapa en standardkostnad genom att välja **Artikelpris** i gruppen **Ställ in** på fliken **Hantera kostnader** i Åtgärdsfönstret. Om du använder den här metoden måste du använda en standardkostnadsversion, och kostnaden måste aktiveras.
- Definiera en självkostnad för en frisläppt produkt som standard genom att ange ett värde i fältet **Pris** på snabbfliken **Hantera kostnader**.

Förutom att ange eller skapa ett pris kan du välja kryssrutan **Använd senaste självkostnadspris** på snabbfliken **Hantera kostnader** på sidan **Information om frisläppt produkt**. I detta fall uppdateras fältet **pris** automatiskt när du bokför en ekonomisk uppdatering. Om du exempelvis bokför en inköpsorderfaktura sätts fältet till inköpspriset från den fakturan.

Om du har en självkostnad i en aktiv kostnadsversion, och anger ett pris på snabbfliken **Hantera kostnader**, använder systemet priset från den aktiva kostnadsversionen innan det pris som har definierats på snabbfliken **Hantera kostnader** används.

## <a name="using-the-running-average-cost-price"></a>Använda löpande genomsnittlig självkostnad

Följande tabell visar när systemet bokför lagertransaktioner med den löpande genomsnittliga självkostnaden och när den självkostnad som definierats i artikelns huvudpost används istället.

| Villkor | Systemet använder den uppskattade löpande genomsnittliga självkostnaden | Systemet använder standardartikelns självkostnadspris |
| --- | --- | --- |
| Både täljaren\* och nämnaren\*\* är positiva. | Ja | Nej |
| Täljaren\*, nämnaren\*\* eller båda är negativa. | Nej | Ja |
| Nämnaren\*\* är 0 (noll). | Nej | Ja |

\*Täljare = (Fysiskt belopp + ekonomiskt belopp)  
\*\* Nämnare = (Fysisk kvantitet + ekonomisk kvantitet)

> [!NOTE]
> Om alternativet **Inkludera fysiskt värde** inte markeras för en artikel använder systemet 0 (noll) för både fysiskt belopp och den fysiska kvantiteten. Information om det här alternativet finns i [Inkludera fysiskt värde](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Undvika prissättningsförstärkning

Vid sällsynta tillfällen prissätter systemet flera uttag innan det finns tillräckligt många inleveranser att basera ett pris på. I det här scenariot kan uppskattningarna av genomsnittlig självkostnad blåsas upp alltför mycket. Det finns dock steg du kan vidta för att undvika prissättningsförstärkning eller begränsa dess effekter när det inträffar.

**Scenario:** Följande transaktioner görs för en artikel som du har valt **Inkludera fysiskt värde** för:

1. Du får ekonomiskt en kvantitet av 100 om vardera 1 000,00 kronor.
2. Du utlevererar ekonomiskt en kvantitet på 200.
3. Du tar fysiskt emot en kvantitet av 101 om vardera 2 020,00 kronor.

När du undersöker den uppskattade löpande genomsnittliga självkostnaden för artikeln, räknar du med en självkostnad på 15,1 kronor vardera. I stället hittar du ett uppskattat löpande 102,00 USD som baseras på följande formel:

Uppskattat pris = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

Denna prissättningsförstärkning beror på att när 200 artiklar utkommer ekonomiskt i steg 2 måste systemet prissätta 100 av artiklarna innan motsvarande inleveranser finns. Situationen orsakar negativt lager. Systemet beräknar sedan enhetspriset 1,00 USD, som du kan förvänta dig. När motsvarande 100 inleveranser ankommer har de enhetspriset 20,00 kronor vardera.

> [!NOTE]
> Trots att utleveranserna leder till ett negativt lager, är lagret positivt när utleveranspriset beräknas. Därför används den löpande genomsnittliga självkostnaden istället för priset i artikelns huvudpost. I det här läget har systemet en lagervärdesförskjutning på 1 000,00 SEK. Även om förskjutningen bygger på 100 enheter, där det finns en enhetsförskjutning på 1,00 USD vardera, har vi nu bara en enhet i lagret. Därför tilldelas förskjutningen på 1 000,00 kr till denna enda enhet. Resultatet blir den alltför uppblåsta uppskattade självkostnaden.
>
> För en jämförelse, observera att om steg 2 och 3 byter plats i scenariot ovan kommer 200 artiklar att utlevereras till enhetspriset 1,51 USD och en enhet finns kvar med enhetspriset 1,51 USD. Eftersom detta scenario för prissättningsförstärkning kan inträffa när negativt lager är involverat, är det svårt att undvika i följande fall:
>
> - Du måste uppskatta utleveranspriser på värdet och kvantiteten av lagerbehållningen.
> - Du måste justera värdet och kvantiteten av lagerbehållningen för ut- och inleveranser.
> - Din affärsmodell tillåter utsändning, eller prissättning av fler enheter än du har.
> - Du måste acceptera alla värden och kvantiteter för inleverans som skickas till dig.

Om din affärsmodell tillåter det kan följande metoder hjälpa dig att undvika de negativa kvantiteter som gör scenariot för prissättningsförstärkning möjligt:

- Om du väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Fysiskt negativt lager** på sidan **Artikelmodellgrupper**.
- Om du **inte** väljer alternativet **Inkludera fysiskt värde** för en artikel, avmarkera kryssrutan **Ekonomiskt negativt lager** på sidan **Artikelmodellgrupper**.

Tänk även på att den maximala förskjutningen av ditt fysiska lagervärde begränsas av antalet fysiska transaktioner och differensen mellan fysiska och ekonomiska priser. Så länge som alla fysiska transaktioner uppdateras ekonomiskt kan det fysiska värdet inte stiga till extrema nivåer. Dessutom minskar förstärkningseffekten betydligt när den ackumulerade förskjutningen sprids ut på ett flertal tillgängliga enheter istället för bara på en enda enhet.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Undvik noll självkostnad i utärenden

När alternativet **Inkludera fysiskt värde** inte valts på sidan **Artikelmodellgrupp** kan en utleverans från lagret ha en noll självkostnad om det inte finns några ekonomiskt uppdaterade inleveranser i lagret. För att undvika detta scenario, överväg följande alternativ:

- Markera alternativet **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp**. Det här alternativet förhindrar att självkostnaden för en utleverans blir noll, förutsatt att inleveransen uppdateras fysiskt. Om du inte tillåter negativt fysiskt lager, beräknas det löpande medelvärdet från de fysiskt uppdaterade transaktionerna.
- Skapa ett standardkostnadspris för artikeln genom att aktivera en kalkylversion som har en standardkostnad, eller ange priset på snabbfliken **Hantera kostnader** på sidan **Information om frisläppt produkt**. Det här alternativet är bäst när alternativet **Inkludera fysiskt värde** inte har valts på sidan **Artikelmodellgrupp**, eftersom systemet alltid har ett reservpris att använda.
- Välj alternativet **Använd senaste självkostnad** på snabbfliken **Hantera kostnader** på sidan **Information om frisläppt produkt**. Det här alternativet håller fältet **Pris** uppdaterat varje gång som du uppdaterar en inleverans ekonomiskt. Om du väljer det här alternativet, men inte anger ett standardpris eller aktiverar en kostnad i en standardkostnadsversion, kan du fortfarande ha nollkostnad i en utfråga.

Om du har problemtransaktioner som har noll kostnad, processen *Lagerstängning och justering* kommer att korrigera självkostnadspriset genom att skapa en justering efter att kvittona har uppdaterats ekonomiskt. Tänk på att den ekonomiska perioden när denna uppdatering sker kan skilja sig från den ekonomiska period då artiklarna fysiskt togs emot eller skickades.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
