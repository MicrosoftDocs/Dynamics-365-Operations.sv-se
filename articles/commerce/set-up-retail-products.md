---
title: Ställa in butiksprodukter
description: Den här artikeln beskriver hur du ställer in produkter i Dynamics 365 Commerce.
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
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
ms.openlocfilehash: 22a3ecb235b21e239b23e5450ca4a2f12f9a41ac
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276085"
---
# <a name="set-up-retail-products"></a>Ställa in butiksprodukter

[!include [banner](includes/banner.md)]

Den här artikeln beskriver hur du ställer in produkter i Dynamics 365 Commerce.

Innan det går att erbjuda produkter för vidareförsäljning i handelskanalerna måste du skapa och konfigurera produkterna. I Commerce skapas företagsomfattande produkter i produktmallen. Det går att skapa produkterna, definiera produktegenskaperna och attributen och tilldela produkterna till handelskategorihierarkier. Gör produkterna tillgängliga i kanalerna och lägg till dem i ett aktivt sortiment och släpp sedan produkterna till juridiska personer där de finns tillgängliga. Gör på följande sätt när du vill ställa in produkterna som du säljer, genom att använda kanaler.

1. **Definiera en produkthierarki.** Genom att använda kategorihierarkifunktionerna i Commerce kan du definiera kategorihierarkier om du vill gruppera och kategorisera de produkter som du fördelar till dina kanaler. Användardefinierade och systemattribut kan definieras på kategorinivån. Därefter ärver alla produkter som tilldelas kategorin dessa attribut. Flera kategorihierarkier kan definieras och varje produkt kan tilldelas flera hierarkier. Men i en enda hierarki kan varje produkt bara tilldelas en kategori.
2. **Lägg till produkter och produktvarianter i produktmallen.** Produkter som läggs till produktmallen, representerar en global lista med produkter. Du kan lägga till produkter manuellt, en i taget, eller så kan du importera produktdata från leverantörerna.
3. **Frisläpp produkter till juridiska personer.** Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina kanaler. När du först definierar en produkt, anger du den på en företagsomfattande nivå. Du kan sedan välja en eller flera juridiska personer att frisläppa produkten till. Produkten blir sedan tillgänglig för flera kanaler i din organisation. Du kan använda den här funktionen om du vill skapa en produkt en gång, för att lägga till och uppdatera produktattribut och egenskaper på ett ställe och sedan om du vill fördela produkten i organisationen, till kanaler där den är tillgänglig.
4. **Lägg till produkter i sortimentet.** Ett sortiment representerar en samling av produkter som du erbjuder i dina kanaler. Du kan definiera en eller flera sortiment, och varje produkt kan tilldelas en eller flera sortiment. Om du vill tilldela produkter i kanaler tilldelar du sortimenten till dessa kanaler. När du skapar ett sortiment kan du lägga till produkter som ännu inte har frisläppts till en juridisk person. Men du måste frisläppa produkterna till en juridisk person innan dessa produkter kan göras tillgängliga i kanalerna.
5. **Lägg till produkter i navigeringshierarkier.** Innan produkter kan bläddras i online eller i butiker (POS), måste de kategoriseras i en handelsnavigeringhierarki.
6. **Lägg till produkter i kataloger** Även om detta steg är valfritt för butiker, kräver onlinebutiker att produkter inkluderas i minst en katalog.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
