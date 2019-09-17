---
title: Nyheter och ändringar i Dynamics 365 for Talent (20 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
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
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d316aff83bd9f60f054a970e223777db5e214adb
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741646"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-20-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (20 mars 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="setting-the-audience-on-activities"></a>Ange målgruppen för aktiviteter
Aktiviteter i systemet kan nu ha målgruppen definierad. Processrelaterade aktiviteter (t.ex. intervjunschema, feedback och EEO) kan tilldelas alla kandidater, interna kandidater och externa kandidater. Anpassade aktiviteter, till exempel Microsoft Forms YouTube videoklipp och webbinnehåll kan levereras till alla kandidater, interna kandidater, externa kandidater eller anställningsteamet.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Bättre genomsynlighet för karriärwebbplats: sökmotoroptimering
Den här funktionen aktiverar sökmotorernas sökrobotar så att de når och indexerar lediga jobb på karriärwebbplatsen Attract. Detta hjälper kandidater att söka efter jobb som publicerats i Attract karriärwebbplatsen med populära sökmotorer.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Visa tips för inloggning till kandidater som har glömt sina autentiseringsuppgifter
Om en kandidat har glömt de sociala autentiseringsuppgifter som användes för att ansöka om ett ledigt jobb när de öppnade en länk som har sparats eller skickats via e-post till dem, ser de nu ett tips med leverantörsnamn och användarnamn (döljs). Detta hjälper dem att använda rätt autentiseringsuppgifter för att komma åt jobbansökningarna.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Hjälp interna kandidater att utforska interna jobb
Ett problem har åtgärdats där externa kandidater kunde se namnet på rekryteraren eller anställande chef för ett jobb. Nu ser endast interna kandidater anställningsteamets medlemmar för ett jobb. Det är också enklare för interna kandidater att visa och ansöka om endast jobb jobb. När en kandidat försöker använda länken för att visa eller lägga till ett endast internt jobb tvingas de att autentisera med Azure Active Directory inloggningsuppgifter. Interna kandidater har också möjlighet att kontakta anställningsteamets medlemmarna för att uttrycka intresse eller veta mer om jobbet. Den här funktionen är tillgänglig för alla jobb för endast interna kandidater. Mer information finns i [Funktionen för karriärwebbplats i Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Dela ut silvermedaljörer för att tilldela sökande med högt värde för framtida befattningar
Rekryterare och anställande chefer har ofta en löpande förteckning över de sökande som passar bra för befattningen men kunde inte utöka erbjudanden eftersom befattningen redan var tillsatt. Sådana sökande kallas silvermedaljörer och är värdefulla men kan ändå minska den tid det tar för att anställa nästa gång en liknande befattning blir ledig. Attract tillåter nu att rekryterare och anställande chefer utser silvermedaljörer i listan över sökande om sökanden har avancerat till steget Erbjudandet. Silvermedaljörens utnämning visas i listan över sökande för jobbet, men även i vyn för talangpoolen när dessa sökande tillhör någon av rekryterarens eller anställande chefernas pooler. Dessutom visas utnmäningen i jobbhistoriken som en del av talangpoolprofilen för en sökande. Du kan förhandsgranska den här funktionen genom att låta en administratör aktivera den med hjälp av [Funktionshantering i administratörscenter](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="add-applicants-to-talent-pools"></a>Lägg till sökande i en talangpooler
Nu är det enklare att lägga till sökande i talangpooler med en ny åtgärd i listan med sökande. Genom att välja ikonen **lägga till talangpool** kan rekryterarens eller anställande chefen välja från listan med talangpooler och enkelt lägga till sökande till talangpooler direkt från listan med sökande för ett jobb.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Konfigurera om en meritförteckning krävs för att ansöka om ett visst jobb
Baserat på kundernas feedback kan rekryterare nu konfigurera om en meritförteckning i form av en överförd fil krävs vid ansökan av ett visst jobb. Denna konfiguration är del av ansökningsaktiviteten som finns i anställningsprocessen. När den är aktiverad uppmanas potentiella ansökande att skicka en meritförteckning när de ansöker om den här befattningen. Programmet kommer inte betraktas som slutfört om inte en meritförteckning överförs. Detta minskar bruset i sökandepoolen genom att säkerställa att alla sökande ger tillräckligt mycket information för att låta rekryteraren sortera dem.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Kandidater kan ansöka om ett jobb med sin LinkedIn-profil
Kandidater som redan har sin aktuella uppdaterade profil på LinkedIn kan ansöka om jobb med bara ett enda klick med hjälp av den profilen.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Spåra var en kandidaprofil kommer från i systemet och om sökandena upptäcker de jobb de sökte
Nu kan nu ta reda på hur profilen för en viss kandidat har sitt ursprung i Attract genom att titta på profilens källa under kandidatens information på en sökandes **profil**sida eller talangpoolprofil. På samma sätt kan du se hur varje sökande upptäcker jobbet genom att titta på ansökningskällan som finns i **Ansökningsaktivitet** i feed för ansökningsaktivitet. Den här informationen finns också tillgänglig i jobbhistoriken i talangpoolprofilen. När rekryterare eller anställande chefer lägger till kandidater manuellt uppmanas de också att ange källan till ansöknings- eller kandidatprofil. När en kandidat ansöker för första gången, blir deras profilkälla detsamma som ursprunget till ansökningarna. Du kan förhandsgranska den här funktionen genom att låta en administratör aktivera den med hjälp av [Funktionshantering i administratörscenter](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). Observera att befintliga kandidater och sökande inte har någon källinformation. Rekryterare kan emellertid lägga till informationen manuellt.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2195.

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>Attract-integration kastar dubblettpostfel för ansökningar
Ett problem med dubblettposter i den här uppdateringen har åtgärdats. Det här problemet visas när du öppnar arbetsytan **personalhantering**.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Det går inte att stänga formuläret när du redigerar namnordning
Ändringar har gjorts för att korrigera ett problem när du redigerar namnordningen i arbetarformuläret.

## <a name="coming-soon"></a>Kommer snart

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)
I många organisationer kan kompensations- och förmånsansvariga endast ha tillgång till vissa kompensationsposter. Posterna kan vara för chefer eller nationella medarbetare. Med den här ändringen kan personalavdelningen hantera och underhålla kompensationsplaner för olika medarbetargrupper i organisationen. Du ska tilldela säkerhetsroller till fasta och variabla planer som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter. Endast roller med åtkomst kan bearbeta kompensation för dessa anställda.

###  <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 24 kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse.

### <a name="duplicate-employee-check-interface-changes"></a>Dubblettkontroll av medarbetare: gränssnittsändringar
Med denna ändring detekteras dubbletter när du anger namnfält och status visar antalet dubbletter som hittades. Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna. Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.


