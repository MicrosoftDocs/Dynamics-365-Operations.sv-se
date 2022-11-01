---
title: Automatisera redovisningskvittning
description: Den här artikeln innehåller information om automatisera redovisningskvittningsprocess.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708338"
---
# <a name="automate-ledger-settlements"></a>Automatisera redovisningskvittning

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics 365 Finance version 10.0.31, funktionen  **Automatisera redovisningskvittningsprocess** är tillgänglig i arbetsytan  **Funktionshantering** . Du kan bara aktivera funktionen **Automatisera redovisningskvittningsprocess** om **Medvetenhet mellan redovisningskvittning och årsbokslut** är aktiverad.

Redovisningskvittning är processen för att matcha debet- och kredittransaktioner i huvudboken. Organisationer som utför redovisningskvittningsaktiviteter på ett återkommande schema kan nu automatisera processen. Under den automatiska redovisningkvittningsprocessen kan en debettransaktion och en kredittransaktion bara matchas automatiskt om deras belopp i redovisningsvalutan är lika.Till exempel kan ett debetbelopp $1,00 matchas automatiskt mot ett kreditbelopp på $1,00. Ett debetvärde på $1,00 kan emellertid inte automatiskt matchas mot två kredit, som värderas till $0,50. Delvis matchning av redovisningstransaktionsbelopp som inte stöds.

I redovisningskvittningsautomatisering definieras följande information:

- När redovisningskvittningar körs
- Vilka kriterier som används för att matcha debet- och kreditbelopp som kan kvittas automatiskt
- Vilken ordning som redovisningskvittningsinformationen bearbetas i

## <a name="define-the-occurrence-of-ledger-settlements"></a>Definiera förekomsten av redovisningskvittningar

Redovisningskvittningsautomatisering använder ramverket Processautomatisering. Olika affärsprocesser använder det här ramverket för att definiera upprepningen av en vald process. För redovisningskvittningar, gå till  **Systemadministration \> Inställning \> Processautomatisering** eller **Redovisning \> Redovisningsinställning \> Processautomatisering**.

Använd först alternativet  **Skapa ny processautomatisering** och markera  **Redovisningskvittningar**. En guide vägleder dig genom processen att ställa in automatisering.

## <a name="general-page"></a>Sidan allmänt

På sidan  **Allmänt**  i guiden anger du namnet på redovisningskvittning som du skapar. Till exempel, om dina matchande debiteringar och krediter är redovisningsreglerade på måndag, ange ett beskrivande namn som t.ex. **LedgerSettle\_Mon**. Namnet du anger visas i kolumnen **Automationsregel** på sidan  **Redovisningkvittning** .

De återstående inställningarna på sidan är allmänna definierar förekomstmönstret för den här versionen av redovisningskvittningar. Om en förekomst t.ex. är för måndag kan du definiera den så att den körs varje vecka och välja måndag som veckodag när den körs. Du kan också ange en tidig planeringstid, t.ex. kl. 02:00 så att processautomatiseringen slutförs innan nästa arbetsdag börjar. Vi rekommenderar att du tidsplanerar processautomatiseringen så att den utförs utanför dina normala arbetstider. På det här sättet minskar du påverkan på redovisningspersonalen under arbetsdagen.

Mer information om de övriga fälten på sidan  **Allmänt**  finns i dokumentationen för processautomatisering.

## <a name="ledger-settlements-match-criteria-page"></a>Sida för matchningsvillkor för redovisningskvittningar

Nästa sida i guiden är sidan  **Redovisningskvittningar**  matchar kriterier. Den används för att definiera huvudkontona som ingår i processautomatisering förekomsten och de kriterier som används för att bestämma matchande debet och kredit.

### <a name="account-selection"></a>Kontomarkering

Huvudkontona som du tidigare har definierat som redovisningskvittningskonton för den juridiska personen visas. (Du definierar huvudkonton som konton för redovisningskvittning på **Redovisning \> Redovisningsinställning \> Allmänna huvudboksparametrar \> Redovisningskvittning**.)

### <a name="main-account-and-posting-layer"></a>Huvudkonto och bokföringsskikt

Värdena  **huvudkonto** och **bokföringsskikt** måste matchas. Värden **Huvudkonto** och **Bokföringsskikt** av redovisningen debettransaktion och kredittransaktion måste vara lika för att matchas under den automatiska redovisningkvittningsprocessen.

### <a name="posting-type"></a>Bokföringstyp

Välj alternativet **bokföringstyp** om redovisningens debet- och kredittransaktioner måste ha samma bokföringstyp för att matchas under processen för automatiska redovisningskvittningar.

### <a name="financial-dimensions"></a>Ekonomiska dimensioner

Välj alternativet **ekonomiska dimensioner** om redovisningens debet- och kredittransaktioner måste ha samma ekonomiska dimensioner för att matchas under processen för automatiska redovisningskvittningar. När det här alternativet är valt måste kriterierna för ekonomiska dimensionsvärden väljas i listan **Tillgängliga ekonomiska dimensioner**. Listan **Tillgängliga ekonomiska dimensioner** innehåller inte huvudkontodimensionen, eftersom den automatiskt krävs som en del av matchningskriteriet.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Visa resultaten av en automatisering av redovisningskvittning

Efter att automatisering av redovisningskvittning skapats visas förekomsterna för varje redovisningskvittning i veckovy för processautomatisering. Dessutom visas status för varje förekomst. Följande statusvärden används:

- **Planerad** – Automatiseringen är planerad, men den har inte körts ännu.
- **Kör** – Automatiseringen körs för tillfället.
- **Fel** – Automatiseringen har körts, men ett fel uppstod. Du kan visa felen genom att välja knappen  **Visa resultat** .
- **Slutfört** – Automatiseringen har körts framgångsrikt. Du kan visa kvittningsresultaten på sidan **Redovisningskvittningar**.

Om du vill visa matchningsresultaten går du till **Redovisning \> Periodiska uppgifter \> Redovisningskvittningar**. Fältet **Automationsregel** på sidan **Redovisningskvittningar** visar namnet på den schemalagda schemalagda uppgiften för automatiserad redovisningskvittning som användes för att kvitta transaktionen. Misslyckat kvittningsförsök uppdaterar inte värdet för **automationsregeln**. Om du återför en transaktion som tidigare kvittats manuellt genom automationsprocessen tas värdet för **automationsregeln** bort.

Fältet **Kvittningsdatum** för matchade poster visar datumet när automatiseringsprocessen utfördes.

## <a name="editing-a-ledger-settlement-automation"></a>Redigera automatisering av redovisningskvittning

Med ramverk för processautomatisering kan du redigera serien och de händelser som skapas för redovisningskvittning. Serien kan redigeras från sidan  **Processautomatisering**  eller veckovis visning av processens automatisering. Om till exempel chefen bestämmer sig för att utföra redovisningskvittning på onsdag, i stället för måndag, kan han eller hon hitta en förekomst i vyn vecka och välja  **Visa/redigera – serie**.

Om du redigerar en serie uppmanas du att ange om ändringen ska göras för alla befintliga förekomster eller bara för nya förekomster. Historiska händelser som redan har statusen **slutförd** eller som slutade i  **fel**  status ändras inte.

Du kan också lägga till en ny förekomst eller ändra en befintlig förekomst. Nästa exempel på redovisningskvittning är inställt på onsdag 1 januari, men detta datum är en helgdag. Du kan ändra förekomsten från antingen sidan **processautomatisering** eller den veckovisa vyn för processautomatisering. En sida öppnas som visar schemainformation och matchningsvillkor. Här kan du redigera den planerade tiden och det aktuella datumet. Du kan även redigera matchningsvillkor om det behövs ändringar. 

Du kan också inaktivera en förekomst eller en serie. Om du vill inaktivera en förekomst och avbryta bearbetningen av den markerar du den i vyn bearbeta en veckovis process och väljer  **inaktivera**. Du kan inaktivera en serie på sidan **processautomatisering** .

## <a name="security-for-ledger-settlement-automation"></a>Säkerhet för automatisering av redovisningskvittning

Behörigheten **Underhåll inställningar för automationsserie för redovisningskvittningar** har lagts till rollerna redovisningschef och redovisningsansvarig och **Visa inställningar för automationsserie för redovisningskvittningar** har lagts till rollerna revisor, redovisningschef och redovisningsansvarig för automatisering av redovisningskvittningar. Dessa uppgifter är standardsäkerhetsinställningar, men de kan ändras utifrån organisationens krav.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Redovisningsparametrar för automatisk redovisningskvittning

Fältet **Typisk kvittningsbalans** visar i vilken ordning den automatiska redovisningskvittningen kommer att bearbetas. För att ställa in eller visa **Typisk kvittningsbalans**, gå till **Redovisning \> Inställningar \> Redovisningsparametrar** och välj flik **Redovisningskvittningar**.

Om **Debet** har valts startar den automatiska redovisningskvittningsprocessen på debetsidan och söker efter motsvarande kredit. Om **Kredit** har valts startar den automatiska redovisningskvittningsprocessen på kreditsidan och söker efter motsvarande debet. Det här alternativet ska återspegla huvudkontots typiska saldo.

## <a name="processing-a-ledger-settlement-automation"></a>Bearbeta automatisering av redovisningskvittning

När automationen körs väljer systemet redovisningstransaktioner för de huvudkonton som har definierats för processautomatiseringsserien. I programmet beställer den transaktionerna efter datum med ett datumintervall från räkenskapsårets början till det datum då processautomatisering körs. Den matchar baserat på det angivna matchningskriteriet. De absoluta värdena för debetbeloppen i redovisningsvalutan och kredit måste matcha för kvittning.

När ett huvudkonto bearbetas av en förekomst av en redovisningskvittning, kan du inte visa det på sidan **Redovisningskvittningar**. Du måste vänta tills automatiseringsprocess är klar. Vi rekommenderar att du schemalägger den processautomatisering som ska köras utanför arbetstid för att förhindra konflikter.

Automationsprocessen omfattar alla transaktioner som uppfyller kriterierna, utom transaktioner som har markerats manuellt för kvittning på sidan **Redovisningskvittning**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Återföring av transaktioner som kvittas med automationsprocessen

Du kan återföra en kvittning som har gjorts av den automatiska redovisningsprocessen. När en transaktion som avvecklades av automatiseringsprocessen återförda tas **automationsregeln** bort.
