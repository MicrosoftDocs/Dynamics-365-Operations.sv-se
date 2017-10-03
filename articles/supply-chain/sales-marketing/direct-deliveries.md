---
title: Direktleveranser
description: "Den här artikeln innehåller information om direktleveranser. Direktleveranser är leveranser som skickas direkt till din kund från leverantören."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fd1e98f677835f2ef3449adbb452d536441b0a65
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="direct-deliveries"></a>Direktleveranser

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om direktleveranser. Direktleveranser är leveranser som skickas direkt till din kund från leverantören.

Direktleveranser minskar leveranstiden och lagerhållningskostnaderna, eftersom inga produkter behöver förvaras i lagret innan de skickas till kunden.  

Du kan skapa direktleveranser från sidan **Försäljningsorder**. Skapa först en försäljningsorder och orderrader. Klicka sedan på fliken **Försäljningsorder** i åtgärdsfönstret och välj **Direktleverans**. Ange slutligen de rader som ska behandlas som en direktleverans. Nu skapas en länk mellan försäljningsorderraderna för direktleverans och motsvarande inköpsorderrader.  

**Obs!** Om en del av den beställda kvantiteten redan har levererats måste du dela upp resterande kvantitet. Skapa en ny rad för kvantiteten som ska levereras direkt och dra ifrån den här kvantiteten från den ursprungliga raden. Om till exempel den ursprungliga kvantiteten var 15 och fem har levererats måste du skapa en ny rad för resterande kvantitet på tio och sedan minska den ursprungliga kvantiteten efter beloppet.  

När du har skapat direktleveranslänken mellan försäljningsorderraderna och inköpsorderraderna kan du uppdatera försäljningsordern med en följesedel. Köra antingen en följesedelsuppdatering eller en fakturauppdatering från inköpsordern. Du måste fakturauppdatera försäljningsordern från sidan formuläret **Försäljningsorder**. En fakturauppdatering kan inte göra att kvantiteten i försäljningsordern blir större än kvantiteten som registrerats som mottagen. En försäljningsorderrad kan till exempel ha tio enheter, men endast fem enheter från försäljningsorderraden har uppdaterats med hjälp av en följesedel. Om du väljer **Alla** i listan **Kvantitet** när du fakturauppdaterar försäljningsordern, fakturauppdateras enbart de artiklar som fysiskt har mottagits eller har uppdaterats med hjälp av en följesedel. Hela försäljningsorderraden blir inte uppdaterad.

## <a name="delivery-date"></a>Leveransdatum
När du uppdaterar fältet **Begärt inleveransdatum** på försäljningsorderraden uppdateras även fältet **Leveransdatum** på motsvarande inköpsorderrad. På samma sätt, när du uppdaterar fältet **Bekräftat** på inköpsorderraden uppdateras också fälten **Bekräftat inleveransdatum** och **Bekräftat transportdatum** på motsvarande försäljningsorderrad.

## <a name="delivery-address"></a>Leveransadress
Företagets adress är normalt leveransadressen för en inköpsorder. Men när du skapar en direktleverans anger du kundens adress som leveransadress. Om du ändrar leveransadressen på en inköpsorderrad som har leveranstypen **Direktleverans** uppdateras även leveransadressen på motsvarande försäljningsorderrad. På samma sätt, om du ändrar leveransadressen på försäljningsorderraden uppdateras även leveransadressen på inköpsorderraden.

## <a name="deleting-order-lines"></a>Ta bort orderrader
Om du vill ta bort en försäljningsorderrad med leveranstypen **Direktleverans** visas ett meddelande om att det finns inköpsorderrader som är kopplade till raden. Om försäljningsorderraden har dellevererats går det inte att ta bort försäljningsorderraden eller de inköpsorderrader som är kopplade till den.

## <a name="warehouse"></a>Lagerställe
När du skapar en direktleverans kommer artiklarna som du säljer aldrig fysiskt anlända till lagerstället. Du måste dock fortfarande ange ett lagerställe på försäljningsorderraden. På samma sätt kan plockkrav anges på artikelmodellgruppen för artikeln. Men eftersom artiklarna aldrig anländer fysiskt till ditt lagerställe ignoreras dessa krav om försäljningsordern är en direktleverans.




