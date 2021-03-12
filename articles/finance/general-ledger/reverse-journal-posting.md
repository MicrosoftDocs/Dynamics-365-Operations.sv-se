---
title: Återför journalbokföring
description: I det här avsnittet beskrivs funktioner som gör att du kan återföra verifikationer från en verifikationstransaktionslista eller från ekonomiska journaler.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 697ca7557b26026783626e843ee1e5d1fd27db9a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990274"
---
# <a name="reverse-journal-posting"></a>Återför journalbokföring

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs Microsoft Dynamics 365 Finance-funktioner som gör att du kan återföra en hel journal eller återföra en eller flera verifikationer från verifikationstransaktionslistan oavsett ursprung. 

## <a name="reversing-journals"></a>Återföra journaler

Du kan återföra journalrader individuellt. Med en omvänd journalbokföring kan du även återföra en hel redovisningsjournal. För att återföra en journal: 

- Öppna redovisningsjournalen och filtrera på bokförda journaler.
- Klicka på menyn **Återför** högst upp på sidan.
- Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.
- Välj **Ja** om du vill använda de befintliga transaktionsdatumen eller **Nej** om du vill ange ett nytt. I vissa fall kan perioden för den ursprungliga transaktionen stängas och du måste ange ett nytt transaktionsdatum för återföringen.
- Om du har valt **nej** anger du ett transaktionsdatum för återföringen. 
- Ange en kommentar som du vill lägga till i återföringstransaktionen.
- Välj knappen **Återför**.

Transaktionerna kommer att återföras. 

Om antalet verifikationer innehåller mer än 100 rader, kommer återföringsprocessen att köras med batch-processen. Du kan granska resultatet genom att visa kommentarerna i batch-jobbet. Alla transaktioner som inte kunde återföras visas i historiken för batchjobbet.

Om verifikationen innehåller fler än 100 rader eller färre, kommer återföringsprocessen att köras omedelbart. Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras. Välj **OK** för att stänga dialogrutan.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Återför verifikationer från listan med verifikationstransaktioner. 

Du kan även återföra verifikationer från **transaktionslistan för verifikationer** i alla redovisningstransaktioner. Dessutom kan du återföra fler än en verifikation åt gången. 

Så här återför du en eller flera verifikationer: 

- Klicka på menyn **Återför** högst upp på sidan.
- Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.
- Välj **Ja** om du vill använda de befintliga transaktionsdatumen eller **Nej** om du vill ange ett nytt. I vissa fall kan perioden för den ursprungliga transaktionen stängas och du måste ange ett nytt transaktionsdatum för att återföra den.
- Om du har valt **nej** anger du ett transaktionsdatum för återföringen. 
- Ange en kommentar som beskriver återföringstransaktionen.
- Välj knappen **Återför**.

Transaktionerna kommer att återföras. 

Om det finns fler än 100 verifikationsrader, kommer återföringsprocessen att köras med batch-processen. Du kan granska resultatet genom att visa kommentarerna i batch-jobbet. Alla transaktioner som inte kunde återföras antecknas i historiken för batchjobbet.

Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart. Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför. Välj **OK** för att stänga dialogrutan.

Transaktioner kan bara återföras om de uppfyller affärsreglerna för att återföra dem. Leverantörsbetalningar kan inte återföras med funktionen som beskrivs i det här avsnittet. Leverantörsbetalningar måste återföras genom att följa stegen i [återför en leverantörsbetalning](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).

