---
title: Sök efter leverantörer
description: Läs hur du vill söka efter leverantörer baserat på specifika kriterier.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory, VendSearchAddReviewCriterionGroup, VendSearchResults, VendSearchAddReviewCriterion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc28deb979fe8dc4e31befe6d4d5f6f91388f13e
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018062"
---
# <a name="search-for-vendors"></a>Sök efter leverantörer

[!include [banner](../../includes/banner.md)]

Läs hur du vill söka efter leverantörer baserat på specifika kriterier. I det här exemplet visas hur du söker efter leverantörer som har godkänts för en viss anskaffningskategori och har sin primära adress i ett visst land. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.

1. Gå till Anskaffning och källa > Leverantörer > Leverantörssökning.
2. Klicka på plusikonen om du vill öppna sidan Val av anskaffningskategori.  
3. Välj "ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\OFFICE-DATORER" i trädet.
    * Om du kör den här proceduren som en uppgiftsguide, måste du klicka på fliken Lås upp innan du kan välja korrekt nod. Om du inte använder USMF väljer du en av de kategorier som du har.  
4. Klicka på Lägg till.
    * Det går att välja fler än en kategori här. Om du gör det kommer alla leverantörer som har godkänts för minst en av kategorierna att hittas vid sökningen.  
5. Klicka på OK.
6. Skriv ett värde i fältet Land/region.
7. Klicka på OK.

