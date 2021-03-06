---
title: Inställningarna för avräkningsprincipen på strukturlisterader respekteras inte
description: Inställningarna för avräkningsprincipen på strukturlisterader (BOM) respekteras inte.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026917"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Inställningarna för avräkningsprincipen på strukturlisterader respekteras inte

KB-nummer: 4612725

## <a name="symptoms"></a>Symtom

Det här problemet uppstår när fältet **Automatisk BOM-konsumtion** under fliken **Automatisk uppdatering** på sidan **Produktionskontrollparametrar** är inställt på *Avräkningsprincip*. Denna inställning visar att alla strukturlisterader (BOM) automatiskt ska förbrukas när en inköpsorder tas emot. Om fältet **Avräkningsprincip** på BOM-rader har ställts in på *Manuellt*, kan du förvänta dig att BOM-raderna inte förbrukas automatiskt. När det här problemet uppstår förbrukas dock strukturlisterader där fältet **Avräkningsprincip** är inställt på *Manuellt* automatiskt.

## <a name="resolution"></a>Upplösning

Om du upplever det här problemet kan produktionskontrollparametrarna ställas in så att de åsidosätter inställningen för **Avräkningsprincip** på strukturlisterader. På sidan **Produktionskontrollparametrar**, under fliken **Automatisk uppdatering**, kontrollerar du värdet för fältet **Automatisk strukturlisteförbrukning**. Vid inställning på *Alltid* ignorerar systemet inställningen för **Avräkningsprincip** på alla strukturlisterader och avräknar alltid raderna. Om du vill att systemet respekterar inställningen för **Avräkningsprincip** på strukturlisterader, ändrar du värdet för fältet **Automatisk strukturlisteförbrukning** till *Avräkningsprincip*.
