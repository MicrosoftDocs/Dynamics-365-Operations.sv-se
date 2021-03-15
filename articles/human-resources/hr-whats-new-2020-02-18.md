---
title: Nyheter och ändringar i Dynamics 365 Human Resources (18 februari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 18 februari 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/18/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e087095807f587536f2dad7e65fbc8beaa88878e
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128075"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (18 februari 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2903. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="platform-update-32"></a>Plattform update 32 

Plattformsuppdateringen 32 finns nu tillgänglig. Mer information finns i [Nyheter och ändringar i plattformsuppdatering 32 för Finance and Operations-appar (februari 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>Sökvärden sparas vid ändring av visningsalternativ i förenklat medarbetarformulär (383833)

Det nya formuläret **arbetare** kommer nu ihåg sökvärden när du ändrar visningsalternativen och tillämpar ändringar.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Sammanfattningspaneler för kompensationshantering i förhandsgranskningsfunktionen omdirigera till felformulär (401861)

Fasta och variabla kompensationshanteringspaneler visar nu korrekta poster i formuläret **Arbetare**. Gäller endast förhandsgranskningsfunktionen för formulär för förenklad medarbetare. Du kan aktivera den här förhandsgranskningsfunktionen i **funktionshantering**. Mer information finns i [Hantera funktioner](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Tomt statusfält för vissa poster för ledighetsansökan i Dataverse (414915)

Den här ändringen åtgärdar ett problem i Dataverse när fältet **status** i en ledighetsansökan anges till **granskning**. Dataverse visar nu statusen.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>Analys av kompetensluckor är endast möjlig för tilldelat jobb (411390)

Du kan nu utföra en analys av kompetensluckor på alla jobb som definierats i personal.

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>Systemvalutan synkroniseras inte från Dataverse till personal i nya miljöer (418011)

Systemvalutan i Dataverse kan nu synkronisera med personal.

## <a name="in-preview"></a>I förhandsgranskning

- [Funktioner för förhandsgranskning av tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Förhandsgranskningsfunktion för förmånshantering](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Kommer snart

### <a name="updated-dataverse-solution"></a>Uppdaterad Dataverse-lösning

En ny Dataverse-lösning kommer snart att vara tillgänglig med följande ändringar:

| Beskrivning | Växel |
| ----------------------------------------- | --- |
| **Jobb/befattning** enhetsändringar | **Kompensationsregion** tillagd</br>**Ekonomiska dimensioner** tillagd |
| **Arbetare** enhetsändringar | **Namnordning** tillagd</br>**Arbetar hemifrån** tillagd</br>**Språk** tillagt</br>**Datum för tjänsteålder** tillagt</br>**Jubileumsdatum** tillagt</br>**Ursprungligt anställningsdatum** tillagt |
| **Anställning** enhetsändringar | **Ekonomiska dimensioner** tillagd</br>**Uppsägningsorsak** tillagd</br>**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</br>**Provanställningsdatum** tillagt |
| **Arbetaradress** enhetsändringar | **Gatuadress** tillagd</br>**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell |
| Inställningsenheter för ny variabelkompensation | **Typ av variabel kompensationsplan**</br>**Variabel kompensationsplan**</br>**Överlåtelseregler**</br>**Variabel kompensationsplannivå** |
| Ny enhet för **Arbetarkalender anställning** | **Enheten arbetskalender** tillagd |
| Ny enhet för **lönepositionsuppgift** | **Lönepositionsuppgift** tillagd |
| Ny enhet för **Rubrik** | **Rubrik** tillagd. Den nya entiteten **Rubrik** kommer att inkluderas i synkroniseringsprocessen mellan personal och Dataverse. Den kommer då inte från **Jobbefattning** eller **Jobb** enheter. |

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]