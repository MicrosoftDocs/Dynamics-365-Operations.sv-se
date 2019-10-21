---
title: Ta emot artiklar i inköpsorder från artikelbehov
description: I det här avsnittet beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
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
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174430"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Ta emot artiklar i inköpsorder från artikelbehov

[!include [task guide banner](../../includes/task-guide-banner.md)]

I det här avsnittet beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.

Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen. 

I den här uppgiften används datauppsättningen USSI.

1. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Projekt > Alla projekt**.
2. Klicka på länken på önskad rad i listan.
3. Klicka på **Plan** i åtgärdsfönstret.
4. Välj **Artikelbehov**.
5. Välj **Ny**.
6. På den nya raden ange eller välj ett värde i fältet **Artikelnummer**.
7. Ange ett nummer i fältet **Kvantitet**.
8. Välj **Spara**.
9. I åtgärdsfönstret klicka på **Hantera**.
10. Välj **Funktioner**.
11. Välj **Skapa inköpsorder**.
12. Markera kryssrutan **Inkludera alla**.
13. I **leverantörskonto** fält, ange eller välj ett värde.
14. Välj **OK**.
15. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Inköpsorder > Alla inköpsorder**.
16. Klicka på länken på önskad rad i listan.
17. I åtgärdsfönstret, välj **Inköp**.
18. Välj **Bekräfta**.
19. Välj **Ta emot** i åtgärdsfönstret.
20. Välj **produktinleverans**
21. I fältet **Produktinleverans**, skriv ett värde.
22. Välj **OK**.

