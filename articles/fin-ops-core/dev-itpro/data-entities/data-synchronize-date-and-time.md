---
title: Synkronisera datum och tid i importjobb
description: Använd UTC-tidszoner i importjobb för att undvika problem med tidszonskonverteringen.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae04b09a68e64d6d70c0329e689ab08c3903fca0
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798729"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Synkronisera datum och tid i importjobb

[!include [banner](../includes/banner.md)]

Det är viktigt att ange tidszonen för ditt importjobb till Coordinated Universal Time (UTC). Oväntade datum och tider i importerade data kanske visas om du använder en annan inställning. Utan rätt inställning konverterar importprocessen UTC-datumet till det lokala formatet och sedan konverterar systeminställningarna det igen.

Denna dubbla konvertering gör att datum ändras mellan program. Till exempel kan den dubbla konverteringen orsaka att en anställds startdatum skiljer sig mellan Dynamics 365 Human Resources och Dynamics 365 Finance på grund av skillnader i lokala tidszoner. Om du ställer in importjobbet på UTC löser du problemet.

1. I Dynamics 365 Finance and Operations, välj **Datahantering**.

2. Välj **Importera projekt** och välj sedan projektet.

3. Under **Källdatumformat**, välj **CSV-Unicode**.

   [![Ändra källdatumformat till UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Ändra **Tidszon** till **Coordinated Universal Timezone** och ändra **Språk** till **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]