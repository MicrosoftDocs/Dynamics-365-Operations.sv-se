---
title: Tilldela butiker eller medarbetare uppgiftslistor
description: I denna artikel beskrivs hur du tilldelar en uppgiftslista till butiker eller medarbetare i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.openlocfilehash: faff772051738f624b86fd23fb6bf29173e909ea
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746205"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Tilldela butiker eller medarbetare uppgiftslistor

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du tilldelar en uppgiftslista till butiker eller medarbetare i Microsoft Dynamics 365 Commerce.

Med uppgiftshantering i Dynamics 365 Commerce kan du tilldela en uppgiftslista till flera butiker eller medarbetare, eller till en kombination av butiker och medarbetare. En regional chef för 20 butiker kan till exempel vilja tilldela uppgiftslistan **förberedelse av semestertider** till alla 20 butiker.

## <a name="start-the-task-list-assignment-process"></a>Starta listan för aktivitetstilldelningar

Innan du börjar processen att tilldela uppgifter, se till att du skapat en uppgiftslista genom att följa stegen i artikeln [Skapa uppgiftslistor och lägga till uppgifter](task-mgmt-create-lists.md). Om du vill börja tilldela en uppgiftslista följer du stegen nedan.

1. Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.
1. Markera uppgiftslistan som du vill tilldela.
1. Select **Starta process**.
1. I dialogrutan **Starta process** på fliken **Allmänt** i fältet **Processnamn** anger du ett namn (t.ex. **Butiker i östra regionen**).
1. Ange ett datum i fältet **Måldatum**.
1. Om du vill tilldela en uppgiftslista till butiker, på fliken **butiker** använder du filtret **Organisationshierarki** för att hitta och välja butikerna.

    Om du vill tilldela uppgiftslistan till medarbetare, går du till fliken **arbetare** och väljer medarbetarna.

1. Starta processen genom att välja **OK**. Uppgiftslistan tilldelas till de valda butikerna eller medarbetarna.

I bilden nedan visas ett exempel på hur du hittar och väljer butiker i dialogrutan **Starta process**.

![Söka efter och välja butiker i dialogrutan Starta process.](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Tilldela uppgiftslistor regelbundet

Återförsäljare har ibland återkommande uppgifter, t.ex. "Checklista för stängning torsdag" eller "Checklista för första dagen i månaden". De kan därför vilja tilldela aktivitetslistan på en återkommande basis.

1. Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.
1. Markera uppgiftslistan som du vill tilldela.
1. Select **Starta process**.
1. I dialogrutan **Starta process** på fliken **Allmänt** i fältet **Processnamn** anger du ett namn.
1. Ge alternativet **Upprepning** värdet **Ja**.
1. I fältet **Återkommande förskjutning av måldatum i dagar** anger du antal dagar. Om du till exempel anger **4** är måldatumet det återkommande datumet plus fyra dagar.
1. På fliken **kör i bakgrunden** väljer du **återkommande**.
1. I dialogrutan **Definiera återkommande** anger du frekvenskriterier och väljer sedan **OK**.

I bilden nedan visas ett exempel på hur du anger frekvenskriterier i dialogrutan **definiera återkommande**.

![Ange frekvenskriterier i dialogrutan Definiera upprepning.](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Status för spåra uppgiftslista

Om du är en regional chef eller butikschef kanske du vill spåra status för uppgiftslistor som har tilldelats flera butiker eller medarbetare. Du kan sedan följa upp med butiker eller arbetare som inte slutfört sina tilldelade uppgifter i tid. Med Commerce backoffice kan du visa status för uppgiftslistor, tilldela om uppgifter eller ändra status för en uppgift.

Följ stegen nedan om du vill spåra uppgiftslistans status för alla uppgifter.

1. Gå till **Retail och Commerce \> Uppgiftshantering \> Processer för uppgiftshantering**.
1. Välj fliken **alla uppgiftslistor** om du vill visa status för alla uppgiftslistor som har tilldelats olika butiker.

Följ dessa steg för att spåra uppgiftslistans status för alla uppgifter som tilldelats dig.

1. Gå till **Retail och Commerce \> Uppgiftshantering \> Processer för uppgiftshantering**.
1. Välj fliken **mina uppgifter** eller **aktiviteter** om du vill visa eller uppdatera status för de uppgifter som har tilldelats dig.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över uppgiftshantering](task-mgmt-overview.md)

[Konfigurera uppgiftshantering](task-mgmt-configure.md)

[Skapa uppgiftslistor och lägga till uppgifter](task-mgmt-create-lists.md)

[Uppgiftshantering i POS](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
