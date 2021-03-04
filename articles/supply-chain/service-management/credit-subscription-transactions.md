---
title: Kreditera abonnemangstransaktioner
description: Det här avsnittet beskriver hur du krediterar abonnemangstransaktioner.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4cbc3cd5deff709ac0818358dcc87fa69a7d872
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437787"
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