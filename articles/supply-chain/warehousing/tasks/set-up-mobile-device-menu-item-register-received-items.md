---
title: Ställ in ett menyalternativ för mobila enheter för att registrera mottagna artiklar
description: Detta avsnitt är avsett för inställningar av ett menyalternativ för mobila enheter.
author: ShylaThompson
manager: tfehr
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu, WHSRFDefaultData
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f636a1f3d598a069c3922160eedbe05b68bc91eb
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438024"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Ställ in ett menyalternativ för mobila enheter för att registrera mottagna artiklar

[!include [banner](../../includes/banner.md)]

Detta avsnitt är avsett för inställningar av ett menyalternativ för mobila enheter. Menykommandot används för registrering av inleverans av artiklar som har beställts via inköpsorder. 

Du kan använda den här guiden i demonstrationsföretaget USMF. Den här proceduren är avsedd för lagerchefen.


## <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter
1. I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Menyalternativnamn**. Detta är den unika identifieraren för det här menykommandot för mobil enhet. Du kan exempelvis skriva `My PO registration`.  
4. Ange ett värde i fältet **Rubrik**. Detta är en rubrik som visas för användaren på den mobila enheten. Du kan exempelvis skriva `PO registration`.  
5. Välj **Arbete** i fältet **Läge**. Registrering av lagerbehållning som tagits emot för en inköpsorderrad skapar arbetsuppgift för flyttning av artiklar från inleveransområdet till lagret. Arbetsuppgiften skapas inte förrän artiklarna registreras. Därför ska du lämna alternativet **Använd befintligt arbete** inställt på **Nej**.
6. I fältet **Process för att skapa arbete** i avsnittet **Allmänt** väljer du **Inleverans av inköpsorderartikel**.
    - En inköpsorderrad måste identifieras som unik om lagerbehållning ska kunna registreras på lagerstället. I detta scenario registrerar den mobila enheten inköpsordernumret och artikelnumret, och denna gör att systemet kan identifiera inköpsordern. En inlagringsuppgift skapas och kan väljas av en annan medarbetare. Genereringsmetoden för arbetsuppgiften du väljer avgör vilka fält som är tillgängliga på snabbfliken **Allmänt**.  
    - Om du väljer alternativet **Använd standarddata** aktiveras knappen **Standarddata**. Här kan du välja fält som ska innehålla uppgifter som en medarbetare vanligtvis behöver i det dagliga arbetet, så att värdena visas på den mobila enheten.  
    - Parametern för **gruppering av id-nummer** fungerar tillsammans med enhetsekvensgruppen som är tilldelad till artikeln som inlevereras. Du kan ange om inleveranser av mindre än eller fler än en lastpall ska grupperas under ett id-nummer eller delas upp på flera nummer.  
    - Om du väljer alternativet **Generera id-nummer** skapas ett unikt id-nummer på grundval av nummerserievalet.  
    - Du kan välja mallen som ska användas när arbetsuppgiften skapas. Om du till exempel registrerar en artikel för en inköpsorder genereras den inlagrade arbetsuppgiften baserat på arbetsmallen. Om du inte väljer någon arbetsmall här, tilldelas en mall baserat på frågevillkoren som associeras med mallarna.  
    - Om dispositionskoder visas på den mobila enheten, kan medarbetare utvärdera statusen eller kvaliteten på artiklarna och välja lämplig kod. Reglerna för dispositionskoden bestämmer om artiklarna ska vara tillgängliga för andra lagerprocesser. Reglerna avgör också vilket platsdirektiv som används för arbetsuppgiften som skapas.   
    - Om du väljer alternativet  **Batchdispositionskoder**, kan medarbetare utvärdera statusen eller kvaliteten på en batch och välja lämplig kod. Reglerna på batchdispositionskoden bestämmer om batchen ska vara tillgängliga för andra lagerprocesser.  
    - Om du väljer **Skriv ut etiketter**, skrivs ett id-nummer ut automatiskt när artiklarna tas emot.  
7. Välj **Spara**.
8. Stäng sidan.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Lägg till menykommandot på en meny för mobila enheter
1. I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.
2. Använd **snabbfiltret** för att filtrera på fältet **Namn** med värdet `inbound`.
3. Välj **Redigera**.
4. I trädet Tillgängliga menyer och artiklar ska du välja menyartikeln som du skapade tidigare.
5. Välj pilen som pekar åt höger.
6. Välj **Spara**.
7. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]