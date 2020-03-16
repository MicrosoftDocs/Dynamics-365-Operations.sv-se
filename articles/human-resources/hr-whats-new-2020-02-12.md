---
title: Nyheter och ändringar i Dynamics 365 Human Resources (12 februari 2020)
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
ms.openlocfilehash: 1d352cae4b49efa8c893dceed448b30460e0eda5
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076303"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (12 februari 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2867. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>Det går att komma åt befintliga entiteter CompFixedEmpls och HcmPersonImage från OData (414178)

Med den här veckans utgivning är **CompFixedEmpls** och **HcmPersonImage**-enheterna offentliga och tillgängliga via ODAta.

## <a name="delete-employment-from-common-data-service-doesnt-work-when-employment-details-arent-active-403193"></a>Radera anställning från Common Data Service fungerar inte när medarbetarinformation inte är aktiv (403193)

Denna förändring möjliggör nu att radera anställning via Common Data Service när det inte finns någon aktiv anställningsinformation.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>Kursregistrering ändra arbetsflödesstatus till slutförd och fel efter det andra godkännandet (409749)

Arbetsflödet för kursregistrering har uppdaterats för att tillåta flera godkännare.

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
| Ny enhet för **Rubrik** | **Rubrik** tillagd. Den nya entiteten **Rubrik** kommer att inkluderas i synkroniseringsprocessen mellan personal och Common Data Service. Den kommer då inte från **Jobbefattning** eller **Jobb** enheter. |

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)