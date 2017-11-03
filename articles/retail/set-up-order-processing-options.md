---
title: "Ställ upp för bearbetningsalternativ"
description: "Det här avsnittet innehåller information om hur du bearbetar beställningar för kundtjänst med Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a0f3d1aea49f0251ecc68e70b4b6054e1813c8ad
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-order-processing-options"></a>Ställ in alternativ för orderbearbetning

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om hur du bearbetar beställningar för kundtjänst med Microsoft Dynamics 365 for Retail. 

Retail stöder flera butikskanaler, till exempel onlinebutiker, onlinemarknadsplatser, fysiska butiker och kundtjänst. I kundtjänster tar anställda emot kundorder per telefon och skapar försäljningsorder. I det här avsnittet beskrivs hur du skapar en kundtjänst och konfigurerar kundtjänstalternativ. Varje kundtjänst kan ha sina egna användare, betalningsmetoder, prisgrupper, ekonomiska dimensioner och leveranssätt. Du kan konfigurera dessa alternativ, när du skapar kundtjänst. **Viktigt!** Innan call center-arbetsflöden kan användas när användaren skapar försäljningsorder måste användaren tilldelas call center som en call center-användare. Du kan använda **Call center-** sidan för att aktivera eller inaktivera grupper av funktioner som är unika för call centers. Följande grupper av funktioner kan aktiveras:

-   **Orderns färdigdatum** – Denna grupp omfattar funktioner som är relaterade till betalningar och beställningen slutförs på **försäljningen** .
-   **Riktad försäljning** – Denna grupp omfattar funktioner som är relaterade till källkoder, manuskript, och katalog.

När du aktiverar funktionerna i call center-inställningarna, de finns på **Sales beställningssida** för användare som är associerade med call center. De flesta av dessa funktioner kräver ytterligare inställningar innan de kan användas. Bilder och skript är aktiverat som en del av det riktade försäljning för specifika call center. Om funktionen är aktiverad, manuskript och bilder visas i rutan faktaruta av **försäljningsorder** sida. Standard-bild som är inställd för en produkt visas. Manuskript kan konfigureras för ett objekt, katalog, kund eller i samband med en katalog. Call center-order kan visa ytterligare detaljer om hur priset för en specifik orderrad härleddes. Exempelvis order visa vilka rabatter som tillämpades. Du aktiverar funktionen på **Kundfordringar** &gt; **Installationer** &gt; **Kundfordrings parametrar** &gt; **Priser** &gt; **Prisuppgifter**. Du kan få tillgång till **prisuppgifter** från **försäljningsorderrad** listrutan. Du kan använda vid tracking för granskningsändamål, att granska åtgärder som vidtas på en beställning under dess livstid, eller spåra en specifik användare. Du kan till exempel spela in varje gång som en användare skapar en försäljningsorder, lägger ned på en order, åsidosätter en avgift, eller uppdaterar en orderrad. Du kan ställa in ordning händelser händelser för specifika användare, grupper av användare eller för alla användare under en viss period. Du kan visa de åtgärder som vidtagits på ett dokument genom att öppna **för sidan händelser** i rutan Åtgärd på sidan för dokumentet. Du kan konfigurera för händelser vid **Försäljning och marknadsföring** &gt; **Inställningar** &gt; **Händelser** &gt; **Orderhändelser**. När en kunds beställning inte kan levereras i tid, ett företag kan automatiskt skicka e-post meddelanden till kunden att förklara orderstatus och ge kunden en möjlighet att avbryta ordern. Om en fördröjning sträcker sig efter en angiven tröskel kan ordern annulleras automatiskt. Upp till tre e-postmeddelanden kan skickas vid specificerade intervall:

1.  **Första uppsägning** – Kunden kan makulera ordern.
2.  **Andra uppsägning** – Kunden kan makulera ordern.
3.  **Sista uppsägning** – systemet avbryts beställningen och kunden informeras om uppsägning.

Du kan undanta enskilda kunder och produkter från den automatiska meddelande- och annulleringsprocessen. En marginalnotifiering utlöses när du lägger till en artikel i en order. Alert innehåller viktig information om objektet, t.ex. priset marginal och lönsamhet. Du kan använda den här informationen för att avgöra om en prisåsidosättning är lämplig när du lägger till en artikel till försäljningsordern. Till exempel kan du ställa in tröskelvärden för handelsmarginaler, för att ange att en tröskel på 40 procent eller mer ovanför kostnaden är acceptabel för ett objekt, men en tröskel på 20 till 39 procent högre kostnad kan ifrågasättas. I det här fallet, något som har en tröskel mellan 20 och 39 procent utlöser en varning. Alla objekt som har en tröskel på mindre än 20 procent högre kostnad kan inte säljas, och priset kan inte justeras. Du kan konfigurera marginal varnar på **Kundfordringar** &gt; **Installationer** &gt; **Kundfordringsparametrar** &gt; **Marginalvarningar**. När du ställer in momstilldelningen baserat på standardregeln, kan du definiera en matchande prioritet för adresselement. Du kan till exempel ange att matcha en momsgrupp med postnummer har högre prioritet än motsvarande en momsgrupp av staten. Såsom dig träda in den nya kundens adress register momsgrupp tilldelas automatiskt, baserat på hur kundens adress matchar med standard regler och prioriterade matchande som du definierade. Du kan konfigurera den här funktionen på **redovisningsparametrar** sidan.




