---
title: Skicka arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skickar arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 3b1621cf0f1e47d7bd5fe2fa0b41fbcd61f14def
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887215"
---
# <a name="dispatch-work-order"></a>Skicka arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Du kan schemalägga en arbetsorder eller arbetsorderjobb till en arbetare med funktionen **Skicka ut**.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsordern i listan.

3. Klicka på **Skicka ut** på fliken **Allmänt**.

4. I dialogrutan **Schemalägg arbetsorder** väljer du arbetaren i fältet **Arbetare**.

5. I fältet **Schemalägg timmar** kan du infoga förväntade arbetstimmar i fall förväntade arbetstimmar skiljer sig från prognostimmar.

6. I fältet **Schemalagd start** kan du ändra startdatum och starttid om det behövs.

7. Om tidsplaneringsprocessen ska ta hänsyn till kapacitetsbegränsningar för resurser som redan har schemalagts för andra jobb, kontrollera att växlingsknapparna **Tillgång**, **Verktyg** och **Arbetare** är inställda på "Ja". Om du vill visa detaljerad information om tidsplaneringsprocessen väljer du "Ja"på växlingsknappen **Utförligt**. Det innebär att detaljerad information om de beräknade poängen på arbetsordern visas i informationsloggen.

8. Välj "Ja" på växlingsknappen **Ignorera schema** om du vill ignorera stängda dagar i kalendern (gäller för till gång, arbetare och verktyg). Välj "Ja" på växlingsknappen **Ignorera schemalagt utförande** om du vill ignorera begränsningar som kan ha valts på arbetsordern om planeringen. Information om hur ställer in schemalagt utförande finns i avsnittet [Schemalagt utförande](../setup-for-work-orders/scheduled-execution.md).

9. Klicka på **OK**. Livscykeltillståndet för arbetsordern uppdateras automatiskt till tillståndet "Schemalagt"som anges i **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Livscykelmodeller**.

I bilden nedan visas ett exempel på val för skicka ut i dialogrutan **Schemalägg arbetsorder**.

![Figur 1](media/04-work-order-scheduling.png)

>[!NOTE]
>Om du vill ta bort schemat för en arbetsorder gör du det genom att välja arbetsordern i **Alla arbets order** och klicka på **Ta bort schema** på fliken **Allmänt**. Kom ihåg att uppdatera arbetsorderns livscykeltillstånd manuellt om du tar bort schemat.

