---
title: Nyheter och ändringar i Dynamics 365 Human Resources (9 augusti 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 9 augusti 2021.
author: marcelbf
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad1397084dd3eb210065fe6d8c20c5b8253cd206
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882878"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources (9 augusti 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4393.

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
| --- | --- | --- |
| 558385 | Standardbefullmäktige väljs inte när alternativet **Befullmäktigade** aktiveras för standardbefullmäktig. | Det här problemet är nu fast. Flera standardbefullmäktigade väljs automatiskt i berättigade planer när alternativet **Välj befullmäktigade automatiskt** på sidan **Delade parametrar för Personal** aktiveras. |
| 589617 | På sidan **Ledig tid** är saldona **Tillgängliga för inköp** och **Tillgängliga för försäljning** tomma när åtkomsten är begränsad till ett specifikt företag. | Det här problemet är nu fast. Sidan **Ledig tid** angr korrekta saldon för **Tillgängliga för inköp** och **Tillgängliga för försäljning** när användaren är begränsad till ett specifikt företag. |

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
