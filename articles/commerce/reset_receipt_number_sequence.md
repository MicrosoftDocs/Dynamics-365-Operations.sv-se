---
title: Återställa kvittonummer
description: I denna artikel beskrivs hur du återställer de kvittonummer som används för olika åtgärder på ett önskat datum (t.ex. räkenskapsår eller kalenderår).
author: ShalabhjainMSFT
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: 5dc9f3f977e04866562781d9768141a4a96166f4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858866"
---
# <a name="reset-receipt-numbers"></a>Återställa kvittonummer 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Vi kräver att du väljer egenskapen **oberoende sekvens** för alla kvittotyper i funktionsprofilen innan du använder den här funktionen. Även systemets tidszon för enheten, där POS används, bör matcha motsvarande lagringstidszon. På grund av dessa begränsningar rekommenderar vi att du inte använder den här funktionen i produktionen medan vi arbetar med att åtgärda problemen i en senare version. 

Åter försäljare genererar kvittonummer för olika åtgärder i butiken, t.ex. kontanter och hämtköpstransaktioner, returtransaktioner, kundorder, offerter och betalningar. Även om återförsäljare definierar sina egna kvittoformat, har vissa länder eller regioner regler som begränsar dessa kvittoformat. Dessa förordningar kan t.ex. begränsa antalet tecken på kvittot, kräva efterföljande kvittonummer, begränsa vissa specialtecken eller kräva att kvittonummer måste återställas vid början av året. Microsoft Dynamics 365 Commerce gör processen att hantera kvittonummer mycket flexibel, så att återförsäljarna kan uppfylla gällande krav. I denna artikel beskrivs hur du använder funktionen för att återställa kvittonummer.

I Commerce kan kvittoformat vara alfanumeriska. Du kan både placera statiskt innehåll och dynamiskt innehåll i dem. Statiskt innehåll innehåller alfabetiska tecken, siffror och specialtecken. Dynamiskt innehåll innehåller ett eller flera tecken som representerar information som butiksnummer, terminalnummer, datum, månad, år och nummerserier som automatiskt ökas. Formaten definieras i avsnittet **kvittonummer** i funktionsprofilen. I följande tabell beskrivs de tecken som representerar det dynamiska innehållet.

| Tecken | Beskrivning |
|------------|-------------|
| L          | Tecknet **S** används som butiksnummer. Om till exempel en butik är numrerad HOUSTON1, visas formatet **SSS** "ON1" på kvittot. Formatet **SSSSS** visar "STON1" på kvittot. |
| T          | Tecknet **T** används som terminalnummer. Om till exempel en terminal är numrerad 0001, visas formatet **TTTT** "0001" på kvittot. |
| C          | Tecknet **C** används som personalens ID-nummer. Om en personalmedlem till exempel har ett ID på 000160, visar formatet **CCCC** "0160" på kvittot. |
| ddd        | Tecknen **ddd** motsvarar dagen på året, från 1 till 366. Exempel: den 15 januari visar formatet **ddd** "015" på kvittot. |
| MM         | Tecknen **MM** används i månaden med två siffror. Exempel: i januari visar formatet **MM** "01" på kvittot. |
| DD         | Tecknen **DD** används i dagen månaden med två siffror. Exempel: den 15 januari visar formatet **DD** "15" på kvittot. |
| YY         | Tecknen **ÅÅ** används i år med två siffror. T.ex. en månad under år 2020 visar formatet **ÅÅ** "20" på kvittot. |
| \#         | Ett nummertecken (**\#**) används för sekventiell numrering. Till exempel formatet **####** visar "0001," "0002," "0003," osv. på kvittot. |

Du kan återställa den sekventiella numreringen på kvittot ett visst datum. För den första transaktionen som inträffar efter 12:00 på det valda återställningsdatumet återställer systemet kvittots nummerserie till 1. Du kan också ange om återställningen bara ska ske en gång eller om den ska återkomma varje år. Om årlig upprepning anges sker återställningen automatiskt varje år tills åter försäljaren väljer att stoppa den. 

Så här aktiverar du återställning.

1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**.
1. På snabbfliken **Kvittonummer** väljer du **Återställningsnummer, återställningsdatum**.
1. I listrutan i fältet **återställningsdatum** väljer du ett framtida datum då återställningen ska ske.
1. I fältet **Återställ kvittotyp** väljer du **endast e gång** eller **varje år**.
1. Välj **OK**.

![Välja ett återställningsdatum för kvitto.](media/Enable_receipt_reset.png "Välja ett återställningsdatum för kvittot")

När du har valt ett datum visas det i kolumnen **Nästa kvittonummer, återställningsdatum**. Återställningsdatumet gäller för alla typer av kvittotransaktioner. Därför återställs kvittots nummerserie av alla typer av kvitton.

När återställningsdatum infaller återställs kvittonumret för den första transaktionen av varje typ. I funktionsprofilen flyttas dessutom återställningsdatumet från kolumnen **Nästa kvittonummer, återställningsdatum** till kolumnen **Aktuellt kvittonummer, återställningsdatum**. Den här ändringen anger att om en kassa inte används på återställningsdatumet återställs kvittonumret nästa gång POS *används*. Till exempel den 3 december 2019, väljer du **1 januari 2020** som återställningsdatum. Den 1 januari när kassorna gör sin första transaktion återställs kvittonumret. Men en kassa används inte alls under december och januari, utan börjar sedan användas i februari. I detta fall, eftersom en återställningsåtgärd har definierats, återställs kvittonumret för POS när POS gör den första transaktionen i februari.

Du kan använda funktionen **rensa återställningsdatum** för att rensa framtida återställningsdatum. Om återställningsdatumet har passerat kan det dock inte ångras. Därför görs en återställning av alla kassor där återställningen ännu inte har förekommit.

> [!NOTE]
> Beroende på vilket återställningsdatum du väljer och kvittoformatet, kan du ha duplicerade kvittonummer. Även om kassasystemet kan hantera dessa situationer, ökar den tid som krävs för att bearbeta returer, eftersom säljare måste välja bland de duplicerade kvittona. Andra komplikationer som rör datarensning kan inträffa om de duplicerade inleveranserna inte är en planerad följd. Därför rekommenderar vi att du använder dynamiska datumtecken (t.ex. **ddd**, **MM**, **DD** och **ÅÅ**) ör att förhindra att kvittonumren dupliceras efter en återställning.


[!INCLUDE[footer-include](../includes/footer-banner.md)]