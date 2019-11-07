---
title: Redigera och granska butikstransaktioner
description: I det här avsnittet beskrivs funktionerna för att redigera och granska butikstransaktioner.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0201d31cd83b4360f96a7d8e2113caf9d913715
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622537"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Redigera och granska butikstransaktioner

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Dynamics 365 Retail‑kunder använder såväl förstaparts som tredjeparts kassaprogram. Kassaprogrammet från första part hämtar butikstransaktionerna till Retail Headquarters från kanalerna via en batchprocess. Programmet från tredje part hämtar transaktionerna till Retail Headquarters via integration. Efter att transaktionerna har hämtats till Retail Headquarters måste i båda fallen en konsekvenskontroll utföras som kör flera valideringar på transaktionerna så att bara felvaliderade transaktioner hämtas till utdraget som ska bokföras i Retail Headquarters. 

Butikstransaktionerna kunde inte valideras av olika orsaker. Till exempel kan ett programfel i integrationskoden eller i kassaprogrammet orsaka inkonsekventa data, liksom ett användarfel som att ta bort en produkt efter att den synkroniserats till kanalen eller stänga en räkenskapsperiod utan att bokföra butikstransaktionerna för perioden.

Även om transaktionerna flaggas och exkluderas från utdragen kan transaktionerna störa en kunds dagliga bokföring av butiksförsäljning.

I Retail kan du redigera de specifika butikstransaktioner som inte kan valideras samtidigt som du upprätthåller granskningen av alla ändringar. 

## <a name="edit-and-audit-transactions"></a>Redigera och granska transaktioner

I Retail version 10.0.5 är hämtköpstransaktioner de enda transaktioner som kan redigeras. Redigering av kundorder eller onlinebeställningar stöds inte. I Retail version 10.0.6 och högre stöds även redigering av transaktioner för likviditetshantering.

1. Installera tillägget Dynamics Excel.

2. Gå till arbetsytan **Butiksekonomi**. Sidan **Transaktionsvalideringsfel** innehåller en förhandsfiltrerad vy av formuläret för butikstransaktioner som bröt mot en eller flera valideringsregler.
 
3. Öppna formuläret. Klicka på den post som inte kunde valideras, klicka på **Office-tilläggstjänst** och klicka sedan på **Redigera vald transaktion**. En Excel-fil med information om den valda transaktionen öppnas med följande kalkylblad:

    - Rader: i det här kalkylbladet finns rubrik- och produktrader och relaterade data för transaktionen.
    - Betalningar: det här kalkyl bladet innehåller detaljinformation om betalningsraderna för transaktionen.
    - Rabatter: i det här kalkylbladet finns rabattrelaterad information för transaktionen.
    - Moms: i det här kalkylbladet finns momsrelaterad information för transaktionen.
    - Avgifter: i det här kalkylbladet finns avgiftsrelaterad information för transaktionen.

4. I Excel-filen ändrar du lämpliga fält och skickar tillbaka informationen till Retail Headquarters med hjälp av publiceringsfunktionen i Dynamics Excel-tillägget. När du har publicerat den visas ändringarna i systemet. Under publiceringen görs ingen validering på ändringar som användarna gör.

5. En fullständig granskningsspårning av ändringarna kan visas genom att du klickar **Visa redovisningsspårning** i rubriken för **Butikstransaktion** för ändringarna på rubriknivå och i det relevanta avsnittet på den aktuella transaktionssidan. Alla ändringar som rör försäljningsrader visas t. ex. på sidan **Försäljningstransaktioner** och ändringar som rör betalningar visas på sidan **Betalningstransaktioner** osv. Granskningsinformationen som underhålls för ändringarna är följande.

   - Datum och tid för ändring
   - Fält 
   - Gammalt värde
   - Nytt värde
   - Ändrades av

6. När du har gjort och publicerat ändringarna kör du alternativet **Validera butikstransaktioner** igen för att validera att de ändringar du har gjort är konsekventa och giltiga.

> [!NOTE]
> Du kan bara redigera transaktioner som inte kunde valideras. Om du vill redigera transaktioner som har godkänts vid valideringen ändrar du valideringsstatusen för den transaktion som du vill ändra till **Fel** eller **Ingen** och sedan kan du redigera den. 


## <a name="bulk-edit-transactions"></a>Bulkredigera transaktioner

I Retail version 10.0.6 och högre stöds alternativet för bulkredigering av butikstransaktioner på utdragsnivå. 

1. Använd Excel-tillägget för att öppna ett utdrag med transaktioner som du vill ändra med hjälp av steg 1-3.

2. Välj ett av alternativen nedan.

    - **Redigera hämtköpstransaktioner**. Med det här alternativet kan du redigera alla hämtköpstransaktioner som ingår i utdraget. Följande Excel-arbetsblad är tillgängliga.
    
       - **Transaktion**: i det här kalkylbladet finns information på rubriknivå för försäljningstransaktionerna.
       - **Försäljningstransaktion**: i det här kalkylbladet finns information på rubriknivå för försäljningstransaktionerna.
       - **Betalningstransaktion**: i det här kalkylbladet finns information på rubriknivå för betalningstransaktionerna.
       - **Rabattransaktion**: i det här kalkylbladet finns information på rubriknivå för rabattransaktionerna.
       - **Momstransaktion**: i det här kalkylbladet finns information på rubriknivå för momstransaktionerna.
       - **Avgiftstransaktion**: i det här kalkylbladet finns information på rubriknivå för avgiftstransaktionerna.

    - **Redigera kontanthanteringstransaktioner**. Med det här alternativet kan du redigera alla kontanthanteringstransaktioner som ingår i utdraget. Följande Excel-arbetsblad är tillgängliga.
     
       - **Transaktion**: i det här kalkylbladet finns information på rubriknivå för kontanthanteringstransaktionerna.
       - **Betalningsmedelstransaktioner (bank)**: i det här kalkylbladet finns uppgifter om alla bankinsättningstransaktioner.
       - **Betalningsmedelstransaktioner (kassaskåp)**: i det här kalkylbladet finns uppgifter om alla kassaskåpsinsättningstransaktioner.
       - **Kassaavstämning**: i det här kalkylbladet finns uppgifter om alla kassaavstämningstransaktioner.
       - **Intäkts-utgiftstransaktion**: i det här kalkylbladet finns raddetaljer om alla intäkts-utgiftstransaktioner.
       - **Betalningstransaktioner**: i det här kalkylbladet finns all betalningsrelaterad information både för åtgärden **Betala fakturan** och intäkts‑utgiftstransaktionen.

3.  Valideringar utförs inte när du publicerar bulkredigerade transaktioner. Du måste se till att alla redigeringar är korrekta och att exaktheten i dataåtergivningen i kalkylbladen upprätthålls. Om du till exempel vill ändra transaktionsdatumet för att hantera scenarier där räkenskaps- eller lagerperioden för öppna detaljhandelstransaktioner är stängd, måste du ändra datumet på alla Excel-kalkylblad med kolumnen **Affärsdatum**. Om du vill validera transaktionerna efter att de redigerats kan du använda **Validera om transaktioner** på sidan **Butiksutdrag**.
