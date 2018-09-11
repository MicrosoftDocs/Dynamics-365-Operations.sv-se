--- 
title: "Ställ in ett menyalternativ för mobila enheter för att registrera mottagna artiklar"
description: "Denna uppgift är avsedd för inställningar av ett menykommando för mobila enheter."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem, WHSRFMenu
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 7b5d757361c1163bbd0300abd3da4e0a2dd6b0e0
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Ställ in ett menyalternativ för mobila enheter för att registrera mottagna artiklar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift är avsedd för inställningar av ett menykommando för mobila enheter. Menykommandot används för registrering av inleverans av artiklar som har beställts via inköpsorder. 

Du kan använda den här guiden i demonstrationsföretaget USMF. Den här proceduren är avsedd för lagerchefen.


## <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter
1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Menyalternativ.
    * Detta är den unika identifieraren för det här menykommandot för mobil enhet. Du kan exempelvis skriva Min IO-registrering.  
4. Ange ett värde i fältet Titel.
    * Detta är en rubrik som visas för användaren på den mobila enheten. Du kan exempelvis skriva IO-registrering.  
5. Välj Arbete i fältet Läge.
    * Registrering av lagerbehållning som tagits emot för en inköpsorderrad skapar arbetsuppgift för flyttning av artiklar från inleveransområdet till lagret. Arbetsuppgiften skapas inte förrän artiklarna registreras.  Därför ska värdet värdet på Använd befintligt arbete vara Nej.  
6. Utöka eller komprimera avsnittet Allmänt.
7. Markera Inleverans av inköpsorderartikel i fältet Process för att skapa arbete.
    * En inköpsorderrad måste identifieras som unik om lagerbehållning ska kunna registreras på lagerstället. I detta scenario registrerar den mobila enheten inköpsordernumret och artikelnumret, och denna gör att systemet kan identifiera inköpsordern. En inlagringsuppgift skapas och kan väljas av en annan medarbetare.    Genereringsmetoden för arbetsuppgiften du väljer avgör vilka fält som är tillgängliga på snabbfliken Allmänt.  
    * Om du väljer alternativet Använd standarddata aktiveras knappen Standarddata. Här kan du välja fält som ska innehålla uppgifter som en medarbetare vanligtvis behöver i det dagliga arbetet, så att värdena visas på den mobila enheten.  
    * Parametern för id-nummer fungerar tillsammans med enhetsekvensgruppen som är kopplad till artikeln som inlevereras. Du kan ange om inleveranser av mindre än eller fler än en lastpall ska grupperas under ett id-nummer eller delas upp på flera nummer.  
    * Om du markerar alternativet för generering av id-nummer, skapas ett unikt id-nummer på grundval av nummerserievalet.   
    * Du kan välja mallen som ska användas när arbetsuppgiften skapas. Om du till exempel registrerar en artikel för en inköpsorder genereras den inlagrade arbetsuppgiften baserat på arbetsmallen. Om du inte väljer någon arbetsmall här, tilldelas en mall baserat på frågevillkoren som associeras med mallarna.  
    * Om dispositionskoder visas på den mobila enheten, kan medarbetare utvärdera statusen eller kvaliteten på artiklarna och välja lämplig kod. Reglerna för dispositionskoden bestämmer om artiklarna ska vara tillgängliga för andra lagerprocesser. Reglerna avgör också vilket platsdirektiv som används för arbetsuppgiften som skapas.   
    * Om du väljer alternativet Batchdispositionskoder, kan medarbetare utvärdena utvärdera statusen eller kvaliteten på en batch och välja lämplig kod.  Reglerna på batchdispositionskoden bestämmer om batchen ska vara tillgängliga för andra lagerprocesser.  
    * Om du väljer Skriv ut etiketter, skrivs ett id-nummer ut automatiskt när artiklarna tas emot.  
8. Klicka på Spara.
9. Stäng sidan.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Lägg till menykommandot på en meny för mobila enheter
1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet.
2. Använd snabbfiltret för att filtrera på fältet Namn med värdet inkommande.
3. Klicka på Redigera.
4. I trädet markerar du ett alternativ som lyder ungefär så här: Välj menyalternativet du skapade tidigare i trädet för menyn Tillgänglig och artikelträdet.
    * Välj menykommandot som du skapade tidigare.  
5. Klicka på pilen som pekar åt höger.
6. Klicka på Spara.
7. Stäng sidan.


