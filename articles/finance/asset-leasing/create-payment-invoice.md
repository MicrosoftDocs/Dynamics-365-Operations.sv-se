---
title: Skapa betalningsfakturor
description: Det här avsnittet innehåller information om hur du skapar månatliga leasingfakturor. Du kan skapa fakturor för enskilda leasingar eller använda en batchprocess för att skapa dem för flera leasingar.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 94657a1c423fafb89d2fe2c16937947e0d898771ddb30a029d0938cc17aaf7d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716679"
---
# <a name="create-payment-invoices"></a>Skapa betalningsfakturor

[!include [banner](../includes/banner.md)]

Du kan skapa månatliga fakturor för enskilda leasingar eller använda en batchprocess för att skapa dem för flera leasingar. Följande procedur visar hur du skapar en enskild leasingbetalningspost när parametern **Betala till leverantör** på sidan **Konfiguration av leasingbok** aktiveras.

1. På sidan **Sammanfattning av leasing** väljer du en leasing och väljer sedan **Böcker \> Betalningsplan**.
2. Välj den betalning som måste göras och välj sedan **Skapa journal**. Ett meddelande visas om att en journal har skapats mot den valda betalningen.
3. Välj **Fakturajournaler** och välj sedan den faktura som måste betalas.
4. På fliken **Rader** granskar du journalposten innan du bokför den i redovisningen.

    > [!NOTE]
    > Som standard använder leverantörsfakturaraderna som skapas bokföringsprofilen från sidan **Parametrar för leverantörsreskontra**.

5. Välj rätt journal och välj sedan den faktura som måste betalas.

    I det här exemplet aktiveras parametern **Betala till leverantör** i leasingboken. Därför kommer fakturan att finnas i fakturajournalen. I avsnittet **Översikt** visas en sammanfattning av journalposten och i avsnittet **Rader** visas information om de faktiska journalraderna.

    > [!NOTE]
    > Om parametern **Betala till leverantör** är inaktiverad kommer betalningsjournalposter att visas på sidan **Leasing av tillgångar** för leasingboken, och systemet skapar en post för leasingtillgångar i stället för en faktura. Leasingbetalningsposten kommer att bokföras till det journalnamn som anges i fältet **Månatlig leasingjournal**.

6. När transaktionen har bokförts kan du visa transaktionsinformation och det bokförda värdet för leasingskulden genom att välja **Skuldtransaktioner** i leasingboken.

    I betalningsplanen markeras kryssrutan **Journal bokförd** och raden visar fakturajournalnumret. När en betalningsjournal och en post för journalen har skapats, måste du återföra posten innan den kan skapas på nytt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
