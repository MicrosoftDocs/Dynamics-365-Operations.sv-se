---
title: Ställ in serviceintervall
description: I denna artikel beskrivs hur du konfigurerar serviceintervall. Serviceintervallet anger frekvensen med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder.
author: sorenva
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b8a31af061b90aeddfb460f6e86c2c5636b280
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845965"
---
# <a name="set-up-service-intervals"></a>Ställ in serviceintervall  

[!include [banner](../includes/banner.md)]

Serviceintervallet anger frekvensen med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder.

1. Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceintervall**.
2. Skapa ett nytt serviceintervall.
3. Ange ID och beskrivning för serviceintervall.
4. Välj intervall i fältet för **intervall**.
5. Ange ett namn på arbetsflödet i fältet för **frekvens**. Frekvensen är den faktor med vilken du måste multiplicera intervallet för att erhålla serviceavtalsintervallet.
6. Tryck på **Alt+S** om du vill spara serviceintervallet.

## <a name="example"></a>Exempel

Du vill skapa ett serviceintervall på 10 dagar.

**Skapa ett 10-dagars serviceintervall**

1. Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceintervall**.
2. Skapa ett nytt serviceintervall.
3. Ange ID och beskrivning för serviceintervall.
4. Välj **varje dag** i fältet för **intervall**.
5. Ange 10 i fältet för **frekvens**.
6. Tryck på **Alt+S** om du vill spara serviceintervallet.

## <a name="related-articles"></a>Relaterade artiklar

[Serviceintervall](service-intervals.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]