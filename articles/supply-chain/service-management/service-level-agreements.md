---
title: Servicenivåavtal – översikt
description: I ett serviceavtal går kunden med på en minimisvarstid från det att serviceföretaget registrerar ärendet tills det har lösts.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f2cfa8b72e515b6237914499af626ff8262429d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974370"
---
# <a name="service-level-agreements-overview"></a>Servicenivåavtal – översikt       

[!include [banner](../includes/banner.md)]


Ett servicenivåavtal (SLA) är ett avtal mellan ett serviceföretag och en servicekund. I ett SLA går kunden med på en minimisvarstid från det att serviceföretaget registrerar ärendet tills det har lösts.

Ett SLA utgör en standardmall för vilken servicenivå som erbjuds en kund, så att det blir lätt för serviceföretaget att se när ett servicejobb ska slutföras.

Du kan skapa valfritt antal servicenivåavtal för att kunna erbjuda servicekunder olika servicenivåer.

## <a name="create-a-service-level-agreement"></a>Skapa ett servicenivåavtal.

1.  Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceavtal**.

2.  Välj du ett namn för serviceavtal i fältet **serviceavtal**.

3.  Ange den tidpunkt då du vill att servicesamtal som är kopplade till serviceavtalet. Välj en kalender om du vill basera serviceavtalet på för en specifik kalender.

## <a name="apply-a-service-level-agreement"></a>Tillämpa ett servicenivåavtal

Avtalet tillämpas direkt för ett serviceavtal.

Serviceorder som du skapar manuellt och kopplar till ett serviceavtal med ett servicenivåavtal jämförs med detta servicenivåavtal.

Serviceorder som skapas automatiskt kopplas inte till något servicenivåavtal.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Tillämpa servicenivåavtalet för ett serviceavtal

1.  Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**. Välj det serviceavtal som du vill tillämpa serviceavtalet för och klicka på **redigera** på **åtgärdsfönstret**.

2.  I fältet **serviceavtal**, markera serviceavtalet som du vill tilldela.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>Tillämpa servicenivåavtalet för en serviceavtalsgrupp

1.  Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceavtalsgrupper**.

2.  I fältet **serviceavtal**, markera serviceavtalet som du vill tilldela.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Spåra tid på en serviceorder mot ett servicenivåavtal

När du skapar en ny serviceorder för ett serviceavtal som har tilldelats ett serviceavtal initieras tidsintervallet för leverans av tjänsten och systemet börjar spåra leveranstiden. Du kan dessutom ange följande alternativ:

  - Du kan starta och stoppa tidsregistreringen på serviceordern för att registrera den totala tid som läggs på en serviceorder.

  - Du kan övervaka efterföljandegraden inom det intervall som har angetts i serviceavtalet.

  - Du kan definiera orsakskoder som måste anges om det intervall som har angetts i serviceavtalet överskrids.

## <a name="see-also"></a>Se även

[Visa efterlevnad av servicenivåavtal](view-compliance-with-service-level-agreements.md)

  


