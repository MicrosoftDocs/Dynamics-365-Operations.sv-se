---
title: Köpa och sälja tjänstledighet
description: I Dynamics 365 Human Resources kan du skicka en begäran om att köpa och sälja på grund val av principerna köp och försäljning som ställs in av ditt företag.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271505"
---
# <a name="buy-and-sell-leave"></a>Köpa och sälja tjänstledighet

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I Dynamics 365 Human Resources kan du skicka en begäran om att köpa och sälja på grund val av principerna köp och försäljning som ställs in av ditt företag.  

## <a name="request-to-buy-leave"></a>Begäran om att köpa tjänstledighet

1. I arbetsyta **Självbetjäning för medarbetare**, välj **Begäran om att köpa tjänstledighet** panelen **ledighetssaldon**. 

2. Lägg till en **Tjänstledighetstyp** och ange ett **Belopp** för den mängd tjänstledighet du vill köpa. 

3. Välj **skicka** när du är redo att skicka din begäran. 

Dina saldon kommer antingen att uppdateras automatiskt eller gå igenom en godkännande process innan du uppdaterar. Detta beror på hur inköpsprincipen har konfigurerats.

## <a name="request-to-sell-leave"></a>Begäran om att sälja tjänstledighet

1. I arbetsyta **Självbetjäning för medarbetare**, välj **Begäran om att sälja tjänstledighet** panelen **ledighetssaldon**. 

2. Lägg till en **Tjänstledighetstyp** och ange ett **Belopp** för den mängd tjänstledighet du vill sälja. 

3. Välj **skicka** när du är redo att skicka din begäran.

Dina saldon kommer antingen att uppdateras automatiskt eller gå igenom en godkännande process innan du uppdaterar. Detta beror på hur inköpsprincipen har konfigurerats.


## <a name="troubleshooting"></a>Felsökning 

Om ett arbetsflöde för begäran om köp eller försäljning misslyckas misslyckas användare med **EssLeaveBuySellRequestApprover** privilegium kan granska meddelandeloggen för alla begäran om köp och försäljning. För att göra detta, gå till **Tjänstledighet > Länk > Köpa och sälja tjänstledighetsansökningar > Meddelandelogg** (upp till vänster). I **meddelandeloggen** visas hur transaktionerna bearbetas och vilken arbetsflödeshistorik som har associerats.


## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Hantera policyer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
