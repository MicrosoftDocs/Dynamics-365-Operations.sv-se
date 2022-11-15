---
title: Ställ in uppgifter i uppgiftshantering
description: I denna artikel beskrivs hur du konfigurerar uppgifter i uppgiftshantering i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745395"
---
# <a name="set-up-tasks-in-task-management"></a>Ställ in uppgifter i uppgiftshantering

[!INCLUDE [PEAP](../includes/peap-1.md)]

I versioner av Microsoft Dynamics 365 Human Resources före version 10.0.30 måste användare som vill redigera en uppgift individuellt redigera den uppgiften på varje checklista som innehåll den. I personalversion 10.0.30 kan användarna dock välja hur redigerade uppgifter ska hanteras. Om en uppgift som redigeras finns i en checklista måste alternativet **Aktivera uppgradering av uppgiftshantering** väljas på fliken **Uppgiftshantering** på sidan **Delade personalparametrar** för att checklista ska kunna använda den redigerade uppgiften.

[![Aktivera alternativet för uppgradering av uppgiftshantering på sidan Delade parametrar för Personal.](./media/task-update.png)](./media/task-update.png)

Om redigeringar av uppgifter ska tillämpas på alla associerade checklisteuppgifter, måste det redan finnas en relation mellan uppgiften i uppgiftsbiblioteket och uppgiften på checklistan. Ett alternativ lades till för att skapa relationen mellan biblioteksuppgiften och checklistauppgiften.

Du kan skapa uppgifter individuellt och sedan återanvända dem i flera checklistor. Du skapar en uppgift på sidan **Inställning av registrering** på fliken **Uppgifter** välj **Ny**.

## <a name="set-up-tasks"></a>Ställa in uppgifter

Du kan tilldela en skapad uppgift till flera checklistor genom att välja uppgiften och sedan **använda som checklistor** på menyn.

Du kan också lägga till uppgifter direkt i en checklista. Om du vill lägga till en uppgift i en checklista, på sidan **Inställning av registrering** på fliken **Checklista**, antingen skapa en ny checklista för att lägga till uppgiften eller lägg till uppgiften i en befintlig checklista.

Om du vill redigera en uppgift i biblioteket väljer du **Redigera** på uppgiftsbiblioteksmenyn. Om uppgiften är kopplad till någon checklista, visas dessa checklistor på sidan **Redigera uppgift**. Om du vill att uppgifterna i checklistorna ska uppdateras med redigeringarna markerar du de uppgifterna i avsnittet **Använd checklistor**.

Om du vill ta bort uppgifter från biblioteket väljer du **Ta bort**. Om en uppgift är kopplad till en checklista tas uppgiften inte bort från checklistan. En separat åtgärd krävs för att ta bort en uppgift från en checklista.

### <a name="set-up-checklists"></a>Ställa in checklistor

En checklista är en grupp med uppgifter. Du kan skapa så många checklistor som du behöver och du kan tilldela samma uppgifter till flera checklistor. När du skapar en checklista anger du en ägare och en kalender.

Om du vill skapa en ny uppgift i en checklista väljer du **Ny** i menyraden Uppgifter. När du skapar en ny uppgift kan du välja att lägga till uppgift i uppgiftsbiblioteket så att den kan delas mellan flera checklistor. För att lägga till uppgiften i uppgiftsbiblioteket måste du ställa in **Använd uppgift till bibliotek** är inställt på **Ja**. Om du lägger till uppgiften i uppgiftsbiblioteket kan du också lägga till den i andra checklistor samtidigt genom att välja checklistorna i avsnittet **Tillämpa på checklistor**. Om du inte lägger till uppgiften i biblioteket finns den bara i checklistan som du skapade den i.

Om du vill redigera en uppgift i en checklista väljer du **Redigera** på uppgiftsmenyn. Om uppgiften är kopplad till någon checklista, visas dessa checklistor på sidan **Redigera uppgift**. Om du vill att uppgifterna i checklistorna ska uppdateras med redigeringarna markerar du de uppgifterna i avsnittet **Använd checklistor**.

Om du vill ta bort uppgifter från checklistan väljer du **Ta bort**. Denna åtgärd tar bara bort uppgifter från checklistan. Det kommer dock inte att ta bort uppgifterna från uppgiftsbiblioteket. För att ta bort uppgifter från uppgiftsbiblioteket, öppna **Uppgiftsbibliotek** och väljer **Ta bort**.
