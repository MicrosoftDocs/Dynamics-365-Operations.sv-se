---
title: Hantera policyer för köpa och sälja tjänstledighet
description: Du kan göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fe7ce7eafdec175e3395a6ac37b33cb2bb8dbda
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066685"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Hantera principer för köpa och sälja tjänstledighet


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan göra det möjligt för medarbetare att sälja tjänstledighet genom att skapa en policy för sälja tjänstledighet. Du kan konfigurera dessa principer till att använda arbetsflöden för godkännanden, ställa in högsta belopp och tariffer och ange kostnader för inköp och försäljning. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet.

1. På sidan **Parametrar för tjänstledighet** och frånvaro välj **Ja** för **Tillåt medarbetare att köpa tjänstledighet** och **Tillåt medarbetare att sälja tjänstledighet**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Skapa policy för att köpa och sälja tjänstledigt

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**. 

2. Välj **policy för att köpa och sälja tjänstledighet**.

3. Välj **Ny**.

4. Ange ett **Namn** och **Beskrivning** för policyn under **Policy för att köpa och sälja tjänstledighet**. 

5. Välj en **Policytyp**. 

   De tillgängliga policytyperna är **belopp** och **timmar per vecka**. Välj **belopp** för att ange ett **fast belopp** för de maximala belopp som medarbetarna kan köpa och sälja. Om du väljer **timmar per vecka**, används den arbetstid som definierats i medarbetarens tilldelade arbetstidskalender för att bestämma det maximala beloppet för policyn. 

6. Välj ett **startdatum** och ett **slutdatum** för policyn. Begäran om att köpa eller sälja tjänstledighet är bara tillgänglig för överföring under den här tidsperioden. 

7. Välj ett **arbetsflödes-ID** för policyn. Alla köp- och säljbegäranden kommer att använda det här arbetsflödet för granskning och godkännande. 

8. Under **köppolicy** väljer du **Heltidslön** (FTE) för att göra proportionell fördelning det högsta beloppet baserat på den heltidslön som definierats för medarbetarens befattning. Om policytypen är **belopp** anger du ett **maximalt fast belopp**. 

9. Välj **Lägg till** om du vill lägga till tjänstledighetstyperna för medarbetare att köpa tjänstledighet. Du kan lägga till flera tjänstledighetstyper till policyn. 

10. Ange **servicemånader** för den tjänstledighetstyp om du vill tillåta olika månaders service att avgöra det maximala belopp en medarbetare kan köpa. 

11. Ange det **högsta beloppet** för tjänstledighetstypen. 

12. Ange **Priset** som medarbetaren ska köpa tjänstledigheten för. 

13. Alternativt kan du ange den **Inkomstkod** som ska användas för att köpa tjänstledighet. 

14. Ange om du vill använda en motsvarande avskrivningstyp för att fastställa det högsta beloppet för tjänstledighetstypen. 

15. Skapa en försäljningspolicy genom att följa steg 8 till 14 under **försäljningspolicy**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Lägg till policyn köp och försäljning av tjänstledighet till en plan för tjänstledighet och frånvaro

1. På sidan **Tjänstledighet och frånvaro** väljer du en tjänstledighets- och frånvaroplan.

2. Under **Regler**, välj **Policy för att köpa och sälja tjänstledighet**.

## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)</br>
[Periodisera planer för tjänstledighet och frånvaro](hr-leave-and-absence-accrue.md)</br>
[Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
