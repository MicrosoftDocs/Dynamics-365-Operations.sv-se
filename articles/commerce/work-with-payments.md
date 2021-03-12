---
title: Betalsätt i kundcenter
description: Det här avsnittet beskriver olika betalsätt som du kan använda i en kundtjänst i Dynamics 365 Commerce.
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
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8fede81aa8c61eddba72b9ba2e780d61731f8253
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989263"
---
# <a name="payment-methods-in-call-centers"></a>Betalsätt i kundcenter

[!include [banner](includes/banner.md)]

I Dynamics 365 Commerce innehåller konfigurationen av kundtjänst en inställning som heter **Aktivera slutförande av order**. Den här inställningen hjälper till att garantera att alla order som användare av kanalen skapar endast släpps till orderbearbetning om de har en förauktoriserad betalning inom godkända toleranser. Om inställningen **Aktivera slutförande av order** är aktiv, kan kundtjänstanvändarna ange betalningar mot försäljningsorder för kunder genom att använda kundtjänsts funktioner för betalningsprocess. Om inställningen är inaktiverad kan kundtjänstanvändare inte använda kundtjänsts funktioner för betalningsprocessen, men de kan fortfarande använda förskottsbetalningar på försäljningsorder med hjälp av standardfunktionen för Kundreskontra.

Som en del av kanalkonfigurationen kan ett företag definiera de betalsätt som ska tillåtas för en kundtjänstkanal. Kundtjänstkanalen använder samma betalsätt som har definierats för kanalerna.

Konfigurera betalsätt för en kundtjänstkanal genom att gå till **Butik och handel** \> **Kanaler** \> **Kundtjänst** \> **Alla kundtjänster**, och sedan på den **Ställ in** väljer du alternativet **Betalsätt**.

Det finns fem funktioner för betalning som du kan tilldela när du skapar ett betalsätt.

| Funktion            | beskrivning |
|---------------------|-------------|
| Normal              | Använd funktionen **Normal** på betalsättet när du definierar betalsätt såsom kontanter eller verifikationer. När dessa typer av betalningar används för en försäljningsorder i kundtjänst kommer flaggan **Förskottsbetala** att visas som standard **Ja**. Detta kommer i stället att omedelbart bokföra en förskottsbetalningsverifikation till kundkontot när produktionsordern har skickats. Användare kan ändra flaggan **Förskottsbetala** till **nr** om så önskas så att betalningsverifikationen inte har skapats innan du bokför fakturan. Förskottsbetalningsverifikationen bokförs i kundens transaktionshistorik där den kvittas systematiskt mot fakturan för försäljningsordern. |
| Check               | Använd funktionen **Check** när du definierar en bankcheck som betalningsmetod. När den här typen av betalning används till en försäljningsorder, måste användaren ange kundens checknummer som en del av betalningsprocessen. Kontrollera att betalningar alltid behandlas som förskottsbetalningar när de tillämpas och betalningsverifikationer skapas direkt när beställningen gjordes. Dessa förskottsbetalningsverifikationer kvittas systematiskt mot fakturor som har skapats för ordern. |
| Kort               | Kortbetalningstyperna representerar alla typer av betalning som kräver registrering av ett kortnummer som har definierats på kundens betalkort. Exempel är kreditkort och presentkort. När du konfigurerar sådana betalningar, måste du använda menyn **Kortinställningar** för att definiera de kort-ID som associeras med den här betalsättet. Vid tidpunkten för orderregistrering kan användarna ange om kortbetalningen ska betalas i förväg, med hjälp av alternativet **Förskottsbetala** som visas på sidan för betalningsposten. Om inte verksamheten kräver förskottsbetalningar, är det normala flödet för en sann kreditkortsbetalning en tvåstegsprocess där tillstånd erhålls vid tidpunkten för orderregistreringen och sedan kvittas betalningen från kundens kort vid tidpunkten för fakturering. Vid presentkortbetalningar rekommenderas förskottsbetalning eftersom presentkortssaldot omedelbart bör minskas så att kunden inte kan använda samma värde någon annanstans. |
| Kund            | **Kundfunktionen** på ett betalsätt innebär att betalningen tillämpas på kundens kreditgräns eller sätts på ” à conto”. I Commerce kan en kund tilldelas en kreditgräns som kan valideras vid tidpunkten för orderregistreringen. Betalningar som har gjorts med ett betalsätt som är kopplad till funktionen **Kund** skapar en skuld mot kundens konto. När försäljningsordern faktureras visas sedan ett förfallet saldo. I sådana fall måste skickar kunden vanligtvis en betalning enligt villkoren som har tilldelats. Alternativt kan en föregående öppen kreditverifikation på kundens konto användas om du vill kvitta saldot som förfaller. Observera att även om du definierar den här betalsättet visas den inte bland betalningsalternativen i orderregistrering för kundtjänst om inte flaggan **Tillåt à conto** anges i kundposten för kunden som du arbetar med. Den här flaggan finns på fliken **Standardvärden för betalningar** för kundposten. |
| Betalningsmedelborttagning/växelkassa | Funktionen **Betalningsmedelborttagning/växelkassa** används inte av kundtjänst. Den gäller bara när du definierar betalsätten som butiksprogrammet använder i en butikskanal. |

När betalsätt definieras ska de länkas till ett redovisnings- eller bankkonto. Om du hoppar över det här steget visas fel när de försöker spara betalningstypen.

## <a name="refund-payment-methods"></a>Betalningsmetod för återbetalning

För scenarier för bearbetning av återbetalning använder kundtjänst även vissa av de betalsätt som definierats i Kundreskontra. Om du vill konfigurera dessa betalsätt, gå till **Butik och handel** \> **Kanalinställning** \> **Kundtjänstinställning** \> **Återbetalsätt för kundtjänst**. Du måste slutföra den här konfigurationen om du vill bearbeta återbetalning av checkar till kunder. Exempelvis om en kund ursprungligen har betalat för en order med kontanter eller check kanske användaren vill skicka kunden en återbetalningscheck via Kundreskontra. I det här fallet måste betalningstyperna kontanter och check i kundtjänst mappas till korrekt betalningsmetod i Kundreskontra för att säkerställa att återbetalningen behandlas på rätt sätt.

Dessutom, om en användare bearbetar en returorder som en kundtjänstanvändare i Commerce men han eller hon inte kan länka returen till en ursprunglig försäljning måste betalsättet **Retur** definieras i kundtjänstparametrarna. Gå till **Butik och handel** \> **Kanalinställning** \> **Kundtjänstinställning** \> **Kundtjänstparametrar** och sedan till fliken **RMA/retur** i fältet **Betalningsmetod** och se till att du har angett ett betalsätt. Betalsättet kommer att bli det betalsätt som används för återbetalningar. Vanligtvis definieras den som antingen en checkmetod eller en kundkontometod.
