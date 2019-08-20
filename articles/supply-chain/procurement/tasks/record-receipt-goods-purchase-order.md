---
title: Registrera inleverans av varor på en inköpsorder
description: Det häravsnittet visar dig hur du registrerar inleverans av varor direkt i en inköpsorder.
author: FrankDahl
manager: AnnBe
ms.date: 07/09/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e81bb3fe95326636c28885d4decad69f841e3db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844019"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrera inleverans av varor på en inköpsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det häravsnittet visar dig hur du registrerar inleverans av varor direkt i en inköpsorder. Det går också att registrera produktinleveransen på lagret och bokföra den senare på inköpsordern. Denna uppgift görs vanligtvis av en inköpsagent eller en leverantörsreskontrakoordinator. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Exemplet omfattar steg för att skapa en enda inköpsorder, så att du kan spela upp proceduren som en uppgiftsguide. Om du använder proceduren på dina egna data ska du börja med underuppgiften **Registrera inleverans av varor**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Förbered en ny inköpsorder för inleverans av varor.
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsorder > Alla inköpsorder**.
2. Välj **Ny**.
3. I fältet **Leverantörskonto** ange `US-101`.
4. Välj **OK**.
5. I fältet **artikelnummer** anger du `M0001`.
6. I fältet **Kvantitet** anger du `5`.
7. I åtgärdsfönstret, välj **Inköp**.
8. Välj **Bekräfta**.

## <a name="record-receipt-of-goods"></a>Registrera inleverans av varor
1. Välj **Ta emot** i åtgärdsfönstret.
2. Välj **produktinleverans** Fältet **Kvantitet** låter dig välja olika alternativ för den kvantitet som du vill ta emot. Till exempel om en kvantitet tidigare har registrerats i lagerstället, kan du välja **registrerad kvantitet**. Använd värdet **Beställd kvantitet** för det här exemplet.
3. Expandera valet **Översikt**.
4. I fältet **Produktinleverans** anger du ett värde. Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.  
5. Expandera avsnittet **Rader**.
6. Ställ in **kvantiteten** på 4. Här kan du manuellt ange den kvantitet som har inlevererats för varje rad i ordern.  
7. Välj **OK**. Varorna har nu registrerats som inlevererade på inköpsordern och en produktinleveransjournal har skapats som dokumentet för att återspegla detta. Du kan använda åtgärden Produktinleverans om du vill granska journalerna som skapats med inköpsordern och se vad som har levererats och när.  

