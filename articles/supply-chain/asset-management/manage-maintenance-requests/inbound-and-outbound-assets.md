---
title: Inkommande och avgående tillgångar
description: Det här avsnittet förklarar hur du registrerar inkommande och avgående tillgångar i tillgångshantering.
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
ms.openlocfilehash: bb318c24424c291f08ba7527b2258c0da4cba9a8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571678"
---
# <a name="inbound-and-outbound-assets"></a>Inkommande och avgående tillgångar

[!include [banner](../../includes/banner.md)]

 

Om ditt företag utför reparationsjobb eller underhållsjobb på tillgångar som tas emot från andra platser eller kunder, kan tillgångshanteraren spåra både inkommande tillgångar som är på väg till ditt företag och utgående tillgångar som returneras.

> [!NOTE]
> Om du vill använda inkommande och utgående livscykeltillstånd för att hantera tillgångar som kommer in och som returneras, måste du ställa in livscykeltillstånd och livscykelmodeller för underhållsbegäranden för att stödja dessa åtgärder. Mer information finns i [Inställning för underhållsbegäran](../setup-for-maintenance-requests/requests.md).

Inställningen av tillgångshantering avgör om du kan arbeta med inkommande och utgående tillgångar.

## <a name="register-assets-as-inbound"></a>Registrera tillgångar som inkommande

1. Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.
2. Markera underhållsbegäran.
3. Välj **uppdatera underhållsbegärantillstånd**.
4. Välj **inkommande** (eller ett annat livscykeltillstånd som du har skapat för inkommande tillgångar) och välj **OK**.

![Registrera tillgångar som inkommande](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Registrera inkommande tillgångar som inlevererade

1. Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **inkommande tillgångar**.
2. Markera tillgången eller underhållsbegäran.
3. Ta emot **anläggningstillgångar**
4. I fältet **Inlevererad** ställer du in datum och tid. Välj sedan **OK**. Posten tas bort från listsidan **inkommande tillgångar**.

![Registrera inkommande tillgångar som inlevererade](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Registrera tillgångar som utgående

När du har slutfört underhålls- eller reparationsjobbet kan du registrera tillgången som returnerad.

1. Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.
2. Markera underhållsbegäran.
3. Välj **uppdatera underhållsbegärantillstånd**.
4. Välj **utgående** (eller ett annat livscykeltillstånd som du har skapat för utgående tillgångar) och välj **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Registrera utgående tillgångar som levererade

1. Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **utgående tillgångar**.
2. Markera tillgången eller underhållsbegäran.
3. Välj **leverera tillgångar**.
4. I fältet **Levererad** ställer du in datum och tid. Välj sedan **OK**. Posten tas bort från listsidan **utgående tillgångar**.
