---
title: Butikshierarkier
description: "Den här artikeln beskriver butikshierarkierna i Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 817696566473bc5f31a7ff11c04291351dfd4764
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="retail-hierarchies"></a>Butikshierarkier

[!include[banner](includes/banner.md)]


Den här artikeln beskriver butikshierarkierna i Microsoft Dynamics 365 for Retail.

Du kan skapa en butikskategorihierarki för att strukturera de produkter som du säljer via butikskanaler. Du kan använda butiksprodukthierarkier för att kategorisera eller gruppera produkter. Du kan sedan använda dessa produkter om du vill skapa produktsortiment och kundbonusprogram. Du kan också tilldela produktattribut och egenskaper, tilldela en prissättningstruktur, inkludera produkter i produkterbjudanden och använda produkterna för rapportering. Du kan skapa en butikskategorihierarki som representerar alla produkter och kategorier i organisationen och använder sedan kategorihierarkin för flera syften. Du kan också skapa flera butikskategorihierarkier för särskilda syften, till exempel produkterbjudanden. När du skapar en Produkthierarki (butik), måste du tilldela en kategorihierarkityp för att identifiera syftet med kategorihierarkin. Om du till exempel om endast produkthierarkier som tilldelas typen **Butiksnavigeringshierarki** är refererade när du bläddrar i produkter efter kategori online eller på betalningsplatsen (POS).

## <a name="retail-hierarchy-types"></a>Typ av butikshierarki
Följande tabell listar de tillgängliga kategorihierarkityperna och det allmänna syftet med varje typ.

| Kategorihierarkityp       | Syfte                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Produkthierarki (butik)      | Använd markera den här hierarkityp för att definiera den allmänna odukthierarkin (butik) för din organisation. Du kan använda den här hierarkitypen för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering. Endast en butiksprodukthierarki kan tilldelas den här hierarkitypen.                                       |
| Tilläggshierarki | Använd den här hierarkitypen för eventuella ytterligare butikskategorihierarkier som du vill skapa. Till exempel på våren har du en kampanj för badkläder. Därför kan du använda dina badklädesprodukter i en separat kategorihierarki och tillämpa kampanjprissättningen i de olika produktkategorierna. |
| Butiksnavigeringshierarki   | Använd den här hierarkitypen om du vill gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller på betalningsstället.                                                                                                                                                                                       |

Genom att använda en butikskategorihierarki för strukturering av dina produkter, kan du ställa in och underhålla produktattribut och egenskaper på kategorinivån. Dessa attribut och egenskaper omfattar inställningar för produktdimensioner och butiksinställningar. Vissa produkter som du tilldelar kategorierna automatiskt, ärver de attribut och egenskaper som du definierar. Du kan också kopiera egenskapsinställningarna för en produkt till flera produkter i en vald kategori samtidigt.




