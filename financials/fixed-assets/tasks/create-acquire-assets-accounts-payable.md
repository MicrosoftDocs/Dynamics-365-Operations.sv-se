--- 
title: "Skapa och anskaffa tillgångar från leverantörsreskontra"
description: "Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f814d20bc16bb3334ae4bc449cc0d45843487023
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Skapa och anskaffa tillgångar från leverantörsreskontra

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


