---
title: Konfigurera kontantbenämningar för POS
description: Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån POS.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.industry: Retail
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
ms.openlocfilehash: c61cde76bf2bfe3ff48b306a8a161fa27f50ac41
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273704"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a>Konfigurera kontantbenämningar för POS

[!include [banner](includes/banner.md)]

Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån POS. Dessa benämningar kan användas vid beräkning av kontanter i kassaavstämningar i slutet av dagen eller för att genomföra en försäljning snabbt.

## <a name="define-denominations"></a>Definiera benämningar

Benämningar ställs in per butik på alternativet **Ställ in** \> **kontantavstämning** från sidan butiksegenskaper.

![Alternativ för kontantavstämning.](./media/image1-denomination.png)

För att definiera en benämning:

1. Klicka på **Ny**.
1. Ange typen (mynt eller sedel).
1. Ange beloppet (värde).

![Sida för valörer vid kontantavstämning.](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Konfigurera funktionsprofilen

Vid betalning av kontanter i POS kan användaren använda sedelbenämningar för att snabbt ange det belopp som betalats av kunden. Du kan konfigurera två alternativ för visning av benämningen i POS i funktionsprofilen.

- **Större eller lika med det förfallna beloppet** – som standard visar POS endast de sedelbenämningar som är större än beloppet som förfaller till betalning, vilket gör det möjligt för snabb genomföring av transaktionen. Om till exempel det förfallna beloppet är 7,50 visar POS följande benämningar: 10, 20, 50 och 100. Om du rör något av dessa belopp kommer försäljningaen att genomföras automatiskt för detta belopp. Sedlarna 1 och 5 visas inte eftersom dessa belopp är mindre än beloppet som förfaller.
- **Alla benämningar** – Markera det här alternativet för att alltid visa alla sedelbenämningar i POS, oavsett hur mycket förfaller. Detta innebär att användaren kan använda en kombination av sedlar till det förfallna beloppet. Om till exempel det förfallna beloppet är 25,00 kan användaren välja 20 och 5 för att slutföra försäljningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
