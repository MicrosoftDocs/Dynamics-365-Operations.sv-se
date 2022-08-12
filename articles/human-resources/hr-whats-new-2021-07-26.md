---
title: Nyheter och ändringar i Dynamics 365 Human Resources 26 juli 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 26 juli 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14041dfc753b508a0d68b90ee99d79510d07e622
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070093"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 26 juli 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4384.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Plattform update 10.0.20 | -- | [Plattformsuppdateringar för version 10.0.20 av appar för ekonomi och drift (augusti 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  Beskrivning |
| --- | --- | --- |
| 600422 | Löneadressvalidering misslyckas för Klar att betalas. | Valideringen har uppdaterats så att endast en adress av typen "Löneplats" och bara en adress av typen "Löneplats" krävs. |
| 601226 | Dataintegrationsutbetalning: Exportprojektet löneintegrering har inte alternativet full push | Löneintegreringen med Ceridian DayForce utför en stegvis push istället för en full push. Ceridian måste alltid vara fullständig uppdatering. Det här problemet är nu fast, enheterna i dataexportprojektet går nu inte längre att flytta till stegvis push. |
| 602272 | Det som har lagts till i arbetstytan För medarbetarens självbetjäning saknas och det går inte längre att lägga till dem i den | Vi har åtgärdat personanpassningsproblemet för medarbetarnas självbetjäning. Nya uppgifter kan läggas till i vyn och all befintlig personanpassning visas för användarna |
| 600711 | Halvdagsdefinitionsurvalsfält aktiverat för fullständiga tjänstledighetsansökningar | Det här problemet är nu fast och halvdagsdefinitionsfältet aktiveras bara när medarbetare väljer en tjänstledighetstyp med en halvdagsdefinition aktiverad och en halv dag som det valda beloppets värde |
| 602208 | Periodiseringsgradsenheter som visar timmar i stället för dagar | Det här problemet är nu fast. I formuläret **Ledighet** visas korrekt tjänstledighetsenhet (timmar eller dagar) för kolumnen **Periodiseringsgrad**. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegrering-API](hr-admin-integration-payroll-api-introduction.md)|
|  Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Med den här versionen uppdaterar vi vyn arbetsyta för frånvaroansvarig. Mer information finns i [konfigurera roll för frånvaroansvarig](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Konfigurera kopplingsbehov per tjänstledighetstyp | [Konfigurera kopplingsbehov per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Konfigurera ledighetsenheter per tjänstledighetstyp | [Konfigurera ledighetsenheter per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Klar att betalas](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

