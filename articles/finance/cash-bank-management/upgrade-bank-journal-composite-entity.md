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
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6c990208f26dde26b7adc306198f7cd16e0e69b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978924"
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




