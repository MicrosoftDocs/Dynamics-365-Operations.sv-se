---
title: Skapa uppgiftslistor och lägga till uppgifter
description: I denna artikel beskrivs hur du skapar en uppgiftslista och lägger till uppgifter i dem i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f754ee78547e785fa2386dee6c3d89371bc0de41
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268930"
---
# <a name="create-task-lists-and-add-tasks"></a>Skapa uppgiftslistor och lägga till uppgifter

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du skapar en uppgiftslista och lägger till uppgifter i dem i Microsoft Dynamics 365 Commerce.

En *uppgift* definierar en specifik del av arbetet eller en åtgärd som någon måste utföra på eller före ett angivet förfallodatum. I Dynamics 365 Commerce kan en uppgift innehålla detaljerade instruktioner och information om en kontaktperson. Den kan också inkludera länkar till åtgärder på arbetsplatsen, kassaåtgärder (POS) eller webbplatssidor, för att förbättra produktiviteten och ge den kontext som uppgiftsägaren kräver för att kunna slutföra uppgiften på ett effektivt sätt.

En *uppgiftslista* är en samling uppgifter som måste utföras som en del av en affärsprocess. Det kan till exempel finnas en uppgiftslista som en ny arbetare måste fylla i vid registrering, en uppgiftslista för kassörer som arbetar kvällsskift eller en uppgiftslista som måste slutföras för att förbereda butiken för en kommande julsäsong. I Commerce kan varje uppgiftslista som har ett måldatum tilldelas ett valfritt antal butiker eller medarbetare, och den kan konfigureras att återkomma.

Både chefer och arbetare kan skapa uppgiftslistor i Commerce backoffice och sedan tilldela dem till en uppsättning butiker.

## <a name="create-a-task-list"></a>Skapa en uppgiftslista

Gör så här om du vill skapa en uppgiftslista.

1. Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.
1. Välj **Ny** och ange sedan värden i fälten **Namn**, **Beskrivning** och **Ägare**.
1. Välj **Spara**.

## <a name="add-tasks-to-a-task-list"></a>Lägga till uppgifter i en uppgiftslista

Om du vill lägga till uppgifter till en uppgiftslista gör du följande.
 
1. På snabbfliken **uppgifter** i en befintlig uppgiftslista väljer du **ny** om du vill lägga till en uppgift.
1. I dialogrutan **Skapa en ny uppgift** i fältet **Namn** anger du ett namn för uppgiften.
1. I fältet **Förfallen data förskjuten från måldatum** anger du ett positivt eller negativt heltalsvärde. Ange till exempel, ange **-2** om uppgiften ska vara slutförd två dagar före förfallodatum för uppgiftslistan.
1. Ange detaljerade instruktioner i fältet **Anteckningar**.
1. I fältet **Kontaktperson** anger du namnet på en ämnesexpert som uppgiftsägaren kan kontakta om uppgiftsägaren behöver hjälp.
1. I fältet **Uppgiftslänk**, ange en länk baserat på uppgiftens natur.

> [!TIP]
> Du kan använda fältet **Tilldelad till** för att tilldela uppgifter till någon medan du skapar en uppgiftslista, rekommenderar vi att du undviker att tilldela uppgifter under skapandet av uppgiftslistan. Tilldela i stället uppgifterna när listan är instansierad för enskilda butiker.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Använd aktivitetslänkar för att hjälpa till att förbättra produktiviteten i arbetare

Med hjälp av Commerce kan du länka uppgifter till specifika kassaåtgärder, t.ex. att köra en försäljningsrapport, visa en utbildningsvideo för den nya personal orienteringen eller utföra en backoffice-åtgärd. Den här funktionen hjälper aktivitetsägarna att få den information som de behöver för att utföra en uppgift på ett effektivt sätt.

Lägg till aktivitetslänkar under tiden som du skapar en uppgift genom att följa stegen nedan.

1. På snabbfliken **uppgifter** i en befintlig uppgiftslista väljer du **Redigera**.
1. I dialogrutan **Redigera uppgift** i fältet **Uppgiftslänk**, välj ett eller flera av följande alternativ:

    - Välj **menyalternativet** för att konfigurera en backoffice-åtgärd, t.ex. "produktuppsättning".
    - Välj **kassaåtgärd** för att konfigurera en kassaåtgärd, t.ex. försäljningsrapporter.
    - Välj **URL** om du vill konfigurera en absolut URL.

Följande bild visar hur du väljer aktivitetslänkar i dialogrutan **redigera uppgift**.

![Markera uppgiftslänkar i dialogrutan Redigera uppgift.](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Konfigurera en kassaåtgärd så att den kan länkas till en uppgift

Konfigurera en kassaåtgärd så att den kan länkas till en uppgift med följande steg.

1. Navigera till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassaåtgärder**.
1. Välj **redigera**, sök efter kassaåtgärden och markera sedan kryssrutan **Aktivera aktivitetshantering** för den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över uppgiftshantering](task-mgmt-overview.md)

[Konfigurera uppgiftshantering](task-mgmt-configure.md)

[Tilldela uppgiftslistor till butiker eller medarbetare](task-mgmt-assign-lists.md)

[Uppgiftshantering i POS](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
