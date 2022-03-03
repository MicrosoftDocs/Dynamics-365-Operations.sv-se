---
title: Placera B2B-webbplatsorder snabbt
description: I det här avsnittet beskrivs möjligheterna med Microsoft Dynamics 365 Commerce att låta B2B-användare (business-to-business) snabbt placera bulk och upprepa order.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 4909056435425f251efb45f5a4355f103a420ba8
ms.sourcegitcommit: 4d52c67f52ad0add63cd905df61367b344389069
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8312600"
---
# <a name="place-b2b-website-orders-quickly"></a>Placera B2B-webbplatsorder snabbt

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs möjligheterna med Microsoft Dynamics 365 Commerce att låta B2B-användare (business-to-business) snabbt placera bulk och upprepa order.

Dynamics 365 Commerce B2B e-handelswebbplatser låter användare utföra standardoperationer som att upptäcka nya produkter via sökning och surfning, visa produktinformation, lägga till varor i kundvagnen och checka ut. Men medan kunder på företag-till-konsument-webbplatser (B2C) vanligtvis beställer varor i små kvantiteter och beställer dem bara en gång, beställer B2B-kunder vanligtvis varor i stora kvantiteter och beställer om dem flera gånger. Eftersom dessa kunder vanligtvis vet exakt vilka artiklar de vill köpa hoppar de ofta över produktinköpsfasen och går direkt till order. För att uppfylla dessa kunders behov har Commerce B2B-e-handelswebbplatser olika möjligheter som hjälper dem att placera order snabbt.

## <a name="bulk-order-by-item-number"></a>Massbeställning efter artikelnummer

Commerce B2B-näthandelssajter låter webbplatsanvändare lägga till artiklar i vagnen genom att ange produktartikelnummer tillsammans med önskad kvantitet.

Följande bild visar ett exempel på snabb orderinmatning efter produktartikelnummer.

![Snabb orderinmatning via produktartikelnummer.](../media/QuickAddByItem.png)

## <a name="bulk-order-by-variant"></a>Bulkorder per variant

Med Commerce B2B-e-handelswebbplatser kan webbplatsanvändare snabbt lägga till olika varianter av samma produkt i en enda vy som visar lagertillgänglighet efter storlek, färg och utförande. Dessutom kan webbplatsanvändare enkelt ange samma kvantitet för alla lagerprodukter genom att välja **Ange alla kvantiteter**.

I följande bild visas ett exempel på snabborderinmatning där funktionen "ange alla kvantiteter" används.

![I snabborderfunktionen används funktionen "ange alla kvantiteter".](../media/MatrixView.png)

## <a name="use-order-templates-for-quick-order-entry"></a>Använd ordermallar för snabborderinmatning

Inköpare på B2B-webbplatser beställer ofta specifika artiklar tillsammans. Om du till exempel beställer för en byggplats kanske du vill beställa skjortor, jackor, byxor, skor och mössor tillsammans. Om du beställer för ett sjukhus där läkare, sjuksköterskor och städpersonal har olika uniformer, kanske du vill gruppera varje uniformstyp för enklare beställning. I dessa typer av scenarier kan ordermallar skapas på Commerce B2B-webbplatser. Webbplatsanvändare kan skapa ett val valt antal anpassade mallar och sedan beställa alla eller vissa av artiklarna från dessa mallar efter behov.

I följande illustration visas ett exempel på en ordermall.

![Exempel på en ordermall.](../media/OrderTemplateHeader.png)

Följande illustration visar ett exempel på detaljvy för en beställningsmall.

![Exempel på detaljvyn för en ordermall.](../media/OrderTemplateLines.png)

## <a name="reorder-from-order-history"></a>Beställning från orderhistorik

Commerce B2B-e-handelswebbplatser låter webbplatsanvändare snabbt beställa om artiklar från sin orderhistorik. Webbplatsanvändare kan antingen köpa valda artiklar från sin orderhistorik eller lägga till alla tidigare inköpta artiklar i vagnen.

I bilden nedan visas ett exempel på en användares orderhistorik och alternativen för att beställa om artiklar från den.

![Beställning från orderhistorik.](../media/Reorder.png)

I det här avsnittet beskrivs bara några av de sätt som Commerce B2B-webbplatser hjälper användarna att snabbt hitta, beställa och beställa de produkter de vill ha. Fler möjligheter finns i utveckling för att ytterligare förenkla processen för att fånga bulkorder.
