---
title: Tillgångslån
description: Det här avsnittet beskriver hur du registrerar lånetillgångar i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8680241b1300aceda3280893982a1eff3d2e09e0
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847492"
---
# <a name="asset-loans"></a>Tillgångslån

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Om ditt företag tar emot tillgångar för reparations- eller underhållsjobb från antingen interna platser eller kunder, och om du tillfälligt lånar tillgångar till dessa platser eller kunder, kan tillgångshantering spåra tillgångslånen.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Registrera tillgångslån på en underhållsbegäran

1. Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **alla underhållbegäran** eller **aktiva underhållbegäran**.
2. Välj underhållbegäran för att registrera ett tillgångslån på och välj sedan **redigera**.
3. På sidan **begäran** väljer du **skicka lånetillgång**.
4. Välj tillgången och ange förväntat returdatum.
5. Välj **OK**.

> [!NOTE]
> - Du kan bara skicka en lånetillgång om en tillgång av samma tillgångstyp är tillgänglig.
> - Den tillgång som du lånar måste ha en tillgångs livscykeltillstånd som gör att den kan användas som en lånetillgång, t.ex. **InStorage**. När tillgångslånet registreras uppdateras tillgångens livscykeltillstånd automatiskt till till exempel **OnLoan**.

Om du vill visa en lista över alla tillgångar som du har lånat till andra platser eller kunder väljer du **tillgångshantering** \> **allmänt** \> **tillgångslån** \> **alla tillgångslån**. Om kryssrutan **avslutad** markeras för en tillgång har tillgången registrerats som returnerad till ditt företag.

![Figur 1](media/06-manage-maintenance-requests.png)

På sidan **aktiva tillgångslån** kan du visa en lista över alla lånetillgångar som ännu inte har returnerats till ditt företag.

## <a name="register-loan-assets-as-returned"></a>Registrera lånetillgångar som returnerade

1. Välj **tillgångshantering** \> **allmänt** \> **tillgångslån** \> **aktiva tillgångslån**
2. Välj tillgångslånet som ska registreras som returnerat och välj **returnera tillgångslån**.
3. I fältet **Returnerad** ställer du in datum och tid.
4. Välj **OK**.
5. Uppdatera listsidan **aktiva tillgångslån** och observera att tillgångslånet inte längre visas i listan.
