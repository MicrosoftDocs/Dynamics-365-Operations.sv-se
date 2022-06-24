---
title: Planera arbetsorder på specifikt datum och tid
description: I denna artikel beskrivs hur du planerar en arbetsorder på ett visst datum och tid i Tillgångshantering.
author: johanhoffmann
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ec7e300f60f76aaa467238d7a2c2a199fdeafeed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857936"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Planera arbetsorder på specifikt datum och tid

[!include [banner](../../includes/banner.md)]

 

Om en arbetsorder måste tidsplaneras på ett visst datum *och* en viss tid, kan du åsidosätta standardtidsplaneringsprocessen i Tillgångshantering och skapa ett specifikt schema för en arbetsorder.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Klicka på arbets orderns ID i kolumnen **Arbetsorder** i listan med arbetsorder.

3. Klicka på **Redigera**.

4. På snabbfliken **Arbetsorderhuvud** infogar du start-och slutdatum och -tider i fälten **Förväntad start** och **Förväntat slut**.

    ![Figur 1.](media/05-work-order-scheduling.png)

5. På fliken **Allmänt**, klicka på **Schema** om du vill använda standardplaneringsprocessen, eller klicka på **Skicka ut** om du vill tilldela arbetsordern till en särskild arbetare.

6. Om du vill åsidosätta befintliga kapacitetsreservationer för att se till att arbetsordern planeras i förväntad period, gör du valen enligt bilden nedan i dialogrutan **Schemalägg arbetsorder** > avsnittet **Begränsad kapacitet**. Detta innebär att planeringsprocessen ignorerar befintliga kapacitetsreservationer eftersom arbetsordern måste starta på den förväntade starttiden.

    ![Figur 2.](media/06-work-order-scheduling.png)

7. Klicka på **OK** för att starta planeringen.

8. Om tidsplaneringsprocessen leder till dubbel bokföring visas ett meddelande på skärmen och du kan justera relaterade arbetsorder.

>[!NOTE]
>För att kunna tidsplanera en underhållsarbetare för arbetsordern måste underhållsarbetare vara tillgängliga på det förväntade startdatumet och starttiden. Arbetarens tillgänglighet ställs in i [arbetarkalendern](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]