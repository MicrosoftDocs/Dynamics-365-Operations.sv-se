---
title: Nyheter och ändringar i Dynamics 365 Human Resources (1 maj 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 1 maj 2020.
author: Darinkramer
manager: AnnBe
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 074c678d9d8294aabf4e78b2a6ee0fa53efbaf23
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712290"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (1 maj 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3196. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Nya prestationshanteringsenheter finns i datahanteringsramverk (DMF)

Följande entiteter är nu tillgängliga. Om dessa entiteter inte visas i listan entiteter använder du alternativet **uppdatera entiteter** i **Ramverksparametrar > Enhetsinställningar > Uppdatera enhetslistan**.

- **Diskussionskompetens**
- **Diskussionsmål**
- **Diskussionsmätning**
- **Diskussionsämne**
- **Prestationsjournal**
- **Mått**
- **Målmätning**

Dessutom har **Totalpoäng** och **Genomsnittspoäng** lagts till i **Diskussions**-enheten.

## <a name="increase-length-of-leave-request-comments-275641"></a>Öka längden på tjänstledighetskommentarer (275641)

Kommentarer om tjänstledighet får nu fler än 100 tecken.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Slutgiltiga kommentarer till recensioner visas inte när chefen eller medarbetaren är inloggad i ett annat företag (431688)

Alla kommentarer visas nu när granskningarna visas.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>Användardefinierade länkar stöds inte i nytt arbetarformulär (390374)

Användardefinierade länkar är nu aktiverade i formuläret för strömlinjeformad **arbetare**.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity orsakar OData API-krasch (439476)

Den här ändringen korrigerar API-kraschen. Ett dubblettnamn orsakade det här felet.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="leave-suspension"></a>Lämna uppehåll

Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Uppdatera användarupplevelsen att anger att periodiseringen är pausad (429550)

Användarupplevelsen anger nu att periodiseringen har avbrutits för en plan.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper (272447)

I den här versionen kan HR skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet. Obetald tjänstledighet kan vara en typ, men behöver inte vara det. Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF-enhet tillgänglig för periodiserade avstängningar (429549)

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Lägg till orsakskod för periodiserade avstängningar (429547)

Orsakskoder har lagts till den periodiserade avstängningen.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Påbörja övergång från Human Resources-parametrar till tjänstledighets- och frånvaroparametrar

Den här versionen börjar kombinera Human Resources-parametrar med parametrar för tjänstledighet och frånvaro.

## <a name="carry-forward-rules"></a>Överför regler

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Kända problem

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint förhandsgranskning fungerar inte i vissa miljöer

Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:

1. Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten. Du kan visa den här informationen på sidan **Användare**. Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData. Standard är att e-postadressen inte finns i Excel-designen. Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera. När du är klar med dessa steg kan du uppdatera administratörskontot.

2. När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.

3. Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.

4. Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)