---
title: "Ställ in butiksprodukter"
description: "I den här artikeln beskriver hur du ställer in i Microsoft Dynamics 365 för verksamhet – Retail återförsäljarprodukter."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 116c49174989ff14982027cc235640c2ad7322f2
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-retail-products"></a>Ställ in butiksprodukter

I den här artikeln beskriver hur du ställer in i Microsoft Dynamics 365 för verksamhet – Retail återförsäljarprodukter.

Innan du kan erbjuda produkter för återförsäljning i din återförsäljare, måste du skapa och konfigurera produkter i Dynamics 365 för operationer AX - Retail. Retail använder produktfunktionerna i Dynamics 365 för att skapa produkter på företagsnivå i produktmallen. Du kan skapa produkterna, definiera produktegenskaperna och attributen och tilldela produkterna till butikskategorihierarkier. Om du vill göra dina produkter tillgängliga för butikskanaler och lägga till dem till ett aktivt sortiment måste du frisläppa produkterna till de juridiska personerna där de är tillgängliga. Gör på följande sätt när du vill ställa in produkterna som du säljer, genom att använda butikskanaler.

1.  Definiera en produkthierarki för butik. Med funktionen hierarki för kategori i Dynamics 365 för operationer kan definiera du butikshierarkier kategori om du vill gruppera och sortera de produkter som levereras till din återförsäljare. Användardefinierade och systemattribut kan definieras på kategorinivån. Därefter ärver alla produkter som tilldelas kategorin dessa attribut. Flera kategorihierarkier kan definieras och varje produkt kan tilldelas flera hierarkier. Men i en enda hierarki kan varje produkt bara tilldelas en kategori.
2.  Lägg till produkter och produktvarianter i produktmallen. Produkter som läggs till produktmallen, representerar en global lista med produkter. Du kan lägga till produkter manuellt, en i taget, eller så kan du importera produktdata från leverantörerna.
3.  Frisläpp produkter till juridiska personer. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina butikskanaler. När du först definierar en produkt, anger du den på en företagsomfattande nivå. Du kan sedan välja en eller flera juridiska personer att frisläppa produkten till. Produkten blir sedan tillgänglig för flera butikskanaler i din organisation. Du kan använda den här funktionen om du vill skapa en produkt en gång, för att lägga till och uppdatera produktattribut och egenskaper på ett ställe och sedan om du vill fördela produkten i organisationen, till butikskanaler där den är tillgänglig.
4.  Lägg till produkter i sortimentet. Ett sortiment representerar en samling av produkter som du erbjuder i dina butikskanaler. Du kan definiera en eller flera sortiment, och varje produkt kan tilldelas en eller flera sortiment. Om du vill tilldela produkter i butikskanaler tilldelar du sortimenten till dessa butikskanaler. När du skapar ett sortiment kan du lägga till produkter som ännu inte har frisläppts till en juridisk person. Men du måste frisläppa produkterna till en juridisk person innan dessa produkter kan göras tillgängliga i butikskanalerna.
5.  Lägg till produkter navigeringshierarkier. Innan produkter kan granskas online eller ingångspunkten för försäljning (PO), kategoriseras de i en Butikshierarki för navigering.
6.  Lägga till produkter i kataloger. Även om detta steg är valfritt för POS kräver onlinebutiker att produkter ingå i åtminstone en katalog.



