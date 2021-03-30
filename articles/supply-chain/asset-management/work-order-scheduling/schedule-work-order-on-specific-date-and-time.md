---
title: Planera arbetsorder på specifikt datum och tid
description: I det här avsnittet beskrivs hur du planerar en arbetsorder på ett visst datum och tid i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 921e78f2fc7e6254aa27ce70cdbbf0516aad7e11
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214996"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Planera arbetsorder på specifikt datum och tid

[!include [banner](../../includes/banner.md)]

 

Om en arbetsorder måste tidsplaneras på ett visst datum *och* en viss tid, kan du åsidosätta standardtidsplaneringsprocessen i Tillgångshantering och skapa ett specifikt schema för en arbetsorder.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Klicka på arbets orderns ID i kolumnen **Arbetsorder** i listan med arbetsorder.

3. Klicka på **Redigera**.

4. På snabbfliken **Arbetsorderhuvud** infogar du start-och slutdatum och -tider i fälten **Förväntad start** och **Förväntat slut**.

    ![Figur 1](media/05-work-order-scheduling.png)

5. På fliken **Allmänt**, klicka på **Schema** om du vill använda standardplaneringsprocessen, eller klicka på **Skicka ut** om du vill tilldela arbetsordern till en särskild arbetare.

6. Om du vill åsidosätta befintliga kapacitetsreservationer för att se till att arbetsordern planeras i förväntad period, gör du valen enligt bilden nedan i dialogrutan **Schemalägg arbetsorder** > avsnittet **Begränsad kapacitet**. Detta innebär att planeringsprocessen ignorerar befintliga kapacitetsreservationer eftersom arbetsordern måste starta på den förväntade starttiden.

    ![Figur 2](media/06-work-order-scheduling.png)

7. Klicka på **OK** för att starta planeringen.

8. Om tidsplaneringsprocessen leder till dubbel bokföring visas ett meddelande på skärmen och du kan justera relaterade arbetsorder.

>[!NOTE]
>För att kunna tidsplanera en underhållsarbetare för arbetsordern måste underhållsarbetare vara tillgängliga på det förväntade startdatumet och starttiden. Arbetarens tillgänglighet ställs in i [arbetarkalendern](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]