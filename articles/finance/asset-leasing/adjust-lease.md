---
title: Justera leasingar
description: Ämnet förklarar hur du justerar en leasing. Justering kan krävas om leasingvillkoren ändras, leasingen utökas eller andra omständigheter ändras.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448220"
---
# <a name="adjust-leases"></a>Justera leasingar

[!include [banner](../includes/banner.md)]

Ämnet förklarar hur du justerar en leasing. Justering kan krävas om leasingvillkoren ändras, leasingen utökas eller andra omständigheter ändras. Leasing av tillgång följer riktlinjerna i Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16) om ändringar av leasing. ASC 842-20-15-1 definierar en leasingändring precis som alla ändringar av villkoren för ett kontrakt som orsakar en ändring av omfattningen av eller ersättningen av en leasing. Punkt 39 i IFRS 16 anger att en leasetagare måste omvärdera leasingskulden så att den återspeglar ändringar av leasingbetalningarna.

För organisationer som följer ASC 842 eller IFRS 16 omvärderas en leasing för att återspegla en förändring av nuvärdet för de framtida lägsta leasingbetalningarna (PVFMLP). Om PVFMLP ökar kommer journalposten som skapas att vara en debitering till ROU-tillgången (Right-Of-Use, tillgång med nyttjanderätt) och en kredit till leasingskulden för differensen mellan den nya PVFMLP och den tidigare PVFMLP. Om PVFMLP minskar, kommer journalposten att vara ett debetbelopp för leasingskulden och en kredit till ROU-tillgången för differensen.

Om justeringen minskar ROU-tillgången till lägre än 0 (noll) krediteras resten till bokföringskontot för förlust vid leasingändring som har angetts på sidan **Bokföringskonton för leasing**. Systemkontona för dessa transaktioner och andra justeringsposter, till exempel klassificeringsändringar, direkta utgifter, leasingincitament, förskottsbetalningar och nedmonteringskostnader som uppstår vid leasingändringar.

Om du vill ha mer information om leasingjusteringstransaktioner rekommenderar vi att du läser i IFRS 16 och ASC 842.

Justera ett lån enligt följande instruktioner. De modifierade data kommer att uppdatera leasingplaner när processen Skapa schema körs.

1. Gå till **Leasing av tillgångar \> Leasing \> Sammanfattning av leasing**.
2. På sidan **Sammanfattning av leasing** väljer du den leasing du vill justera och väljer sedan **Justera leasing**.
3. På sidan **Justera leasing** anger du den nya informationen för den justerade leasingen.

    Observera att sidan **Justera leasing** liknar sidan **Lägg till leasing**. På samma sätt som startdatumet som du anger när du lägger till en leasing avgör när den nya leasingen startar, så avgör fältet **Ändringsdatum** på sidan **Justera leasing** när den ändrade leasingen startar. Datumet kan inte infalla efter startdatumet på betalningsplanraderna.

    > [!NOTE]
    > Fälten **ROU-överväganden** gäller för leasingjusteringen. Om inga direkta utgifter, leasingincitament, förskottsbetalningar eller nedmonteringskostnader är associerade med den ändrade leasingen ska du lämna dessa fält tomma. De ursprungliga beloppen gäller inte för den uppdaterade leasingen. Eventuella ytterligare kostnader som uppstår när leasingen ändras ska anges på sidan **Justera leasing**.
    > 
    > En leasegivare ger till exempel ett 1 000 USD incitament för att godkänna ett leasingtillägg. I detta fall anger du **1 000** i fältet **Leasingincitament** när du justerar leasingen för att ta med tillägget. Om det inte finns några incitament kopplade till leasingjusteringen bör du rensa alla värden som tidigare angetts i det här fältet. Samma logik används för andra ROU-överväganden.

    Betalningsplanraderna för den justerade leasingen bör skapas på en potentiell grund. Betalningsplanrader som skapas med hjälp av en potentiell grund kan inte starta innan leasingändringarna börjar gälla.

    Följande steg är nästan identiska med stegen för att initialt redovisa en leasing.

4. Välj **Skapa scheman** för att generera den justerade betalningsplanen. Ett meddelande visas om att betalningsplanen har skapats för leasingen.

    > [!IMPORTANT]
    > Innan du väljer **Skapa scheman** måste du se till att ändringsdatum och betalningsplanrader är korrekta. Se också till att alla direkta utgifter, leasingincitament, förskottsbetalningar och nedmonteringskostnader bara motsvarar de kostnader som uppstår vid justeringen.

5. Om du vill visa den nyss skapade betalningsplanen väljer du **Böcker** och öppnar sidan **Betalningsplan**.
6. På sidan **Betalningsplan** kan du redigera de justerade betalningsbeloppen innan du bekräftar betalningsplanen. För att bekräfta planen väljer du **Bekräfta plan**.

    När betalningsplanen är bekräftad skapas de nya avskrivningarna för tillgångar och nya planer för leasingskulder.

7. Om du vill visa den nya amorteringsplanen för leasingskulder som har genererats från nya indata, stänger du sidan **Betalningsplan** och öppnar sidan **Plan för amortering av skuld**.
8. Om du vill visa den nya avskrivningsplanen för tillgångar öppnar du sidan **Avskrivningsplan för tillgång** från sidan **Information om bok**.
9. För att generera justeringsjournalposten väljer du **Funktion \> Leasingjustering**. Ett meddelande visas om att justeringsjournalposten har skapats. 
10. För att visa journalposten väljer du **Journaler \> Journal för leasing av tillgång**.
11. För att bokföra journalposten väljer du raden och väljer **Bokför**.

## <a name="view-lease-versions"></a>Visa leasingversioner

Om en leasing har ändrats kan du visa olika versioner av den. Du kan också visa historiska planer och tidigare leasinguppgifter.

1. På sidan **Sammanfattning av leasing** väljer du leasingen och i åtgärdsfönstret väljer du sedan **Versionshistorik för leasing**.

    Om den valda leasingen har justerats visar sidan **Versionshistorik för leasing** de olika versionerna av den. Den ursprungliga leasingen är märkt **1** och efterföljande versioner har stigande numerisk ordning.

    För en vald leasingversion kan du visa de ekonomiska dimensionerna, kontraktsinformation, plats och betalningsplansrader.

2. Om du vill visa historiska planer öppnar du den ändrade leasingen från sidan **Sammanfattning av leasing**, väljer önskad bok och väljer sedan **Versionshistorik för bok** i åtgärdsfönstret.
3. På sidan **Version av bok** väljer du önskad version och önskad plan att visa.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]