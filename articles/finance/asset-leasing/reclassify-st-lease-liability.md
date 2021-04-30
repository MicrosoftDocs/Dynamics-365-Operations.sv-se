---
title: Omklassificera den kortfristiga delen av en leasingskuld
description: I det här ämnet beskrivs hur du skapar en månatlig journalpost som klassificerar en del av leasingskulden som kortsiktig.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ae5aebab507479775626579e8b08d68001326a06
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881576"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Omklassificera den kortfristiga delen av leasingskuld

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du skapar en månatlig journalpost som klassificerar en del av leasingskulden som kortsiktig. När det schema som har valts i batchprocessen är **Omklassificering av korttidsleasingskuld**, skapas en journalpost. Den här posten används för att bokföra den aktuella delen av leasingskulden den sista dagen i månaden. Samtidigt bokförs en återföringspost från den första dagen i nästa månad.

Den kortfristiga delen av leasingskulden visas i planen för amortering av skulder. När journaltransaktionen bokförs blir kolumnen **Omklassificeringsjournal för skuld skapad** tillgänglig, och journal-ID:t anges också i planen.

Om du vill skapa och bokföra journalposten för omklassificering av kortfristiga skulder följer du dessa steg.

1. Gå till **Leasing av tillgångar \> Periodisk \> Batchgenerering av journal**.
2. I dialogrutan **Batchgenerering av journal**, i fältet **Välj plan**, väljer du **Omklassificering av kortfristig leasingskuld**.
3. Välj en leasinggrupp i fältet **Leasinggrupp**. Du kan också välja bok-ID i fältet **Bok-ID**.
4. Aktivera parametern **Bokför**. Om posten ska skapas men inte bokföras lämnar du den här parametern inaktiverad.
5. Välj **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
