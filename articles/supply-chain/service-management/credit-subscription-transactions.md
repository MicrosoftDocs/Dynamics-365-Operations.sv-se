---
title: Kreditera abonnemangstransaktioner
description: Det här avsnittet beskriver hur du krediterar abonnemangstransaktioner.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 898dd8f689a89430c4f307a414fe865a4a15a995
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675752"
---
# <a name="credit-subscription-transactions"></a>Kreditera abonnemangstransaktioner 

[!include [banner](../includes/banner.md)]


## <a name="credit-subscription-transactions"></a>Kreditera abonnemangstransaktioner

1.  Klicka på **Servicehantering** \> **Vanligt** \> **Serviceabonnemang** \> **Alla serviceabonnemang**.

2.  Välj det abonnemang som är kopplat till abonnemangstransaktionen som du vill skapa en kreditfaktura för.

3.  Välj fliken **Analys** och klicka sedan på knappen **Avgiftstransaktioner** på åtgärdsfönstret.

4.  Från formuläret **Avgiftstrasnsaktioner**, välj det abonnemang som är kopplat till abonnemangstransaktionen som du vill skapa en kreditfaktura för.

5.  Klicka på **Funnktioner** \> **Välj för kreditfaktura**.

6.  Från formuläret **Välj för kreditfaktura** markerar du den transaktion du vill kreditera och klicka sedan på **OK**.


> [!NOTE]
> <P>När du skapar kreditfakturan, se till att du väljer <STRONG>kreditfakturor</STRONG>. Den finns i listan <STRONG>faktureringsmetod</STRONG> i dialogrutan <STRONG>Skapa faktura</STRONG>.</P>

Om fältet **Återför periodisering vid kreditering** i formuläret **Servicehanteringsparametrar** anges till **Manuell** måste du återföra alla transaktioner med upplupna intäkter var för sig innan du skapar ett kreditfakturaförslag för transaktionen.

## <a name="see-also"></a>Se även

[Fakturera abonnemangstransaktioner](invoice-subscription-transactions.md)


 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]