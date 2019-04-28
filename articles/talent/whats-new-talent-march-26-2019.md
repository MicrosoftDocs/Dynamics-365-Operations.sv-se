---
title: Nyheter och ändringar i Dynamics 365 for Talent (26 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
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
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 568a16a17ed3269c7b72f27f0d4b7bbdbd56630e
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/12/2019
ms.locfileid: "949838"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-26-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (26 mars 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="enhancements-to-interview-scheduling"></a>Förbättringar av tidsplanering av intervjuer
Följande förbättringar finns vid tidsplanering av intervjun.

- Rekryterare och anställande chefer kan nu manuellt utlösa en påminnelse för en intervjuare om att skicka feedback. Associerade e-postmallen för påminnelsen kan också konfigureras.
- Medan sammanfattningen av intervjun med kandidaten delas kan intervjuplaneraren välja att dölja namnen på intervjuarna och också välja att dölja rader från vyn för intervjusammanfattningen.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

### <a name="embedded-images-in-activities"></a>Inbäddade bilder i aktiviteter
Du kan nu bädda in bilder direkt i aktiviteter. Förutom att kopiera och klistra in bilder från webben kan du överföra bilder från det lokala filsystemet. Storleken på aktiviteten är begränsad till 1 MB. Om bilden är för stor, ändra storlek och försök överföra igen.

[![Mappning](./media/embedimages.png)](./media/embedimages.png)

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
**Skapa 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Anpassat fältstöd är tillgängligt för utvalda entiteter i Common Data Service 

Följande Common Data Service entiteter stöder nu kundfälten som skapats i Dynamics 365 for Talent:

- Arbetare
- Etniskt ursprung
- Veteranstatus
- Språkkod
- Befattning
- Jobbtyp
- Jobbfunktion
- Befattning
- Befattningstyp
 
### <a name="employment-history-not-displayed-chronologically"></a>Anställningshistorik visas inte kronologiskt
Förutom denna ändring visar nu anställningshistoriksidan medarbetarposter i kronologisk ordning, oberoende av företaget. Du kan också använda sorteringsalternativ för att sortera efter företag.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>Planer för fast kompensation visas inte vid begränsning av användare av företag i säkerhet.
I den här versionen visas nu fasta kompensationsplaner vid begränsning av användare av företag i säkerhet. Alla säkerhetsinställningar kommer att hedras och fasta planer kommer att visas för de företag som användaren har behörigheter att få åtkomst till. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Kan inte ta bort jobbposter med Öppna i Excel-alternativ i Talent
Med den här versionen kan du nu ta bort jobbposter med alternativet **öppna i Excel** i Dynamics 365 for Talent.

### <a name="upgrade-to-common-data-service"></a>Uppgradera till Common Data Service
Tidsgränser för uppgradering till Common Data Service för appar närmar sig snabbt. Logga in på PowerApps administrationscenter för att avgöra om databasen måste uppgraderas. Mer information om deadlines och nödvändiga instruktioner för uppgradering finns i [uppgradera till Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>I förhandsgranskning

För information om hur du aktiverar funktioner för förhandsgranskning finns i [Få åtkomst till förhandsfunktioner i Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Tillåt att orsakskoder anges på tjänstledighetstyper
Organisationer kanske behöver ytterligare information relaterad till ledighetsbegäranden. Om du vill ha den här informationen måste medarbetare inkludera en orsakskod på deras ledighetsbegäran. Med den här versionen kan du kan nu ange orsakskoder som är associerade med en viss ledighetstyp och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Konfigurera orsakskoder för att köras när du skickar tjänstledighetstyper för vissa ledighetstyper
Organisationer kan kräva att orsakskoder anges för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Detta kan krävas utifrån lagstadgat krav i deras land/region eller en företagspolicy. Den här versionen ger möjlighet för personalavdelningen att ange vilka tjänstledighetstyper som kräver en orsakskod. Detta kommer att aktiveras när medarbetare skickar begäranden där ledighet kräver en orsakskod.

## <a name="coming-soon"></a>Kommer snart

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)
I många organisationer kan kompensations- och förmånsansvariga endast ha tillgång till vissa kompensationsposter. Posterna kan vara för chefer eller nationella medarbetare. Med den här ändringen kan personalavdelningen hantera och underhålla kompensationsplaner för olika medarbetargrupper i organisationen. Du ska tilldela säkerhetsroller till fasta och variabla planer som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter. Endast roller med åtkomst kan bearbeta kompensation för dessa anställda.

###  <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 25 kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Dubblettkontroll av medarbetare: användargränssnittsändringar
Med denna ändring detekteras dubbletter när du anger namnfält och status visar antalet dubbletter som hittades. Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna. Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.
