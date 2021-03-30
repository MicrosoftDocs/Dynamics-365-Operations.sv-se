---
title: Underhållsstopp för arbetsorder
description: Detta ämne förklarar hur du skapar registreringar av underhållsstopp för den valda tillgången på en arbetsorder.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba24ae9e82debf9a67761e4e2ca0817e1645db28
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209741"
---
# <a name="maintenance-downtime-for-work-orders"></a>Underhållsstopp för arbetsorder

[!include [banner](../../includes/banner.md)]


Du kan skapa registreringar av underhållsstopp för den valda tillgången på en arbetsorder. Denna funktion är användbar om du vill registrera underhållsstopp på en eller flera maskiner i produktionsområdet. Först skapar du de orsakskoder för underhållsstopp som du vill använda, t.ex. **uppdelning** och **planerat stopp**. Detta steg görs på sidan **Orsakskoder för underhållsstopp**. Sedan kan du skapa registreringar av underhållsstopp på sidan **Underhållsstopp** och lägga till relevanta orsakskoder för underhållsstopp.

## <a name="create-maintenance-downtime-reason-codes"></a>Skapa orsakskoder för underhållsstopp

1. Välj **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Orsakskoder för underhållsstopp**.

2. Välj **Ny**.

3. I fältet **Orsakskod för underhållsstopp** anger du ett ID för orsakskoden för underhållsstopp.

4. Ange sedan ett namn i fältet **Namn**.

5. Markera kryssrutan **KPI inkludera** om orsakskoden ska inkluderas i beräkningen av tillgångens nyckeltal (KPI:er). I allmänhet ska planerade produktionsstopp inte inkluderas i KPI-beräkningar eftersom de inte påverkar förväntad prestanda.

6. Välj **Spara**.

Bilden nedan visar ett exempel på sidan **Orsakskoder för underhållsstopp**.

![Figur 1](media/15-work-orders.png)

När du har skapat de orsakskoder för underhållsstopp som du vill använda kan du skapa registreringar av underhållsstopp för arbetsorder och tillgångar.


## <a name="create-maintenance-downtime-registrations"></a>Skapa registreringar av underhållsstopp

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj en arbetsorder och sedan på fliken **Arbetsorder**, i gruppen **Tillgång**, välj **Underhållsstopp**.

3. Välj **Ny**.

4. I fälten **Från** och **Till** definierar du datum- och tidsintervall för registreringen av underhållsstopp.

>[!NOTE]
>När du lämnar fältet **Till** infogas varaktigheten i timmar automatiskt i fältet **Varaktighet**.

5. Välj en orsakskod i fältet **Orsakskod för underhållsstopp**.

6. Upprepa steg 3 till och med 5 om du vill lägga till fler registreringar.

7. Välj **Spara**.

Bilden nedan visar ett exempel på listan Registrering för underhållsstopp.

![Figur 2](media/16-work-orders.png)

Den kalender som används för att beräkna en registrering av underhållsstopp beror på ditt val i inställningarna av tillgångar och parametrar. Om en resurs väljs för en tillgång i fältet **Resurs** på snabbfliken **Anläggningstillgång** på sidan **Alla tillgångar** används den kalender som har ställts in för den associerade resursgruppen, vilket visas i bilden nedan.

![Figur 3](media/17-work-orders.png)

Om ingen resurs väljs för tillgången används standardkalender som valts på sidan **Parametrar för tillgångshantering** som visas i följande bild.

![Figur 4](media/18-work-orders.png)

Om du vill se en översikt över alla underhållsstoppregistreringar, klicka på **Tillgångshantering** > **Förfrågningar** > **Underhållsstopp**.

>[!NOTE]
>Alla kalendrar som används i modulen **Tillgångshantering** ställs in i **Organisationsadministration** > **Inställningar** > **Kalendrar** > **Kalendrar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]