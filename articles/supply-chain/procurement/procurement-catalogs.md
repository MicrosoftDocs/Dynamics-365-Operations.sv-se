---
title: Översikt över anskaffningskataloger
description: Den här artikeln beskriver, på en hög nivå, hur professionella inköpare kan ställa in och underhålla anskaffningskataloger. Anskaffningskataloger definierar de artiklar och tjänster som anställda i företaget kan beställa för intern användning.
author: GalynaFedorova
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, CatDisplayProductRelationAdd
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd267cbbe7767faab538cacad26636ff1f37a551
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672022"
---
# <a name="procurement-catalogs-overview"></a>Översikt över anskaffningskataloger

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver, på en hög nivå, hur professionella inköpare kan ställa in och underhålla anskaffningskataloger. Anskaffningskataloger definierar de artiklar och tjänster som anställda i företaget kan beställa för intern användning.

Inköpsproffs kan skapa och underhålla kataloger av de artiklar och tjänster som kan köpas i för intern användning i en organisation. När kataloger ställs in kan företagets anställda skapa inköpsrekvisitioner för att beställa från dem. Katalogerna kan användas för att framtvinga inköpspolicyer så att medarbetare kan beställa enbart de artiklar och tjänster som tillåts för deras köpande juridiska person. När du skapar en anskaffningskatalog bör du beakta följande uppgifter:

-   Konfigurera din anskaffningskategorihierarki innan du skapar katalogen.
-   Fastställ vilka produkter du vill att dina medarbetare ska kunna beställa. Du kan visa eller dölja specifika produkter i en nod i katalogen och du kan visa eller dölja alla produkter i en nod.
-   Bestäm hur många anskaffningskataloger du behöver. Åtkomsten till en anskaffningskatalog bestäms av katalogpolicyregeln som du konfigurerar för den juridiska personen och driftenheten som en medarbetare har tilldelats till.

Flera faktorer bestämmer produkterna som medarbetare kan beställa och anskaffningskategorierna som de kan använda när de skapar inköpsrekvisitioner:

-   Kategoriåtkomstpolicyregeln i inköpspolicyn avgör vilka anskaffningkategorier som är tillgängliga i inköpsrekvisitionen. Om ingen regel definieras är alla anskaffningkategorier tillgängliga.
-   Medarbetare kan beställa en produkt om den finns i den aktiva anskaffningskatalogen för din organisation, och om den är aktiverad i en nod och inte dold. Produkten måste också vara i en kategori som en viss medarbetare har tillgång till enligt kategoriåtkomstpolicyregeln.
-   Katalogpolicyregeln anger mappen som används. Om ingen katalogpolicyregel definieras, bestämmer kategoriåtkomstregeln de produkter som en medarbetare kan beställa på inköpsrekvisitionen.

## <a name="prerequisites"></a>Krav
I tabellen nedan beskrivs vilka uppgifter som måste utföras innan en inköpare kan skapa en anskaffningskatalog.

| Uppgift                                                | Roll               | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ställa in en kategorihierarki för anskaffning.            | Inköpschef | Anskaffningskategorihierarkier används för att klassificera artiklar eller transaktioner för rapportering och analys. Genom att använda en anskaffningskategorihierarki kan företag hantera kategorier, produkter, leverantörer och andra anskaffningsfaktorer på ett strategiskt sätt från en central plats. En anskaffningskategorihierarki definieras för en hel organisation. Katalogen baseras på anskaffningskategorihierarkin: kategorierna i hierarkin blir noder i katalogen. Leverantörerna och produkterna som ingår i din katalog. |
| Lägg till leverantörer och produkter i anskaffningskategorier. | Inköpschef | När anskaffningskategorihierarkin skapas för din organisation, kan varje anskaffningskategori associeras med specifika leverantörer, produkter, osv. Dessa associationer kopieras automatiskt till katalogen.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Ställa in en katalog
När förutsättningarna uppfylls kan du ställa in kataloger. Du kan skapa antingen en katalog som hela din organisation använder, eller kataloger som de olika avdelningarna i din organisation använder. Om du skapar en katalog för hela organisationen, kontrolleras åtkomsten till katalogen av dina inköpspolicyregler.  

Katalogen definierar vilka produkter som är tillgängliga när inköpsrekvisitioner skapas, men du kan använda en kategoripolicyregel för åtkomst för att tillämpa ytterligare begränsningar. Eftersom noderna i en katalog är anskaffningkategorier, kan de undertryckas av en kategoripolicyregeln för åtkomst. Då är produkterna i kategorin inte tillgängliga för medarbetare för användning i inköpsrekvisitioner. Du definierar policyreglerna för kategoriåtkomst på sidan **Inköpspolicyer**. I tabellen nedan beskrivs vilka uppgifter som måste utföras för att ställa in en katalog.

| Uppgift                                                   | Roll             | Beskrivning                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa en ny katalog.                                  | Inköpsagent | När du skapar en katalog, anger du ett namn och en beskrivning för katalogen. Du anger även om katalogen uppdateras manuellt eller automatiskt och anger katalogägaren.                                                                                                                                      |
| Produkter för kontroll som är tillgängliga i katalogen. | Inköpsagent | Eftersom produkterna ärvs från anskaffningkategorierna, visas de i lämpliga katalognoder. Du kan kontrollera om alla produkter i en nod visas eller döljs när katalogen används i en inköpsrekvisition. Du kan också kontrollera om enskilda produkter i en nod döljs eller visas. |
| Publicera katalogen.                                   | Inköpsagent | Innan en katalog är tillgänglig för medarbetare att använda i en rekvisition, måste du definiera en katalogpolicyregel för katalogen, ange katalogens status till **Aktiv** och publicera katalogen. Du kan inaktivera kataloger som du vill inte längre vill ska vara tillgängliga för dina användare.                                              |

Uppdateringar publiceras automatiskt eller fylls i manuellt, beroende på det alternativ som du väljer för katalogen i fältet **Standarduppdateringstyp** på sidan **Kataloger**. Följande standarduppdateringtyper är tillgängliga för kataloger:

-   **Dynamiskt** - Katalogen uppdateras automatiskt när som helst den har ändrats.
-   **Statisk** – Katalogerna måste uppdateras manuellt.
-   **Båda** – Om katalogen som inkluderar produktkategorier har standarduppdateringtypen **Statisk** måste den uppdateras manuellt när dessa kategorier uppdateras. Om katalogen inkluderar produktkategorier har standarduppdateringstypen **Dynamiskt**, uppdateras den automatiskt när som helst den har ändrats.


## <a name="additional-resources"></a>Ytterligare resurser

[Ställ in en anskaffningskategorihierarki](tasks/set-up-procurement-category-hierarchy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]