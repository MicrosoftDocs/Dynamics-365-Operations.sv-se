---
title: Konfigurera en arbetare med den mobila jobbenheten
description: I den här proceduren visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571368"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Konfigurera en arbetare med den mobila jobbenheten

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar.


## <a name="assign-roles-to-user-account"></a>Tilldela roller till användarkontot
1. Gå till Systemadministration > Användare > Användare.
2. Använd snabbfiltret för att filtrera på namnet på en arbetare där användarkontot associeras med rollen maskinoperatör. I exempeldata skulle namnet vara Shannon.
3. Markera användarkontoposten.
4. I listan, klicka på den ”Namn” länken i den valda raden för att visa information om användarkontot.
5. I trädet, välj Roller\Maskinoperatör.
6. Stäng sidan för användarkontodetaljer.
7. Stäng sidan.

## <a name="configure-worker-account"></a>Konfigurera arbetarkonto.
1. Gå till Personal > Arbetare > Arbetare.
2. Använd snabbfiltret för att filtrera på namnet på en arbetare där användarkontot associeras med rollen maskinoperatör. I exempeldata skulle namnet vara Shannon.
3. Markera användarkontoposten.
4. I listan, klicka på den ”Namn” länken i den valda raden för att visa information om användarkontot.
5. Klicka på fliken Anställning.
6. Expandera snabbfliken Tidsregistrering och klicka på Aktivera på registreringsterminaler.
7. Klicka på Aktivera på registreringsterminaler.
8. I fältet Beräkningsgrupp, ange eller välj ett värde.
9. I fältet Standardberäkningsgrupp, ange eller välj ett värde.
10. I fältet Godkännandegrupp, ange eller välj ett värde.
11. I fältet Standardprofil, ange eller välj ett värde.
12. I fältet Profilgrupp, ange eller välj ett värde.
13. Klicka på OK.
14. Klicka på Redigera för att ange ett bricknummer för den nya tidsregistreringsarbetaren.
15. I fältet ID-bricka, ange ett värde.
16. Klicka på Spara.
17. Använd genvägen SaveRecord.
18. Stäng sidan med arbetardetaljer.
19. Stäng sidan.

## <a name="assign-worker-to-device-group"></a>Tilldela arbetare till enhetsgrupp.
1. Gå till Produktionskontroll > Inställningar > Tillverkningskörning > Konfigurera jobbkort för enheter.
2. Klicka på Lägg till.
3. Markera vald rad i listan.
4. Klicka på OK.
5. Klicka på Redigera.
6. I fältet Produktionsenhet kan du ställa in standardfiltret för arbetaren. Då säkerställs att endast produktionsjobb för den valda produktionsenheten visas när arbetaren loggar in på enheten.
7. Stäng sidan.

