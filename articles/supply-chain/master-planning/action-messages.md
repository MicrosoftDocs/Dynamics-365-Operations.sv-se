---
title: Åtgärdsmeddelanden
description: Ett åtgärdsmeddelande är ett systemgenererat förslag om att ändra en befintlig planerad eller bekräftad order.
author: ChristianRytt
manager: tfehr
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd9efebbe5cfea1bb2c9beedfea4fa0492040ddc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989778"
---
# <a name="action-messages"></a>Åtgärdsmeddelanden

[!include [banner](../includes/banner.md)]

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







[!INCLUDE[footer-include](../../includes/footer-banner.md)]