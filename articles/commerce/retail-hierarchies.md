---
title: Commerce-hierarkier
description: Den här artikeln beskrivs hierarkier i Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
audience: Application User
ms.reviewer: josaw
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 94b391ab5028f76debb75d25ac9469e25361cb12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979626"
---
# <a name="commerce-hierarchies"></a>Commerce-hierarkier

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]