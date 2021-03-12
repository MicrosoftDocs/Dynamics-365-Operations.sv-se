---
title: Hantera omdömen och recensioner
description: Det här avsnittet innehåller information om hur du hanterar recensioner i Microsoft Dynamics 365 Commerce-webbplatsskaparen.
author: gvrmohanreddy
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a70d0526fb2443605a6b11df3ee281d4dd12f1d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982576"
---
# <a name="manage-ratings-and-reviews"></a>Hantera omdömen och recensioner

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om hur du hanterar recensioner i Microsoft Dynamics 365 Commerce-webbplatsskaparen.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce använder Microsoft Azure kognitiva tjänster för att automatiskt moderera granskningstext genom att ta bort redigering av svordomar. Dessutom kan moderatorer använda Dynamics 365 Commerce webbplatsskaparen för att implementera följande manuella uppgifter:

- Moderera granskningar genom att svara på dem eller ta bort dem.
- Ta bort en kunds recensioner på kundens begäran.
- Massimport av omdömen och granskningsdata för alla produkter i en Microsoft Power BI-mall, så att trender för omdömen och recensioner kan analyseras.

## <a name="read-a-review"></a>Läs en recension 

För läs till en recension i din Commerce-webbplatsskapare.

1. Gå till **start \> recensioner \> moderator**.
1. Använd sökfältet högst upp till höger på sidan om du vill filtrera granskningarna som visas i produkt-ID, produktnamn eller granska text.

Med hjälp av fler filter kan du begränsa granskningarna efter period, klassificering, kanal eller problemstatus (tas upp, svaras eller rapporteras).

![Startsida för moderator](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Besvara på en recension 

Ibland kan kunder som köpte en produkt uttrycka sig eller vara missnöjda, eller så förstår de inte hur produkten används. Som moderator kan du publicera ett svar på en recension. Det här svaret visas tillsammans med recensionen på webbplatsen. 

För svara till en recension i din Commerce-webbplatsskapare.

1. Gå till **start \> recensioner \> moderator**.
1. Sök efter och välj den recension som kräver ett svar.
1. I egenskapsrutan till höger, välj egenskapen **Lägg till ett svar**.
1. Ange svarstexten och namnet som ska visas för den svarande. Namnet på standardsvarande är **moderator**.
1. Välj **Publicera svar** när du är klar.

![Besvara en recension](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Ta ner en recension 

Ibland finns det en affärsjustering för moderatorer som kan ta ned kundens recension. 

För de här stegen en recension i din Commerce-webbplatsskapare.

1. Gå till **start \> recensioner \> moderator**.
1. Sök efter och välj den recension som måste tas ned.
1. I egenskapsrutan till höger väljer du en orsak till nedtagning under **Ta ner en recension** och sedan **Ta ned**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Ta bort en kunds recensioner på kundens begäran. 

Ibland vill kunderna ha sina värderingar och granska data permanent från en näthandelssajt. En moderator som tar emot en begäran om borttagning från en kund kan ta bort kundens data genom att använda funktionen borttagning av recension. För att kunna söka efter och ta bort en kunds data måste moderatorn ange e-postadressen som kunden använde för att logga in och ge recensioner. 

Om du vill söka efter och ta bort kunddata i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till **start \> recensioner \> ta bort**.
1. I rutan **Sök efter användare via e-postadress**, ange kundens e-postadress och välj **Sök**.
1. Om kunden har en recensionsaktivitet (t.ex. skicka recensioner, röster om användbarheten hos en annan kunds recension eller kommentarer om en annan kunds recension) visas resultatet. För varje artikel finns det en **borttagnings**-knapp.
1. Välj **ta bort** för varje artikel som måste tas bort. Välj **ja** när du ombeds bekräfta att det är klart. 
    
![Ta bort kunddata](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - Det kan ta upp till sju dagar innan data tas bort helt från systemet. Moderatorer bör meddela kunderna om denna fördröjning.
> - Om kunder har ändrat sina namn i sina kontoinställningar kan flera artiklar visas i sökresultaten. Om du vill ta bort kundens data fullständigt måste moderatorn välja **ta bort** för varje artikel. 

## <a name="download-ratings-and-reviews-data"></a>Hämta klassificerings- och granskningsdata

Commerce-webbplatsbyggaren låter moderatorer importera klassificeringar och granska data i bulk, så att de kan analysera trender. En Power BI-mall som innehåller grundläggande mått finns tillgänglig. Moderatorerna kan använda den här mallen för att ansluta data i massimporterade och visa en instrumentpanel. De behöver inte skapa en egen instrumentpanel. Moderatorerna kan också anpassa Power BI-mallen efter specifika behov. 

Om du vill ladda ner betyg och recensionsdata i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till **start \> recensioner \> rapporter**.
1. Välj **hämta recensionsdata** om du vill hämta klassificeringar och granska data i bulk i CSV-format (kommaavgränsade värden).

## <a name="view-ratings-and-reviews-trends"></a>Visa trender för omdömen och recensioner

Moderatorerna kan hämta Power BI-mallen så att de kan visa trender på en instrumentpanel.

Om du vill visa klassificeringar och recensionstrender i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till **start \> recensioner \> rapporter**.
1. Välj **PowerBI-mall** om du vill hämta mallen.

    ![Hämta Power BI-mallen](media/rnr-moderation-reports.png) 

1. Öppna den hämtade mallen med hjälp av Power BI-appen. Stäng dialogrutan **åtkomst till webbinnehåll** som visas och stäng sedan felmeddelandet "uppdatera" som visas.
1. Gå till sidan **Start**, välj **Redigera frågor** och sedan **inställningar av datakälla**.
1. I dialogrutan **inställningar av datakälla** välj **ändra källa**.
1. I fältet **URL** anger du sökvägen till de granskningsdata som du hämtade i föregående procedur (t.ex. **c:\\reviews\\ReviewsData.csv**).

    ![URL-fält i dialogrutan kommaavgränsade värden](media/rnr-powerbi-datasource-settings.png) 

1. Välj **OK** och sedan **Tillämpa ändringar**. Det tar en till två minuter innan ändringarna i datakällan tillämpas.
1. Välj **Trendark** om du vill visa trender och recensioner.

    ![Trender för omdömen och recensioner](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar i Dynamics 365 Retail](sync-product-ratings.md)
