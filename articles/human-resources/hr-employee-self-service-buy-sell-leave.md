---
title: Köpa och sälja tjänstledighet
description: I det här ämnet beskrivs hur du skickar begäranden om att köpa och sälja ledighet i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6d38a69a73ce14f099beb6b6b560bf6c5686b0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875725"
---
# <a name="buy-and-sell-leave"></a>Köpa och sälja tjänstledighet


>[!Important]
>Funktionen som anges i den här artikeln är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.

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

Om ett arbetsflöde för begäran om köp eller försäljning misslyckas misslyckas användare med **EssLeaveBuySellRequestApprover** privilegium kan granska meddelandeloggen för alla begäran om köp och försäljning. För att göra detta, gå till **Ledighet och frånvaro > Länkar > Köpa och sälja ledighetsansökningar > Meddelandelogg** (högst upp till vänster). I **meddelandeloggen** visas hur transaktionerna bearbetas och vilken arbetsflödeshistorik som har associerats.


## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Hantera policyer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
