---
title: Nyheter och ändringar i Dynamics 365 Human Resources (7 februari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78043273fb98a12a8d33f7bb94ba8ad2e9fb49fb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029967"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (7 februari 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2835. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>Learning Analytics visar inte kursen om klassrummet är tomt (388289)

Sidan Learning Analytics visar nu kursen om klassrummet är tomt.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>Befattningssökning tar inte hänsyn till tidszonen (405344)

Sökningen efter lediga befattningar tar nu hänsyn till tidszonen när den validerar om en befattning är öppen.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>Aktuell saldoanalysvy uppdateras inte med korrekt aktuell tjänstledighet efter att du har skickat in ledighetsansökningar (409756)

Det aktuella saldot inkluderar nu skickade förfrågningar om ledighet.

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner är tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** - För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** - För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Kommer snart

### <a name="platform-update-32"></a>Plattform update 32 

Plattformsuppdatering 32 kommer snart att vara tillgänglig. [Få mer information om plattformsuppdatering 32 här](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

### <a name="updated-common-data-service-solution"></a>Uppdaterad Common Data Service-lösning

En ny Common Data Service-lösning kommer snart att vara tillgänglig med följande ändringar:

| Beskrivning | Växel |
| ----------------------------------------- | --- |
| **Jobb/befattning** enhetsändringar | **Kompensationsregion** tillagd</br>**Ekonomiska dimensioner** tillagd |
| **Arbetare** enhetsändringar | **Namnordning** tillagd</br>**Arbetar hemifrån** tillagd</br>**Språk** tillagt</br>**Datum för tjänsteålder** tillagt</br>**Jubileumsdatum** tillagt</br>**Ursprungligt anställningsdatum** tillagt |
| **Anställning** enhetsändringar | **Ekonomiska dimensioner** tillagd</br>**Uppsägningsorsak** tillagd</br>**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</br>**Provanställningsdatum** tillagt |
| **Arbetaradress** enhetsändringar | **Gatuadress** tillagd</br>**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell |
| Inställningsenheter för ny variabelkompensation | **Typ av variabel kompensationsplan**</br>**Variabel kompensationsplan**</br>**Överlåtelseregler**</br>**Variabel kompensationsplannivå** |
| Ny enhet för **Arbetarkalender anställning** | **Enheten arbetskalender** tillagd |
| Ny enhet för **lönepositionsuppgift** | **Lönepositionsuppgift** tillagd |
| Ny enhet för **Rubrik** | **Rubrik** tillagd. Enhet **Rubrik** tas med i synkroniseringsprocessen mellan Personal och Common Data Service, men kommer inte att refereras till från enheten **Jobbefattning** eller **Jobb**. |

