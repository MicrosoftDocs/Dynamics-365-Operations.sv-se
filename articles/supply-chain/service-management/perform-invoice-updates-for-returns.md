---
title: Utföra fakturauppdateringar för returer
description: Denna funktion stöder även de affärsprocesser som många företag använder som väljer att fakturera returorder och försäljningsorder samtidigt och av samma person.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
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
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec803aaa2f750c43a1865c9536730b275e6ef1d4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202156"
---
# <a name="perform-invoice-updates-for-returns"></a>Utföra fakturauppdateringar för returer 

[!include [banner](../includes/banner.md)]


En returorder i är en typ av försäljningsorder som har markerats som en returorder. Därför används listsidan **alla försäljningsorder** för att generera fakturor för returorder i stället för formuläret **returorder**. Denna funktion stöder även de affärsprocesser som många företag använder som väljer att fakturera returorder och försäljningsorder samtidigt och av samma person.

Eftersom fakturan för en returnerad artikel är för ett negativt belopp kallas den kreditfaktura.

När du ställer in fakturauppdateringen för batchbearbetning måste försäljningsordern **Returnerad order** ha returradstatusen **Inlevererad**, vilket betyder att orderns följesedel har uppdaterats.

## <a name="post-an-invoice-for-a-return-order"></a>Bokföra en faktura för en returorder

1.  Klicka på **Kundreskontra** \> **Vanligt** \> **Försäljningsorder** \> **Alla försäljningsorder**.

2.  Välj en försäljningsorder för vilken **returnerad order** visas i fältet **Ordertyp**.

3.  I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.

4.  Välj fliken **Parameters**, markera kryssrutan **Bokföring**.

5.  Gå igenom informationen i formuläret och gör de ändringar som behövs.

6.  Klicka på **OK**. Kreditfakturan är bokförd.

## <a name="see-also"></a>Se även

[Följesedelsuppdateringar för returer](packing-slip-updates-returns.md)

  


