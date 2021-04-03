---
title: Ställ in orsakskoder
description: Dynamics 365 Human Resources använder orsakskoder för att förklara varför en medarbetares förmåner ändras.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c799a81f38a5dbd5996afbda9529fa83d7fe5cf9
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468405"
---
# <a name="set-up-reason-codes"></a>Ställ in orsakskoder

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources använder orsakskoder för att förklara varför en medarbetares förmåner ändras.

> [!NOTE]
> Från och med januari 2021 migrerar orsakskoderna till arbetsytan **Personalhantering** istället för till arbetsytan **Förmånshantering**. Mer information finns i [Flytta orsakskoder till Personalhantering manuellt](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Skapa orsakskoder

1. I arbetsytan **Personalhantering** (eller arbetsytan **Förmånshantering**, om dina orsakskoder ännu inte har migrerats) väljer du **Länkar** och sedan **Orsakskoder**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Orsakskod** | Ett unikt namn som identifierar orsaken till att en medarbetare ändrar en anmälan av förmånsplan. |
   | **Beskrivning** | En beskrivning av orsakskoden. |

4. Under **Tillämpliga scenarier** anger du **Förmånshantering** som **Ja**. (Ej tillämpligt om orsakskoderna ännu inte migrerat till arbetsytan **Personalhantering**)

5. Välj **Spara**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Flytta orsakskoder till Personalhantering manuellt

I januari 2021 migrerar orsakskoderna till arbetsytan **Personalhantering** istället för till arbetsytan **Förmånshantering**. De flesta orsakskoddata migrerar automatiskt i din miljö. Vissa orsakskoddata kanske inte migrerar. Exempelvis har orsakskoder nu högst 15 tecken, varför orsakskoder som är längre än 15 tecken inte migrerar automatiskt.

Du kommer att se en banner på sidan **Länkar** i arbetsytan **Förmånshantering** som informerar dig om migreringen och om någon orsakskod inte migrerar.

1. Välj **Orsakskoder** om du vill ha mer information om migreringsstatus.

   [![Orsakskoder](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Välj en orsakskod som inte migrerade.

   [![Status för orsakskodsmigrering](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Välj **Orsakskod för migrering**.

   [![Migrera orsakskod](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. I fönstret **Migrering av orsakskod för förmån** har du två alternativ för att mappa till en orsakskod för personalhantering:

   - Om du vill använda en befintlig orsakskod i Personalhantering kan du välja en från listrutan **Använd befintlig orsakskod**.
     > [!NOTE]
     > Du kan bara använda en befintlig orsakskod i Personalhantering om en annan orsakskod för förmånshantering inte redan har migrerats till den.
   - Om du vill skapa en ny orsakskod i Personalhantering anger du en ny i **Ny orsakskod** innan du anger en beskrivning i **Ny beskrivning**.

   [![Mappa till en orsakskod för personalhantering](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

När orsakskoderna migrerar till Personalhantering ställs alternativet för användning av dem i Förmånshantering automatiskt in som **Ja**.

[![Använd orsakskoder i Förmånshantering](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]