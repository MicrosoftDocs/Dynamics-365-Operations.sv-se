---
title: Lägga upp ett sortiment
description: Denna artikeln beskriver vad ett sortiment är och förklarar hur du ställer in sortiment i Dynamics 365 Commerce.
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
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.industry: Retail
ms.search.form: RetailAssortmentDetails
ms.openlocfilehash: 26827a09962dbbb6be4e0a054e22424260592702
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271834"
---
# <a name="set-up-assortments"></a>Ställa in sortiment

[!include [banner](includes/banner.md)]

Denna artikeln beskriver vad ett sortiment är och förklarar hur du ställer in sortiment i Dynamics 365 Commerce.

Ett sortiment är en samling relaterade produkter som du tilldelar en handelskanal, till exempel en fysisk butik eller en onlinebutik. Du använder sortiment för att identifiera de produkter som är tillgängliga i varje butik. Ett sortiment kan inkludera kategorier av produkter. Alla produkter som tilldelats den valda kategorin, ingår i sortimentet. Ett sortiment kan också ta med specifika produkter och specifika varianter av produkter. Om du ställer in ett sortiment, kan du tilldela tusentals produkter till dina kanaler samtidigt, i valfri kombination som din butik kräver. Du kan ställa in så många produktsortiment, som du behöver. Varje produkt kan inkluderas i ett eller flera sortiment, och varje produkt kan tilldelas en eller flera kanaler. Om du till exempel anger ett sortiment som innehåller en basuppsättning med produkter. Alla butiker tar emot sortimentet. Du definierar sedan ett annat sortiment som inkluderar en större sportutrustning. Endast dina större butiker får sortimentet. Följande diagram visar hur produkter kan tilldelas sortiment, och hur de sortimenten kan tilldelas kanaler.

![Relationer för produktsortiment.](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Förutsättningar

Innan du kan ställa in ett sortiment och tilldela den till en kanal, måste du göra följande.

| Uppgift                              | Beskrivning |
|-----------------------------------|-------------|
| Ställ in en kanal.          | En kanal representerar den fysiska butiken, onlinebutiken och onlinemarknadsplatsen. Du måste ställa in minst en kanal och konfigurera alternativen för butiken. Sortiment tilldelas butikerna för att identifiera de produkter som en viss butik har. |
| Skapa en organisationshierarki. | När du har ställt in kanalerna för din organisation, måste du konfigurera en organisationshierarki som representerar organisationsstrukturen hos dina kanaler. Du kan använda organisationshierarkin för sortiment, påfyllnad eller rapportering. Genom att lägga till dina kanaler till en organisationshierarki kan du tilldela sortiment till grupper av butiker. Istället för att tilldela sortimentet individuellt för varje butik tilldelar du sortimentet i organisationnoden på hög nivå. Därefter, när en ny kanal läggs till i organisationnoden på hög nivå, kommer kanalen automatiskt att ärva de sortiment som har tilldelats i organisationsnoden. Du kan bara tilldela sortiment för kanaler som är inkluderade i en organisationshierarki, som tilldelas syftet **Handelssortiment**. |
| Definiera produkter.                  | Innan du kan lägga till produkter till ett sortiment, måste du lägga till dem i Commerce. Du kan lägga till produkter manuellt, eller så kan du importera dem från en leverantör. När du har lagt till produkterna, måste du frisläppa dem till en juridisk person. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina kanaler. Produkter, som ännu inte har frisläppts till en juridisk person, kan läggas till ett sortiment och sortimentet kan godkännas. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina kanaler. |
| Ställ in en kategorihierarki      | När du skapar dina produkter, kan du gruppera dem och kategorisera dem genom att använda kategorihierarkifunktionen. Du kan skapa en huvudhierarki för att gruppera och kategorisera alla produkter som du distribuerar via kanaler. Du kan också skapa separata extra kategorihierarkier för att gruppera eller kategorisera dina produkter för särskilda syften, till exempel kampanjer eller sortiment. Genom att använda kategorihierarkier, kan du tilldela alla produkter i en specifik kategori till ett sortiment. Vissa produkter som läggs till en kategori, som är inkluderade i sortimentet, inkluderas automatiskt i sortimentet. Nästa gång som sortimentplaneraren körs blir dessa produkter tillgängliga för de kanaler som sortimentet tilldelas. |

## <a name="setting-up-an-assortment"></a>Ställa in ett sortiment

När du har slutfört förberedelserna, kan du skapa ett sortiment och tilldela den till dina kanaler. Om du vill ställa in ett sortiment måste du göra följande.

1. Skapa ett nytt sortiment eller kopiera ett befintligt sortiment.
2. Välj de kanalerna eller grupper med kanaler på hög nivå som sortimentet gäller för.
3. Lägg till produktkategorier, enskilda produkter eller produktvarianter till sortimentet. Du kan inkludera alla produkter i en specifik kategori, eller så kan du utesluta valda produkter från en kategori som ingår i sortimentet.
4. Publicera sortimentet. När du publicerar sortimentet kommer sortimentsschemaläggaren att köras automatiskt. Den här processen genererar listan med produkter. När den här processen slutförs blir produkterna tillgängliga för de kanaler som produktsortimentet tilldelas. Om ändringar görs i ett sortiment som har publicerats, eller till de kanaler som sortimentet har tilldelats, måste sortimentet uppdateras. Om du vill uppdatera sortimentet när ändringar görs kan du köra en lämpligt sortimentplanerare som ett batchjobb.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
