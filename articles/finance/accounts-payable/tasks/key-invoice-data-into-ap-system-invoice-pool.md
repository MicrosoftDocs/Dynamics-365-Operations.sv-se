---
title: Mata in fakturadata i LR-systemet genom att använda fakturapool
description: I det här avsnittet beskrivs hur du använder fakturaregister för att skapa fakturor.
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4768ee6ddbaba8ae5bab5e2f9f7df9239efeb90
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358299"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Mata in fakturadata i LR-systemet genom att använda fakturapool

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du använder fakturaregister för att skapa fakturor. Använd sedan fakturapoolen för att matcha fakturan till en inköpsorder och för att slutföra utgiften i leverantörsfakturasidan.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Inköpsorder > Inköpsorder**.
2. Skapa en inköpsorder genom att välja **Ny**.
3. I fältet **Leverantörskonto** väljer du en levernatör i den nedrullningsbara listan. Välj till exempel leverantör **1001**.
4. Välj **OK**.
5. I fält **Artikelnummer** klicka på tjänstartikeln i den nedrullningsbara listan. Välj till exempel **S0001**. Nettobeloppet är 75,00.  Det är det belopp som ska förvänta vi på fakturan.  
6. I åtgärdsfönstret, välj **Inköp**.
7. Välj **Bekräfta**.

## <a name="create-and-post-and-invoice"></a>Skapa och bokför och fakturera
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturaregister**.
2. Välj **Ny**.
3. Öppna sökningen för att välja namnet på det fakturaregister som du vill använda.
4. Välj namnet på det fakturaregister som du vill använda.
5. Välj **Rader** om du vill öppna registret och ange utgiftsrader.
6. Välj en leverantör i sökningen. Välj till exempel leverantör **1001**.
7. Ange fakturanumret i fältet **Faktura**.
8. I fältet **Beskrivning** anger du ett värde.
9. I fältet **Kredit** väljer du ett tal.
10. I fältet **Inköpsorder** öppnar du den nedrullningsbara listan för att välja den inköpsorder som du skapade tidigare.
11. Markera en godkännare i den nedrullningsbara listan i fältet **Godkänd av** och klicka på **Välj** för att välja godkännare.
12. Vald **bokföring**

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Öppna en faktura från poolen och matcha den till en inköpsorder för att slutföra fakturaprocessen
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturapool**.
2. Välj **Inköpsorder** om du vill skapa en leverantörsfaktura från fakturan i poolen.
3. Välj fakturan som du vill granska.
4. Välj **Uppdatera matchningsstatus** så utförs matchningen.
5. Välj **Alternativ** i åtgärdsfönstret.
6. Välj **Byt visning**.
7. Välj **Rutnätsvy**.
8. Vald **bokföring**
9. Stäng sidan.
10. I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Leverantörer > Leverantörer**.
11. Välj providern på inköpsordern. Välj till exempel leverantör **1001**.
12. Klicka på **Leverantör** i åtgärdsfönstret.
13. Markera **transaktioner**
14. Välj den faktura som du själv har skapat. Ankomstregistreringaccrualen återfördes och bokförts i lämplig utgiftskonto.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
