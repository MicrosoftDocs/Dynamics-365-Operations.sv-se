---
title: Nyheter och ändringar i Dynamics 365 Human Resources (25 februari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 25 februari 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/25/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4faecb83518f3ef8af825872abc2a6ffb94162fc
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128032"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (25 februari 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2927. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Aktivera hantering av ärendehantering och DMF-entiteten (Data Management Framework) (414754)

Den här förhandsgranskningsfunktionen möjliggör ytterligare navigering till ärenden som hanteras av ärendet. Du kan aktivera den här förhandsgranskningsfunktionen i arbetsytan **funktionshantering**. Dessa menyalternativ visas på arbetsytan **Regelefterlevnad** för Dynamics 365 Human Resources. Med den här ändringen kan Personal komma åt:

- Alla ärenden
- Mina ärenden
- Mina öppna ärenden
- Mina förfallna ärenden
- Ärenden tilldelade till mig genom arbetsflödet

Tillsammans med dessa nya vyer i ärenden finns även DMF-entiteten **Ärendedetalj**.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Aktivera relationsdefinitioner i globala adressboken (414762)

Relationerna är nu aktiverade i den globala adressboken. Innan den här veckans frisläppning visas faktarutan, **Relationer** alla systemdefinierade relationer. Nu kan du definiera dessa relationer på sidan för den globala adressboken.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>En befattning kan tas bort när aktiva kompensationsposter finns för positionen (414568)

Med den här ändringen visas en varning när du försöker ta bort en position och arbetaren har en aktiv kompensationspost för samma position. När detta inträffar måste du uppdatera medarbetarens fasta kompensationspost innan du tar bort positionen.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>Arbetsflödet för prestandagranskning infogar ibland godkännandena från personer som inte ingår i processen (414171)

Den här ändringen åtgärdar ett problem där ytterligare godkännande deltagare läggs till i prestandagranskningen.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>Tilldelning av arbetarposition skapas inte i Dataverse när den väljs i dialogrutan Ny arbetare (413479)

Den här ändringen åtgärdar ett problem vid anställning av en ny arbetare och tilldelar den nya anställningen till en position via dialogrutan **Ny arbetare**. Nu återspeglas befattningstilldelning reflekteras i Dataverse.

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

Under de närmaste veckorna kommer dessa enhetsändringar att vara tillgängliga i alla miljöer. Så här installerar du den senaste Dataverse-lösningen för personal manuellt:

1.  Gå till [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2.  Välj **Miljö**.

3.  Leta upp den miljö som du vill uppgradera. Detta bör motsvara **Miljönamn** i avsnittet **Common Data Service-information** i formuläret **Om** i Personal.

4.  Välj miljö om du vill visa information om miljön.

5.  I åtgärdsfältet längst upp, välj **Hantera lösningar**. Ett nytt webbläsarfönster öppnas och navigera till **Dynamics 365 administrationscenter** inom ramen för din miljö.

6.  I listan **Lösningar** välj **Dynamics 365 Human Resources Förankra**.

7.  Välj **uppgradering** om du vill använda den senaste lösningen.

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner blir tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** – För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** – För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)