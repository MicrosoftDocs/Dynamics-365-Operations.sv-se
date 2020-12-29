---
title: Använd fasorsakskoder
description: Med en orsakskod kan du ange varför ett serviceavtal har annullerats eller varför en serviceorder har överskridigt tidsgränsen som du angav i avtalet.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74594871e9eeed86ae2914d1e5a08c0af28ab643
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437822"
---
# <a name="use-stage-reason-codes"></a>Använd fasorsakskoder 

[!include [banner](../includes/banner.md)]


Med en orsakskod kan du ange varför ett serviceavtal har annullerats eller varför en serviceorder har överskridigt tidsgränsen som du angav i avtalet.

Du kan även ange att en orsakskod krävs när ett serviceavtal annulleras, eller när tidsgränsen som har angetts i servicenivåavtalet för serviceordern överskrids.

Om du har angett att en orsakskod krävs måste du ange en orsakskod i följande situationer:

  - När en serviceordern flyttas till en fas som stoppar tidsregistreringen enligt serviceavtalet för serviceordern.

  - När serviceordern kvitteras.

  - När tidsregistreringen stoppas manuellt.

## <a name="set-up-reason-codes"></a>Ställ in orsakskoder

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceorder**\>**Ange orsakskoder**.

2.  I formuläret **Fasorsakskoder**, klicka på **Ny** för att skapa en ny orsakskod.

3.  Ange en unik orsakskod för fas i fältet **Fasorsakskod**.

4.  Ange en orsakskod för fas i fältet **Beskrivning**.

5.  Stäng formuläret så att ändringarna sparas.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Kräv orsakskoder när ett serviceavtal annulleras

1.  Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.

2.  I formuläret **Serviceparametrar** klickar du på länken **allmänt** och markerar sedan kryssrutan **orsakskod vid annullering**.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Kräv orsakskoder när en serviceorder överskrider tidsgränsen som anges i serviceavtalet

1.  Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.

2.  I formuläret **Serviceparametrar** klickar du på länken **allmänt** och markerar sedan kryssrutan **Orsakskod för överskriden tidsgräns**.

## <a name="see-also"></a>Se även

[Registrering av start- och stopptid för en serviceorder](start-and-stop-time-recording-on-a-service-order.md)

  


