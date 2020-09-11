---
title: Nyheter och ändringar i Dynamics 365 Human Resources (23 juli 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 23 juli 2020.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 30662ccf7e37f7f1e131e3b18b5a770c53fea0d1
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711878"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (23 juli 2020)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3416. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>Att ta bort ekonomiska dimensioner för en position fungerar inte som förväntat (445476)

Om du tar bort dimensioner från en befattning tas nu samma positioner bort från Common Data Service.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Positioner som inte är i hierarkin visa inaktiva positioner (397257)

Positioner som är inaktiva (har en förfallen varaktighet), visas inte längre i positionshierarkin som **positioner som inte finns i hierarkin**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>Valideringen sker mellan LeaveEnrollmentEntity och HcmWorkerEntity i import av datahanteringsramverk (DMF) orsakar långsam databelastning (442324)

Ändringar i den här versionen ökar prestanda för **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Det går inte att personanpassa i organisationsadministrationen (447490)

Med den här ändringen kan du nu anpassa länkarna i **organisationsadministrationen**.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="mandatory-fields"></a>Obligatoriska fält 

Du kan nu göra fält obligatoriska genom att använda anpassningsfunktioner för personal. Den här funktionen kräver **sparade vyer**.

## <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>DMF-enheter (Data Management Framework) för förmånshantering
 
Entiteter för hantering av förmåner släpps. DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner. En mall för hantering av förmåner kan användas för att flytta data. Mallen exporterar och importerar data sekventiellt för att respektera databeroenden.

## <a name="buy-and-sell-leave"></a>Köpa och sälja tjänstledighet 

Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet. Den här processen hanteras ofta manuellt. Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen. Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag. Mer information finns i:

- [Hantera principer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Lämna periodisering för ett enskilt företag eller en plan

Kunder kan bearbeta periodiseringar för ett enskilt företag eller en enskild plan för tjänstledighet och frånvaro. Denna möjlighet ger klarhet i den periodiserade processen för kunder med olika tjänstledighetsår eller principer för periodisering av tjänstledighet. Mer information finns i [tjänstledighet per företag eller per tjänstledighetsplan](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Lägg till bifogade filer i ledighetsansökningar

Möjligheten att lägga till bilagor till godkända ansökan om tjänstledighet är viktigt i den aktuella COVID-19 miljön. Medarbetarna kan nu lägga till dessa bilagor. De har också mer inblick i hur uppdateringar görs för att lämna förfrågningar. Mer information finns i [lägga till en bilaga till en befintlig begäran](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Lägg till orsakskod för periodiserade avstängningar 

Orsakskoder har lagts till den periodiserade avstängningen.

## <a name="carry-forward-rules"></a>Överför regler 

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper

Du kan skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet. Obetald tjänstledighet kan vara en typ, men behöver inte vara det. Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF-enhet tillgänglig för periodiserade avstängningar 

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="coming-soon"></a>Kommer snart

## <a name="checklist-entities-included-in-common-data-service"></a>Entiteter för checklista inkluderade i Common Data Service

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Common Data Service.

## <a name="platform-changes"></a>Plattformsändringar

Plattformsuppdatering 10.0.12 (36)

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)
