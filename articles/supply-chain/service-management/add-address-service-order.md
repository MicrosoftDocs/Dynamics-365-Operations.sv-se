---
title: Lägg till en adress till en serviceorder
description: I denna artikel beskrivs hur du lägger till en kundadress i en serviceorder.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015737"
---
# <a name="add-an-address-to-a-service-order"></a>Lägg till en adress till en serviceorder

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du lägger till en kundadress i en serviceorder. När du skapar en serviceorder förs adressinformationen över från det projekt som serviceordern är kopplad till. Du kan dock välja en alternativ plats från adresser som redan finns i Microsoft Dynamics AX för kunder, leverantörer, platser, lagerställen, serviceorder och projekt.

Du kan också skapa en ny adress. Som standard överförs den nya adressen till projektet. Du kan dock ange att den nya adressen bara är relevant för den här instansen av tjänsten. Om du gör det överförs den nya adressen inte till projektet.

## <a name="create-a-customer-address-for-a-service-order"></a>Skapa en kundadress för en serviceorder

Om du vill lägga till en adress till en serviceorder:

1. Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.

1. Öppna den serviceorder som du vill skapa en adress för.

1. Öppna fliken **huvud**.

1. Expandera snabbflikarna **Adress** och välj sedan **Lägg till adress** i verktygsfältet Snabbflik.

1. Ange ett unikt namn för adressen och fyll i de återstående fälten i dialogrutan **Ny adress**. 

    > [!WARNING]
    > Om du anger samma namn som en befintlig adress, kommer informationen som du anger i de återstående fälten skriva över informationen för den befintliga adressen.

1. Klicka på **OK** för att kopiera den nya adressen till din serviceorder.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Ange en alternativ adress på en serviceorder

Om du vill lägga till en alternativ adress till en serviceorder:

1. Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.

1. Öppna den serviceorder som du vill ange en alternativ adress för.

1. Öppna fliken **huvud**.

1. Expandera snabbflikarna **Adress** och välj sedan **Annan adress** i verktygsfältet Snabbflik.

1. I dialogrutan **Adressurval** väljer du **Serviceorder** i listrutan ovanför nedrullningslistan.

1. Välj en adress och klicka sedan på **OK** om du vill kopiera den till din serviceorder.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]