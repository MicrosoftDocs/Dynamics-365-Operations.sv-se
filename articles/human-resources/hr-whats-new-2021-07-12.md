---
title: Nyheter och ändringar i Dynamics 365 Human Resources 12 juli 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 12 juli 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2851c36594384dd62f4bb95263cfd4407aec104
ms.sourcegitcommit: 71952e97774547230285026c6a3a6caea2512920
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2021
ms.locfileid: "6614843"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 12 juli 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4353.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
|  Växling av visningsperiod för service | |Med den här funktionen kan du använda olika datum vid beräkning av serviceåren som visas på sidan **Strömlinjeformad medarbetarpost** och på sidan **Personer**.  Denna kommer att vara tillgänglig i [Personal-parametrar](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  beskrivning |
| --- | --- | --- |
| 595871 | Om fönstret i Personal har fel Dataverse terminologi | Med ommärkning av Common Data Service till Dataverse, terminologi uppdaterats i informationsfönstret för Microsoft Dynamics 365 Human Resources (**Hjälp och support > Om**). |
| 598676 | Ett strömlinjeformat inmatningsformulär för medarbetare åsidosätter uppgiften kan skapa ett fel när det används med sparad vy| På sidan **Arbetare** om funktionen "Strömlinjeformad medarbetarpost" är aktiverad på arbetarsidan kanske programmet inte aktiveras om **Alltid öppen för redigering** har ställts in i den sparade vyn. |
| 592344 |Avsnittet Arbetares kompensation för befattning ska vara skrivskyddade när förmånshantering är aktiverad | Information om Arbetares kompensation skapas med hjälp av äldre förmånsfunktioner.  När förmånshantering är aktiverad är fälten skrivskyddade. När förmånshantering är aktiverad och **Dölj formulären för tidigare förmåner** anges till **Ja** i gemensamma parametrar för personal för fliken **Arbetares kompensation** döljs. |
| 598617 | Formuläret **HcmDiscussion** aktivering av fliken orsakar oändlig loop när anpassningar tillämpas | När både rutnät och detaljvy har **Alltid öppen för redigering** aktiverad, strider koden som aktiverar fliken i den åsidosatta uppgiftsmetoden med personalisering om vilken kontroll som ska ha fokus och skapar en oändlig loop. |
| 593553 | Journaldatumfältet i prestandajournalen visas i UTC | Fältet **Journaldatum** för prestandatidskrifter visas i UTC-tidszonen snarare än den tidszon som definieras i systemdatuminställningen, vilket gör att datumet är felaktigt för vissa tidszoner. |
| 586930 | När du öppnar aktiviteter för resultatmål öppnas en helt annan post | När funktionen "Prestandajournaler för utvidgade rapporter" är aktiverad i Funktionshantering väljer du prestandamål för utökade rapporter om fliken **Mitt team** i **Självbetjäning för medarbetare** öppnas målen för en anställd istället för den utvalda medarbetaren. |
| 569959 |  HcmPositionWorkerAssignmentV2-entitet tilldelar inte en arbetare till en befattning | Användarna fick ett felmeddelande när en befattningstilldelningspost läggs till via enheten och publiceringen misslyckades. |
| 582259 | VETS 4212-rapporten används formuläret 2017 i stället för formuläret 2020 | Uppdaterad till 2020-formatet.  Läs in det nya formatet genom att gå till **Rapportkonfigurationer** och ta VETS-4212 rapporten i den vänstra kolumnen. Gå till **Elektronisk rapportering - Databaser - Personalresurser** och välj **Öppna**.  Välj **VETS-4212 PDF utskrift** och välj sedan **Importera**.|


## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md)|
|  Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Konfigurera rollen för frånvarochefen](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Konfigurera kopplingsbehov per tjänstledighetstyp | [Konfigurera kopplingsbehov per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Konfigurera ledighetsenheter per tjänstledighetstyp | [Konfigurera ledighetsenheter per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Klar att betalas](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Plattformsuppdatering 10.0.20 (44) | Plattformsuppdatering 10.0.20 planeras i och med nästa serviceversion den 26 juli 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.20 av Finance and Operations-appar (augusti 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
