---
title: Godkänn leverantörer för specifika produkter
description: I den här proceduren visas hur du godkänner leverantörer för specifika produkter.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237285"
---
# <a name="approve-vendors-for-specific-products"></a>Godkänn leverantörer för specifika produkter

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du godkänner leverantörer för specifika produkter. På så sätt kan du kontrollera vilka leverantörer som kan användas när produkten läggs till en inköpsorder. Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data. Uppgiften utförs vanligtvis av en inköpschef.

1. I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Expandera snabbfliken **Inköp**. Om det visas en primär leverantör som i fältet **Leverantör** måste du lägga till den här leverantören som en godkänd leverantör på följande sätt. Gör en notering av leverantörnumret om ett sådant visas.  
5. I åtgärdsrutan, klicka på **Köp**.
6. Klicka på **Inställningar**.
7. Klicka på **Lägg till**.
8. Ange eller välj ett värde i fältet Leverantör. Välj godkänd leverantör. Minst en av raderna måste vara primär leverantör, om det finns en i produktposten. Om du gjorde en notering av leverantörsnumret tidigare, väljer du den här.  
9. I fältet **Utgång** anger du ett datum. Välj ett datum som infaller alla månader framåt.  
10. Klicka på **Lägg till**.
11. Ange eller välj ett värde i fältet **Leverantör**.
12. I fältet **Utgång** anger du ett datum. Välj ett datum som är annorlunda än det föregående utgångsdatumet.  
13. Stäng sidan.
14. Klicka på **Godkända leverantörer** i åtgärdsfönstret.
15. I fältet **Utgång** anger du ett datum. Detta datum fungerar som ett filter så att du kan se vilka som är godkända leverantörer, fram till ett visst datum.  
16. Stäng sidan.
17. Klicka på **Giltighetstid** i åtgärdsfönstret.
18. Ange ett datum i fältet **Visa leverantörer som upphör den**. Du kan använda den här sidan för att identifiera leverantörer där godkännande upphör att gälla efter ett visst datum.  
19. Stäng sidan.
20. Klicka på **Redigera**.
21. Välj ett alternativ i fältet **Kontrollmetod för godkänd leverantör**. I det här fältet kan du välja policyn för vad som ska hända om produkten läggs till i en inköpsorderrad där leverantören inte är en godkänd leverantör.  
22. Klicka på **Spara**.
23. Stäng sidan.
24. Stäng sidan.
25. I navigeringsfönstret, gå till **Moduler > Leverantörer > Leverantör/artikelrelationer > Godkänd leverantörslista per artikel**. På den här sidan finns en översikt över alla produkter och godkända leverantörer.  
26. Stäng sidan.
27. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**. Du kan också starta från en leverantör och sedan gå till listan över godkända produkter för det leverantörskontot.  
28. Hitta och markera önskad post i listan.
29. Klicka på **Anskaffning** i åtgärdsfönstret.
30. Klicka på **Godkänd leverantörslista per leverantör**.
31. Stäng sidan.
32. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]