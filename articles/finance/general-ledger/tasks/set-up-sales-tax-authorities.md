---
title: Ställ in momsmyndigheter
description: Skattemyndigheter är enheter dit den insamlade momsen måste rapporteras och betalas.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc6aeb39591c68cae78537faa077010d68628b02
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144776"
---
# <a name="set-up-sales-tax-authorities"></a>Ställ in momsmyndigheter

[!include [banner](../../includes/banner.md)]

Skattemyndigheter är enheter dit den insamlade momsen måste rapporteras och betalas. Du kan betala moms direkt till myndigheten eller via ett leverantörskonto som du skapar för skattemyndigheten. Om du gör detta kan företaget använda sina vanliga betalningsrutiner för att betala skattemyndigheten i tid. Om du inte registrerar skattemyndigheten som en leverantör måste någon förbereda en manuell betalning till skattemyndigheten på relevant förfallodatum. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Skatt > Indirekta skatter > Moms > Skattemyndigheter.
2. Klicka på Ny.
3. Ange ett värde i fältet Myndighet.
4. Skriv ett värde i fältet Namn.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Välj rapportlayout för ditt land/region, om det finns tillgängligt. Om rapportlayouterna inte motsvarar kraven från skattemyndigheten, ska du använda standardlayouten.
9. Ange värden i avrundningformuläret och avrundningsfälten för att ange hur det totala momsbeloppet för betalning ska avrundas. Alla avrundningsdifferenser bokförs på konton för automatiska transaktioner som ställts in i redovisningen.
10. Välj ett tal i fältet Avrundning.
11. Klicka på Spara.

