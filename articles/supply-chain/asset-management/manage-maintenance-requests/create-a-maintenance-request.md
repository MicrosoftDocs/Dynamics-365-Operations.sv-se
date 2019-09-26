---
title: Skapa underhållsbegäranden
description: I det här avsnittet beskrivs hur du skapar en underhållsbegäran i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 03e090633276cd264ad03f561ddb425a9816357e
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847515"
---
# <a name="create-maintenance-requests"></a>Skapa underhållsbegäranden

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Underhållsbegäran kan användas om underhållsarbetare eller produktionsarbetare upptäcker att utrustning behöver repareras, men reparationsjobbet inte kan utföras direkt.

**Exempel:** när en underhållsarbetare gör en reparation, upptäcker hon att en annan tillgång på samma plats måste servas. Underhållsarbetaren har dock inte tid eller nödvändiga reservdelar för att utföra reparationsjobbet. Därför skapar hon en underhållsbegäran på tillgången och anger en kort beskrivning av problemet.

Avsnittet **aktiva underhållsbegäran** i rutan **relaterad information** till höger på sidan **alla tillgångar** eller **aktiva tillgångar** (**tillgångshantering** \> **allmänt** \> **tillgångar** \> **alla tillgångar** eller **aktiva tillgångar**) visar aktiva underhållsbegäran som är kopplade till den valda tillgången.

1. Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **alla underhållbegäran** eller **aktiva underhållbegäran**.
2. Välj **Ny**.
3. I dialogrutan **Skapa begäran** i fältet **underhållsbegärantyp** väljer du typ av underhållsbegäran. En standardtyp föreslås.
4. I fältet **beskrivning** anger du ett namn eller en rubrik som kortfattat beskriver underhållsbegäran.
5. I fälten **funktionsplats** och **tillgång** väljer du en funktionsplats eller en tillgång, eller en kombination av en funktionsplats och en tillgång, som du behöver. Du kan skapa en underhållsbegäran utan att välja en tillgång och tillgången kan läggas till underhållbegäran senare. Om underhållsarbetaren som är inloggad på Microsoft Dynamics 365 for Finance and Operations är relaterad till en resurs som är relaterad till en tillgång, ställs fältet **tillgång** in automatiskt.

    Om en underhållsbegäran redan är kopplad till den valda tillgången, visas ett meddelandefält överst i dialogrutan **skapa begäran** för att meddela dig om ID för den befintliga underhållsbegäran. Ett meddelandefält meddelar dig också om tillgången täcks av ett garantiavtal.

6. I fältet **Servicenivå** väljer du en servicenivå som anger begärans brådskande.
7. Om du har valt en tillgång i steg 5 kan du använda fälten **felsymptom**, **felområde** och **feltyp** för att skapa en felregistrering.
8. Om underhållsbegäran har orsakat underhållsstopp, ange startdatum och tid för driftstopp.

    Fältet **Startad av** anges automatiskt till ditt namn.

10. Fältet **Faktisk start** är automatiskt inställt på aktuellt datum och aktuell tid. Du kan dock ändra värdet som du vill.
11. I fältet **noteringar** anger du eventuella ytterligare noteringar som krävs.
12. Välj **OK**.

![Figur 1](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Efterföljande behandling av underhållsbegäran

När en underhållsbegäran har skapats, men innan den konverteras till en arbetsorder, bör olika information uppdateras på den. Vanligtvis slutför en planerare eller en annan administrativ medarbetare den här uppgiften.

- På sidan **alla underhållsbegäran** eller **aktiva underhållsbegäran** väljer du den begäran att arbeta med och väljer sedan **redigera**.

I informationsvyn kan du uppdatera olika information. Nedan följer några exempel:

- Välj och verifiera tillgången. Om du måste välja en annan tillgång senare, kan du ange alternativet **tillgång verifierad** till **nej**.
- Välj en ansvarig underhållsarbetsgrupp och/eller en ansvarig underhållsarbetare. Mer information om de nödvändiga inställningarna finns i [ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).
- Välj en typ av underhållsjobb och, om denna information är relevant, en relaterad underhållsjobbvariant och en jobbhandel.
- Ange geografiska koordinater i fälten **latitud** och **longitud**. Alla koordinater som läggs till i en underhållsbegäran överförs automatiskt till en relaterad arbetsorder. 

![Figur 2](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Om du väljer en tillgång när du skapar en underhållsbegäran kan du lägga till ett fel till tillgången. När underhållsbegäran har skapats kan du lägga till fler fel, som du behöver. Om du vill lägga till fel väljer du **tillgångsfel** på sidan **alla underhållsbegäran**.