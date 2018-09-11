--- 
title: "Godkänn leverantörer för specifika anskaffningskategorier"
description: "När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 83945932d56abf6bf44476e5647f8ae7abdc3602
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Godkänn leverantörer för specifika anskaffningskategorier

[!include [task guide banner](../../includes/task-guide-banner.md)]

När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in. Den här proceduren visar hur du anger att en leverantör är godkänd eller föredras för en viss anskaffningkategori. Den här uppgiften utförs vanligtvis av ett anskaffningsproffs. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.

1. Gå till Anskaffning och källa > Leverantörer > Alla leverantörer.
2. Markera leverantören som du vill ange som godkänd eller prioriterad leverantör för en kategori.
3. Klicka på Allmänt i åtgärdsfönstret.
4. Klicka på kategorier.
5. Klicka på Lägg till kategori.
6. I fältet Kategori väljer du KONTORS- OCH SKRIVBORDSTILLBEHÖR (KONTORS- OCH SKRIVBORDDTILLBEHÖR).
7. I fältet Leverantörkategoristatus väljer du "Föredragen".
    * Det är möjligt att ange mer än en prioriterad leverantör för en kategori.  
8. Klicka på Spara.
9. Gå till Anskaffning och källa > Anskaffningskategorier.
10. Välj "ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\KONTORS- OCH SKRIVBORDSTILLBEHÖR" i trädet.
11. Visa avsnittet Leverantörer.
    * Kontrollera om leverantören som du valde, visas som en prioriterad leverantör för kategorin Kontor- och skrivbordtillbehör. Om du kör den här proceduren som en uppgiftsguide måste du eventuellt klicka på fliken Lås upp för att kunna bläddra nedåt i listan över leverantörer.  Det går också att lägga till prioriterade och godkända leverantörer på det här sidan.  
12. Expandera "KONTORS- OCH SKRIVBORDSTILLBEHÖR" i trädet.
13. Välj "Saxar" i trädet. 
14. Välj Nej i fältet Ärv leverantörer från överordnad kategori.
15. Välj Ja i fältet Ärv leverantörer från överordnad kategori.


