---
title: Registrering av start- och stopptid för en serviceorder
description: Registrering av start- och stopptid för en serviceorder
author: sorenva
ms.date: 05/07/2018
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
ms.openlocfilehash: 7b110c6a08d946b4527f47f6d4181819f3508fee
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016345"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a>Registrering av start- och stopptid för en serviceorder 

[!include [banner](../includes/banner.md)]


Använd den här proceduren om du vill starta och stoppa tidsregistrering för en serviceorder som har ett definierat serviceavtal.

## <a name="start-time-recording"></a>Starta tidsregistrering

1.  Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.

2.  Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **starta**.

3.  Ange datum och tid då tidsregistreringen ska startas.

## <a name="stop-time-recording"></a>Stoppa tidsregistrering

1.  Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.

2.  Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **stopp**.

3.  Ange datum och tid då tidsregistreringen ska stoppas.

4.  Välj **Lägg till en återkallningsorsak**, och välj en orsakskod i **Fasorsakskod** om du vill ange en orsak till varför tidsregistreringen stoppas.


> [!NOTE]
> <P>Om <STRONG>Orsakskod för överskriden tidsgräns</STRONG> väljs i formuläret <STRONG>Serviceparametrar</STRONG> måste du ange en orsakskod innan du kan stoppa tidsregistreringen.</P>



## <a name="see-also"></a>Se även

[Starta tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/library/hh242297\(v=ax.60\))

[Stoppa tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/library/hh242241\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]