---
title: Skapa arbetsorder från underhållsbegäran
description: I denna artikel beskrivs hur du skapar en arbetsorder från en underhållsbegäran i Tillgångshantering.
author: johanhoffmann
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb54ec3466086afbd87a023a40e346a6a3464c98
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017186"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Skapa arbetsorder från underhållsbegäran

[!include [banner](../../includes/banner.md)]

 


När du har skapat underhållsbegäran kan du enkelt konvertera dem till arbetsorder. I denna artikel beskrivs det snabbaste sättet att arbeta med underhållsbegäran, uppdatera flera underhållsbegäran samtidigt och sedan skapa en arbetsorder för flera underhållsbegäran samtidigt. På sidan **aktiva underhållsbegäran** eller **underhållsbegäran för min funktionella plats** kan du också arbeta med en underhållsbegäran i taget och konvertera en underhållsbegäran till en arbetsorder.

> [!NOTE]
> Varje underhållsbegäran kan endast relateras till en arbetsorder. Flera underhållsbegäran kan dock inkluderas i en arbetsorder, även om underhållsbegäran har olika tillgångar.

1. Välj **Tillgångshantering** \> **underhållbegäran** \> **alla underhållbegäran**.
2. Innan du kan skapa en arbetsorder från underhållbegäran måste du minst välja en underhållsjobbtyp för underhållbegäran och även en underhålljobbtypvariant och handel, om den här informationen är relevant. I rutnätsvyn kan du enkelt uppdatera information för en underhållsbegäran.
3. När du är redo att skapa en arbetsorder väljer du de underhållbegäran som ska inkluderas i den.

    - Om du väljer flera underhållbegäran för att konvertera till en arbetsorder måstebåde fältet **tillgång** och fältet **underhållsjobbtyp** anges innan du skapar arbetsordern.
    - Om du väljer en underhållsbegäran för att konvertera till en arbetsorder måste endast fältet **tillgång** anges innan du skapar arbetsordern. När du skapar arbetsordern kan du dock välja en typ av underhållsjobb (och en relaterad typ av underhållsjobbtypvariant och handel, om den här informationen är relevant) i dialogrutan **skapa arbetsorder**.

4. Välj **arbetsorder**.
5. I dialogrutan **skapa arbetsorder** anger du fälten och väljer sedan **OK**.

    Ett meddelandefält kan meddela dig att en ny arbetsorder har skapats.

    När du skapar en arbetsorder som baseras på en underhållbegäran, om tillgången som är relaterad till underhållbegäran ingår i ett garantiavtal, meddelar dessutom ett meddelandefält dig om garantiavtalet.

6. Välj **Tillgångshantering** \> **arbetsorder** \> **alla arbetsorder** och öppna den nya arbetsordern.

    ![Öppna ny arbetsorder.](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]