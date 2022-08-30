---
title: Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering
description: Den här artikeln beskriver hur du redigerar och granskar hämtköps- och kassahanteringstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: 22a0f76b6797e1051af6a7f3069f79c3be832d46
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283735"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du redigerar och granskar hämtköps- och kassahanteringstransaktioner i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce-kunder använder både förstaparts och tredjeparts kassaprogram. Kassaprogrammet från första part hämtar butikstransaktionerna till Commerce-administration från kanalerna via en batchprocess. Programmet från tredje part hämtar transaktionerna till Commerce-administration via integration. I båda fallen måste en konsekvenskontroll utföras efter att transaktionerna har hämtats till Commerce-administration. I den här processen körs flera verifieringar av transaktionerna och endast transaktioner som valideras utan fel hämtas till utdraget så att de kan bokföras i Commerce-administration.

Commerce-transaktionerna kanske inte kan valideras av olika orsaker. En bugg i integrationskoden eller i kassaprogrammet kan medföra att data blir inkonsekventa. Alternativt kan ett användarfel orsaka detta. En användare kanske tar bort en produkt efter att den synkroniserats till kanalen, eller stänger en räkenskapsperiod utan att transaktioner för den perioden bokförs. Även om transaktionerna flaggas och exkluderas från utdragen kan de störa en kunds dagliga bokföring av försäljning. I Commerce kan du redigera transaktioner som inte kan valideras samtidigt som du upprätthåller granskningen av alla ändringar.

## <a name="edit-transactions"></a>Redigera transaktioner

I Commerce version 10.0.5 är hämtköpstransaktioner, som försäljningar och returer, de enda transaktioner som kan redigeras. Kundorder och onlinebeställningar kan inte redigeras. I Commerce version 10.0.6 och senare kan även kontanthanteringstransaktioner redigeras.

Följ de här stegen om du vill redigera transaktioner i Commerce-administration.

1. Installera [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Öppna arbetsytan **Butiksekonomi** i Commerce-administration. Sidan **Transaktionsvalideringsfel** innehåller en förhandsfiltrerad vy av sidan för transaktioner som bröt mot en eller flera valideringsregler.
1. Öppna transaktionssidan, välj posten som inte kunde valideras, välj **Office Add in** och välj sedan **Redigera vald transaktion**. En Excel-fil som visar detaljerna för den valda transaktionen öppnas. Den här filen innehåller följande kalkylblad:

    - **Rader**: – I det här kalkylbladet finns rubrik- och produktrader för transaktionen och relaterade data för transaktionen.
    - **Betalningar** – I det här kalkyl bladet finns detaljinformation om betalningsraderna för transaktionen.
    - **Rabatter** – I det här kalkylbladet finns rabattrelaterad information för transaktionen.
    - **Moms** – I det här kalkylbladet finns momsrelaterad information för transaktionen.
    - **Avgifter** – I det här kalkylbladet finns avgiftsrelaterad information för transaktionen.

1. I Excel-filen ändrar du lämpliga fält och skickar tillbaka informationen till Commerce-administration med hjälp av publiceringsfunktionen i Dynamics Excel Add-in. När du har publicerat data visas ändringarna i systemet. Under publiceringen görs ingen validering av ändringar som användarna gör.
1. Du kan visa en fullständig granskningsspårning av ändringarna genom att välja **Visa redovisningsspårning** i rubriken för **Butikstransaktion** för ändringarna på rubriknivå och i det relevanta avsnittet och den relevanta posten på den aktuella transaktionssidan. Till exempel kommer alla ändringar som är relaterade till försäljningsrader att visas på sidan **Försäljningstransaktioner** och alla ändringar som är relaterade till betalningar kommer att visas på sidan **Betalningstransaktioner**. Följande granskningsinformation underhålls för ändringarna:

    - Datum och tid för ändring
    - Fält
    - Gammalt värde
    - Nytt värde
    - Ändrades av

1. När du har gjort och publicerat ändringarna kör du **Validera butikstransaktioner** för att validera att dessa ändringar är konsekventa och giltiga.

> [!NOTE]
> Du kan bara redigera transaktioner som inte kunde valideras. Om du vill redigera en transaktion som har godkänts vid valideringen ändrar du valideringsstatusen för den transaktion som du vill ändra till **Fel** eller **Ingen** och sedan kan du publicera ändringen. Du kan sedan redigera data i huvudet eller i alla andra underordnade poster i transaktionen, och publicera huvudet eller posterna.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Massredigera transaktioner som är länkade till ett utdrag

I Commerce version 10.0.6 och senare stöds alternativet för massredigering av transaktioner på utdragsnivå.

Om du vill massredigera transaktioner som är länkade till ett utdrag i Commerce-administration följer du de här stegen.

1. Öppna sidan **Utdrag** och välj utdraget som innehåller de transaktioner som måste redigeras.
1. Välj knappen **Öppna i Microsoft Office**.
1. Beroende på vad som måste redigeras väljer du något av följande alternativ:

    - **Redigera hämtköpstransaktioner** – Med det här alternativet kan du redigera alla hämtköpstransaktioner som ingår i utdraget. Följande Excel-arbetsblad är tillgängliga:

        - **Transaktion** – I det här kalkylbladet finns information på rubriknivå för försäljningstransaktionerna.
        - **Försäljningstransaktion** – I det här kalkylbladet finns information på radnivå för försäljningstransaktionerna.
        - **Betalningstransaktioner** – I det här kalkylbladet finns betalningsinformation på radnivå för försäljningstransaktionerna.
        - **Rabattransaktioner** – I det här kalkylbladet finns rabattinformation på radnivå för försäljningstransaktionerna.
        - **Momstransaktioner** – I det här kalkylbladet finns momsinformation på radnivå för försäljningstransaktionerna.
        - **Avgiftstransaktioner** – I det här kalkylbladet finns avgiftsinformation på radnivå för försäljningstransaktionerna.

    - **Redigera kontanthanteringstransaktioner** – Med det här alternativet kan du redigera alla kontanthanteringstransaktioner som ingår i utdraget. Följande Excel-arbetsblad är tillgängliga:

        - **Transaktion** – I det här kalkylbladet finns information på rubriknivå för kontanthanteringstransaktionerna.
        - **Betalningsmedelstransaktioner (bank)** – I det här kalkylbladet finns uppgifter om alla bankinsättningstransaktioner.
        - **Betalningsmedelstransaktioner (kassaskåp)** – I det här kalkylbladet finns uppgifter om alla kassaskåpsinsättningstransaktioner.
        - **Kassaavstämning** – I det här kalkylbladet finns uppgifter om alla kassaavstämningstransaktioner.
        - **Intäkts-utgiftstransaktion** – I det här kalkylbladet finns raddetaljer om alla intäkts-utgiftstransaktioner.
        - **Betalningstransaktioner** – I det här kalkylbladet finns all betalningsrelaterad information både för åtgärden **Betala fakturan** och intäkts‑utgiftstransaktionen.

1. Redigera de transaktioner som behövs.

    > [!NOTE]
    > Valideringar utförs inte när du publicerar massredigerade transaktioner. Du måste se till att alla redigeringar är korrekta och att exaktheten i dataåtergivningen i kalkylbladen upprätthålls. Om du till exempel vill ändra transaktionsdatumet för att hantera scenarier där räkenskaps- eller lagerperioden för öppna transaktioner är stängd, måste du ändra datumet på alla Excel-kalkylblad med kolumnen **Affärsdatum**. Om du vill validera transaktionerna efter att de redigerats kan du välja **Validera om transaktioner** på sidan **Utdrag**. Vänta tills valideringsjobbet har körts färdigt innan du bokför utdraget.

1. Om sammansättningen redan har genererats öppnar du sidan **Sammansatta transaktioner** och väljer **Generera om XML för försäljningsorder**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Massredigera transaktioner som inte är länkade till ett utdrag

I Commerce version 10.0.10 och senare går det att massredigera transaktioner som inte kunde valideras men som är länkade till ett utdrag.

Om du vill massredigera transaktioner som inte är länkade till ett utdrag i Commerce-administration följer du de här stegen.

1. Öppna sidan **Alla butiker** och välj den butik som transaktioner måste redigeras för.
1. Välj knappen **Öppna i Microsoft Office** och välj sedan **Redigera hämtköpstransaktioner**.
1. Redigera de transaktioner som behövs och publicera dem sedan.

## <a name="additional-resources"></a>Ytterligare resurser

[Redigera och granska onlineorder- och asynkrona kundordertransaktioner](edit-order-trans.md)

[Redigera ekonomiska dimensioner för butikstransaktioner](edit-financial-dim.md)

[Skapa en Excel-arbetsbok för att redigera butikstransaktioner](create-excel-edit.md)

[Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
