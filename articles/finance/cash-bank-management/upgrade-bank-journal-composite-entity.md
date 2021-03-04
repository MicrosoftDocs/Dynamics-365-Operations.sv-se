---
title: Uppdatera den sammansatta enheten för bankjournal
description: Följande steg behövs för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec196600a54a2aed4565cf422dc386d6646ff524
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447872"
---
# <a name="update-the-bank-journal-composite-entity"></a>Uppdatera den sammansatta enheten för bankjournal

[!include [banner](../includes/banner.md)]

Följande steg behövs för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).

Gör på följande sätt när du vill lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).

1.  Kompilera och synkronisera följande sammansatta enheter, enheter och mellanlagringsregister:
    -   Sammansatt enhet\\BankJournalEntity
    -   Enhet\\BankJournalHeaderEntity
    -   Enhet\\BankJournalLineEntity
    -   Tabell\\BankJournalHeaderStaging
    -   Tabell\\BankJournalLineStaging

2.  Datahantering\\dataprojekt
    -   Exponera typen **Banktransaktion** i layouten **Källdata**.
        -   Källdataformat = XML-Element
        -   Enhetsnamn = Bank Journal
        -   Överföra datafil = den nya versionen SampleBankJournalCompositeEntity.xml
        -   Klicka på **Ja** om du vill skriva över den befintliga filen.
        -   Klicka på **Ja** för att generera mappning från grunden.
        -   Kontrollera att typen Banktransaktion har mappats.
            -   Klicka på **Visa karta** på enheten Line.
            -   Kontrollera att banktransaktionstypen mappas från källa (Source) till mellanlagring (Staging).

3.  Importera det nya utdraget.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]