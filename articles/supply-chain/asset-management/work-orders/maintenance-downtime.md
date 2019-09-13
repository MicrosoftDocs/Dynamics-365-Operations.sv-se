---
title: Underhållsstopp
description: I det här avsnittet beskrivs underhållsstopp i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918254"
---
# <a name="maintenance-downtime"></a>Underhållsstopp


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Du kan skapa registreringar av underhållsstopp för den valda tillgången på en arbetsorder. Detta är användbart om du vill registrera underhållsstopp på en eller flera maskiner i produktionsområdet. Först skapar du de orsakskoder för underhållsstopp som du vill använda, t.ex. uppdelning och planerad stopp. Detta görs i **Orsakskoder för underhållsstopp**. Sedan kan du skapa registreringar av underhållsstopp i **Underhållsstopp** och lägga till relevanta orsakskoder.

## <a name="create-maintenance-downtime-reason-codes"></a>Skapa orsakskoder för underhållsstopp

1. Klicka på **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Orsakskoder för underhållsstopp**.

2. Klicka på **Ny**.

3. Infoga ett ID i fältet **Orsakskod för underhållsstopp**.

4. Infoga ett namn för orsakskoden i fältet **Namn**.

5. Markera kryssrutan **Inkludera i KPI** om orsakskoden ska inkluderas i beräkningar av tillgångs-KPI. I allmänhet ska planerade produktionsstopp inte inkluderas i KPI-beräkningar eftersom de inte påverkar förväntad prestanda.

6. Klicka på **Spara**.

![Figur 1](media/15-work-orders.png)


När du har skapat de orsakskoder för underhållsstopp som du vill använda kan du skapa registreringar av underhållsstopp för arbetsorder och tillgångar.


## <a name="create-maintenance-downtime-registrations"></a>Skapa registreringar av underhållsstopp

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder och klicka på **Underhållsstopp**.

3. Klicka på **Ny**.

4. Infoga datum- och tidsintervall för registreringen av underhållsstopp i fälten **Från** och **Till**.

5. När du lämnar fältet **Till** infogas varaktigheten i timmar automatiskt i fältet **Varaktighet**.

6. Välj en orsakskod i fältet **Orsakskod för underhållsstopp**.

7. Upprepa steg 3-6 om du vill lägga till fler registreringar.

8. Klicka på **Spara**.


![Figur 2](media/16-work-orders.png)


Den kalender som används för att beräkna en registrering av underhållsstopp beror på ditt val i inställningarna av tillgångar och parametrar. Om en resurs väljs för en tillgång i **Alla tillgångar** >  snabbfliken **Anläggningstillgång** > fältet **Resurs**, används den kalender som har ställts in för den associerade resursgruppen, vilket visas i bilden nedan.

![Figur 3](media/17-work-orders.png)


Om ingen resurs väljs för tillgången används standardkalender som valts i fältet **Parametrar för tillgångshantering** som visas i följande bild.

![Figur 4](media/18-work-orders.png)


Klicka på **Hantering av företagstillgångar** > **Förfrågningar** > **Underhållsstopp** för att se en översikt över alla registreringar av underhållsstopp.

>[!NOTE]
>Alla kalendrar som används i modulen **Tillgångshantering** ställs in i **Organisationsadministration** > **Inställningar** > **Kalendrar** > **Kalendrar**.

