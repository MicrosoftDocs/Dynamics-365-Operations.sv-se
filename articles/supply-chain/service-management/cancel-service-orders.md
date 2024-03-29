---
title: Avbryt serviceorder
description: Du kan avbryta en serviceorder eller serviceorderrad från själva serviceordern, och du kan avbryta flera serviceorder genom att köra ett periodiskt jobb.
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228b76d6f6f0bb048662c8e82df76f51b7cb3652
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017388"
---
# <a name="cancel-service-orders"></a>Avbryt serviceorder   

[!include [banner](../includes/banner.md)]


Du kan avbryta en serviceorder eller serviceorderrad från själva serviceordern, och du kan avbryta flera serviceorder genom att köra ett periodiskt jobb.


> [!NOTE]
> <P>Du kan inte avbryta en serviceorder om detta inte är tillåtet i serviceorderns aktuella fas, om serviceordern innehåller artikelbehov eller om serviceordern redan har bokförts.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Avbryta en serviceorder i formuläret för serviceorder

1.  Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**. Välj serviceorder och klicka sedan på **Avbryt order** i åtgärdsfönstret.

## <a name="cancel-a-service-order-line"></a>Avbryta en serviceorderrad

1.  Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**. Dubbelklicka på den serviceorder som innehåller raden du vill annullera.

2.  Välj serviceorderraden som du vill avbryta och klicka sedan på **Avbryt orderrad** för att ändra status för raden till **Har avbrutits**.


> [!TIP]
> <P>Om du vill återkalla annulleringen av en serviceorderrad och ändra tillbaka status till <STRONG>Skapad</STRONG>, klickar du på <STRONG>Återkalla avbrott</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Avbryta flera serviceorder

1.  Klicka på **Servicehantering**\>**Periodisk**\>**Serviceorder**\>**Avbryt serviceorder**.

2.  Klicka på **Välj**.

3.  I formuläret **Förfrågan** i kolumnen **Kriterier** väljer du de serviceorder som du vill avbryta.

4.  Klicka på **OK** när du vill stänga formuläret **Förfrågan**.

5.  Markera kryssrutan **Visa informationslogg** om du vill skapa en informationslogg som anger avbrutna serviceorder.

6.  Markera kryssrutan **Återkalla avbrott** om du vill återkalla statusen **Har avbrutits** för en serviceorder.

7.  Klicka på **OK**.

Markerade serviceorder kommer då antingen att annulleras eller få sin status **Har avbrutits** ändrad till **Pågår**.


> [!NOTE]
> <P>Om du markerar kryssrutan <STRONG>Återkalla avbrott</STRONG> kommer serviceorder med statusen <STRONG>Har avbrutits</STRONG> att återkallas och inga serviceorder med statusen <STRONG>Pågår</STRONG> avbryts.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]