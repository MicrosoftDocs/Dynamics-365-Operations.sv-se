---
title: Nyheter och ändringar i Dynamics 365 Talent (21 januari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c0c303ec5d009fce0c975eb797f018b5e27a41eb
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982417"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Nyheter och ändringar i Dynamics 365 Talent (21 januari 2020)

[!include [banner](includes/banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract. Vi har lagt till funktioner för att kunna stödja vårt senaste meddelande [Skapa en bättre arbetsstyrka med Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Hämta miljödata

Administratörer kan hämta sina data till sin miljö. Data exporteras i JSON-standardformat med alla jobb, kandidater och konfigurationen som exporteras i en zip-fil. Mer information finns i [exportera data från Attract och Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Begränsa åtkomst till miljöer för användare som inte är administratörer

Administratörer kan nu begränsa åtkomsten till miljön för användare som inte är administratörer. Denna åtgärd kan inte ångras. Mer information finns i [Begränsa åtkomst till Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Exportera integrationsguider

Du kan nu exportera alla sina integrationsguider och mallar för registrering i Word-dokument. Mer information finns i [exportera data från Attract och Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2726. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>Fältet senaste årlig kompensation i formuläret bekräfta anställning är inte konsekvent (392092)

I den här versionen ingår en ändring som på ett konsekvent sätt visar den senaste valutan baserat på företagsväljaren i formuläret **verifiera anställning**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Känd som fält lagt till i feedbackmottagarens sökning (407789)

När du ger prestandafeedback har inte uppslaget för arbetare tillräckligt med information för att avgöra om feedback kommer till rätt person. Vi lade till kolumnen **känd som** för att identifiera medarbetarens unika namn.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>HcmWorkerPayrollInfo-post skapas utan koppling till en arbetare (394526)

I den här versionen ingår en ändring av att inte skriva HCMWorkerPayrollInfo-poster utan referens till en medarbetare.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Kan redigera avdelning när navigering från webbplatshierarki flyttas (341001)

När säkerhet har ställts in för att neka åtkomst till redigeringsavdelningar inaktiveras redigering när du navigerar till formuläret **avdelningar** i alla scenarier.

## <a name="coming-soon"></a>Kommer snart

En ny Common Data Service-lösning kommer snart att vara tillgänglig med följande ändringar:

| Beskrivning | Växel |
| --- | --- |
| **Jobb/befattning** enhetsändringar | <ul><li>**Kompensationsregion** tillagd</li><li>**Ekonomiska dimensioner** tillagd</li></ul> |
| **Arbetare** enhetsändringar | <ul><li>**Namnordning** tillagd</li><li>**Arbetar hemifrån** tillagd</li><li>**Språk** tillagt</li><li>**Datum för tjänsteålder** tillagt</li><li>**Jubileumsdatum** tillagt</li><li>**Ursprungligt anställningsdatum** tillagt</li></ul> |
| **Anställning** enhetsändringar | <ul><li>**Ekonomiska dimensioner** tillagd</li><li>**Uppsägningsorsak** tillagd</li><li>**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</li><li>**Provanställningsdatum** tillagt</li></ul> |
| **Arbetaradress** enhetsändringar | <ul><li>**Gatuadress** tillagd</li><li>**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell</li></ul> |
| Inställningsenheter för ny variabelkompensation | <ul><li>**Typ av variabel kompensationsplan**</li><li>**Variabel kompensationsplan**</li><li>**Överlåtelseregler**</li><li>**Variabel kompensationsplannivå**</li></ul> |
| Ny enhet för **Arbetarkalender anställning** | <ul><li>**Enheten arbetskalender** tillagd</li></ul> |
