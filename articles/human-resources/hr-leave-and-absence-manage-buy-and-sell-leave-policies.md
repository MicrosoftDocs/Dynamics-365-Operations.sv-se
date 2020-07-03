---
title: Hantera policyer för köpa och sälja tjänstledighet
description: Du kan göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429023"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Hantera policyer för köpa och sälja tjänstledighet

[!include [banner](includes/preview-feature.md)]

Du kan göra det möjligt för medarbetare att köpa tjänstledighet genom att skapa en policy för köpa tjänstledighet.  

## <a name="enable-employees-to-buy-and-sell-leave"></a>Göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet.

1. På sidan **Parametrar för tjänstledighet och frånvaro** välj **Ja** för **Tillåt medarbetare att köpa tjänstledighet**. 

## <a name="create-a-buy-leave-policy"></a>Skapa en policy för att köpa tjänstledighet

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**. 

2. Välj **policy för att köpa och sälja tjänstledighet**.

3. Välj **Ny**.

4. Ange ett **Namn** och **Beskrivning** för policyn under **Policy för att köpa och sälja tjänstledighet**. 

5. Välj en **Policytyp**. 

   De tillgängliga policytyperna är **belopp** och **timmar per vecka**. Välj **belopp** för att ange ett **fast belopp** för de maximala belopp som medarbetarna kan köpa och sälja. Om du väljer **timmar per vecka**, används den arbetstid som definierats i medarbetarens tilldelade arbetstidskalender för att bestämma det maximala beloppet för policyn. 

6. Välj ett **startdatum** och ett **slutdatum** för policyn. Begäran om att köpa eller sälja tjänstledighet är bara tillgänglig för överföring under den här tidsperioden. 

7. Under **köppolicy** väljer du **Heltidslön** (FTE) för att göra proportionell fördelning det högsta beloppet baserat på den heltidslön som definierats för medarbetarens befattning. Om policytypen är **belopp** anger du ett **maximalt fast belopp**. 

8. Välj **Lägg till** om du vill lägga till tjänstledighetstyperna för medarbetare att köpa tjänstledighet. Du kan lägga till flera tjänstledighetstyper till policyn. 

9. Ange **servicemånader** för den tjänstledighetstyp om du vill tillåta olika månaders service att avgöra det maximala belopp en medarbetare kan köpa. 

10. Ange det **högsta beloppet** för tjänstledighetstypen. 

11. Ange **Priset** som medarbetaren ska köpa tjänstledigheten för. 

12. Alternativt kan du ange den **Inkomstkod** som ska användas för att köpa tjänstledighet. 

13. Ange om du vill använda en motsvarande avskrivningstyp för att fastställa det högsta beloppet för tjänstledighetstypen. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Lägg till policyn köp och försäljning av tjänstledighet till en plan för tjänstledighet och frånvaro

1. På sidan **Tjänstledighet och frånvaro** väljer du en tjänstledighets- och frånvaroplan.

2. Under **Regler**, välj **Policy för att köpa och sälja tjänstledighet**.

## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)</br>
[Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)</br>
[Periodisera planer för tjänstledighet och frånvaro](hr-leave-and-absence-accrue.md)</br>
[Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)

