---
title: Stämma av ett bankkonto
description: I den här artikeln beskrivs hur du stämmer av ett bankkonto.
author: angelad116
ms.date: 11/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 576dcd320600f4741a43bfeee53198637bffce15
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779538"
---
# <a name="reconcile-a-bank-account"></a>Stämma av ett bankkonto

[!include[banner](../includes/banner.md)]

När du tar emot ett bankutdrag bör du regelbundet stämma av juridiska personens banktransaktioner med transaktionerna på bankutdraget.

Du kan inte stämma av ett bankutdrag med ett bankkonto om några av checkarna eller insättningskvittobetalningarna som listas på kontoutdraget har statusen **Väntar på annullering**. När en granskare bokför eller avvisar en återföring av bankcheck eller annullering av insättningskvittobetalning är statusen inte längre **Väntar på annullering** och du kan stämma av bankkontot.

1. Gå till **Kassa- och bankhantering** \> **Bankkonton** \> **Bankkonton**. Välj det bankkonto som du vill stämma av med bankutdraget och välj **stämma av** > **kontoavstämning**.

2. Ange information i fälten **bankutdragsdatum** och **bankutdrag**. I fältet **Slutsaldo** anger du saldot för bankkontot som det visas på bankutdraget.

3. Välj **transaktioner** för att öppna sidan **kontoavstämning**.

4. För varje transaktion som inkluderas i bankkontoutdraget väljer du **Reglerat** om beloppet i Dynamics 365 Finance motsvarar beloppet på bankutdraget. Du kan också ange eller ändra värdet i fältet **banktransaktionstyp**. Detta fältvärde är viktigt för statistiken över dina banktransaktioner samt för vissa rapporter.
    

>[!NOTE]
>Markera inte kryssrutan **Reglerat** för transaktioner som inte finns på bankutdraget. Dessa transaktioner visas även fortsättningsvis på den här sidan tills de har stämts av med ett kommande bankutdrag.
>Kryssrutan **Reglerat** är inte tillgänglig om transaktionen har statusen **Väntar på annullering**. En transaktion kan ha det här statusvärdet om Finance har ställts in så att återföringar eller annulleringar måste skickas för granskning innan de bokförs. När en granskare bokför eller avvisar en återföring eller annullering är statusen inte längre **Väntar på annullering** och du kan stämma av bankkontot med bankutdraget.


Om du vill välja kryssrutan **Reglerat** för ett intervall med checkar som alla visas på bankutdraget väljer du **Markera checkintervall** och anger sedan intervallet.

5.  Om beloppet för en bankkontotransaktion inte motsvarar beloppet för transaktionen på bankutdraget anger du beloppet för korrigeringen i fältet **korrigeringsbelopp**.
    

> [!NOTE]
> Om räkenskapsperioden för transaktionen som ska korrigeras har stängts, kan fältet **Korrigeringsbelopp** inte användas. Skapa då istället en rad med ett transaktionsdatum i en öppen räkenskapsperiod för korrigeringen. I det här fallet måste du lägga till de ekonomiska dimensionerna som användes på den ursprungliga transaktionen, och även motbokningshuvudkontot.



6.  Skapa transaktioner för poster som avgifter och ränta som finns på bankkontoutdraget, men som inte registrerats i Finance. Ange **banktransaktionstypen** och lämpliga ekonomiska dimensioner.

7.  När transaktionerna på bankkontoutdraget markeras som **Reglerat** närmar sig värdet i fältet **Icke avstämd** som omberäknas kontinuerligt när du gör ändringar, noll. När det närmar sig noll väljer du **Stäm av konto** för att bokföra avstämningen och de transaktioner och korrigeringar som du har skapat.
    
    När avstämningen har bokförts kan de transaktioner som har inkluderats inte längre ändras eller korrigeras och de visas inte på några fler kontoavstämningar.

8.  Om du vill visa banktransaktioner som ännu inte har stämts av använder du rapporten **ej avstämda banktransaktioner**. Om du vill visa bankutdraget för ett bankkonto använder du rapporten **bankutdrag**.

## <a name="cancel-bank-statement-reconciliation"></a>Avbryt avstämning av bankkontoutdrag 

Med funktionen Avbryt avstämning av bankutdrag kan du annullera avstämning av bankutdrag. Om du vill använda den här funktionen aktiverar du funktionen **Avbryt avstämning av bankkontoutdrag** i arbetsytan **funktionshantering**. Du måste också aktivera parametern **Tillåt redigering av bankutdrag**. För att göra detta går du till **Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering > Bankavstämning**.
 
Avstämningar av bankutdrag kan bara annulleras i kronologisk ordning som de angavs. När en avstämning av bankutdraget annulleras, kommer nya transaktioner och korrigeringar att återföras och alla andra transaktioner markeras som ej avstämda.
 
Om du vill avbryta avstämningen av bankutdraget väljer du bankutdraget och väljer **bankutdrag > Avbryt bankavstämning**. På sidan **Avbryt bankavstämning** anger du **orsakskoden**, **orsakskommentaren** och **annulleringsdatumet**. Välj **OK** för att påbörja annulleringen. Observera att annulleringsdatumet för bankutdraget måste vara på eller efter bankutdragsdatumet. När avstämningen av bankutdraget har annullerats kommer fältet **Annulleringsdatum** för bankutdraget att uppdateras med det angivna **Annulleringsdatumet**. Välj knappen **transaktioner** om du vill visa transaktionerna som avstämningen annullerades.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
