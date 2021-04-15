---
title: Tillgångslån
description: Det här avsnittet beskriver hur du registrerar lånetillgångar i tillgångshantering.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 712f3e7cdfb8d521ae2afb59d90bc5102da53cb7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813397"
---
# <a name="asset-loans"></a>Tillgångslån

[!include [banner](../../includes/banner.md)]

 

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

![Hantera underhållsbegäranden](media/06-manage-maintenance-requests.png)

På sidan **aktiva tillgångslån** kan du visa en lista över alla lånetillgångar som ännu inte har returnerats till ditt företag.

## <a name="register-loan-assets-as-returned"></a>Registrera lånetillgångar som returnerade

1. Välj **tillgångshantering** \> **allmänt** \> **tillgångslån** \> **aktiva tillgångslån**
2. Välj tillgångslånet som ska registreras som returnerat och välj **returnera tillgångslån**.
3. I fältet **Returnerad** ställer du in datum och tid.
4. Välj **OK**.
5. Uppdatera listsidan **aktiva tillgångslån** och observera att tillgångslånet inte längre visas i listan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]