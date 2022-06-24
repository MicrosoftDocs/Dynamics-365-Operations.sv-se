---
title: Nyheter och ändringar i Dynamics 365 Human Resources (23 augusti 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 23 augusti 2021.
author: marcelbf
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 91c2cd396ca26cc78c3fd4fab40a29b98a7826c3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909742"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources (23 augusti 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4419.

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
| --- | --- | --- |
| 594066 | Det gick inte att ta bort kontaktinformation | När du väljer att ta bort en kontaktinformationspost för en medarbetare tas en annan kontaktinformationspost bort än den valda posten. |
| 611339 | Om du lägger till en personanpassning ignoreras filtret och den första posten hämtas av bankkontot | Om du lägger till en personanpassning leder det till att bankkontolistan kör en personanpassningsfråga efter att datakällsfrågan har körts, vilket leder till att frågan hämtar den översta posten oavsett vilken arbetare som detaljerna visas för. |
| 591806 | Uppgifterna för registreringens förfallodatum beräknas på fel sätt | Förfallodatum beräknas på fel sätt när följande villkor föreligger: Checklistorna som skapas använder en kalender med ett utökat tidsperioder (till exempel från 2005 till 2050) och användarens inställningar använder en annan tidszon än central standardtid. |   
| 592749 | Ledighetssaldo är fel i **Självbetjäning för medarbetare** | Om medarbetaren har anställning i mer än en juridisk person och ledighetsvyn för flera företag har aktiverats, kan det hända att ledighetssaldot blir fel. |
| 603133 | Oväntat varningsmeddelande vid begäran om ledighet | En oväntat varning visas om du begär ledighet och fyller i fältet **Halvdag** innan fältet **Antal**. |
| 606546 | Välj fält som inte är synligt i Godkänd ledighet | Kryssrutan för att välja flera godkända ledighetsansökningar visas inte. |
| 597059 | Arbetare visas inte i **företagskalendern för ledighet och frånvaro** | En arbetare visas inte i **företagets kalender för ledighet och frånvaro** om det använda datumintervallet innehåller dagar för vilken han eller hon har avslagits en ledighetsförfrågan. |


## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar och inaktiverar funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegrering-API](hr-admin-integration-payroll-api-introduction.md)|
| Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | I denna version uppdaterar vi vyn för arbetsyta för frånvaroansvarig. Mer information finns i [konfigurera roll för frånvaroansvarig](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Konfigurera kopplingsbehov per tjänstledighetstyp | [Konfigurera kopplingsbehov per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Konfigurera ledighetsenheter per tjänstledighetstyp | [Konfigurera ledighetsenheter per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Klar att betalas](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funktion | Information |
| --- | --- |
| Plattformsuppdatering 10.0.21 (45) | Lansering av plattformsuppdatering 10.0.21 planeras i och med nästa serviceversion den 4 oktober 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.21 av Ekonomi och Drift-appar (oktober 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
