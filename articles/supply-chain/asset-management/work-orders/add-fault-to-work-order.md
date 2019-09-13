---
title: Lägg till fel i arbetsorder
description: I det här avsnittet beskrivs hur du lägger till felregistreringar i arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875908"
---
# <a name="add-fault-to-work-order"></a>Lägg till fel i arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Du kan lägga till fel som ställts in i feldesignern till en arbetsorder. Den tillgång som väljs i arbetsordern måste innehålla tillgångstyper som har en eller flera felposter kopplade till sig. Mer information om inställningar finns i avsnittet [Felhantering](../setup-for-work-orders/fault-management.md).

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. I listan väljer du den arbetsorder för vilken du vill göra en felregistrering och klickar på **Tillgångsfel**.

3. På snabbfliken **Symptom** klickar du på **Lägg till rad**. Ett sekventiellt felnummer infogas automatiskt i fältet **Fel**.

4. Välj relevant symptom i fältet **Felsymptom**.

5. Välj **Felområde** och **Feltyp**.

6. Fältet **Feldatum** ställs automatiskt in på aktuellt datum. Om det behövs kan du välja ett annat datum.

7. På snabbfliken **Orsaker till valda symptom** lägger du till en rad som beskriver orsaken till problemet.

8. På snabbfliken **Åtgärder för valda symptom** lägger du till en rad som beskriver möjliga lösningar på problemet.

9. Klicka på **Spara**.

![Figur 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Visa tillgångsfel

I listan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar.

Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel** för att öppna listan.


## <a name="print-asset-fault-report"></a>Skriv ut rapport om tillgångsfel

Från listsidan **Alla tillgångar** kan du skriva ut en rapport över tillgångsfel som visar alla felregistreringar samt en grafisk översikt över felstatistik.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.

2. I listan **Tillgångar** väljer du den tillgång du vill skriva ut en felrapport för.

3. Klicka på fliken **Allmänt** > **avsnittet Rapporter**, klicka på **Tillgångsfel**.

4. Infoga en viss period eller välj en feltyp.

5. Klicka på **OK** om du vill skriva ut rapporten.

>[!NOTE]
>Du kan också skriva ut en felrapport för flera tillgångar eller tillgångstyper genom att klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsfel**.

