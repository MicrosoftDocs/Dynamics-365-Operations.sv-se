---
title: Registrera inleverans av varor på en inköpsorder
description: Denna artikel förklarar hur du registrerar inleverans av varor direkt i en inköpsorder.
author: GalynaFedorova
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22baf6d0f6db04b3c6ce3c09ee8cb286e9a1e590
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882472"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrera inleverans av varor på en inköpsorder

[!include [banner](../../includes/banner.md)]

Denna artikel förklarar hur du registrerar inleverans av varor direkt i en inköpsorder. Det går också att registrera produktinleveransen på lagret och bokföra den senare på inköpsordern. Denna uppgift görs vanligtvis av en inköpsagent eller en leverantörsreskontrakoordinator. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Exemplet omfattar steg för att skapa en enda inköpsorder, så att du kan spela upp proceduren som en uppgiftsguide. Om du använder proceduren på dina egna data ska du börja med underuppgiften **Registrera inleverans av varor**.


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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]