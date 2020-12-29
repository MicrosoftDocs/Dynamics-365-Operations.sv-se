---
title: Lägg till en adress till en serviceorder
description: I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41497eacae8bcc0e57df8062f7f318a39c2b4909
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437851"
---
# <a name="add-an-address-to-a-service-order"></a>Lägg till en adress till en serviceorder    

[!include [banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder. När du skapar en serviceorder förs adressinformationen över från det projekt som serviceordern är kopplad till. Du kan dock välja en alternativ plats från adresser som redan finns i Microsoft Dynamics AX för kunder, leverantörer, platser, lagerställen, serviceorder och projekt.

Du kan också skapa en ny adress. Som standard överförs den nya adressen till projektet. Du kan dock ange att den nya adressen bara är relevant för den här instansen av tjänsten. Om du gör det överförs den nya adressen inte till projektet.

## <a name="create-a-customer-address-for-a-service-order"></a>Skapa en kundadress för en serviceorder

Om du vill lägga till en adress till en serviceorder:

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Öppna den serviceorder som du vill skapa en adress för.

3.  I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.

4.  På snabbfliken **adress** klicka på **lägga till adress**.

5.  Ange ett unikt namn för adressen och fyll i de återstående fälten i formuläret **Ny adress**. 
    

    > [!WARNING]
    > <P>Om du anger samma namn som en befintlig adress, kommer informationen som du anger i de återstående fälten skriva över informationen för den befintliga adressen.</P>


6.  Klicka på **OK** för att kopiera den nya adressen till din serviceorder.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Ange en alternativ adress på en serviceorder

Om du vill lägga till en alternativ adress till en serviceorder:

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Öppna den serviceorder som du vill ange en alternativ adress för.

3.  I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.

4.  På snabbfliken **adress** klicka på **Annan adress**.

5.  I formuläret **Val av adress** i fältet **posttyp** väljer du **serviceorder**.

6.  Välj en adress och klicka sedan på **OK** om du vill kopiera den till din serviceorder.


  


