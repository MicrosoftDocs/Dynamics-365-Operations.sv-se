---
title: Registrering av start- och stopptid för en serviceorder
description: Registrering av start- och stopptid för en serviceorder
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16d9f48ed38a5033fab94d45821f0ed6f7f1f011
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558398"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a>Registrering av start- och stopptid för en serviceorder 

[!include [banner](../includes/banner.md)]


Använd den här proceduren om du vill starta och stoppa tidsregistrering för en serviceorder som har ett definierat serviceavtal.

## <a name="start-time-recording"></a>Starta tidsregistrering

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **starta**.

3.  Ange datum och tid då tidsregistreringen ska startas.

## <a name="stop-time-recording"></a>Stoppa tidsregistrering

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **stopp**.

3.  Ange datum och tid då tidsregistreringen ska stoppas.

4.  Välj **Lägg till en återkallningsorsak**, och välj en orsakskod i **Fasorsakskod** om du vill ange en orsak till varför tidsregistreringen stoppas.


> [!NOTE]
> <P>Om <STRONG>Orsakskod för överskriden tidsgräns</STRONG> väljs i formuläret <STRONG>Serviceparametrar</STRONG> måste du ange en orsakskod innan du kan stoppa tidsregistreringen.</P>



## <a name="see-also"></a>Se även

[Starta tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/en-us/library/hh242297\(v=ax.60\))

[Stoppa tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/en-us/library/hh242241\(v=ax.60\))

  


