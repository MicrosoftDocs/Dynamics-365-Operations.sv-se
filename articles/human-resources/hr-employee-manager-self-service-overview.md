---
title: Översikt över självbetjäning för medarbetare och chef
description: Den här artikeln innehåller en översikt över arbetsytan för självbetjäning för medarbetare och chef.
author: andreabichsel
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2effea18c149ae4fe8a4fd6a1a26882d4adb058f3f09e4f9fdac7d594db3acc9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719633"
---
# <a name="employee-and-manager-self-service-overview"></a>Översikt över självbetjäning för medarbetare och chef

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln innehåller en översikt över arbetsytan för självbetjäning för medarbetare och chef.

## <a name="edit-personal-details"></a>Redigera persondetaljer

Om du behöver lägga till eller ändra personuppgifter, se [redigera personuppgifter](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Användaren har inte tilldelats till en arbetarpost

Om du inte har länkat din användare till en post för **arbetare** på sidan **användare** visas följande meddelande:

**Ditt användar-ID är inte associerat med din medarbetarpost i systemet och du kan inte visa eller uppdatera din information förrän den kan associeras. Kontakta din chef eller ditt supportteam för hjälp.**

Om du vill koppla en användare till en post för **arbetare**, navigerar du till **användare** och väljer användaren. Välj **Redigera**, lägg till motsvarande arbetare i fältet **Person** i formuläret och välj **Spara**. Du bör nu ha till gång till Självbetjäning för medarbetare.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Säkerhetskrav för självbetjäning för medarbetare och chef

Självbetjäning för medarbetare och chef kräver två säkerhetsroller:

- Medarbetare måste ha medarbetarrollen.
- Chefer behöver båda rollerna medarbetare och chef.

>[!NOTE]
>Du kan också använda anpassade roller för att komma åt självbetjäning för medarbetare och chef så länge som de har beviljats åtkomst till arbetsytorna medarbetare och chef.<br>
>Chefsåtkomst till medarbetarinformation baseras på den aktuella positionsradens hierarki som definieras i personal.

## <a name="employee-self-service"></a>Självbetjäning för medarbetare

På fliken **Min information** visas följande information om självbetjäning för medarbetare.  

### <a name="summary"></a>Sammanfattning

**Arbetsuppgifter som har tilldelats mig** visar alla godkännanden och arbetsflödesartiklar som har tilldelats medarbetaren. Du kan konfigurera arbetsflödesartiklar så att de skickar e-post till användaren.

**Enkäter som har tilldelats mig** visar alla planerade enkäter som är tilldelade direkt till medarbetaren eller gruppen.

**Företagets katalog** låter medarbetarna slå upp information som är relaterad till personer i organisationen. Allmän kontaktinformation är tillgänglig för alla medarbetare. Företagskatalogen är begränsad till det företag som medarbetaren har loggat in på.

**Teamkalender** innehåller information om teamets kalender. Mer information finns i [Visa team- och företagskalendrar](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Min karriärinformation

Avsnittet **Min karriärinformation** i självbetjäning för medarbetare innehåller kort som är relaterade till ledighet och frånvaro, prestandahantering, kompetenser, förmåner, uppgifter och bifogade filer.

Kortet **ledighetssaldon** visar saldona för alla eventuella registrerade planer. Det här kortet prognoserar saldot baserat på din avskrivningsmetod. Du kan ange och skicka ut förfrågningar om ledighet, som sedan går igenom en arbetsflödesprocess för godkännande. Läs mer om ledighet och frånvaro i [Översikt av tjänstledighet och frånvaro](hr-leave-and-absence-overview.md).

På kortet **aktiviteter** visas uppgifter som du har tilldelats och där kan du visa och hantera dem.

Kortet **Nästa registrerade kurs** visar nästa kurs som du har registrerat för. Du kan bara visa och registrera för alla öppna kurser. Alla kurser som är öppna för anmälan har statusvärdet **startad** och låter medarbetare göra självregistrering visas på det här kortet. Beroende på din organisations inställningar kan kursregistreringen gå igenom en godkännandeprocess.

Kortet **Certifikat** visar certifikatet och utgångsdatumet för certifikatet som förfaller närmast aktuellt datum. Du kan uppdatera, lägga till eller ta bort certifikat. Beroende på din organisations inställningar kan certifikatuppdateringar gå igenom en godkännandeprocess.

Kortet **Nästa schemalagda granskning** visar nästa resultatöversyn. Du kan starta en ny granskning från det här kortet. Din chef eller din HR-representant kan också initiera recensioner. Beroende på din organisations inställningar kanske du också kan visa, uppdatera och skicka ut avstängningsgranskning från det här kortet.

Du kan hantera dina mål med kortet **resultatmål**. Det här kortet visar antalet mål du har för varje status (**inte startat**, **pågår** och **behöver förbättras**). Du kan skapa, uppdatera och ta bort mål, beroende på vilken rollbaserad säkerhet som har tilldelats. Om du vill kan du lägga till nya mål från grupper eller mallar. Chefer och HR kan också skapa mål för medarbetare och bestämma hur detaljerat varje mål ska vara. Chefer och medarbetare kan samarbeta om mål och uppdatera aktiviteter, mått och status. Du kan också inkludera bilagor.

Du kan visa dina befintliga kunskaper på kortet **Kompetenser**. Du kan uppdatera kompetenser, lägga till nya eller ta bort sådana som inte längre är relevanta. Beroende på din organisations inställningar kan ändringar i dina kompetenser gå igenom en godkännandeprocess.

Du kan visa din aktuella kompensation via kortet **kompensationer**. Välj **Visa** om du vill visa din årliga lön och det senaste ökningsbeloppet. Om du är anställd i fler än ett företag visas varje årligt belopp på kortet. Om du vill visa detaljerad kompensations Historik väljer du den årliga lönesumman för att öppna formuläret **Historik över fast och variabel kompensation**. Framtida kompensation visas inte i det här formuläret. Om du har fler än en anställning kan du växla mellan företag i det här formuläret och visa din kompensationshistorik utan att logga in på varje företag.

Visa och hantera dokument med kortet **bifogade filer**. Du kan hantera alla **externa** bilagor. Både HR och anställda kan lägga till bilagor genom självbetjäning för medarbetare eller formuläret **arbetare**. Bilagor ställs in på **externa** som standard.

### <a name="additional-information"></a>Ytterligare information

Det här avsnittet innehåller länkar till andra självbetjäningsområden för medarbetare, liknande avsnittet **Min karriärsinformation**.

Anmäl dig till förmåner via länken **förmåner**. Mer information om förmånshantering finns i [Översikt över förmåner](hr-benefits-management-overview.md)

Under **prestanda** kan du välja **prestandajournaler** för att skapa poster i resultatjournaler som kan användas på både resultatmål och recensioner. Du kan välja **skicka feedback** om du vill ge feedback för andra medarbetare inom organisationen. Beroende på inställningarna för din organisation kan e-postmeddelanden skickas till mottagaren, avsändaren och cheferna. Du kan skicka feedback till alla medarbetare inom organisationen. Sändning av feedback begränsas inte av företaget.

Under **kompetenser**, kan du göra ändringar i **kurser**, **utbildningar**, **förtroendeuppdrag** och **yrkeserfarenhet**. Beroende på din organisations inställningar kan uppdatering av dessa kompetenser gå igenom en godkännandeprocess.

Du kan visa jobbinformation under **organisation**. Jobbinformation omfattar färdigheter, certifikat och ansvarsområden för din primära befattning. Du kan också se alla utlånade utrustningar som är utcheckade till dig. Beroende på din organisations inställningar kan ändringar i utlånad utrustning gå igenom en godkännandeprocess.

Under **enkät** kan du visa genomförda enkäter. Du kan också visa företagets enkäter som inte har genomförts. Du kan välja att slutföra en enkät när du vill. Författaren till enkäten kan bestämma den tidsram och för vilken enkäten är tillämplig.

Du kan konfigurera användardefinierade länkar i **personalparametrar**. Du kan till exempel definiera länkar till löneutdrag, årsslutsdokumentation eller externa lösningar. Dessa länkar visas längst ned i det här avsnittet, men du kan flytta dem genom att använda anpassningar.

Du kan också skapa ytterligare flikar genom att bädda in Power Apps i arbetsytan Självbetjäning för medarbetare. Använd menyn **inställningar** om du vill anpassa sidan med någon Power Apps. På menyn **inställningar** kan du välja att lägga till en Power App, slutföra detaljerna och infoga appen. Som standard visas Power Apps som den första fliken i sekvensen. Du kan ändra ordningen genom att använda standardanpassning.

## <a name="my-team"></a>Mitt team

På fliken **Min team** visas följande information om självbetjäning för chef. Endast chefer har åtkomst till fliken **Mitt team**.

### <a name="personnel-actions"></a>Personalåtgärder

Personalåtgärder som baseras på konfigurationsalternativ inom **Delade personalparametrar** och **Personalparametrar**. När den är aktiverad för **arbetare** kommer personalåtgärder aktivera nya menyalternativ, inklusive:

- **Begär ny anställd**
- **Begär ny leverantör**
- **Begär omplacering av arbetare**
- **Begär uppsägning**
- **Begär ändring av fast kompensation**

Du kan konfigurera dessa alternativ till att gå igenom ett valfritt arbetsflöde för granskning och godkännande.

Om du aktiverar **positionsåtgärder** aktiverar du följande alternativ:

- **Begär ny befattning**
- **Begär ändring av befattningsåtgärder**

Du kan också konfigurera dessa alternativ till att gå igenom ett valfritt arbetsflöde för granskning och godkännande.

### <a name="summary"></a>Sammanfattning

Informationen i avsnittet **sammanfattning** beror på alternativen HR har valts i **personalparametrar**. På fliken **Självbetjäning för chef** på sidan **personalparametrar** page, kan du konfigurera alternativ för att visa utgående poster och öppna befattningar. Om du aktiverar dessa alternativ bestäms vilka chefer som kan se i avsnittet **sammanfattning**.

Du kan konfigurera följande paneler för chefer:

- **Intyg som upphör för mitt team**
- **Utgående ID-nummer för mitt team**
- **Utgående prövningar för mitt team**
- **Utgående kontroller för mitt team**
- **Utgående tester för mitt team**
- **Öppna befattningar för direkta och/eller utökade rapporter**
- **Väntande ledighetsansökningar för mitt team**
- **Bedömning av teamkompetenser**
- **Analys av kompetenslucka**
- **Teamprestationsjournaler**
- **Teamprestationsmål**
- **Teamprestationsgranskningar**
- **Arbetare som slutar**

Du kan konfigurera följande alternativ för chefer för att göra ändringar eller lägga till tjänstledighet för deras underställda:

- Intyg
- Kurser
- Låneartiklar
- Kompetenser
- Begäran om tjänstledighet och frånvaro

### <a name="my-team-information"></a>Min teaminformation

Med min teaminformation kan chefer visa och uppdatera direkt och utökade rapporter. Om du vill få till gång till utökade rapporter markerar du den medarbetare som har direkt och **visa team** på kortet. Alla samma alternativ gäller för utökade rapporter som underställda. 

#### <a name="summary-tab"></a>Fliken Sammanfattning

Fliken **Sammanfattning** ger en översikt över dina underställda. Om en direkt rapport också har arbetstagarna rapporterar till sig, visar kortet antalet direktrapporter i det övre avsnittet, tillsammans med knappen **Visa grupp**. Alternativen ovanför varje kort gäller för den markerade medarbetaren. Om du till exempel vill ange en ledighets ansökan för en medarbetares räkning väljer du medarbetaren och väljer sedan **Begära ledig tid** ovanför korten. 

Om du väljer knappen **Detaljer** när du har valt en medarbetare visas följande alternativ:

- **Intyg**
- **Kompensation**
- **Kurser**
- **Granskningar**
- **Semester**
- **Lånade objekt**
- **Resultatmål**
- **Registrerade kurser**
- **Kompetenser**
- **Skicka feedback**

Beroende på din organisations inställningar kan du antingen endast göra ändringar eller endast visa.

#### <a name="position-tab"></a>Fliken Befattning

Fliken **positioner** visas en sammanfattningsvy för medarbetare i deras primära befattning. Namn, sida och avdelning visas i rubrikområdet på varje kort. Det här kortet innehåller:

- **Datum för tjänsteålder** – visas i avsnittet medarbetarens sammanfattning i formuläret arbetare
- **Tjänsteår** – Beräknad baserat på medarbetarens startdatum
- **Antal tidigare positioner** – baserat på positionshistorik. Om du väljer det här numret öppnas den detaljerade vyn över alla tidigare placerade positioner
- **Födelsedatum** – månad och dag för medarbetarens födelsedatum

Du kan visa befattningsdata för både direkta och utökade rapporter.

#### <a name="compensation-tab"></a>Fliken Kompensation

Fliken **kompensation** visar medarbetarens årslön. En företags identifierare visas under lönebeloppet. Om en medarbetare har fler än en anställning och får betalt från flera juridiska personer, kommer medarbetaren att ha flera kompensationsplaner. Om du vill visa alla kompensationsplaner över juridiska personer utan att växla mellan företag, måste du aktivera kompensation mellan företag under **personal > delade parametrar > avancerad åtkomst > aktivera kompensation mellan företag**.

Om du vill visa kompensationshistorik väljer du lönebeloppet som du vill öppna formuläret **Detaljer** för. Endast aktuella och historiska fasta och variabla kompensations poster visas i formuläret **kompensation**. Om en medarbetare har fler än en anställning kan du växla mellan företag för att visa kompensationshistoriken i varje företag eller aktivera en kompensation mellan företag i gemensamma parametrar för personal för att visa alla kompensationsplaner.

Du kan visa kompensation för både direkta och utökade rapporter.

#### <a name="leave-and-absence-tab"></a>Fliken tjänstledighet och frånvaro

På fliken **tjänstledighet och frånvaro** visas de högsta saldona för medarbetare som har aktiviteter. Om du vill vidta åtgärder eller visa en fullständig lista med aktiviteter väljer **information** och väljer sedan **Stäng av tid**. På formuläret **Ledighet** kan du visa saldon, begäran, godkänd ledighet och prognostiserade saldon för att hjälpa medarbetare att hantera tid bättre. Beroende på din organisations inställningar kan du också begära ledighet för dina direkta och utökade rapporter.

#### <a name="performance-goals-tab"></a>Fliken resultatmål

Fliken **resultatmål** sammanfattar resultatmålen efter status. Välj en nummer för en status eller välj resultatmål från **detaljer** om du vill visa alla mål för en medarbetare. Chefer och medarbetare kan uppdatera målen efter behov under tiden för målet.

Chefer kan se alla mål för deras team via panelen **Teamprestationsmål** i avsnittet **Sammanfattning** i **Mitt team**.

#### <a name="reviews-tab"></a>Fliken recensioner

På fliken **recensioner** sammanfattas de granskningar som medarbetaren har i varje tillstånd: **pågår**, **klar för granskning** och **slutlig granskning**. Om du vill komma åt en medarbetares granskning väljer du knappen **Detaljer** och väljer sedan granska för att samarbeta på. Beroende på var en granskning är i arbetsflödesprocessen kan du se om granskningen är tillgänglig för uppdatering. 

Du kan se alla recensioner för ditt team genom **Teamprestationsgranskningar** i avsnittet **Sammanfattning** i **Mitt team**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]