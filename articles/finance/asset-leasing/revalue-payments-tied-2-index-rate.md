---
title: Omvärdera leasingbetalningar som är kopplade till en indexränta
description: I det här ämnet beskrivs den justering som görs i leasingskulden för en ROU-tillgång när variabla leasingbetalningar ändras på grund av en ändring i indexräntan.
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
ms.openlocfilehash: 83684afbd5e11b890a59bc1469ddefffd1777c4e
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448199"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Omvärdera leasingbetalningar som är kopplade till en indexränta

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs den justering som görs i leasingskulden för en ROU-tillgång när variabla leasingbetalningar ändras på grund av en ändring i indexräntan. Leasingskulden och ROU-tillgången kommer att justeras för att redovisa de nya betalningsbeloppen. Enligt Accounting Standards Codification Topic 842 (ASC 842), som är standarden för god redovisningssed i USA (US GAAP) ändras bara de variabla betalningarna när betalningar ökar eller minskar på grund av en ändring i indexräntan, om det inte finns några ändringar i kassaflödena. Dessa ytterligare ändringar kan omfatta en ändring av leasingperioden som är relaterad till räntesatser. Mer information finns i ASC 842-10-55-225 och punkt 42(b) i International Financial Reporting Standard 16 (IFRS 16).

## <a name="adjust-lease-payments"></a>Justera leasingbetalningar

Följ de här stegen för att omvärdera leasingbetalningar som är kopplade till en indexränta.

1. Om du vill köra indexomvärderingsprocessen för leasing gå till **Leasing av tillgångar \> Periodisk \> Omvärdering av indexränta**.

    Sidan **Omvärdering av indexränta** visas och visar alla tidigare indexomvärderingsprocesser för leasing som har körts. Informationen på den här sidan omfattar det process-ID som genererades från nummerserieinställningarna, den juridiska personen, antalet leasingböcker som justerades, den totala skuldjusteringen för IFRS 16-leasingar och de totala variabla betalningar som justerats för ASC 842-leasingar.

2. Om du vill köra omvärderingen väljer du **Omvärdering av leasingindex** i åtgärdsfönstret.

    Dialogrutan **Parametrar för omvärdering av index** visas. Här kan du filtrera och välja vilka leasingar, leasinggrupper och andra kriterier som ska användas när du väljer de leasingar som ska omvärderas. På fliken **Kör i bakgrunden** kan du dessutom konfigurera omvärderingen av index så att den körs i en batch.

4. Välj filter för att välja leasingar som ska inkluderas i bakgrundsbearbetningen och välj sedan **OK**.

    Dialogrutan **Omvärdering av indexränta, förhandsversion** visas och visar de leasingar som kommer att omvärderas. Det visar även justeringar av tillgångar och skulder eller justeringar av variabla betalningar.
    
5. Om du vill förhindra att leasingar omvärderas väljer du de leasingar som **ska** omvärderas. Om du inte väljer några leasingar kommer alla leasingar att omvärderas. När du är klar klickar du på **OK** för att omvärdera leasingbetalningarna.
6. Om du vill visa de transaktioner som har skapats för en viss indexomvärderingsprocess väljer du process-ID och väljer sedan **Transaktioner**.

    En dialogruta visas med information om de transaktioner som har skapats under bearbetningen.

> [!NOTE]
> Endast leasingar som har ett omvärderingsdatum som infaller på eller före systemdatumet kan omvärderas. Systemet ignorerar automatiskt alla lån som har ett omvärderingsdatum som är senare än systemdatumet.

## <a name="asc-842-leases--index-revaluation"></a>ASC 842-leasingar – omvärdering av index

Om du vill visa effekterna av leasingomvärderingsprocessen för ASC 842-leasingar öppnar du betalningsplanen för en leasing. På sidan visas endast de variabla betalningar som har gjorts på eller efter att omvärderingsdatumet ändrades på grund av indexomvärdering. Amorterings- och avskrivningsplaner förblir oförändrade. När du skapar en faktura som har en variabel betalning, debiteras den variabla betalningen till bokföringskontot för variabla betalningar. Det variabla betalningsbeloppet läggs också till kreditposten som bokförs direkt på leverantören, eller bokförs i växelskuldkontot, beroende på konfigurationen för leasingboken.

Betalningsplansraderna på sidan med leasinginformation uppdateras automatiskt med en ny rad som anger den nya indexräntan. Dessutom visar en kolumn om raden har skapats manuellt eller via omvärderingsprocessen för index.

## <a name="ifrs-16-leases--index-revaluation"></a>IFRS 16-leasingar – omvärdering av index

Om du vill visa effekterna av leasingomvärderingsprocessen för IFRS 16-leasingar öppnar du leasinginformationen för en justerad leasing. Fälten **Leasingperiod** och **Tillgångens livslängd** har uppdaterats för att återspegla den tiden som gått från startdatumet eller ändringsdatumet till omvärderingsdatumet. Dessutom har betalningsplansraderna uppdaterats för att återspegla de nya betalningarna för leasingavtalet, den nya indexräntan och hur raden skapades.

Du kan visa den nyligen genererade betalningsplanen som startar på omvärderingsdatumet och visar det totala uppdaterade betalningsbeloppet. En ny amorteringsplan för leasingskulder och en avskrivningsplan för tillgångar har också skapats för att återspegla den justerade betalningsplanen.

Journalposten har automatiskt bokfört justeringsjournalposten på kontot för ändringen av leasingbetalningar som hör till indexomvärderingen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]