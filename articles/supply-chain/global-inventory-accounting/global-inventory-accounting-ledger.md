---
title: Transaktionsregister för Global lagerredovisning
description: I det här avsnittet beskrivs redovisning för global lagerredovisning, som definieras av en kombination av en valuta, en kalender, en konferens och en koppling till en juridisk person.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f5f610fa51fce18ecefbf96892b56b05208c666c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676087"
---
# <a name="global-inventory-accounting-ledger"></a>Transaktionsregister för Global lagerredovisning

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Global lagerredovisning har sin egen uppsättning redovisning. Varje gång en lagerrelaterad transaktion bearbetas för en relevant juridisk person kan systemet konto för transaktionen i val enskilt antal redovisningar för global lagerredovisning efter behov.

Redovisningen är ett register för debet- och kreditmått. Dessa mått klassificeras genom användning av kostnadselement och redovisningskonton. Redovisning för global lagerredovisning, som definieras av en kombination av en valuta, en kalender, en konferens och en koppling till en juridisk person.

Om du vill ställa in dina redovisningar för global lagerredovisning går du till **Global lagerredovisning \> Inställningar \> Global lagerredovisning**. För varje redovisning anger du följande fält:

- **Namn** – Ange namnet på redovisning.
- **Beskrivning** – Ange en beskrivning av redovisning.
- **Räkenskapskalender** – Ange räkenskapskalendern för redovisningen.
- **Valuta- och valutakurstyp** – Använd fälten på den här snabbfliken för att välja den redovisningsvaluta som redovisningen använder samt valutakurstypen. Valutan du väljer kan skilja sig från den valuta som den juridiska personen använder. I Global lagerredovisning kan användarna definiera så många kostnadsredovisningar som de behöver. Global lagerredovisning stöder lagerredovisning i flera valutor och vid flera värderingar. Ange följande fält.

    - **Valuta** – Välj den kostnadsvaluta som lagerrelaterade värden underhålls i. Det här värdet inkluderar lagervärde, kostnad för sålda varor, lager under transport och alla typer av avvikelser.
    - **Valutakurstyp** – Välj den valutakurs som ska användas för att konvertera transaktionsbeloppet i transaktionsvalutan och standardkostnaden för artiklarna till kostnadsvalutan.

- **Konventionens namn** – Ange en konvention. En konvention är en samling principer som fastställer hur kostnader ska redovisas i redovisningen.
- **Juridisk person** – I redovisningen bokförs dokumenten som bokförs till den valda juridiska personen.
- **Priming** – Välj om lagertransaktioner som skapades innan huvudboken skapades ska behandlas enligt valutan och konventionen i redovisningen. Välj ett av följande värden:

    - **Aktiverat** – Redovisningen ska bearbeta transaktioner som skapades innan redovisningen skapades.
    - **Inaktiverat** – Redovisningen ska endast bearbeta transaktioner som skapades efter redovisningen skapades.

    > [!IMPORTANT]
    > Du kan **inte** komma tillbaka och ställa in detta fält när du har angett nya dokument.

- **Status** – Systemet ställer automatiskt in statusen för nyligen skapade redovisningar att *förbereda*.
