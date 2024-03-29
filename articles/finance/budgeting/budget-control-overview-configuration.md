---
title: Översikt över budgetkontroll
description: Det här ämnet presenterar budgetkontrollfunktionen och innehåller information som hjälper dig att konfigurera budgetkontroll för att optimera hanteringen av organisationens ekonomiska resurser.
author: panolte
ms.date: 03/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27eb31919937e7f43a785616b547e3d6952eaaf2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898310"
---
# <a name="budget-control-overview"></a>Översikt över budgetkontroll

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet presenterar budgetkontrollfunktionen och innehåller information som hjälper dig att konfigurera budgetkontroll för att optimera hanteringen av organisationens ekonomiska resurser.

Budgetkontroll stöder hantering av ett företags ekonomiska resurser via kontoplaner, arbetsflöden, användargrupper, källdokument, journaler, konfigurerbar beräkning av tillgängliga medel, budgetcykler och trösklar. Med kontroller på plats kan en organisation planera, mäta, hantera och prognostisera sina ekonomiska resurser genom hela räkenskapsåret. 

När budgetar har godkänts i systemet kan du använda budgetplaner för att skapa budgetregisterposter för att registrera omkostnadbudgeten för en organisation. Du kan också skapa eller importera ut budgetregisterposter från ett tredjepartsprogram, i stället för att använda budgetplaneringsfunktionen. 

Omkostnader kan registreras med hjälp av huvudkonton och ekonomiska dimensioner. Du kan konfigurera kontroll över den totala omkostnaden för att uppfylla organisationens policyer och krav genom att gruppera kombinationer av ekonomiska dimensioner och huvudkonton. 

Följande diagram visar budgetkontrollens plats i de olika stegen i en typisk budgetcykel.

[![Typisk budgetcykel.](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Du kan konfigurera budgetkontrollen enligt flera faktorer:

- **Ekonomiska dimensioner** – Vilka ekonomiska dimensioner måste användas för att rapportera budget och utfall och vilka ekonomiska dimensioner krävs för att kontrollera budgeten? Finns det särskilda dimensionskombinationer eller huvudkonton som kräver särskild uppmärksamhet? Finns det till exempel krav på att spåra budget till utfall genom kostnadsställe och program? Kräver resekostnader särskild uppmärksamhet?
- **Tid** – Vilken tidsram (räkenskapsperiod, räkenskapsperiod till dags dato osv.) ska användas för att utvärdera tillgängliga budgetmedel?
- **Källdokument** – Vilket källdokument måste bedömas för budgetkontroll? Bör dokumenten utvärderas per rad eller per dokument?
- **Beräkning av tillgängliga medel** – Ska dokument såsom inköpsrekvisitioner (förinteckning) och inköpsorder (inteckningar) tas med i beräkningen av tillgängliga medel? Ska dokument med utkaststatus tas med i beräkningen av tillgängliga medel?
- **Åsidosättning av behörigheter** – Vem har behörighet att överskrida tillgänglig budget?

Budgetkontroll integreras helt med appen. Du kan därför utvärdera den tillgängliga budgeten för både planerade och faktiska inköp. Budgetförfrågningar och rapporter är tillgängliga. Användaren kan därmed utvärdera budgeten under hela budgetcykeln och göra de justeringar som krävs i form av budgetrevisioner eller överföringar. En budgetchef kan också exportera budget och utfall till Microsoft Excel för att bättre kunna analysera och prognostisera vid behov.

## <a name="configuring-budget-control"></a>Konfigurera budgetkontroll

### <a name="budget-cycle-time-span"></a>Tidsrymd för budgetcykel

När den grundläggande budgeteringen är konfigurerad kan du definiera tiden eller start- och slutperioderna för budgeteringen och budgetkontrollen på sidan **Tidsrymd för budgetcykel**. Budgetcykler motsvarar ofta räkenskapsårets kalendrar men kan omfatta räkenskapsår.

Nästa steg i konfigureringen ska slutföras i flikar som öppnas från sidan **Konfigurering av budgetkontroll**.

### <a name="define-parameters"></a>Definiera parametrar

Baserat på de ekonomiska dimensioner som aktiverats för budgeten kan du använda alla eller en del av de ekonomiska dimensionerna för budgetkontroll. 

Du kan dessutom ange tidsintervallet för standardinställningar (exempelvis **Räkenskapsår**, **Ackumulerat för räkenskapsåret**, **Räkenskapsperiod** eller **Kvartalsvis**) som budgetkontroller ska köras under den relaterade tidsrymden för budgetcykeln. Du kan även specificera en standardbudgetchef och tröskeln som används för att meddela användare när tröskeln har nåtts. Värdena i dessa fält används som förvalda värden i alla nya budgetkontrollregler eller budgetgrupper som skapas. Du kan dock ändra de förvalda värdena för individuella grupper eller regler. 

Sätten som budgetar skapas och registreras på i budgetregistret är avgörande för att fastställa den tidsrymd som ska väljas vid bedömningen av tillgängliga budgetmedel. Om ett årligt belopp för en dimensionsvärdeskombination utvecklas och används kan ett räkenskapsår eller räkenskapsåret hittills vara lämpligt att tillämpa. Om en organisation som skapar budgetar efter räkenskapsperiod eller allokerar till räkenskapsperioder vill ha mer detaljerad kontroll kan den behöva överväga räkenskapsperiod hittills eller kvartalsvisa tidrymder. 

Dessutom kan en organisations kultur användas för att definiera konfigureringen, eftersom den är kopplad till budgetering och budgetkontroll.

### <a name="over-budget-permissions"></a>Behörighet för överskriden budget

På fliken **Behörighet för överskriden budget** kan du därefter specificera användargrupper. Du kan även ange om användare som är medlemmar i en grupp har behörighet att överskrida budgeten. Du kan förhindra användare från att överskrida budgeten förbi budgettröskeln som angavs på sidan **Budgetparametrar** eller så kan du förhindra dem från att överskrida budgeten per alla belopp, oavsett tröskeln. Beroende på hur proaktivt en organisation hanterar sina utgifter kan dessa behörigheter hjälpa till att hantera ekonomiska resurser. 

### <a name="budget-funds-available"></a>Budgetmedel är tillgängliga

På fliken **Tillgängliga budgetmedel** kan du sedan definiera formeln som används för att beräkna tillgängliga budgetmedel. Beroende på hur konservativt en organisation hanterar sina ekonomiska resurser eller beroende på regler eller branschkrav kan beräkningen inkludera utkast eller ej bokförda dokument. 

> [!NOTE]
> Om beräkningen ändras under en budgetcykel kommer ändringarna inte att påverka dokument som tidigare har godkänts i budgetkontroller och som har bokförts eller slutförts. En funktion som kallas **Endast spårade belopp i de tillgängliga budgetmedelsberäkningarna** gör att du kan ändra vilka data som spåras i BudgetSourceTracking-registren. När funktionen aktiveras lagras belopp endast om de har valts för att användas i beräkningen av de tillgängliga budgetmedlen. Mer information finns i [Budgetmedel är tillgängliga](budget-funds-available.md).

### <a name="documents-and-journals"></a>Dokument och journaler

På fliken **Dokument och journaler** kan du välja källdokument och journaler som ska vara föremål för budgetkontroller och om kontrollerna ska utföras på radpostnivån eller på dokumentet som helhet. Dessutom ger den nya funktionen **Filtreringsförbättring av budgetkontrolldokument** som är tillgänglig via Microsoft Dynamics 365 Finance version 10.0.27 ett frågebaserat filteralternativ för varje dokument som ingår i budgetkontrollen. Därför kan du ange vilka budgetkontrolldokument som budgetkontrollerats. På det här sättet går det bara att budgetera en delmängd av en dokumenttyp med funktionen. Du kan till exempel endast kontrollera inköpsorder där fältet **Pool** är inställt på **01**. En ny kolumn som läggs till på fliken **Dokument och journaler** visar om en fråga har definierats för den valda dokumenttypen. Dessutom kan du lägga till, redigera och ta bort filter som läggs till i verktygsfältet ovanför dokumentrutnätet. 

Du bör matcha de valda källdokumenten med de kryssrutor du väljer för saldon som ingår i beräkningen av tillgängliga budgetmedel. Om du t.ex. har valt **Budgetreservationer för inteckningar**, ska du välja alternativet **Inköpsorder**. När en budgetkontroll utförs för beloppen och konton på en ett inköpsrad, är budgetkontrollkategorin som är tilldelat reservationen är **Inteckning**. När en budgetkontroll utförs för belopp och konton på en inköpsrekvisition ska kategorin som tilldelas reservationen vara **Förinteckning**. 

Om **Budgetreservationer för inteckning** och/eller **Budgetreservationer för förinteckning** ingår i beräkningen av tillgängliga budgetmedel och måste återspeglas via poster i huvudboken ska journalförd redovisning aktiveras i gruppen **Journalförd redovisning** på sidan **Redovisningsparametrar**.

### <a name="assign-budget-models"></a>Tilldela budgetmodeller

På fliken **Tilldela budgetmodeller** tilldelar du budgetmodeller till tidsrymder för budgetcykel som ska inkluderas i budgetkontrollen.

### <a name="define-budget-control-rules"></a>Definiera budgetkontrollregler

På fliken **Definiera budgetkontrollregler** måste du skapa särskilda regler som baseras på de ekonomiska dimensioner som är aktiverade för budgetkontroll. Om det till exempel finns ett fokus baserat på en avdelnings omkostnad eller omkostnadsintervall kan du använda inställningarna för den här fliken för att definiera och utvärdera de omkostnaderna. Du kan definiera olika trösklar för varje budgetkontrollregel. 

> [!Important]
> Budgetkontroll kommer att aktiveras för alla huvudkonton av typen **Vinst och förlust**, **Utgift**, **Intäkt, Balansräkning, Skulder, Eget kapital** eller **Tillgång**. Om **Definiera budgetkontrollregler** innehåller en regel som har tomma kriterier kommer budgetkontroll att aktiveras för **alla** ekonomiska dimensionskombinationer som innehåller huvudkonton av de typerna. Därför är det viktigt att skapa budgetkontrollregler som enbart definierar intervallen för kombinationer av ekonomiska dimensioner som är viktiga att aktivera budgetkontroll för.

### <a name="select-main-accounts"></a>Välj huvudkonton

Om **Huvudkonto** inte markeras som en budgetkontrolldimension på sidan **Ange parametrar** men specifika utgifter ändå hanteras, kan du välja dessa utgifter i fliken **Markera huvudkonton**. Om **Huvudkonto** har valts som en budgetkontrolldimension krävs inga poster.

### <a name="define-budget-groups"></a>Definiera budgetgrupper

På fliken **Definiera budgetgrupper** kan du även definiera unika kombinationer av ekonomiska dimensioner där budgetresurser slås samman för sekundär budgetkontroll. Du kan skapa en enskild post som omfattar hela organisationen eller definiera flera grupper som representerar olika avdelningar eller kostnadsställen.

### <a name="define-message-levels"></a>Definiera meddelandenivåer

Om varningsmeddelanden för budgetkontroll ska ignoreras för några användargrupper kan du ange de grupperna på sidan **Definiera meddelandenivåer**. Medlemmarna i användargruppen fortsätter att få felmeddelanden när de överskrider tillgängliga budgetmedel, baserat på deras behörigheter för överskriden budget.

### <a name="activate-budget-control"></a>Aktivera budgetkontroll

När budgetkontrollen har konfigurerats kan du starta och aktivera den på fliken **Aktivera budgetkontroll**. Utkastversionen träder då i kraft.

> [!Important]
> När budgetkontrollen startas och aktiveras och transaktionerna bokförs, bör den inte stängas av i mitten av året. När budgetkontrollen stängs av registreras inte aktiviteter för budgetkontrolländamål och budgetkontroller utförs inte längre. Dokument som redan har bokförts kan därför inte korrekt återspegla alla avlösningsbelopp eller saldon i frågor och rapporter som är relaterade till budgetkontroll. Dessa inkluderar budgetkontrollstatistik för alla underordnade eller justerande dokument och journaler. 

Notera dessutom att transaktioner, inklusive budgetregisterposter, som har bokförts innan budgetkontrollen aktiverades inte beaktas i budgetkontrollen. Det är därför enbart lämpligt att aktivera budgetkontroll i början av en ny budgetcykel. Kontrollera att budgetsaldon för budgetregisterposter som innehåller ingående budgetsaldon för budgetkontroll uppdateras efter att budgetkontrollen aktiveras. Alla öppna dokument (t.ex. inköpsorder) ska kontrolleras med avseende på om de har tillgängliga budgetmedel och kommer att få en budgetreservation för budgetkontroll när användaren manuellt utlöser en budgetkontroll in dokumentet.

## <a name="using-budget-control"></a>Använda budgetkontroll
När budgetkontroll aktiveras kommer användarna att få varnings- och felmeddelanden för budgetkontroll i dokument och journaler som har konfigurerats för budgetkontroll. Kom ihåg du kan konfigurera budgetkontroll så att användare varnas när de överskrider budgetmedlen, men att de kan tillåtas fortsätta bekräfta eller bokföra transaktionen. Användarna kan visa information om misslyckade budgetkontroller på sidan **Budgetkontrollfel och varningar**.

Från den här sidan kan användare titta på sidan **Budgetkontrollstatistik efter period** för att se information om tillgänglig budget och reservationer för en vald kombination av budgetkontrolldimensioner. Användarna kan även titta på sidan **Budgetkontrollstatistik** för att se tillgänglig budget för alla kombinationer av ekonomisk dimension som används i budgetkontroll. 

Om budgetkontroll aktiveras för inköpsorder kan budgetchefen använda arbetsområdet **Redovisningsbudgetar och prognoser** för att granska kön för alla obekräftade inköpsorder som har varningar och fel för budgetkontroll. Om budgetchefen har behörigheter för överskriden budget konfigurerade kan inköpsorder bekräftas direkt i arbetsytan.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
