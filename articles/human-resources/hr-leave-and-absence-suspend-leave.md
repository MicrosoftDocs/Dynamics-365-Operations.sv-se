---
title: Skjut upp tjänstledighet
description: Du kan skjuta upp tjänstledighet för en medarbetare i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7cda14f35969b8a29ddc47d0c19990d9cc3eeb74
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693792"
---
# <a name="suspend-leave"></a>Skjut upp tjänstledighet

>[!Important]
>Funktionen som anges i det här avsnittet är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan skjuta upp tjänstledigheten för att en medarbetare ska stoppa periodiseringar av tjänstledighet från att bearbetas för valda tjänstledighetstyper. 

## <a name="suspend-leave-and-absence-for-an-employee"></a>Skjut upp tjänstledighet och frånvaro för en medarbetare

1. Välj **tjänstledighet** för medarbetarens post.

2. Välj **Skjut upp tjänstledighet**.

3. Välj **Ny**.

4. I dialogrutan **Skjut upp periodisering av tjänstledighet** välj **tjänstledighetstyp** tillsammans med **startdatum** och **slutdatum** för uppskjutningen.

5. Om du vill kan du lägga till en **kommentar** för SUS-uppskjutningen. 

Om periodiseringen bearbetas medan medarbetarens tjänstledighet är uppskjuten, görs ingen periodisering för de uppskjutna tjänstledighetstyperna.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)
- [Periodisera planer för tjänstledighet och frånvaro](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
