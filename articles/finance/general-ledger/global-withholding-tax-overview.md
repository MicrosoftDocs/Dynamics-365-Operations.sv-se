---
title: Global källskatt
description: Detta ämne innehåller information om funktioner för global källskatt och hur du ställer in den. Den globala källskattefunktionen förbättras för leverantörs- och kundtransaktioner så att källskatt beräknas på artikelnivå.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 25fc503d6145872b8e9f28b8d9a4d7b9c1ba53a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249177"
---
# <a name="global-withholding-tax"></a>Global källskatt

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om funktioner för global källskatt och förklarar hur du ställer in den. Den nya funktionen är tillgänglig i version 10.0.17 och senare versioner.

Den globala källskattefunktionen förbättras för leverantörs- och kundtransaktioner så att källskatt beräknas på artikelnivå. Saldot på källskattekontot från inköpstransaktioner kan kvittas genom att du kör betalningsjobbet för källskatt mot kvittningskontot för källskatt.

> [!NOTE]
> Global källskatt har inte stöd för funktionen **Underhållsavgifter** på inköpsorder-, leverantörsfaktura- och försäljningsordersidorna.

## <a name="turn-on-global-withholding-tax"></a>Aktivera global källskatt

1. I arbetsytan **Funktionshantering** väljer du **Global källskatt** och sedan **Aktivera nu**.
2. Gå till **Skatt \> Inställningar \> Parametrar \> Redovisningsparametrar** och sedan, på fliken **Källskatt**, anger du alternativet **Aktivera global källskatt** som **Ja**.
3. Välj **Spara**.
4. Uppdatera sidan i webbläsaren.

> [!NOTE]
> Funktionen för global källskatt kan inte aktiveras för länder/regioner där det redan finns lokala lösningar för källskatt. Dessa områden omfattar, men är inte begränsade till, Indien, Brasilien, Thailand, Saudiarabien, Irland, Storbritannien och USA.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]