---
title: Betalningsmetoder i kundcenter
description: Det här avsnittet beskriver olika betalningsmetoder som du kan använda i en kundtjänst i Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 551a3cc9c0def1c67ab930dbff7cd1c0d296bd21
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018238"
---
# <a name="payment-methods-in-call-centers"></a>Betalningsmetoder i kundcenter

[!include [banner](includes/banner.md)]

I Dynamics 365 Retail innehåller konfigurationen av kundtjänst en inställning som heter **Aktivera slutförande av order**. Den här inställningen hjälper till att garantera att alla order som användare av kanalen skapar endast släpps till orderbearbetning om de har en förauktoriserad betalning inom godkända toleranser. Om inställningen **Aktivera slutförande av order** är aktiv, kan kundtjänstanvändarna ange betalningar mot försäljningsorder för kunder genom att använda kundtjänsts funktioner för betalningsprocess. Om inställningen är inaktiverad kan kundtjänstanvändare inte använda kundtjänsts funktioner för betalningsprocessen, men de kan fortfarande använda förskottsbetalningar på försäljningsorder med hjälp av standardfunktionen för Kundreskontra.

Som en del av kanalkonfigurationen kan ett företag definiera de betalningsmetoder som ska tillåtas för en kundtjänstkanal. Kundtjänstkanalen använder samma betalningsmetoder som har definierats för butikskanalerna.

Konfigurera betalningsmetoder för en kundtjänstkanal genom att gå till **Butik**\>**Kanaler**\>**Kundtjänst**\>**Alla kundtjänster**, och sedan på den **Ställ in** väljer du alternativet **Betalningsmetoder**.

Det finns fem funktioner för betalning som du kan tilldela när du skapar en betalningsmetod.

| Funktion            | beskrivning |
|---------------------|-------------|
| Normal              | Använd funktionen **Normal** på betalningsmetoden när du definierar betalningsmetoder såsom kontanter eller verifikationer. När dessa typer av betalningar används för en försäljningsorder i kundtjänst kommer flaggan **Förskottsbetala** att visas som standard **Ja**. Detta kommer i stället att omedelbart bokföra en förskottsbetalningsverifikation till kundkontot när produktionsordern har skickats. Användare kan ändra flaggan **Förskottsbetala** till **nr** om så önskas så att betalningsverifikationen inte har skapats innan du bokför fakturan. Förskottsbetalningsverifikationen bokförs i kundens transaktionshistorik där den kvittas systematiskt mot fakturan för försäljningsordern. |
| Check               | Använd funktionen **Check** när du definierar en bankcheck som betalningsmetod. När den här typen av betalning används till en försäljningsorder, måste användaren ange kundens checknummer som en del av betalningsprocessen. Kontrollera att betalningar alltid behandlas som förskottsbetalningar när de tillämpas och betalningsverifikationer skapas direkt när beställningen gjordes. Dessa förskottsbetalningsverifikationer kvittas systematiskt mot fakturor som har skapats för ordern. |
| Kort               | Kortbetalningstyperna representerar alla typer av betalning som kräver registrering av ett kortnummer som har definierats på kundens betalkort. Exempel är kreditkort och presentkort. När du konfigurerar sådana betalningar, måste du använda menyn **Kortinställningar** för att definiera de kort-ID som associeras med den här betalningsmetoden. Vid tidpunkten för orderregistrering kan användarna ange om kortbetalningen ska betalas i förväg, med hjälp av alternativet **Förskottsbetala** som visas på sidan för betalningsposten. Om inte verksamheten kräver förskottsbetalningar, är det normala flödet för en sann kreditkortsbetalning en tvåstegsprocess där tillstånd erhålls vid tidpunkten för orderregistreringen och sedan kvittas betalningen från kundens kort vid tidpunkten för fakturering. Vid presentkortbetalningar rekommenderas förskottsbetalning eftersom presentkortssaldot omedelbart bör minskas så att kunden inte kan använda samma värde någon annanstans. |
| Kund            | **Kundfunktionen** på en betalningsmetod innebär att betalningen tillämpas på kundens kreditgräns eller sätts på ” à conto”. I Retail kan en kund tilldelas en kreditgräns som kan valideras vid tidpunkten för orderregistreringen. Betalningar som har gjorts med en betalningsmetod som är kopplad till funktionen **Kund** skapar en skuld mot kundens konto. När försäljningsordern faktureras visas sedan ett förfallet saldo. I sådana fall måste skickar kunden vanligtvis en betalning enligt villkoren som har tilldelats. Alternativt kan en föregående öppen kreditverifikation på kundens konto användas om du vill kvitta saldot som förfaller. Observera att även om du definierar den här betalningsmetoden visas den inte bland betalningsalternativen i orderregistrering för kundtjänst om inte flaggan **Tillåt à conto** anges i kundposten för kunden som du arbetar med. Den här flaggan finns på fliken **Standardvärden för betalningar** för kundposten. |
| Betalningsmedelborttagning/växelkassa | Funktionen **Betalningsmedelborttagning/växelkassa** används inte av kundtjänst. Den gäller bara när du definierar betalningsmetoderna som butiksprogrammet använder i en butikskanal. |

När betalningsmetoder definieras ska de länkas till ett redovisnings- eller bankkonto. Om du hoppar över det här steget visas fel när de försöker spara betalningstypen.

## <a name="refund-payment-methods"></a>Betalningsmetod för återbetalning

För scenarier för bearbetning av återbetalning använder kundtjänst även vissa av de betalningsmetoder som definierats i Kundreskontra. Om du vill konfigurera dessa betalningsmetoder, gå till **Butik**\>**Kanalinställning**\>**Kundtjänstinställning**\>**Återbetalningsmetoder för kundtjänst**. Du måste slutföra den här konfigurationen om du vill bearbeta återbetalning av checkar till kunder. Exempelvis om en kund ursprungligen har betalat för en order med kontanter eller check kanske användaren vill skicka kunden en återbetalningscheck via Kundreskontra. I det här fallet måste betalningstyperna kontanter och check i kundtjänst mappas till korrekt betalningsmetod i Kundreskontra för att säkerställa att återbetalningen behandlas på rätt sätt.

Dessutom, om en användare bearbetar en returorder som en kundtjänstanvändare i Retail men han eller hon inte kan länka returen till en ursprunglig försäljning måste betalningsmetoden **Retur** definieras i kundtjänstparametrarna. Gå till **Butik**\>**Kanalinställning**\>**Kundtjänstinställning**\>**Kundtjänstparametrar** och sedan till fliken **RMA/retur** i fältet **Betalningsmetod** och se till att du har angett en betalningsmetod. Betalningsmetoden kommer att bli den betalningsmetod som används för återbetalningar. Vanligtvis definieras den som antingen en checkmetod eller en kundkontometod.
