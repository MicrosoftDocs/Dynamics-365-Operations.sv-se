---
title: Inkommande och avgående tillgångar
description: Denna artikel förklarar hur du registrerar inkommande och avgående tillgångar i Tillgångshantering.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e0c382efda81067ad4c0cd977e5cfbf37b4e3fc6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908726"
---
# <a name="inbound-and-outbound-assets"></a>Inkommande och avgående tillgångar

[!include [banner](../../includes/banner.md)]

 

Om ditt företag utför reparationsjobb eller underhållsjobb på tillgångar som tas emot från andra platser eller kunder, kan tillgångshanteraren spåra både inkommande tillgångar som är på väg till ditt företag och utgående tillgångar som returneras.

> [!NOTE]
> Om du vill använda inkommande och utgående livscykeltillstånd för att hantera tillgångar som kommer in och som returneras, måste du konfigurera livscykeltillstånd och livscykelmodeller för underhållsbegäranden för att stödja dessa åtgärder. Mer information finns i [Underhållsbegäran](/d365F-O/supply-chain/asset-management/manage-maintenance-requests/../manage-maintenance-requests/maintenance-request-overview).

Inställningen av Tillgångshantering avgör om du kan arbeta med inkommande och utgående tillgångar.

## <a name="register-assets-as-inbound"></a>Registrera tillgångar som inkommande

1. Välj **Tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.
2. Markera underhållsbegäran.
3. Välj **uppdatera underhållsbegärantillstånd**.
4. Välj **inkommande** (eller ett annat livscykeltillstånd som du har skapat för inkommande tillgångar) och välj **OK**.

![Registrera tillgångar som inkommande.](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Registrera inkommande tillgångar som inlevererade

1. Välj **Tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **inkommande tillgångar**.
2. Markera tillgången eller underhållsbegäran.
3. Ta emot **anläggningstillgångar**
4. I fältet **Inlevererad** ställer du in datum och tid. Välj sedan **OK**. Posten tas bort från listsidan **inkommande tillgångar**.

![Registrera inkommande tillgångar som inlevererade.](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Registrera tillgångar som utgående

När du har slutfört underhålls- eller reparationsjobbet kan du registrera tillgången som returnerad.

1. Välj **Tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.
2. Markera underhållsbegäran.
3. Välj **uppdatera underhållsbegärantillstånd**.
4. Välj **utgående** (eller ett annat livscykeltillstånd som du har skapat för utgående tillgångar) och välj **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Registrera utgående tillgångar som levererade

1. Välj **Tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **utgående tillgångar**.
2. Markera tillgången eller underhållsbegäran.
3. Välj **leverera tillgångar**.
4. I fältet **Levererad** ställer du in datum och tid. Välj sedan **OK**. Posten tas bort från listsidan **utgående tillgångar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]