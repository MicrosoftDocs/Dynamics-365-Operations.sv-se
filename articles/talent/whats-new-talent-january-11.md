---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (11 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 38be1da69d8443fd76a81f439f000602ddb75bab
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010393"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-january-11-2019"></a>Nyheter och ändringar i Dynamics 365 Talent: Core HR (11 januari 2019)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2100**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="changes"></a>Ändringar

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Validera ledighetsansökningar genom prognoser tillgängligt saldo
Ändringar i den här versionen tillåter medarbetare att begära framtida ledighet utan att man subtraherar från deras aktuella saldo. Standardarbetsflöden används för alla framtida begäran. Mer information finns i [periodisering av timmar baserat på arbetstid](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Visa prognostiserat ledighetssaldo i ESS och Användare
Den här funktionen låter dig visa saldon för framtida ledighetsperioder av personal, chefer och medarbetare. Medarbetare kan visa framtida saldon i arbetsytan **Självbetjäning för medarbetare** och personal har tillgång till samma information med arbetsytan **Användare**.

### <a name="notifications-for-changing-leave-balances"></a>Meddelanden för att ändra ledighetssaldon
Ledighetssaldon visar det aktuella saldot för medarbetare. Det finns framtida saldon på arbetsytorna **Självbetjäning för medarbetare** och **Användare** genom att ange ”från och med datum” för att beräkna prognostiserade saldot.

Navigering har lagts till för att visa förväntade saldon i följande områden:
  - Kortet **Ledighet** på arbetsytan **Självbetjäning för medarbetare**.
  - Kortet **Ledighet och frånvaro** på arbetsytan **Självbetjäning för chef**.
  - Sidan **Ledighet och frånvaro** på arbetsytan **Användare**.

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Tillåt decimaler för variabla kompensationsplaner (kontantplaner)
Variabel kontant ersättning och planer har nu ytterligare flexibilitet för belopp och åsidosätter värden med decimala belopp.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Det går inte att ändra datumen på registreringar av variabel kompensation när planen har sparats
Denna ändring gör att slutdatumet för planen uppdateras (utökad eller utgången) när planen har sparats. Du kan fortfarande aktivera eller inaktivera planer oberoende av start- och slutdatumen.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Löneinformation som är tillgänglig när säkerhetsrollen Löneadministratör tilldelats
Löneadministratörsrollen har uppdaterats för att komma åt löneinformation under förfråganprocessen.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Självservice för anställda | nedrullningsmenyn för befattningshierarkin från panel misslyckas med att hämta överordnad nod
Ändringar har gjorts för att ta bort ett fel som uppstod när du lägger till befattningshierarkin till nya arbetsytor och navigerar i organisationsstrukturen.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nytt verifieringsmeddelande när personalnummerserien används
En ändring har gjorts för att klargöra vad problemet är när du anställer en medarbetare och nästa personalnumret används.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Arbetsytan för medarbetarens självbetjäning har valts som den ursprungliga startsidan
När arbetsytan **medarbetarens självbetjäning** är markerad som den ursprungliga startsidan för en användare, och användaren inte är tilldelad medarbetarrollen kan systemet dirigeras till standardinstrumentpanel.

### <a name="termination-reason-code-updates-position-assignment-record"></a>Orsakskod till uppsägningen uppdaterar befattningstilldelningsposten
Orsakskoden till uppsägning uppdaterar nu befattningstilldelningen när du säger upp en medarbetare och avslutar befattningen. 
