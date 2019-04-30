---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (6 december 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
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
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80d62492d58a436c15fac82df0d000ab9efa6ea5
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/12/2019
ms.locfileid: "949953"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-6-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (6 december 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2071**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.


## <a name="platform-update-22"></a>Plattform update 22

### <a name="export-up-to-1-million-rows-to-excel"></a>Exportera upp till 1 miljon rader till Excel

Den funktionen Export till Excel kan konfigureras så att användare kan exportera upp till 1 miljon rader från ett rutnät i Talent, en betydande ökning från föregående gränsen på 10 000 rader. 

### <a name="restyled-personalization-toolbar"></a>Nydesignat verktygsfält för anpassning

Verktygsfältet för anpassning har fått en ny design i plattformsuppdatering 22 för att hjälpa användare att lättare anpassa egna erfarenheter i Talent. Följande ändringar gjordes: 

-  Namnet på respektive verktyg för anpassning visas tillsammans med en ikon som hjälper användare att snabbt identifiera verktyget de är intresserade av att använda.
-  Beskrivningen för hur du använder det aktuella verktyget visas nu också, vilket hjälper användarna att förstå hur de kan göra nödvändiga anpassningar.  
-  Hela verktyget för anpassning kan flyttas över skärmen genom att dra och släppa på ett visst område längst till vänster i verktygsfältet. På så sätt kan du anpassa element som tidigare doldes av verktygsfältet.   

### <a name="optimized-is-one-of-filtering-experience"></a>Optimerad "är någon av" filtreringsupplevelsen

Filtreringsoperatorn ”är någon av” är tillgänglig för de flesta fält när du använder i rubriklistrutorna för filterfönster och rutnät. Den här operatorn tillåter att en användare filtrerar ett fält baserat på flera värden. En ny och förbättrad upplevelse för operatorn ”är någon av” finns i plattformsuppdatering 22. För mer information, se [Optimerad "är någon av" filtreringsupplevelse](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Klistra in listor från Excel till filterfält med operatorn ”"är någon av”

För vissa uppgifter kan användare ha en lista över värden i Excel som de skulle vilja använda för att filtrera data i Talent. Exempelvis i Personal kan användaren ha identifierat en grupp av medarbetare i en rapport som kräver ytterligare undersökning i systemet och det skulle vara perfekt för den här användaren att kunna kopiera listan direkt från Excel till ett filterfält i Talent.

Med start i plattformsuppdatering 22 identifieras operatorn ”är någon av” i filterfönstret och filtrering i rutnätskolumner erkänner nu listor som kopieras från Excel så att de kan klistras in direkt i ett filterfält. Detta inkluderar en uppsättning värden som kopieras från olika rader och kolumner i Excel. Mer information om den här funktionen finns i [Klistra in listor från Excel till filterfält med operatorn ”är någon av”](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>I förhandsgranskning

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Konfigurera löneintegration för Storbritannien mellan Talent och Dayforce

Integrationen mellan Microsoft Dynamics 365 for Talent och Ceridian Dayforce är tillgänglig i förhandsgranskning för Storbritannien. Se följande avsnitt för mer information [Konfigurera löneintegrering mellan Talent och Dayforce](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Kommer snart

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Tjänstledighet och frånvaro: framtida tjänstledighet och prognostisering lämnar saldon

Med de ändringar som görs för att möjliggöra för anställda att uppskatta ledig tid och begära framtida ledighetsansökningar utan att påverka deras nuvarande ledighetssaldon, ändrar också hur ledighetssaldon ändras. 

Saldot som visas för tillfället är hur lång ledighet som är tillgänglig för begäranden, inklusive periodiseringar via idag och alla godkända tjänstledighetsansökningar till slutet av tiden. 

När möjligheten att ställa en prognos frisläpps, visar saldot ändringar för att det aktuella saldot för ledighet inklusive periodiseringar via idag och ansökningar via idag. Medarbetare och chefer ser dessa uppdaterade saldon i medarbetares och chefers självbetjäning på kortet **ledighet** och i fönstret **ledighetssaldon**. Personalchefer kommer att se alla dessa uppdaterade saldon på arbetsytan **Personer** och i medarbetarens fönster **Tilldelade tjänstledighetsplaner**.

## <a name="other-changes"></a>Andra ändringar 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>Uppsägningskod fylls inte i på tilldelningsposten för arbetarens befattning

En ändring har implementerats som fyller i orsakskoden för tilldelningsposten för befattningen under uppsägningsprocessen.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>Validering för anställningsnummer som används behöver ytterligare information

Ytterligare information visas när nummerserier används för att bättre förstå problem när det inte går att generera ett nytt nummer.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Knappar för bifogade filer finns inte tillgängliga för arbetare

Ändringar har gjorts för att korrigera bilagor. När du lägger till en ny bilaga till en arbetare kommer knapparna **Ny** och **Redigera** att vara tillgängliga när faktaboxar är öppna i fönstret för arbetare. 

## <a name="known-issues"></a>Kända problem

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Mappningsfel i integrationen med Finance and Operations

Följande problem har identifierats i den aktuella mallen för integrering av Talent med Finance and Operations. En ny mall kommer snart att publiceras och kommer att gälla alla nya integrationsprojekt som har skapats. För befintliga integrationsprojekt uppdateras uppgiftsmappningarna. Se följande tabell för uppdaterade mappningar. 

>[!NOTE]
> Jobbbefattningarna till överordnad jobbuppgiftstilldelning för befattningar integrerar inte data. Detta är ett problem som för närvarande undersöks. Det finns ingen lösning för den aktuella mappningen. 

Avdelningar för driftenhetsuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält          | Nytt källfält |
| -------------------------------|------------------|
| cdm_description (beskrivning)  | cdm_name (namn)  |

En ytterligare mappning måste också läggas till. Välj det senaste fältet **Ingen** för att lägga till följande mappning.

| Källfält                   | Målfält    |
| -------------------------------|----------------------|
| cdm_description (beskrivning)  | NAMEALIAS (NAMEALIAS)|

Uppdaterade mappningar ska se ut så här.

![Avdelningar till driftenhetsuppgift](./media/DepartmentMapping.png)


Jobb till jobbdetaljuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält          | Nytt källfält                   |
| -------------------------------|------------------------------------|
| cdm_name (namn)                | cdm_description (beskrivning)      |
| cdm_name (beskrivning)         | cdm_jobdescription (jobbeskrivning)|


Uppdaterade mappningar ska se ut så här.

![Jobb till jobbdetaljuppgift](./media/JobMapping.png)

Arbetare till arbetsuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält                 | Nytt källfält                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (e-postadress 1)   | cdm_primaryemailaddress (primär e-postadress) |
| cdm_telephone1 (telefon 1)          | cdm_primarytelephone (primär telefon)       |

Transformering av fältet Kön behöver också uppdateras. Välj mapptypen **fn** (funktion) för kön och uppdatera följande värdemappningar.

| Common Data Service Värde   | Finance and Operations-värde | | ------------|------------------ -----------| | 75440000    | Man                         | | 75440001    | Kvinna                       | | 75440002    | Ingen                         | | 75440003    | Ej specifik                  |

Uppdaterade mappningar ska se ut så här.

![Arbetare till arbetaruppgift.](./media/WorkerMapping.png)

![Transformering av fältet Kön](./media/WorkerTransform.png)

