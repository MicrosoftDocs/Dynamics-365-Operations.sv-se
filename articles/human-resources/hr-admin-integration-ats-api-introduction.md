---
title: Introduktion av API för integrering av system för sökandespårning
description: Detta ämne beskriver API för integrering av system för sökandespårning (ATS) för Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8dacca05c47f50099ca1420413ef80430b7ebf1850a799d1208328581699242d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751228"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Introduktion av API för integrering av system för sökandespårning

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver API för integrering av system för sökandespårning (ATS) för Dynamics 365 Human Resources. Syftet med API:et är att möjliggöra effektiviserad integrering mellan Dynamics 365 Human Resources och ATS-partner.

![ATS-integreringsflöde.](media/hr-admin-integration-ats-api-introduction-flow.png)

Den integrerade erfarenheten börjar i Personal när en anställningsansvarig skapar en rekryteringsbegäran. När begäran har aktiverats hämtar ATS uppgifter om förfrågningen för att skapa ett rekryteringsprojekt. Därefter följer det rekryteringsförloppet för att välja och anställa en kandidat för befattningen/befattningarna. Slutligen slutför ATS integreringen genom att skicka den valda kandidatens post till Personal. Kandidatposten kan sedan gå igenom fler registreringsvalideringar och arbetsflöden för att skapa medarbetarposten.

För att aktivera integreringen har Personal lagt till följande komponenter:

1.  Funktion för att skapa en rekryteringsbegäran.
2.  En expanderad kandidatprofil och relaterade arbetsflöden.
3.  Ett integrations-API som öppnar den nya funktionen för integrering av program.

Mer information om hur du ställer in och använder funktionen för rekryteringsbegäran och kandidater finns i [Rekrytera jobbkandidater](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Detta API bygger på Microsoft Dataverse (tidigare Common Data Service). All RESTful-interaktion med denna API sker via webb-API för Microsoft Dataverse, som använder OData. Detta API är en underuppsättning av webb-API för Dataverse. Webb-API för Dataverse definierar egenskaper såsom autentisering, serviceavtal, batch, samtidighetskontroll och felhantering.

Mer allmän information om webb-API för Microsoft Dataverse finns här:

- [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Använd webb-API för Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Utvecklarguide för Microsoft Dataverse](/powerapps/developer/data-platform)

Dokumentationen ovan innehåller information och utvecklarvägledning om hur du använder webb-API för Dataverse, exempelvis [hanterar autentiseringar](/powerapps/developer/data-platform/webapi/authenticate-web-api), [genomför åtgärder](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [använder Postman med API](/powerapps/developer/data-platform/webapi/use-postman-web-api) samt [använder ändringsspårnings- eller delta-tokens](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) med API:t.

### <a name="option-sets"></a>Alternativuppsättningar

Datamodellen för den API för ATS-integrering som beskrivs i det här dokumentet innehåller alternativuppsättningar som tillhandahåller fasta värden associerade med entitetsegenskaper. Mer information om hur du arbetar med alternativuppsättningar i webb-API för Dataverse finns i [Skapa och uppdatera alternativuppsättningar med hjälp av webb-API](/powerapps/developer/data-platform/webapi/create-update-optionsets). Alternativuppsättningar definieras för respektive Dataverse-miljö.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Virtuella register för Personal i Dataverse

Slutpunkterna för API för ATS-integration använder plattformsfunktionerna för det virtuella registret i Microsoft Dataverse. Som standard distribueras inte de virtuella registren och deras associerade API-slutpunkter för Personal-miljöer, vilket låter organisationer att avgöra vilka OData-slutpunkter som ska visas för miljön. Om du vill använda API:t måste de virtuella registren för Personal-entiteterna genereras för miljön. 

Information om hur du genererar virtuella register för API:et finns i [Konfigurera virtuella Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Datamodell

Datamodellen centreras kring två huvudentiteter:

- **RecruitingRequest** representerar en begäran till en ATS att rekrytera för en eller flera öppna befattningar. En exempelfrågeställning finns i [Exempelfrågeställning för Rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** representerar detaljer om en kandidat som har accepterat ett erbjudande om en befattning. **Person** representerar den person som är kandidat. En person kan ha flera roller i företaget, till exempel kandidat, medarbetare, anställd eller entreprenör. För en exempelfrågeställning, se [Exempelfrågeställning för Kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

Följande diagram visar relationer inom API:t. Flera typer har utländska nycklar till andra, befintliga entiteter i Personal som inte visas här. Detta dokument innehåller information om entiteter som är specifika för rekryteringintegreringsscenarier. Det finns dock många andra entiteter i webb-API:t för Dataverse för Dynamics 365 Human Resources som också kan vara relevanta för din integrering. Du kanske till exempel också behöver detaljer för medarbetare, jobb, befattningar eller andra entiteter som inte har definierats här. Många av dessa entiteter refereras i relationer med utländska nycklar eller navigeringsegenskaper.

![API-datamodell för ATS-integrering.](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Rekryteringsbegäran och relaterade entiteter och alternativuppsättningar

Exempelfrågeställning: 

- [Exempelfrågeställning för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Enheter:

- [Rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request.md)
- [Befattning för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Färdighet för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Utbildning för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Plats för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-location.md)

Alternativuppsättningar:

- [Befrielsestatus för jobb](hr-admin-integration-ats-api-job-exempt-status.md)
- [Befattningsstatus för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Status för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Kategori för lagstadgade jobb](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Kandidat att anställa och relaterade enheter och alternativuppsättningar

Exempelfrågeställning:

- [Exempelfrågeställning för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Enheter:

- [Kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Person](hr-admin-integration-ats-api-person.md)
- [Personens utbildning](hr-admin-integration-ats-api-person-education.md)
- [Personens yrkeserfarenhet](hr-admin-integration-ats-api-person-professional-experience.md)
- [Personens adress](hr-admin-integration-ats-api-person-address.md)
- [Partens kontakt](hr-admin-integration-ats-api-party-contact.md)
- [Personens färdighet](hr-admin-integration-ats-api-person-skill.md)
- [Bedömningsnivå](hr-admin-integration-ats-api-rating-level.md)
- [Personens certifikat](hr-admin-integration-ats-api-person-certificate.md)
- [Certifikattyp](hr-admin-integration-ats-api-certificate-type.md)
- [Personkontroller](hr-admin-integration-ats-api-person-screening.md)
- [Kontrolltyper](hr-admin-integration-ats-api-screening-types.md)
- [Personens ID-nummer](hr-admin-integration-ats-api-person-identification-number.md)

Alternativuppsättningar:

- [Resultat för integration av sökande](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Tomt Ja nej](hr-admin-integration-ats-api-blank-yes-no.md)
- [Slutförandestatus](hr-admin-integration-ats-api-completion-status.md)
- [Kontakttyp](hr-admin-integration-ats-api-contact-type.md)
- [Bas för utbildningskredit](hr-admin-integration-ats-api-education-credit-basis.md)
- [Kön](hr-admin-integration-ats-api-gender.md)
- [Civilstånd](hr-admin-integration-ats-api-marital-status.md)
- [Månader under året](hr-admin-integration-ats-api-months-of-year.md)
- [Nej Ja](hr-admin-integration-ats-api-no-yes.md)
- [Periodenhet](hr-admin-integration-ats-api-period-unit.md)
- [Kontrollfrekvens](hr-admin-integration-ats-api-screening-frequency.md)
- [Kontrollfrekvens genereras från](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Typ av färdighetsnivå](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Se även

[Rekrytera jobbkandidater](hr-personnel-recruit.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Använd webb-API för Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Skapa och uppdatera alternativuppsättningar med hjälp av webb-API:t](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]