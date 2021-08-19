---
title: Kundposter visas inte i Commerce-administration
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce-administration.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f551f94cec71ba7d740756c383b55741e9f8d42e20e63846ea6242383dc3ba32
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733903"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Kundposter visas inte i Commerce-administration

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce-administration.

## <a name="description"></a>beskrivning

När du skapar en ny kundpost med hjälp av inloggningsflödet i e-handelsbutiken visas inte motsvarande kundpost direkt i Commerce-administration.

## <a name="resolution"></a>Upplösning

### <a name="disable-customer-creation-in-async-mode"></a>Inaktivera skapande av kunder i asynkront läge

> [!IMPORTANT]
> Om du inaktiverar asynkrona kundgenereringen kan systemprestanda påverkas eftersom varje post skapas en begäran i realtid till Commerce-administration. Om Commerce-administration dessutom är ned (till exempel under serviceflöden), orsakar eventuella nya kundgenereringsflöden fel.

Om du vill inaktivera skapande av kunder i asynkrona läget i Commerce-administration följer du dessa steg.

1. Gå till **Retail och Commerce \> Kanalinställningar \> Inställningen för onlinebutik \> Funktionsprofiler**.
1. Om du inte redan använder en funktionsprofil för din onlinekanal skapar du en.
1. Kontrollera att alternativet **Skapa kund i asynkront läge** anges till **Nej**.
1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj den onlinebutik som du vill inaktivera asynkront kundgenerering för.
1. På fliken **Allmänt**, se till att fältet **funktionsprofilen** är inställd på den funktionsprofil som du använder för din onlinekanal.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-klientorganisation i Commerce](../set-up-b2c-tenant.md)
