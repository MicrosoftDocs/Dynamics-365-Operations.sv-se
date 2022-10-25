---
title: Skapningsläge asynkron kund
description: Denna artikel beskriver det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b2926339021991f87dd3eadef94da3b500c954cf
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690300"
---
# <a name="asynchronous-customer-creation-mode"></a>Skapningsläge asynkron kund

[!include [banner](includes/banner.md)]

Denna artikel beskriver det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.

I Commerce finns det två sätt att skapa kunder: Synkron (eller Synk) och Asynkron (eller Asynk). Kunder skapas som standard synkront. Med andra ord skapas de i Commerce headquarters i realtid. Synkroniseringsläget för kunder är fördelaktigt eftersom nya kunder kan sökas omedelbart över kanaler. Den har emellertid även ett problem. Eftersom det genererar [Commerce Data Exchange: realtidstjänst](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) anropar till Commerce headquarters kan prestanda påverkas om många samtidiga kundsamtal görs.

Om alternativet **Skapa kund i asynkront läge** anges till **Ja** i butikens funktionsprofil (**Retail och Commerce \> Kanalinställning \> Inställning av online-butik \> Funktionsprofiler**), realtidssamtal används inte för att skapa kundposter i kanaldatabasen. Asynkront kundgenereringsläge påverkar inte prestandan i Commerce headquarters. En tillfällig, global unik identifierare (GUID) tilldelas varje ny asynkron kundpost och används som kundkonto-ID. Denna GUID inte visas för kassaanvändare. I stället visas **väntande synkronisering** som kundkonto-ID.

> [!IMPORTANT]
> När kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Därför, oavsett ditt val mellan synkronisera och asynkronisera kundskapande måste Commerce headquarters-administratörer skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

## <a name="async-customer-limitations"></a>Asynkrona kundbegränsningar

Asynkrona kundfunktionen har för närvarande följande begränsningar:

- Förmånskort kan inte utfärdas till asynkrona kunder såvida inte det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.

## <a name="async-customer-enhancements"></a>Asynkrona kundbegränsningar

Om du vill hjälpa organisationer att använda läget för att skapa asynkrona kunder för att hantera kunder, och hjälpa till att minska realtidskommunikationen med Commerce headquarters, har följande förbättringar skapats för att få paritet mellan synkroniserade och asynkrona lägen i kanaler. 

| Förbättrad funktion | Handel version | Information om funktionen |
|---|---|---|
| Prestandaförbättringar när kundinformation hämtas från kanaldatabasen | 10.0.20 och senare | För att förbättra prestandan delas kundenheten upp i mindre enheter. Då hämtar systemet endast den information som krävs från kanaldatabasen. |
| Möjlighet att skapa adress asynkront under utcheckning | 10.0.22 och senare | <p>Funktionsändring: **Aktivera att skapa kundadresser asynkront**</p><p>Information om funktionen:</p><ul><li>Möjlighet att lägga till adresser utan att göra realtidstjänstsamtal i Commerce headquarters</li><li>Möjlighet att identifiera adresser unikt i kanaldatabasen utan att använda ett post-ID (**RecId-värde**)</li><li>Spåra tidsstämplar för att skapa adresser</li><li>Synkronisering av adresser i Commerce headquarters</li></ul><p>Den här funktionen påverkar både synkroniserade kunder och asynkrona kunder. Om du vill redigera adresser asynkront förutom att skapa dem asynkront måste du aktivera funktionen **Redigering av kunder i asynkront läge**.</p> |
| Aktivera paritet mellan synkron och asynkron kundgenerering. | 10.0.24 och senare | <p>Funktionsändring: **Aktivera utökat skapa asynkron kund**</p><p>Funktionsdetaljer: Möjlighet att samla in ytterligare information, till exempel titel, anknytningar från standardkunden och sekundär kontaktinformation (telefonnummer och e-postadress), medan du skapar kunder asynkront</p> |
| Användarvänliga felmeddelanden | 10.0.28 och senare | Dessa förbättringar förbättra användarvänliga felmeddelanden om en användare inte kan redigera information direkt när synkroniseringen pågår. Du aktiverar dessa förbättringar genom att använda inställningen **Tillåt att vissa UI-element inte kan ändras av en asynkron kund** på **Webbplatsinställningar \> Tilläggen** i Commerce-webbplatsbyggaren. |
| Möjlighet att redigera kundinformation asynkront | 10.0.29 och senare | <p>Funktionsändring: **Aktivera redigering av kunder i asynkront läge**</p><p>Funktionsdetaljer: förmåga att redigera kunddata asynkront</p><p>Vanliga frågor om problem som är relaterade till redigering av kundinformation asynkront finns i [Asynkront läget för att skapa kunder](async-customer-mode-faq.md).</p> |
| Förmåga att granska synkronisering av kundhanteringsåtgärder | 10.0.31 och senare | Den här förbättringen gör att användarna kan granska synkroniseringen av kundhanteringsåtgärder i Commerce headquarters. Det gör också att användarna kan göra ändringar om de behövs och synkronisera data. |

### <a name="feature-switch-hierarchy"></a>Hierarki för funktionsändring

På grund av hierarki för funktionsändring, innan du aktiverar funktionen **Aktivera redigering av kunder i asynkront läge** måste du aktivera följande funktioner: 

- **Prestandaförbättringar för kundorder och kundtransaktioner** – Den här funktionen har varit obligatorisk sedan versionen av Commerce version 10.0.28. 
- **Aktivera utökat skapa asynkron kund**
- **Aktivera att skapa kundadresser asynkront**

Vanliga frågor för kunder finns i [Asynkront kundgenereringsläge, där du hittar svar på vanliga felsökningsfrågor](async-customer-mode-faq.md). 

När du har aktiverat de tidigare nämnda funktionerna måste du schemalägga ett återkommande batchjobb för **P-jobb**, jobb **Synkronisera kunder och affärspartner från det asynkrona läget** och jobbet **1010** så att alla asynkroniserade kunder konverteras till synkroniseringskunder i Commerce headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Kundskapa i kassa offlineläge

Som nämndes tidigare, när kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Därför måste kommersiella administratörer för Commerce headquarters skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och jobbet **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

> [!NOTE]
> Om alternativet **Filtrera delade kunddatatabeller** anger **Ja** på sidan **Commerce kanalschema** (**Retail och Commerce \> Administrationsinställning \> Commerce schemaläggare \> Kanaldatabasgrupp**), kundposter skapas inte i kassa offline-läge. Mer information finns i [Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundhantering i butiker](customer-mgmt-stores.md)

[Konvertera asynkrona kunder till synkrona kunder](convert-async-to-sync.md)

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
