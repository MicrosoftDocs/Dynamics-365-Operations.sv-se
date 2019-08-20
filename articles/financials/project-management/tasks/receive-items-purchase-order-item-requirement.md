---
title: Ta emot artiklar i inköpsorder från artikelbehov
description: Nedan beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fee2c965b0c065f00564b849ec93504336fb3f60
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838257"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Ta emot artiklar i inköpsorder från artikelbehov

[!include [task guide banner](../../includes/task-guide-banner.md)]

Nedan beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.

Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen. 

I den här uppgiften används datauppsättningen USSI.

1. Gå till Projekthantering och redovisning > Projekt > Alla projekt.
2. Klicka på länken på den valda raden i listan.
3. Klicka på Plan i åtgärdsfönstret.
4. Klicka på Artikelbehov.
5. Klicka på Ny.
6. Markera vald rad i listan.
7. Ange eller välj ett värde i fältet Artikelnummer.
8. Ange ett tal i fältet Kvantitet.
9. Klicka på Spara.
10. Klicka på Hantera i åtgärdsfönstret.
11. Klicka på Funktioner.
12. Klicka på Skapa inköpsorder.
13. Markera kryssrutan Inkludera.
14. Ange eller välj ett värde i fältet Leverantörskonto.
15. Klicka på OK.
16. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
17. Klicka på länken på den valda raden i listan.
18. Klicka på Inköp i åtgärdsfönstret.
19. Klicka på Bekräfta.
20. Klicka på Ta emot i åtgärdsfönstret.
21. Klicka på Produktinleverans.
22. Markera vald rad i listan.
23. Skriv ett värde i fältet Produktinleverans.
24. Klicka på OK.

