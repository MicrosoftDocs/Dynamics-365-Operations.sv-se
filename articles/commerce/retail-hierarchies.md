---
title: Butikshierarkier
description: Den här artikeln beskrivs butikshierarkier i Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager
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
ms.openlocfilehash: cf8db2c828f99dfd4c220966e31894dcd6eda572
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024099"
---
# <a name="retail-hierarchies"></a>Butikshierarkier

[!include [banner](includes/banner.md)]

Den här artikeln beskrivs hierarkier i Dynamics 365 Commerce.

Du kan skapa en kategorihierarki för att strukturera de produkter som du säljer via kanaler. Du kan använda produkthierarkier för att kategorisera eller gruppera produkter. Du kan sedan använda dessa produkter om du vill skapa produktsortiment och kundbonusprogram. Du kan också tilldela produktattribut och egenskaper, tilldela en prissättningstruktur, inkludera produkter i produkterbjudanden och använda produkterna för rapportering. Du kan skapa en kategorihierarki som representerar alla produkter och kategorier i organisationen och använder sedan kategorihierarkin för flera syften. Du kan också skapa flera kategorihierarkier för särskilda syften, till exempel produkterbjudanden. När du skapar en Produkthierarki, måste du tilldela en kategorihierarkityp för att identifiera syftet med kategorihierarkin. Om du till exempel om endast produkthierarkier som tilldelas typen **Handelsnavigeringshierarki** är refererade när du bläddrar i produkter efter kategori online eller på betalningsplatsen (POS).

## <a name="hierarchy-types"></a>Hierarkityper

Följande tabell listar de tillgängliga kategorihierarkityperna och det allmänna syftet med varje typ.

| Kategorihierarkityp       | Syfte |
|-------------------------------|---------|
| Produkthierarki      | Använd markera den här hierarkityp för att definiera den allmänna odukthierarkin (butik) för din organisation. Du kan använda den här hierarkitypen för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering. Endast en produkthierarki kan tilldelas den här hierarkitypen. |
| Tilläggshierarki | Använd den här hierarkitypen för eventuella ytterligare kategorihierarkier som du vill skapa. Till exempel på våren har du en kampanj för badkläder. Därför kan du använda dina badklädesprodukter i en separat kategorihierarki och tillämpa kampanjprissättningen i de olika produktkategorierna. |
| Navigeringshierarki   | Använd den här hierarkitypen om du vill gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller på betalningsstället. |

Genom att använda en kategorihierarki för strukturering av dina produkter, kan du ställa in och underhålla produktattribut och egenskaper på kategorinivån. Dessa attribut och egenskaper omfattar inställningar för produktdimensioner och butiksinställningar. Vissa produkter som du tilldelar kategorierna automatiskt, ärver de attribut och egenskaper som du definierar. Du kan också kopiera egenskapsinställningarna för en produkt till flera produkter i en vald kategori samtidigt.
