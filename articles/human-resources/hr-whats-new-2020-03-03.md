---
title: Nyheter och ändringar i Dynamics 365 Human Resources (3 mars 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 3 mars 2020.
author: Darinkramer
manager: AnnBe
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bf5b5ce9efbd2014164db213ff20d28d20ecf3e
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712314"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (3 mars 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2955. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>Common Data Service-lösningen finns nu med följande ändringar:

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

Under de närmaste veckorna kommer dessa enhetsändringar att vara tillgängliga i alla miljöer. Så här installerar du den senaste Common Data Service-lösningen för personal manuellt:

1.  Gå till [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2.  Välj **Miljö**.

3.  Leta upp den miljö som du vill uppgradera. Miljön bör motsvara **Miljönamn** i avsnittet **Common Data Service-information** i formuläret **Om** i Personal.

4.  Välj miljö om du vill visa information om miljön.

5.  I åtgärdsfältet längst upp, välj **Hantera lösningar**. Ett nytt webbläsarfönster öppnas och navigera till **Dynamics 365 administrationscenter** inom ramen för din miljö.

6.  I listan **Lösningar** välj **Dynamics 365 Human Resources Förankra**.

7.  Välj **uppgradering** om du vill använda den senaste lösningen.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Importproblem med dataentiteten Anmälan om tjänstledighet (406082)

Du kan nu registrera en medarbetare i en ny tjänstledighetsplan av samma typ, så länge som det nya anmälningsdatumet infaller senare än det utgångna anmälningsdatumet för den föregående planen.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problem med export av lönetariffer i 401K payrollWorkerEnrolledBenefitDetail-entiteten i DMF (420700)

Den här ändringen korrigerar exportfunktionen för entiteten **payrollWorkerEnrolledBenefitDetail** så att den återspeglar de aktuella värdena för arbetsgivarens bidrag.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>Om du söker i det strömlinjeformade arbetarformuläret kan meddelandet som säger att personens fält måste fyllas i (402525)

När du söker efter en medarbetare får du inte längre något meddelande om att du måste fylla i fältet **person**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>Värdet i fältet notering återges inte i formuläret Lägg till fler kompetenser (380134)

Den här ändringen åtgärdar ett problem när du anpassar formuläret **Lägg till fler kompetenser** i Självbetjäning för medarbetare.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Flera fasta kompensationsplaner upphör inte att gälla vid överföring av medarbetare (389466)

Med den här ändringen upphör alla aktiva fasta kompensationsposter för den gamla befattningen att gälla övergångsdatumet.

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner blir tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** - För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** - För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)