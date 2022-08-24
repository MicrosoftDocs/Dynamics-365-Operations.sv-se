---
title: Prisjusteringar och rabatter
description: Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.
author: josaw1
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.industry: Retail
ms.search.form: RetailParameters, RetailPeriodicDiscount
ms.openlocfilehash: ff90df814d6930b5cf92772e430625943e0ae983
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279100"
---
# <a name="price-adjustments-and-discounts"></a>Prisjusteringar och rabatter

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.

I Commerce kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i POS, en försäljningsorder i kundtjänst eller på en beställning online. Både prisjusteringar och rabatter kan länkas till prisgrupper. För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut. 

Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier. Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten. Commerce använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset. Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt. Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Handelsparametrar** innan du definierar en ny prisjustering eller rabatt.

> [!NOTE]
> Du kan ta bort en prisjustering eller rabatt. Statistisk information går dock förlorad.

## <a name="types-of-discounts"></a>Typer av rabatter

Det finns många olika typer av rabatter:

- **Enkel rabatt** – En procentandel eller ett belopp.
- **Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.
- **Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.
- **Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.
- **Kassabaserad rabatt** – En rabatt som tillämpas när transaktionens totalsumma överstiger ett angivet belopp och ett visst betalsätt (t. ex. kassa, kredit eller betalkort) används för betalning.
- **Leveransrabatt** – En rabatt som tillämpas när transaktionssumman är mer än ett angivet belopp och ett specifikt leveranssätt (t. ex. två dagars leverans nästföljande dag) används på ordern.

Både prisjusteringar och rabatter kan associeras till prisgrupper. Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.

> [!NOTE]
> Mixa och matcha-rabatten och tröskelrabatten har egenskaper som kallas "Räkna icke-rabatterbara produkter" respektive "Räkna icke-rabatterbara produkter mot tröskel". Om dessa egenskaper är aktiverade kan en artikel som inte berättigar till rabatt ändå hjälpa till att kvalificera en transaktion för rabatten, men den icke-berättigade artikeln får inte rabatten. 
> 
> Om du till exempel skapar en mixa och matcha-rabatt med två rader, A och B, där en kund ska få 10 % rabatt på båda artiklarna, men artikel A har konfigurationen "Förhindra alla rabatter" markerad, skulle detta normalt hindra artikel A från att inkluderas i rabatten. Om egenskapen "Räkna icke-rabatterbara produkter" är aktiverad kan emellertid artikel A användas för att kvalificera sig för mixa och matcha-rabatten, men 10 %-rabatten tillämpas endast på artikel B. Liknande logik gäller för tröskelrabatten. 
>
> Egenskapen "Räkna icke-rabatterbara produkter mot tröskel" har emellertid en ytterligare kapacitet när den jämförs med egenskapen "Räkna icke-rabatterbara produkter" för mixa och matcha-rabatterna. Om tröskelrabatten är aktiverad, och om det finns en artikel som har en befintlig rabatt som hindrar artikeln från att omfattas av andra rabatter, blir priset som betalas för artikeln lika med eller högre än tröskelvärdet, men artikeln får inte ytterligare rabatt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
