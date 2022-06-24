---
title: Förbättringar av kassahantering
description: I denna artikel beskrivs förbättringar av kassahantering i kassa för Dynamics 365 Commerce.
author: anpurush
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1719e309183042cd7f56be3df8cbbec31cea7c79
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849077"
---
# <a name="cash-management-improvements"></a>Förbättringar av kassahantering

[!include [banner](includes/banner.md)]


Kassahantering är en nyckelfunktion för återförsäljare i fysiska butiker. Återförsäljare vill att deras butiker ska ha system som kan hjälpa dem att ge dig en fullständig spårning av kontanter och dess rörelse i de olika kassorna och kassörerna i en butik. De måste kunna stämma av mot eventuella skillnader och fastställa ansvarsområden.


Microsoft Dynamics 365 Commerce har kontanthanteringskapacitet i sitt kassaprogram (POS). I tidigare versioner av Retail än version 10.0.3 är kassahanteringsfunktionen emellertid inte tillräckligt stabil för att ge en fullständig spårning av kassaflödetsrörelser i butiker. Även om återförsäljare kan stämma av POS för en butik, kan de inte exakt fastställa ansvarsskyldigheten i händelse av en kassaavvikelse.


I Retail version 10.0.3 och senare får detaljhandlare spårning för kassahantering. Som en del av den här spårbarheten kan detaljhandlare definiera kassaskåp, göra tvåsidiga kassatransaktioner och stämma av kassahanteringstransaktioner.

## <a name="set-up-traceability-and-define-safes"></a>Ställa in spårbarhet och definiera kassaskåp

Ställ in de nya funktionerna för kassahantering genom att följa stegen nedan för att konfigurera funktionsprofilen för butikerna.

1. Öppna **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler** och välj en funktionsprofil som är kopplad till butikerna du vill göra förbättringar för kassahantering tillgänglig.
2. På snabbfliken **funktioner** i funktionsprofilen under **avancerad kassahanterng**, ange alternativet **aktivera kassaspårbarhet** till **Ja**.
3. För att konfigurera kassaskåp, gå till **Butik och handel \> Kanaler \> Butiker \> Alla butiker** och välj en butik.
4. På sidan **butiker** i åtgärdsfönstret, på fliken **ställ in** i gruppen **ställ in** markerar du **kassaskåp**. Med det här alternativet kan du definiera och hantera flera kassaskåp för en butik.
4. Innan du kan använda funktionerna måste du köra distributionsschemajobbet **1070 kanalkonfiguration** för att synkronisera dessa konfigurationer med kanaldatabasen.

## <a name="additional-cash-management-changes"></a>Ytterligare kassahanteringsändringar

I Retail version 10.0.3 och senare tillhandahålls även följande funktioner som är relaterade till kassatransaktioner:

- En användare som ombeds att "deklarera startbelopp" måste ange kontantkällan. Användaren kan söka efter de tillgängliga kassaskåp som har definierats i butiken och välja det kassaskåp som kontanterna ska tas ut från så att de kan föras in i kassaapparaten.
- En användare som utför åtgärden "borttagning av betalningsmedel" uppmanas att välja i en lista över öppna transaktioner av typen "växelpost" som den transaktion som åtgärden utförs mot. Om motsvarande växelpost inte finns i systemet kan användaren skapa en icke-kopplad borttagnings tansaktion för betalningsmedel.
- En användare som utför åtgärden "borttagning av betalningsmedel" uppmanas att välja i en lista över öppna transaktioner av typen "växelpost" som den transaktion som åtgärden utförs mot. Om motsvarande borttagning av betalningsmedel inte finns i systemet kan användaren skapa en icke-kopplad växelposttransaktion.
- En användare som "lämnar pengar i ett kassaskåp" uppmanas att välja det kassaskåp där kontanterna lämnas.
- För kassaskåp som har definierats i en butik kan användarna hantera åtgärder som att deklarera startbeloppet, utföra en växelpost, göra en borttagning av betalningsmedel och göra en bankinsättning.
- För användare med rätt användarbehörighet visar åtgärderna "hantera skift" aktiva, uppskjutna och hemligt stängda skift.
- Om du vill stämma av kontanttransaktionerna i ett skift eller över skift väljer du det skift som ska stämmas av och väljer sedan **stämma av**. I den vy som öppnas visas en lista över avstämda och ej avstämda transaktioner på separata flikar. Från den här vyn kan användarna antingen välja ej avstämda transaktioner och stämma av dem, eller välja tidigare avstämda transaktioner och stämma av dem.
- Under avstämningen, om den valda transaktionen inte balanserar, måste användaren ange en beskrivning av orsaken till den obalanserade avstämningen. Användarna kan välja en enda transaktion och sedan stämma av den med relevant orsaksbeskrivning som de kräver.
- Användarna kan fortsätta att stämma av och avstämma av transaktioner tills skiftet stängs. När ett skift har stängts kan transaktionerna inte avstämmas.
- När en användare väljer att stänga ett skift, validerar Commerce att det inte finns några ej avstämda kassahanteringstransaktioner i skiftet. Användare kan inte stänga ett skift om det finns ej avstämda transaktioner.


[!INCLUDE[footer-include](../includes/footer-banner.md)]