---
title: Skapa serviceorder automatiskt
description: Du kan skapa serviceorder, antingen för ett serviceavtal eller för flera serviceavtal.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cc06536827320a35a691330d852ba64532604935
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817615"
---
# <a name="create-service-orders-automatically"></a>Skapa serviceorder automatiskt    

[!include [banner](../includes/banner.md)]


Du kan skapa serviceorder, antingen för ett serviceavtal eller för flera serviceavtal. När du har skapat dem kan du visa dina serviceorder i formuläret **Serviceorder**.

Serviceorder skapas bara för serviceavtalets giltighetsperiod. Om det intervall som du anger i dialogrutan **Skapa serviceorder** ligger före serviceavtalets startdatum eller efter dess slutdatum, skapas bara serviceorder för den del av intervallet som överensstämmer med serviceavtalet.

När du skapar serviceorder manuellt eller automatiskt från serviceavtalsraden, måste serviceordern infalla inom det tidsintervall som definieras av start- och slutdatumen för raden, såvida du inte anger något slutdatum på raden.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Skapa serviceorder automatiskt för ett serviceavtal

1.  Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.

2.  Välj ett serviceavtal.

3.  Klicka på fliken **Leverera** och klicka på fliken **planerade serviceorder**.

4.  Ange datum i fälten **Från datum** och **Till datum** för att definiera serviceperioden.

5.  Välj kryssrutan **Visa informationslogg** om du vill visa en lista med de serviceorder som skapas.

6.  Välj transaktionstyper i fältgruppen **Inkludera transaktionstyper**. Transaktionstyperna representerar raderna som skapas i serviceavtalet och varje transaktionstyp som du väljer genererar flera serviceorder, beroende på vilket serviceintervall som finns angivet på serviceavtalsraden.

7.  Markera kryssrutan **Kontinuerlig** om du vill skapa sådana serviceorder som saknas inom en kontinuerlig serie av serviceorder .

8.  Klicka på **OK**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Skapa serviceorder automatiskt för flera serviceavtal

1.  Klicka på **Servicehantering**\>**Periodisk**\>**Serviceorder**\>**Skapa serviceorder**.

2.  Klicka på **Välj** för att välja alternativ för att lägga till eller ta bort kriterier för att skapa serviceorder.

3.  Klicka på **OK**.

## <a name="see-also"></a>Se även

[Serviceorder](service-orders.md)

[Skapa serviceorder automatiskt](auto-create-service-orders.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]