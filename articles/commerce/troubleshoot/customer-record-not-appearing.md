---
title: Kundposter visas inte i Commerce headquarters
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: f1ad1f45abbc95cbf6d41b3c8681db781c6c9d23
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268849"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Kundposter visas inte i Commerce headquarters

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när kundposter inte visas direkt i Commerce headquarters.

## <a name="description"></a>beskrivning

När du skapar en ny kundpost med hjälp av inloggningsflödet i näthandelsbutiken visas inte motsvarande kundpost direkt i Commerce headquarters.

## <a name="resolution"></a>Upplösning

### <a name="disable-customer-creation-in-async-mode"></a>Inaktivera skapande av kunder i asynkront läge

> [!IMPORTANT]
> Om du inaktiverar asynkrona kundgenereringen kan systemprestanda påverkas eftersom varje post skapas en begäran i realtid till Commerce headquarters. Om Commerce headquarters dessutom är ned (till exempel under serviceflöden), orsakar eventuella nya kundgenereringsflöden fel.

Om du vill inaktivera skapande av kunder i asynkrona läget i Commerce headquarters följer du dessa steg.

1. Gå till **Retail och Commerce \> Kanalinställningar \> Inställningen för onlinebutik \> Funktionsprofiler**.
1. Om du inte redan använder en funktionsprofil för din onlinekanal skapar du en.
1. Kontrollera att alternativet **Skapa kund i asynkront läge** anges till **Nej**.
1. Gå till **Retail och Commerce \> Kanaler \> Onlinebutiker**.
1. Välj den onlinebutik som du vill inaktivera asynkront kundgenerering för.
1. På fliken **Allmänt**, se till att fältet **funktionsprofilen** är inställd på den funktionsprofil som du använder för din onlinekanal.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-klientorganisation i Commerce](../set-up-b2c-tenant.md)
