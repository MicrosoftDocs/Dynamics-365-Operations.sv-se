---
title: "Ställ in butiksprodukter"
description: "Denna artikel beskriver hur du ställer in butiksprodukter i Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 2be44e0000e9730aa93076f21a4204f5d56f6aac
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017



---

# Ställ in butiksprodukter
<a id="set-up-retail-products" class="xliff"></a>

[!include[banner](includes/banner.md)]


Denna artikel beskriver hur du ställer in butiksprodukter i Microsoft Dynamics 365 for Retail.

Innan det går att erbjuda produkter att sälja i butikskanalerna måste du skapa och konfigurera produkterna i Microsoft Dynamics 365 for Retail. Butik använder produktfunktionerna i Dynamics 365 for Retail för att skapa produkter i produktmallen inom organisationen. Du kan skapa produkterna, definiera produktegenskaperna och attributen och tilldela produkterna till butikskategorihierarkier. Om du vill göra dina produkter tillgängliga för butikskanaler och lägga till dem till ett aktivt sortiment måste du frisläppa produkterna till de juridiska personerna där de är tillgängliga. Gör på följande sätt när du vill ställa in produkterna som du säljer, genom att använda butikskanaler.

1.  Definiera en produkthierarki för butik. Genom att använda kategorihierarkifunktionerna i Dynamics 365 for Retail kan du definiera butikskategorihierarkier om du vill gruppera och kategorisera de produkter som du fördelar till dina butikskanaler. Användardefinierade och systemattribut kan definieras på kategorinivån. Därefter ärver alla produkter som tilldelas kategorin dessa attribut. Flera kategorihierarkier kan definieras och varje produkt kan tilldelas flera hierarkier. Men i en enda hierarki kan varje produkt bara tilldelas en kategori.
2.  Lägg till produkter och produktvarianter i produktmallen. Produkter som läggs till produktmallen, representerar en global lista med produkter. Du kan lägga till produkter manuellt, en i taget, eller så kan du importera produktdata från leverantörerna.
3.  Frisläpp produkter till juridiska personer. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina butikskanaler. När du först definierar en produkt, anger du den på en företagsomfattande nivå. Du kan sedan välja en eller flera juridiska personer att frisläppa produkten till. Produkten blir sedan tillgänglig för flera butikskanaler i din organisation. Du kan använda den här funktionen om du vill skapa en produkt en gång, för att lägga till och uppdatera produktattribut och egenskaper på ett ställe och sedan om du vill fördela produkten i organisationen, till butikskanaler där den är tillgänglig.
4.  Lägg till produkter i sortimentet. Ett sortiment representerar en samling av produkter som du erbjuder i dina butikskanaler. Du kan definiera en eller flera sortiment, och varje produkt kan tilldelas en eller flera sortiment. Om du vill tilldela produkter i butikskanaler tilldelar du sortimenten till dessa butikskanaler. När du skapar ett sortiment kan du lägga till produkter som ännu inte har frisläppts till en juridisk person. Men du måste frisläppa produkterna till en juridisk person innan dessa produkter kan göras tillgängliga i butikskanalerna.
5.  Lägg till produkter i navigeringshierarkier. Innan produkter kan bläddras i online eller i butiker (POS), måste de kategoriseras i en butiksnavigeringhierarki.
6.  Lägg till produkter i kataloger Även om detta steg är valfritt för butiker, kräver onlinebutiker att produkter inkluderas i minst en katalog.





