---
title: Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal
description: I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 537418a78f7cc9d1375188076264e38b790e081b
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145995"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Registrera artiklar för en grundläggande lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du registrerar artiklar via artikelinförseljournalen när du använder “grundläggande lagerstyrning” i modulen Lagerhantering. Detta görs vanligtvis av en inleveransansvarig. Du kan köra den här proceduren i demonstrationsdataföretaget USMF med exempelvärdena som visas.  Om du inte använder USMF måste du ha en bekräftad inköpsorder med en öppen inköpsorderrad innan du startar den här guiden. Artikeln på raden måste lagras. Och artikeln behöver associeras med en lagringsdimension grupp, där webbplats och lagerställe är aktiva.


## <a name="create-item-arrival-journal-header"></a>Skapa artikelinförseljournalhuvudet
1. Gå till Lagerhantering > Poster i redovisningsjournal > Artikelinförsel > Artikelinförsel.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
    * Om du använder USMF kan du skriva WHS. Om du använder andra data måste journalen vars namn du väljer ha följande egenskaper: Kontrollera plockplats måste anges till Nej och Karantänhantering måste anges till Nej.  
4. Skriv ett värde i fältet Följesedel.
    * Detta är följesedels-id:t från den följesedel som har utfärdats av leverantören. Lägg till ett unikt nummer.  
5. Välj inköpsordern i fältet Antal i fältet Antal.
6. Klicka på OK.

## <a name="add-lines-to-item-arrival-journal"></a>Lägg till rader till artikelinförseljournal
1. Klicka på Funktioner.
2. Klicka på Skapa rader.
    * Raderna kan anges manuellt i den här journalen eller skapas automatiskt. Detta visar hur du skapar detta automatiskt.  
3. Markera eller avmarkera kryssrutan Initiera kvantitet.
    * Detta initierar kvantiteten på journalraderna med den kvantitet som inte ännu har registrerats från inköpsorderraden.  
4. Klicka på OK.

## <a name="post-the-journal"></a>Bokför journalen
1. Klicka på Bokför.
2. Klicka på OK.

## <a name="generate-the-product-receipt"></a>Generera produktinleveransen
1. Klicka på Funktioner.
2. Klicka på Produktinleverans.
3. Klicka på OK.

