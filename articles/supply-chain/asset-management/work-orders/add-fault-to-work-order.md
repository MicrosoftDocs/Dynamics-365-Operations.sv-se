---
title: Lägg till fel i arbetsorder
description: I det här avsnittet beskrivs hur du lägger till felregistreringar i arbetsorder i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1090d95d381a047e77bca3e18ef7b99151ea3d5f941f2d6c9e4877a339f1385e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761078"
---
# <a name="add-fault-to-work-order"></a>Lägg till fel i arbetsorder

[!include [banner](../../includes/banner.md)]



Du kan lägga till fel som ställts in i feldesignern till en arbetsorder. Den tillgång som väljs i arbetsordern måste innehålla tillgångstyper som har en eller flera felposter kopplade till sig. Mer information om hur du ställer in finns i [Felhantering](../setup-for-work-orders/fault-management.md).

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj den arbetsorder som du gör felregistreringen för och sedan i åtgärdsfönstret, på fliken **Arbetsorder** i gruppen **Tillgång**, välj **Tillgångsfel**.

3. På snabbfliken **Symptom** klickar du på **Lägg till rad**. Ett sekventiellt felnummer infogas automatiskt i fältet **Fel**.

4. I fältet **Felsymptom**, välj relevant symptom.

5. I fälten **Felområde** och **Feltyp** välj lämpliga värden.

6. Fältet **Feldatum** ställs automatiskt in på aktuellt datum. Du kan välja ett annat datum efter behov.

7. På snabbfliken **Orsaker till valda symptom** lägger du till en rad som beskriver orsaken till problemet.

8. På snabbfliken **Åtgärder för valda symptom** lägger du till en rad som beskriver möjliga lösningar på problemet.

9. Välj **Spara**.

Bilden nedan visar ett exempel på en felregistrering.

![Figur 1.](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Visa tillgångsfel

I listan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar.

På listsidan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel** för att öppna listan.


## <a name="print-asset-fault-report"></a>Skriv ut rapport om tillgångsfel

Från listsidan **Alla tillgångar** kan du skriva ut en rapport över tillgångsfel som visar alla felregistreringar samt en grafisk översikt över felstatistik.

1. Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.

2. Välj alla tillgångar för att skriva ut en felrapport för.

3. I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Rapporter**, klicka på **Tillgångsfel**.

4. Ange en viss period eller välj en feltyp.

5. Klicka på **OK** om du vill skriva ut rapporten.

>[!NOTE]
>Du kan skriva ut en felrapport för flera tillgångar eller tillgångstyper genom att klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsfel**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]