---
title: odokumenterade
description: "Ett åtgärdsmeddelande är ett systemgenererat förslag om att ändra en befintlig planerad eller bekräftad order."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: bfeca6506d2452bf7582bdd206f8c3ad3f2a4330
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="action-messages"></a>Åtgärdsmeddelanden

[!include[banner](../includes/banner.md)]


Ett åtgärdsmeddelande är ett systemgenererat förslag om att ändra en befintlig planerad eller bekräftad order.

## <a name="introduction"></a>Introduktion

Åtgärdsmeddelanden genereras av huvudplaneringsberäkningen som svar på ändrade krav. Till exempel kanske transportdatumet eller kvantitet har ändrats på en försäljningsorder för vilken du redan har skapat en inköpsorder för att uppfylla efterfrågan. I detta fall genereras ett eller flera åtgärdsmeddelanden av huvudplaneringsberäkningen för att uppdatera inköpsordern. Du bestämmer om du vill göra ändringarna som föreslås.

Du kan ställa in hur åtgärdsmeddelanden beräknas för en disponeringsgrupp som du kan koppla till en artikel.

## <a name="select-action-messages"></a>Välja åtgärdsmeddelanden

På sidan **Disponeringsgrupper** kan du välja de åtgärdsmeddelanden som du vill att systemet ska generera och de disponeringsgrupper eller artiklar som meddelandena gäller för. Du kan välja följande åtgärdsmeddelanden.

| Meddelande             | Beskrivning                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Förskott**         | Om du väljer detta meddelande genererar systemet åtgärdsmeddelanden, om det behövs, för att flytta order till ett tidigare datum. I fältet **Tidigareläggningsmarginal** kan du även ange det högsta antalet dagar mellan inleverans och utleverans utan tidigareläggningsåtgärd. |
| **Senarelägg**        | Om du väljer detta meddelande genererar systemet åtgärdsmeddelanden, om det behövs, för att flytta order till ett senare datum. I fältet **Senareläggningsmarginal** kan du ange det högsta antalet dagar mellan inleverans och utleverans utan senareläggningsåtgärd.       |
| **Skriv av**        | Om du väljer detta meddelande ska tillverkningsorder, inköpsorder och andra inleveranstransaktioner minskas för att förhindra överskottslagernivåer.                                                                                                   |
| **Öka**        | Om du väljer detta meddelande ska tillverkningsorder, inköpsorder och andra inleveranstransaktioner ökas för att förhindra brist i lager.                                                                                                    |
| **Härledda åtgärder** | Om du väljer detta meddelande skapas åtgärdsmeddelanden för härledda behov, till exempel åtgärder för komponentorder som uppfyller produktionen.                                                                                                   |






