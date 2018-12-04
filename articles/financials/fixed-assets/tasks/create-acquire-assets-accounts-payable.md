--- 
title: "Skapa och anskaffa tillgångar från leverantörsreskontra"
description: "Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Skapa och anskaffa tillgångar från leverantörsreskontra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.  Här används redovisnings- och leverantörsreskontraansvariga och demonstrationföretaget USMF.


## <a name="set-fixed-assets-parameters"></a>Ange parametrar för anläggningstillgångar
1. Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.
2. Utöka eller komprimera avsnittet Inköpsorder.
3. Markera kryssrutan Tillåt förvärv av tillgångar från inköp.
4. Markera kryssrutan Skapa tillgång under bokföring av produktinleverans eller faktura.

## <a name="create-a-new-vendor-invoice"></a>Skapa en ny leverantörsfaktura
1. Gå till Leverantörsreskontra > Arbetsytor > Leverantörsfakturaregistrering.
2. Klicka på Ny leverantörsfaktura.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fakturakonto.
4. Klicka på länken på den valda raden i listan.
5. Ange ett värde i fältet Antal.
6. Ange ett datum i fältet Bokföringsdatum.
7. Klicka på Lägg till rad.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
    * Antingen icke-lagerförda artiklar eller anskaffningkategorier kan användas för anskaffning av anläggningstillgångar.  
9. Klicka på länken på den valda raden i listan.
10. Ange ett tal i fältet Kvantitet.
    * En fakturarad skapar bara en anläggningstillgång, oberoende av kvantitet.  Fakturakvantitetsfältet överförs till anläggningstillgångskvantiteten.  
11. Ange ett tal i fältet Enhetspris.
12. Expandera eller dölj avsnittet Raddetaljer.
13. Klicka på anläggningstillgångsfliken.
14. Markera kryssrutan Skapa en ny anläggningstillgång.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.
16. Välj den anläggningstillgångsgrupp som ska användas när du skapar den nya anläggningstillgången i listan.
17. Klicka på länken på den valda raden i listan.
18. Klicka på Bokför.
    * Anläggningstillgången skapas och förvärvas när fakturan bokförs.  


