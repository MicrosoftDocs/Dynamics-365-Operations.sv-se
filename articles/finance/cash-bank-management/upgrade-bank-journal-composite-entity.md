---
title: Uppdatera bankjournalens sammansatta enhet
description: Detta ämne listar stegen för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: db5f01af6b21b4dc5ff633ee9c11bb6ed41df048
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868559"
---
# <a name="update-the-bank-journal-composite-entity"></a>Uppdatera bankjournalens sammansatta enhet

[!include [banner](../includes/banner.md)]

Detta ämne listar stegen för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).

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
