---
title: Hantera tjänstledighet för medarbetare
description: Hantera tjänstledighet för medarbetare i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d168fe3baac314455b2fefc231ab455a0b85c0e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695828"
---
# <a name="manage-employee-leave"></a>Hantera tjänstledighet för medarbetare

>[!Important]
>Funktionen som anges i det här avsnittet är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan hantera en medarbetares tjänstledighet efter ledighetstyp. Det inkluderar utgångna tjänstledighetsregistreringar och justering av ledighetstypsaldon. 

## <a name="adjust-leave-balances"></a>Justera tjänstledighetssaldon

1. Välj **tjänstledighet** för medarbetarens post.

2. Välj **Inställning för tjänstledighet och frånvaro**.

3. Välj **Justera saldo**.

4. Välj **Tjänstledighetstyp**.

5. Ange **Justeringsbelopp**. 

6. Du kan även välja ett **Datum**. 

Du kan inkludera en orsakskod och en kommentar när du justerar en medarbetares tjänstledighetssaldo. 

När du nu hovrar över ett tjänstledighetssaldo visas följande information:

- **Tillgänglig** – Värdet **Totalt i år** minus värdet **Uttaget detta år**.
- **Total i år** – alla periodiseringar, justeringar och överföringar för året.
- **Taget i år** – alla godkända ledigheter.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Hantera begäranden om ledighet och frånvaro](hr-employee-self-service-manage-requests.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
