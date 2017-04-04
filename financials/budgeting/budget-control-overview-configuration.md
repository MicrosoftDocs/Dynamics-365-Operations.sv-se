---
title: "Budgetöversikt kontroll"
description: "Denna artikel beskriver budgetkontroll och innehåller information som hjälper dig att konfigurera budgetkontroll i Microsoft Dynamics 365 för åtgärder så att du kan hantera ekonomiska resurser."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 04e0c066511c1fedf33784944441326201fc2df8
ms.lasthandoff: 03/31/2017


---

# <a name="budget-control-overview"></a>Budgetöversikt kontroll

Denna artikel beskriver budgetkontroll och innehåller information som hjälper dig att konfigurera budgetkontroll i Microsoft Dynamics 365 för åtgärder så att du kan hantera ekonomiska resurser.

<a name="overview"></a>Översikt
--------

I Microsoft Dynamics 365 för budgetkontroll stöder hantering av ett företags finansiella medel från kontoplanen, arbetsflöden, användargrupper, källdokument och journaler, konfigurerbar beräkningen av tillgängliga medel och budgetcykler tröskelvärden. Med kontroller på plats kan en organisation planera, mäta, hantera och prognostisera sina ekonomiska resurser genom hela räkenskapsåret. 

När budgetarna har godkänts i Dynamics 365 för operationer kan använda du budgetplaner för att generera budgetregisterposter för budgeten utgifter för en organisation. Du kan också skapa eller importera budgetregisterposter från ett fristående program i stället för att planera budgetfunktionerna. 

Omkostnader kan registreras med hjälp av huvudkonton och ekonomiska dimensioner. Du kan konfigurera kontroll över den totala omkostnaden för att uppfylla organisationens policyer och krav genom att gruppera kombinationer av ekonomiska dimensioner och huvudkonton. 

Följande diagram visar budgetkontrollens plats i de olika stegen i en typisk budgetcykel.

[![BudgetingCycle](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Du kan konfigurera budgetkontroll enligt flera faktorer:

-   **Ekonomiska dimensioner** – Vilka ekonomiska dimensioner måste användas för att rapportera budget och utfall och vilka ekonomiska dimensioner krävs för att kontrollera budgeten? Finns det särskilda dimensionskombinationer eller huvudkonton som kräver särskild uppmärksamhet? Finns det till exempel krav på att spåra budget till utfall genom kostnadsställe och program? Kräver resekostnader särskild uppmärksamhet?
-   **Tid** – Vilken tidsram (räkenskapsperiod, räkenskapsperiod till dags dato osv.) ska användas för att utvärdera tillgängliga budgetmedel?
-   **Källdokument** – vilket källdokument för budgetkontroll bedömas? Dokumenten utvärderas per rad eller per dokument?
-   **Beräkning av tillgängliga medel** – Ska dokument såsom inköpsrekvisitioner (förinteckning) och inköpsorder (inteckningar) tas med i beräkningen av tillgängliga medel? Ska dokument med utkaststatus tas med i beräkningen av tillgängliga medel?
-   **Åsidosättning av behörigheter** – Vem har behörighet att överskrida tillgänglig budget?

Budgetkontrollen är helt integrerat med Dynamics 365 för operationer. Du kan därför utvärdera den tillgängliga budgeten för både planerade och faktiska inköp. Budgetförfrågningar och rapporter är tillgängliga. Användaren kan därmed utvärdera budgeten under hela budgetcykeln och göra de justeringar som krävs i form av budgetrevisioner eller överföringar. En budgetchef kan också exportera budget och utfall till Microsoft Excel för att bättre kunna analysera och prognostisera vid behov.

## <a name="configuring-budget-control"></a>Konfigurera budgetkontroll
### <a name="budget-cycle-time-span"></a>Tidsrymd för budgetcykel

När den grundläggande budgeteringen är konfigurerad kan du definiera tiden eller start- och slutperioderna för budgeteringen och budgetkontrollen på sidan **Tidsrymd för budgetcykel**. Budgetcykler motsvarar ofta räkenskapsårets kalendrar men kan omfatta räkenskapsår.

Nästa steg i konfigurationen har slutförts på de olika flikarna på den **budgetkontrollkonfigurationen** sida.

### <a name="define-parameters"></a>Definiera parametrar

Baserat på de ekonomiska dimensioner som aktiverats för budgeten kan du använda alla eller en del av de ekonomiska dimensionerna för budgetkontroll. 

Du kan dessutom ange tidsintervallet för standardinställningar (exempelvis **Räkenskapsår**, **Ackumulerat för räkenskapsåret**, **Räkenskapsperiod** eller **Kvartalsvis**) som budgetkontroller ska utföras för under den relaterade tidsrymden för budgetcykeln. Du kan även specificera en standardbudgetchef och tröskeln som används för att meddela användare när tröskeln har nåtts. Värdena i dessa fält används som förvalda värden i alla nya budgetkontrollregler eller budgetgrupper som skapas. Du kan dock ändra de förvalda värdena för individuella grupper eller regler. 

Sätten som budgetar skapas och registreras på i budgetregistret är avgörande för att fastställa den tidsrymd som ska väljas vid bedömningen av tillgängliga budgetmedel. Om ett årligt belopp för en dimensionsvärdeskombination utvecklas och används kan ett räkenskapsår eller räkenskapsåret hittills vara lämpligt att tillämpa. Om en organisation som skapar budgetar efter räkenskapsperiod eller allokerar till räkenskapsperioder vill ha mer detaljerad kontroll kan den behöva överväga räkenskapsperiod hittills eller kvartalsvisa tidrymder. 

Dessutom kan en organisations kultur användas för att definiera konfigureringen, eftersom den är kopplad till budgetering och budgetkontroll.

### <a name="over-budget-permissions"></a>Behörighet för överskriden budget

På fliken **Behörighet för överskriden budget** kan du därefter specificera användargrupper. Du kan även ange om användare som är medlemmar i en grupp har behörighet att överskrida budgeten. Du kan förhindra användare från att överskrida budgeten förbi budgettröskeln som angavs på sidan **Budgetparametrar** eller så kan du förhindra dem från att överskrida budgeten per alla belopp, oavsett tröskeln. Beroende på hur proaktivt en organisation hanterar sina utgifter kan dessa behörigheter hjälpa till att hantera ekonomiska resurser. 

### <a name="budget-funds-available"></a>Budgetmedel är tillgängliga

På fliken **Tillgängliga budgetmedel** kan du sedan definiera formeln som används för att beräkna tillgängliga budgetmedel. Beroende på hur konservativt en organisation hanterar sina ekonomiska resurser eller beroende på regler eller branschkrav kan beräkningen inkludera utkast eller ej bokförda dokument. 

> [!NOTE] 
> Ändringarna påverkar inte några dokument som tidigare gått budgetkontroller för kontrollen och som har bokförts eller slutförts om beräkningen ändras under en budgetcykel.

### <a name="documents-and-journals"></a>Dokument och journaler

På fliken **Dokument och journaler** kan du välja källdokument och journaler som ska vara föremål för budgetkontroller och om kontrollerna ska utföras på radpostnivån eller på dokumentet som helhet. 

Du bör matcha de valda källdokumenten med de kryssrutor du väljer för saldon som ingår i beräkningen av tillgängliga budgetmedel. Om du t.ex. har valt **Budgetreservationer för inteckningar**, ska du välja alternativet **Inköpsorder**. När en budgetkontroll utförs för beloppen och konton på en ett inköpsrad, är budgetkontrollkategorin som är tilldelat reservationen är **Inteckning**. När en budgetkontroll utförs för belopp och konton på en inköpsrekvisition ska kategorin som tilldelas reservationen vara **Förinteckning**. 

Om **Budgetreservationer för inteckning** och/eller **Budgetreservationer för förinteckning** ingår i beräkningen av tillgängliga budgetmedel och måste återspeglas via poster i huvudboken ska journalförd redovisning aktiveras på sidan **Allmänna redovisningsparametrar**.  

### <a name="assign-budget-models"></a>Tilldela budgetmodeller

På fliken **Tilldela budgetmodeller** tilldelar du budgetmodeller till tidsrymder för budgetcykel som ska inkluderas i budgetkontrollen.

### <a name="define-budget-control-rules"></a>Definiera budgetkontrollregler

På fliken **Definiera budgetkontrollregler** måste du skapa särskilda regler som baseras på de ekonomiska dimensioner som är aktiverade för budgetkontroll. Om det till exempel finns ett fokus baserat på en avdelnings omkostnad eller omkostnadsintervall kan du använda inställningarna för den här fliken för att definiera och utvärdera de omkostnaderna. Du kan definiera olika trösklar för varje budgetkontrollregel. 

> [!Important]
> Budgetkontrollen aktiveras för alla huvudkonto i den **resultat**, **utgift**, **intäkter, balansräkning, skulder, eget kapital** eller **tillgångar** typ. Om denna flik innehåller en regel som har tomma kriterier kommer budgetkontroll att aktiveras för **alla **ekonomiska dimensionskombinationer som innehåller huvudkonton av de typerna. Därför är det viktigt att skapa budgetkontrollregler som enbart definierar intervallen för kombinationer av ekonomiska dimensioner som är viktiga att aktivera budgetkontroll för.  

### <a name="select-main-accounts"></a>Välj huvudkonton

Om **Huvudkonto** inte markeras som en budgetkontrolldimension på sidan **Definiera parametrar**, men specifika omkostnader hanteras, kan du välja de omkostnaderna på fliken **Välj huvudkonton**. Om **Huvudkonto** markeras som en budgetkontrolldimension krävs inga poster.  

### <a name="define-budget-groups"></a>Definiera budgetgrupper

På fliken **Definiera budgetgrupper** kan du även definiera unika kombinationer av ekonomiska dimensioner där budgetresurser slås samman för sekundär budgetkontroll. Du kan skapa en enskild post som omfattar hela organisationen eller definiera flera grupper som representerar olika avdelningar eller kostnadsställen.  

### <a name="define-message-levels"></a>Definiera meddelandenivåer

Om varningsmeddelanden för budgetkontroll ska ignoreras för några användargrupper kan du ange de grupperna på sidan **Definiera meddelandenivåer**. Medlemmarna i användargruppen fortsätter att få felmeddelanden när de överskrider tillgängliga budgetmedel, baserat på deras behörigheter för överskriden budget.

### <a name="activate-budget-control"></a>Aktivera budgetkontroll

När budgetkontroll har konfigurerats kan du aktivera den på fliken **Aktivera budgetkontroll**. Utkastversionen börjar då gälla.
> [!Important]
> När budgetkontrollen är aktiverad och aktiv, och transaktioner bokförs, ska den inte vara avstängd under året. När budgetkontrollen stängs av registreras inte aktiviteter för budgetkontrolländamål och budgetkontroller utförs inte längre. Dokument som redan har bokförts kan därför inte korrekt återspegla alla avlösningsbelopp eller saldon i frågor och rapporter som är relaterade till budgetkontroll. Dessa inkluderar budgetkontrollstatistik för alla underordnade eller justerande dokument och journaler. 

Notera dessutom att transaktioner, inklusive budgetregisterposter, som har bokförts innan budgetkontrollen aktiverades inte beaktas i budgetkontrollen. Det är därför enbart lämpligt att aktivera budgetkontroll i början av en ny budgetcykel. Kontrollera att budgetsaldon för budgetregisterposter som innehåller ingående budgetsaldon för budgetkontroll uppdateras efter att budgetkontrollen aktiveras. Alla öppna dokument (t.ex. inköpsorder) ska kontrolleras med avseende på om de har tillgängliga budgetmedel och kommer att få en budgetreservation för budgetkontroll när användaren manuellt utlöser en budgetkontroll in dokumentet.

## <a name="using-budget-control"></a>Använda budgetkontroll
När budgetkontroll aktiveras kommer användarna att få varnings- och felmeddelanden för budgetkontroll i dokument och journaler som har konfigurerats för budgetkontroll. Kom ihåg du kan konfigurera budgetkontroll så att användare varnas när de överskrider budgetmedlen, men att de kan tillåtas fortsätta bekräfta eller bokföra transaktionen. Användarna kan visa information om misslyckade budgetkontroller på sidan **Budgetkontrollfel och varningar**.   

På denna sida kan användare kan gå till den **budgetkontrollstatistik periodiserat** att visa budgetinformation för tillgänglighet och reservationer för den valda kontrollen dimensionskombination. Användarna kan även titta på sidan **Budgetkontrollstatistik **för att se tillgänglig budget för alla kombinationer av ekonomisk dimension som används i budgetkontroll. 

Om budgetkontroll aktiveras för inköpsorder kan budgetchefen använda arbetsområdet **Redovisningsbudgetar och prognoser** för att granska kön för alla obekräftade inköpsorder som har varningar och fel för budgetkontroll. Om budgetchefen har behörigheter för överskriden budget kan han eller hon bekräfta inköpsorder direkt i arbetsområdet.    

