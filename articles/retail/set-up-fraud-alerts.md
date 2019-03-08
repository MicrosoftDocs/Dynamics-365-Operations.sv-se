---
title: Ställa in och arbeta med bedrägerivarningar för kundtjänst
description: Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som används automatiskt eller manuellt för att spärra misstänkta order.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 13b6a18750e79a17c7f6034780922c64b12390e2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "361508"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Ställa in och arbeta med bedrägerivarningar för kundtjänst

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver hur du ställer in kriterier och regler för att spärra misstänkt bedrägliga försäljningsorder för vidare undersökning. Funktionen för bedrägerigranskning används för att avgöra informationens giltighet i en försäljningsorder. Om informationen i försäljningsordern verkar vara tveksam utifrån organisationens regler och kriterier för bedrägeri, ordern kan spärras för vidare undersökning. Då kan inte ordern frisläppas till distributionslagret för vidare bearbetning förrän spärren har tagits emot.

> [!NOTE]
> Funktionen kan endast användas med bearbetning av försäljningsorder för Retail kundtjänstkanal.

## <a name="turning-on-the-fraud-check-feature"></a>Slå på funktionen för bedrägerikontroll

Om du vill använda funktionen bedrägerikontroll måste du ange alternativet **aktivera slutförande av order** till **Ja** när kundtjänstkanalen är [definieras](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-order-processing-options). När ordern är klar aktiveras måste kundtjänstanvändare välja **komplett** på försäljningsordersidan för alla försäljningsorder som skapas. Slutföringsåtgärden gör att sidan **Sammanfattning av försäljningsorder** att öppnas. När användare skriver betalningsdata på sidan **Sammanfattning av försäljningsorder** kan de välja att **skicka** för att slutföra ordern. När ordern har skickats kommer funktionen bedrägerikontroll utlöses de regler som är aktiva i systemet verifieras automatiskt

Kundtjänstanvändare kan även manuellt spärra försäljningsorder för bedrägerigranskning innan de väljer **skicka**. För att manuellt spärra en försäljningsorder, på sidan **Sammanfattning av försäljningsorder** väljer du **Spärra**\>**manuell bedrägerispärr**. Därefter uppmanas du att ange en kommentar som förklarar orsaken till att ordern spärrats. Kommentaren visas i workbench [order spärrar](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) för att ge kontexten för den användare som granskar ordern som är spärrad för att bestämma om ordern ska frisläppas.

Förutom att konfigurera alternativet **Aktivera slutförande av order** på kanalen måste du konfigurera funktionen för bedrägerikontroll i parametrarna för kundtjänst. Gå till **Retail**\>**kanalinställning**\>**inställning av kundtjänst**\>**parametrar för kundtjänst**. På sidan **parametrar för kundtjänst** på fliken **spärrar** anger du alternativet **bedrägerikontroll** till **Ja**.

På fliken **spärr** bör du även definiera [spärrkoder](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) som ska kopplas till en order som är manuellt eller automatiskt spärrad för bedrägerigranskning. Ange spärrkoder i fälten **Manuell spärrkod för bedrägeri** och **Spärrkod för bedrägeri**. Det är praktiskt att skapa två unika spärrkoder så att användare som arbetar i spärrworkbench snabbt kan filtrera och skilja automatiska spärrar från manuella spärrar.

För att funktionen bedrägericheck ska fungera effektivt måste du också ange fältet **lägsta poäng**. Varje bedrägerivillkor och regler som definieras i systemet har ett poäng. När en försäljningsorder kontrolleras för bedrägeri, om en eller flera matchningar påträffas läggs poängen ihop för att ge ordern ett totalt bedrägeripoäng. Om totalt bedrägeripoäng för en order överstiger värdet i fältet **lägsta poäng** spärras ordern automatiskt. Du kan även använda andra resultatrelaterade fält på fliken **spärrar** för att ange poängen för e-post, telefonpoäng, postnummerpoäng och utökade postnummerpoäng. Om du inte anger poäng för någon av dessa statiska bedrägerikriterier när du definierar dem på sidan **Statiska bedrägeridata** kommer systemet att ge dem poäng med hjälp av standardpoängen som du anger på fliken **spärrar** på sidan **Parametrar för kundtjänst**.

Använd slutligen fältet **bedrägerikommentarstyp** för att ange dokumenttypen som ska användas när användarna ska ange kommentarer när de manuellt spärrar en order för granskning av bedrägeri. Oftast anges det här fältet till **Notering**.

## <a name="defining-fraud-criteria-and-rules"></a>Definiera regler och kriterier för bedrägeri

Systemet hänvisar till två typer av bedrägerikriterier för att avgöra om en order ska spärras för bedrägerigranskning:

- **Statiska bedrägeridata** använder ett specifikt värde, till exempel ett telefonnummer som har placerats i en lista över spärrade nummer eller en e-postadress har flaggats eftersom den har använts för tidigare falsk transaktioner. Konfigurera statiska bedrägeridata genom att gå till **Retail**\>**kanal**\>**kundtjänstinställningar**\>**bedrägeri**\>**statiska bedrägeridata**. På sidan **statiska bedrägeridata** kan du lägga till kriterier för bedrägeri manuellt eller genom dataimport. Poängen är kopplade till falsk information. Om funktionen bedrägerikontroll ska aktiveras kommer varje försäljningsorder som anges att jämföras med statiska data. Om det finns data i kundens faktureringsadress eller leveransadress som är kopplad till orderrubriken eller om det finns data i leveransadresser som är kopplade till alla rader på försäljningsordern läggs alla unika matchningar ihop och jämförs med värdet **lägsta poäng** för att bestämma om ordern ska spärras eller inte.
- **Regler för bedrägeri** består av användardefinierade variabler och de villkor som har definierats för dessa variabler. Du kan skapa regler genom att gå till **Retail**\>**kanalinställningar**\>**kundtjänstinställningar**\>**bedrägeri**\>**regler**. Bedrägeriregler låter ett företag konfigurera en mer komplex regeluppsättning och kan innehålla **AND** eller **OR** -satser och utvärdera flera villkor. Till exempel vill en användare att alla order för kunder som tillhör en viss kundgrupp och som beställde en viss produkt ska spärras för att bedrägerigranskning. I detta fall definieras villkoren för att validera kund och produkter på sidan **regler** sida och ett AND-villkor används. En order spärras sedan bara om båda villkoren har uppfyllts och om poängvärdet som tilldelas denna regel överstiger poängvärdet för alla andra regler som ordern matchar orsakar orderns totala bedrägeripoäng att överstiga värdet **lägsta poäng** som definieras på sidan **parametrar för kundtjänst**.

> [!NOTE]
> Flera regler eller alltför komplexa regler påverkar systemprestanda när försäljningsorder skickas. Funktionen bedrägerikontroll har inte optimerats för att hantera ett stort antal poster av statiska bedrägeridata och många aktiva regler. Kom ihåg att varje regel beräknas när kundtjänstanvändarna väljer **skicka** vid registrering av försäljningsorder. Reglerna utvärderas mot försäljningsorderrubriken och alla orderrader. Det finns flera regler och desto komplexare regelsatser desto längre tid tar de att behandla. Om det finns många rader i en order och många aktiva regler och statiska uppgifter, kan den automatiska processen att granska och validera alla data och beräkna ett bedrägeribalans få en stor inverkan på prestanda. Organisationer som använder den här funktionen ska alltid testa och bekräfta att bearbetningstiden ordersändning är godtagbar innan du tillämpar ändringar i regler eller kriterier för statiska bedrägerivillkor i produktionsmiljön.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identifierae order som är spärrade för bedrägerigranskning

När kundtjänstanvändare skickar en försäljningsorder om ordern matchar bedrägerikriterier eller regler och poängen överstiger lägsta värdet visas ett varningsmeddelande som uppger att ordern har spärrats. Användare kan stänga det här meddelandet eftersom det är bara avsett för information. Användare kan även överlämna dessa uppgifter till kunden. Företaget bör fastställa protokoll som användarna ska följa i det här fallet.

Ordern har sparats, men flaggan **bearbeta inte** anges på den. Den här flaggan kan garantera att ordern frisläpps till lagret. Användare kan när som helst visa inställningen för flaggan **bearbetar inte** för varje försäljningsorder på sidan **detaljerad status**. Den här sidan kan öppnas från sidorna **alla försäljningsorder** och **kundtjänst**. Systemet uppdaterar även värdet på fältet **detaljerad status** för att **bedrägerispärr**.

Om du vill visa och hantera de order som är spärrade för granskning, gå till **Retail**\>**kunder**\>**Orderspärrar**. På sidan **Orderspärrar** markerar du en post i listan och klickar sedan på **Orderspärr** för att se en mer detaljerad vy som innehåller information om orsaken till spärren. På snabbfliken **bedrägeridetaljer** kan du se systematiskt bedrägerikriterie som befanns vara en matchning för ordern och poäng som har använts. Om ordern har spärrats manuellt, kan du granska eventuella kommentarer som angavs av användaren som spärrats ordern genom att titta på avsnittet **bedrägerianteckningar** på snabbfliken **anteckningar**.

Mer information om hur du arbetar med spärra order, se [orderspärrar](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds).
