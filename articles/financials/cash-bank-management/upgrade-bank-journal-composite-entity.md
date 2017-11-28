---
title: "Uppdatera den sammansatta enheten för bankjournal"
description: "Följande steg behövs för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity)."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a8b11df3b21f8d97986d934ff3c65931aa7ee0c6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="update-the-bank-journal-composite-entity"></a>Uppdatera den sammansatta enheten för bankjournal

[!include[banner](../includes/banner.md)]


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





