---
title: Skapa och anskaffa tillgångar från leverantörsreskontra
description: Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b27ccc3b4c4f5470d3a5b8ed7347e269c6793b87
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976051"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Skapa och anskaffa tillgångar från leverantörsreskontra

[!include [banner](../../includes/banner.md)]

Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.  Här används redovisnings- och leverantörsreskontraansvariga och demonstrationföretaget USMF.


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

