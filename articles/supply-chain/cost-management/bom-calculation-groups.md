---
title: Beräkningsgrupper för strukturlista
description: Den här artikeln innehåller information om beräkningsgrupper för strukturlistor och hur du ställer in dem. Om du vill köra en strukturlisteberäkning måste du antingen ställa in beräkningsgrupper och tilldela dem till enskilda artiklar eller ställa en standardberäkningsgrupp. Beräkningsinställningarna från beräkningsgruppen används sedan som standardvärden på sidan Strukturlisteberäkning när strukturlistan beräknas.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5927b1c31cf15e2fb92c15d4abc06bfa0403e33d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266305"
---
# <a name="bom-calculations-groups"></a>Beräkningsgrupper för strukturlista

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om beräkningsgrupper för strukturlistor och hur du ställer in dem. Om du vill köra en strukturlisteberäkning måste du antingen ställa in beräkningsgrupper och tilldela dem till enskilda artiklar eller ställa en standardberäkningsgrupp. Beräkningsinställningarna från beräkningsgruppen används sedan som standardvärden på sidan Strukturlisteberäkning när strukturlistan beräknas. 

Det krävs en standardberäkningsgrupp på sidan **Parametrar för hantering av lager och lagerstyrning** eller en produktspecifik beräkningsgrupp på sidan **Information om frisläppt produkt**. Systemet söker först efter inställningarna för beräkningsgrupper på sidan **Information om frisläppt produkt**. Om det inte finns någon beräkningsgrupp där, söker systemet sidan **Parametrar för hantering av lager och lagerstyrning**. Om systemet inte kan hitta en beräkningsgrupp får användaren ett felmeddelande under beräkningen. En beräkningsgrupp innehåller policyer för självkostnadsmodellen, försäljningsprismodellen och varningschecklistan. Beräkningsinställningar från beräkningsgruppen används som standardvärden på sidan **Strukturlisteberäkning** när strukturlistan beräknas.

## <a name="purposes-of-bom-calculation-groups"></a>Syftet med beräkningsgrupper för strukturlistor
Du kan tilldela en beräkningsgrupp för strukturlistor till artiklar av flera anledningar:

-   Du kan i fältet **Självkostnadsmodell** ange källan för en inköpt komponents kostnadsbidrag vid beräkning av en planerad kostnad för en tillverkad artikel. Vissa tillverkare beräknar planerade kostnader med hjälp av handelsavtal för inköpta komponenter eller något annat underlag såsom inköpsprisposter i en kostnadsversion.
-   Du kan använda fältet **Försäljningsprismodell** för att ange hur artikelns data ska användas för att beräkna ett föreslaget försäljningspris. Du kan ange artikelns försäljningspris eller kostnadsgrupp. Vissa tillverkare vill beräkna ett föreslaget försäljningspris för tillverkade artiklar. Det beräknade priset kan återspegla en metod för summerat pris som baseras på komponentens försäljningsprispost. Alternativt kan det beräknade försäljningspriset återspegla en merkostnadsstrategi som baseras på komponentens kostnad och tillämplig vinstmarginal som är kopplad till artikelns kostnadsgrupp.
-   Använd fältet **Stoppa nedbrytning** för att indikera att en tillverkad artikel ska behandlas som en inköpt artikel för kostnadssummeringsändamål. Vanliga situationer omfattar en inköpt artikel som tillverkas ibland eller en tillverkad artikel som numera köps in. Artikeln betecknas inledningsvis som en tillverkad artikel för att definiera information om strukturlistan och flödet samt så att tillverkningsorder stöds för artikeln. Flaggan **Stoppa nedbrytning** förhindrar dock kostnadsberäkningar från att använda artikelns strukturlista och flöde. I stället använder strukturlisteberäkningen de angivna kostnaderna för den valda artikeln.

## <a name="calculation-groups"></a>Beräkningsgrupper
Du definierar beräkningsgrupper under **Ställ in policyer för fördefinierad kostnad** i Kostnadshantering. Med hjälp av de beräkningsgrupper som tilldelas till artiklarna kan du ange hur kostnaden eller försäljningspriset för komponenter, enligt beskrivningen av beräkningsgruppen, för beräkningen hämtas. På sidan **Beräkningsgrupper** kan du definiera en självkostnadsmodell, en alternativ självkostnadsmodell, en försäljningsprismodell och varningar.

### <a name="cost-price-model"></a>Självkostnadsmodell

Det finns fyra alternativ för fältet **Självkostnadsmodell**:

-   **Artikelns självkostnad** – Antingen används självkostnaden från tabellen **Frisläppt produkt** eller så används en kombination av artikeldimensioner som självkostnad.
-   **Artikelns inköpspris** – Inköpspriset från fältet **Självkostnad** på fliken **Inköp** på sidan **Lista över frisläppta produkter** används.
-   **Handelsavtal** – Du kan konfigurera handelsavtal för särskilda kombinationer av artiklar och leverantörer eller för specifika platser. När du väljer alternativet **Handelsavtal** kommer handelsavtalet som du skapade för inköpspriset tillsammans med artikeln och platsen att användas.
-   **Lagerpris** – Det aktuella lagervärdet för artikeln används för att beräkna enhetspriset i strukturlisteberäkningen. Ett enhetspris beräknas endast om den bokförda kvantiteten och den fysiska kvantiteten är större än 0 (noll).

### <a name="alternative-cost-price"></a>Alternativ självkostnad

Fältet **Alternativ självkostnad** innehåller samma alternativ som fältet **Självkostnadsmodell**. Det här fältet används endast när ett pris inte kan hittas i den primära självkostnadsmodellen.

### <a name="sales-price-model"></a>Försäljningsprismodell

Det finns två alternativ för beräkning av fältet **Försäljningspriser**:

-   **Kostnadsgrupp** – När det här alternativet väljs beräknas försäljningspriset utifrån självkostnaden och inställningen för täckningsbidraget från kostnadsgruppen.
-   **Artikelns försäljningspris** – När det här alternativet väljs används försäljningspriset från snabbfliken **Sälj**.

### <a name="stop-explosion"></a>Stoppa nedbrytningen

Kryssrutan **Stoppa nedbrytning** används för att ange när en tillverkad artikel ska behandlas som en inköpspost. Vanligtvis lämnar du kryssrutan **Stoppa nedbrytning** avmarkerad. Markera den här kryssrutan om du vill visa att en tillverkad artikel ska behandlas som en inköpt komponent och inte som en tillverkad komponent vid en strukturlisteberäkning. Beroende på platsen kan artikelkostnaden fortfarande beräknas med hjälp av strukturlisteberäkningar. Nedbrytningen av planerade inköpsorder och produktionsorder stoppas i en strukturlista som har komponenter kopplade till den beräkningsgrupp som kryssrutan **Stoppa nedbrytning** är markerad för. Huvudplanering genererar planerade order för själva strukturlistan och inte för artiklarna som ingår i strukturlistan. Genom att markera den här kryssrutan kan du i princip ange att en kostnad inte ska läggas till i strukturlisteberäkningen för artiklar som har denna beräkningsgrupp.

### <a name="warnings"></a>Varningar

På snabbfliken **Varningar** väljer du alternativ för eventuella varningsmeddelanden som användarna får när de gör strukturlisteberäkningar. 

Om du till exempel väljer kryssrutan **Ingen strukturlista** får användaren en varning om ingen aktiv strukturlisteversion hittas för en av komponenterna eller den överordnade artikeln som strukturlisteberäkningen ska köras för. Om du väljer kryssrutan **Inget flöde** får användaren en varning om ingen aktiv flödesversion hittas. Om du använder resurser på dina flöden och åtgärder kan du instruera systemet att leta efter de resurserna. Om en resurs sedan inte hittas på varje rad i det aktiva flödet får användaren en varning. 

Du kan också verifiera och leta efter förbrukning. Förbrukningen är kvantiteten i ett visst flöde. Vanligtvis representerar den tidsåtgången för att utföra en viss åtgärd för en produktionsprocess. Du kan kontrollera om en artikel inte har någon självkostnad. Om det inte finns någon aktiv självkostnad för en artikel läggs ingen kostnad till i strukturlisteberäkningen. 

Du kan också kontrollera och verifiera självkostnadens ålder. Ange till exempel **60** för att indikera att självkostnaden per enhet måste omvalideras efter 60 dagar. Om den här gränsen nås genereras en varning. Till exempel angavs självkostnaden för en artikel i januari i år. Om det nu är augusti, vilket är mer än 60 dagar efter att självkostnaden angavs, får användaren en varning när en strukturlisteberäkning körs. Du kan ange en procentsats i fältet **Lägsta täckningsbidrag**. Det här värdet anger den punkt vid vilken det lägsta täckningsbidraget inte är uppfyllt. Om täckningsbidraget för en viss komponent inte uppfylls får användaren en varning. Det här fältet kan därför garantera att du inte underskrider kostnaderna och de extra transportkostnaderna som kan krävas för artiklarna.

### <a name="default-setup-in-inventory-and-warehouse-management-parameters"></a>Standardinställningar för Parametrar för hantering av lager och lagerstyrning

Eftersom beräkningsgrupper krävs för att göra beräkningar måste du ställa in en standardberäkningsgrupp i Parametrar för lagerhantering. Den här inställningen gör att företag kan ha en standardkostnadsgrupp och vinstinställning för alla artiklar. Om en viss artikel sedan har särskilda beräkningskrav kan användaren tilldela en annan beräkningsgrupp för den artikeln. Normalt sett anger du beräkningsgrupper för strukturlistekomponentartiklar i stället för strukturlisteartiklar. När varningsmeddelanden visas tillämpas dock beräkningsgrupper. En beräkningsgrupp som tilldelas artiklarna åsidosätter det standardvärde som har ställts in i Parametrar för lagerhantering. 

Du kan ställa in förvald parameter på **Kostnadshantering** &gt; **Policyinställningar för lagerredovisning** &gt; **Parametrar** &gt; **Lagerredovisning** &gt; **Beräkningsgrupp**. Genom att ställa in en standardkonfigurationsgrupp kan du även konfigurera varningsvillkor som användarna får under beräkningsprocessen för strukturlistan om de markerade komponenterna kan orsaka beräkningsfel.

### <a name="view-warning-messages-on-the-complete-page"></a>Visa varningsmeddelanden på sidan Slutförd

En strukturlisteberäkning genererar varningsmeddelanden. Du kan visa varningar om en vald artikel. Skapa exempelvis en ny försäljningsorder för objektet D0001 i Försäljning och marknadsföring. Klicka sedan på försäljningsorderraden, gå till menyn **Uppdatera rad** och klicka på **Beräkna baserat på strukturlista/formel** för att visa beräkningsinformation och varningar. Du kan också visa resultat för strukturlisteberäkningen på sidan **Slutförd**. För varningsmeddelanden gäller enbart två varningsvillkor för tillverkade artiklar medan fyra varningsvillkor gäller för alla artiklar:
-   Identifiera när en tillverkad artikel inte har någon aktiv strukturlista.
-   Identifiera när en tillverkad artikel inte har något aktivt flöde.
-   Identifiera när artikeln på en strukturlisterad har kvantiteten 0 (noll).
-   Identifiera när artikeln på en strukturlisterad har kostnaden 0 (noll) eller när den inte har någon kostnadspost.
-   Identifiera när artikeln på en strukturlisterad har en inaktuell kostnad. Varningen genereras efter en jämförelse mellan beräkningsdatumet och det angivna antalet dagar för kostnadens maximala ålder.
-   Identifiera när artikeln på en strukturlisterad har en lägre vinstmarginal än du önskar.

Du kan definiera flera beräkningsgrupper för strukturlistor, beroende på dina krav för varianter i varningsmeddelanden. Det kan till exempel räcka med en beräkningsgrupp för strukturlistor som visar ett varningsmeddelande om en aktiv strukturlista eller om en komponentkvantitet som är lika med 0 (noll). När du startar beräkningen av en strukturlista kan du åsidosätta varningsvillkoren som är kopplade till beräkningsgruppen för strukturlistor. Du kan också lägga till eller ta bort varningsvillkor. Om den aktuella situationen inte berör flödesdata kan du exempelvis ta bort varningsvillkoret för ett aktivt flöde. **Obs!** Sidan **Beräkningsgrupper** inkluderas i Tid och närvaro, men har ingen koppling till beräkningsgrupper för strukturlistor. I Tid och närvaro kan arbetstagare tilldelas till beräkningsgrupper som återspeglar grupperingen av arbetstagare som är associerade med samma arbetsledare eller chef. Beräkning av arbetstagarregistreringar kan utföras automatiskt eller manuellt av en arbetsledare eller chef.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]