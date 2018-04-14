---
title: "Ställ upp bedrägerivarningar"
description: "Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
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
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Ställ in bedrägerivarningar

[!INCLUDE [banner](includes/banner.md)]

Det här avsnittet beskriver hur du ställer in kriterier och regler för att spärra misstänkt bedrägliga försäljningsorder för vidare undersökning. Funktionen för bedrägerigranskning används för att avgöra informationens giltighet i en försäljningsorder. Om informationen i försäljningsordern verkar vara tveksam utifrån organisationens regler och kriterier för bedrägeri, ordern kan spärras för vidare undersökning av en administratör.

> [!NOTE]
> Funktionen kan endast användas med Retail kundtjänstkanal för bearbetning av försäljningsorder. 

När kundtjänstkanalen definieras måste **aktivera slutförande av order** anges till **Ja**. När slutförande av order är aktiverad kan användare visa ordersammanfattning och klicka på **skicka** för att slutföra ordern. Användarna får även alternativ för att manuellt spärra försäljningsordern för bedrägerigranskning. Försäljningsorder som matas in av en kundtjänstanvändare bearbetas via bedrägerikontrollregler och kriterier under sändningsprocessen.

Det finns två typer av bedrägerikriterier som systemet ska referera till för att kontrollera om ordern ska spärras för bedrägerigranskning:

-   **Statistikregler** använd ett specifikt värde, till exempel ett telefonnummer som har blivit svartlistat eller en e-postadress har flaggats som använt för tidigare bedrägliga transaktioner. På sidan **Statiska bedrägeridata**, kan bedrägeriinformation läggas till manuellt eller genom dataimport med poäng kopplade till den bedrägliga informationen. Alla försäljningsorder som angetts ska jämföras med statiska data om kontroll av bedrägeri är aktiverat. Om det finns data i kundens faktureringsadress eller leveransadress eller data i leveransadressen som angetts på försäljningsraden ska resultatet för alla unika träffar summeras.  
-   **Dynamiska regler** består av variabler och villkoren för dessa variabler. Andra kriterier som inte har definierats i de statiska reglerna kan kontrolleras med dynamiska regler. Mer komplexa ”OCH/ELLER”-utdrag kan användas för att beakta flera villkor för att avgöra om det finns en positiv matchning mot regelvillkoren och försäljningsordern som har skickats. Till exempel om en användare vill hålla för granskning alla order för kunder som är kopplade till ett visst kundgruppvärde och som har beställt en specifik produkt, kan villkoren för att validera kunden och validera produkterna definieras på sidan **Regler** med ett ”OCH”-villkor. Ordern skulle endast spärras för bedrägeri om båda villkoren stämmer och om poängvärdet som tilldelats regeln sätter orderns totala bedrägeripoäng över minsta bedrägeripoängen enligt kundtjänsts parametrar.

En kundtjänstanvändare användaren kan manuellt placera en order i kön för spärrad för bedrägeri. Om användaren som anger ordern anser att kunden som gör ordern är misstänkt och vill att någon ska granska orderns giltighet ytterligare innan den behandlas, kan den användare som anger ordern välja alternativet **Manuell spärr för bedrägeri** från listrutan **Spärrar** på sidan **Sammanfattning av försäljningsorder** (visas efter att orderfunktionen **komplett** kallas). Användaren uppmanas att ange en notering som ytterligare förklarar varför de anser att ordern kan vara bedräglig så att granskaren har mer sammanhang.

Alla ordrar som hålls under manuell bedrägerispärr eller genom systematiska beräkningar av bedrägeriresultat på sidan **orderspärrar** kan granskas och sedan antingen annulleras eller frisläppas för bearbetning.

> [!NOTE]
> Användning av flera regler eller alltför komplexa regler leder till dålig systemprestanda när försäljningsorder skickas. Funktionen bedrägerivarning har inte optimerats för att hantera ett stort antal poster av statiska bedrägeridata och många aktiva regler. Det är viktigt att komma ihåg att varje regel utvärderas under funktionen skicka vid kundtjänst försäljningsorderregistrering. Reglerna utvärderas mot försäljningsorderrubriken och alla orderrader. Det finns flera regler och desto komplexare regelsatser desto längre tid tar de att behandla. Om du har ett stort antal radposter i ordern och ett stort antal aktiva regler och statiska dataposter kan den systematiska processen av att granska och validera alla data och beräkna bedrägeripoäng påverka prestanda.  Organisationer som använder den här funktionen ska alltid testa och bekräfta att bearbetningstiden ordersändning är godtagbar innan du tillämpar ändringar i regler eller kriterier för statiska bedrägerivillkor i produktionsmiljön.

