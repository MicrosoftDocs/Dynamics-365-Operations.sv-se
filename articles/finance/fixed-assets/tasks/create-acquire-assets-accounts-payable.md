---
title: Skapa och anskaffa tillgångar från leverantörsreskontra
description: Denna procedur går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.
author: moaamer
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4290ced6bcf4432583cffc9122a4bba86266a559
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713625"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Skapa och anskaffa tillgångar från leverantörsreskontra

[!include [banner](../../includes/banner.md)]

Denna procedur går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.  Här används redovisnings- och leverantörsreskontraansvariga och demonstrationföretaget USMF.


## <a name="set-fixed-assets-parameters"></a>Ange parametrar för anläggningstillgångar
1. I **navigeringsfönstret** går du till **Moduler > Anläggningstillgångar > Inställningar > Parametrar för anläggningstillgångar**.
2. Expandera snabbfliken **Inköpsorder**.
3. Markera kryssrutan **Tillåt förvärv av tillgångar från inköp.**
4. Markera kryssrutan **Skapa tillgång under bokföring av produktinleverans eller faktura**.

## <a name="create-a-new-vendor-invoice"></a>Skapa en ny leverantörsfaktura
1. I **Navigeringsfönster**, gå till **Moduler > Leverantörsreskontra > Arbetsytor > Leverantörsfakturapost**.
2. Klicka på **Ny leverantörsfaktura.**
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Fakturakonto**.
4. Klicka på länken på den valda raden i listan.
5. I fältet **Antal**, skriv ett värde.
6. Ange ett datum i fältet **Bokföringsdatum.**
7. Klicka på **Lägg till rad**.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**. Antingen icke-lagerförda artiklar eller anskaffningkategorier kan användas för anskaffning av anläggningstillgångar.  
9. Klicka på länken på den valda raden i listan.
10. Ange ett nummer i fältet **Kvantitet**. En fakturarad skapar bara en anläggningstillgång, oberoende av kvantitet. Fakturakvantitetsfältet överförs till anläggningstillgångskvantiteten.  
11. Ange ett tal i fältet **Enhetspris**.
12. Visa snabbfliken **Radinformation**.
13. Klicka på fliken **Anläggningstillgångar**.
14. Markera kryssrutan **Skapa en ny anläggningstillgång.**
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Anläggningstillgångsgrupp**.
16. Välj den anläggningstillgångsgrupp som ska användas när du skapar den nya anläggningstillgången i listan.
17. Klicka på länken på den valda raden i listan.
18. Klicka på **Bokför**. Anläggningstillgången skapas och förvärvas när fakturan bokförs.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
