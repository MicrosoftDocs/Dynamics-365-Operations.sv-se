---
title: Tillgångslån
description: Det här avsnittet beskriver hur du registrerar lånetillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 07472188051aea7084142cc417c6d725462cf4f9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205263"
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
