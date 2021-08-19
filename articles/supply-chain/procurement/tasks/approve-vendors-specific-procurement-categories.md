---
title: Godkänn leverantörer för specifika anskaffningskategorier
description: I det här avsnittet beskrivs hur du godkänner leverantörer för särskilda anskaffningskategorier i Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65a42e10edda7b492e86029ca05655d7c0175c23589dc55573c7ac5976e820d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717224"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Godkänn leverantörer för specifika anskaffningskategorier

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du godkänner leverantörer för särskilda anskaffningskategorier i Dynamics 365 Supply Chain Management. När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in. Den här proceduren visar hur du anger att en leverantör är godkänd eller föredras för en viss anskaffningkategori. Den här uppgiften utförs vanligtvis av ett anskaffningsproffs. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.

1. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.
2. Markera leverantören som du vill ange som godkänd eller prioriterad leverantör för en kategori.
3. Välj **Allmänt** i åtgärdsfönstret.
4. Välj **Kategorier**.
5. Välj **Lägg till kategori**.
6. I fältet **Kategori**, välj **KONTORS- OCH SKRIVBORDSTILLBEHÖR (OFFICE AND DESK ACCESSORIES)**.
7. I fältet **Leverantörkategoristatus** väljer du **Prioriterad**. Det är möjligt att ange mer än en prioriterad leverantör för en kategori.  
8. Välj **Spara**.
9. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Anskaffningskategorier**.
10. Välj **ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\KONTORS- OCH SKRIVBORDSTILLBEHÖR** i trädet.
11. Expandera avsnittet **Leverantörer**. Kontrollera om leverantören som du valde visas som en prioriterad leverantör för kategorin Kontor- och skrivbordstillbehör. Om du kör den här proceduren som en uppgiftsguide måste du eventuellt välja knappen **Lås upp** för att kunna bläddra nedåt i listan över leverantörer.  Det går också att lägga till prioriterade och godkända leverantörer på det här sidan.  
12. Expandera **KONTORS- OCH SKRIVBORDSTILLBEHÖR** i trädet och välj **Sax.**
13. Välj **Nej** i fältet **Ärv leverantörer från överordnad kategori:**.
14. Välj **Ja** i fältet **Ärv leverantörer från överordnad kategori:**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]