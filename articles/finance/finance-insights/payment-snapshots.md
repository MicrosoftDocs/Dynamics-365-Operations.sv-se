---
title: Översikt över ögonblicksbilder (förhandsversion)
description: Det här ämnet beskriver funktionen för ögonblicksbilder, där du kan spara en kassaflödesprognos för analys eller jämförelse med verkliga värden senare. När du genererar en kassaflödesprognos kan du spara den som en "ögonblicksbild". Du kan sedan använda ögonblicksbilderna för att redigera de konton som inkluderades i prognosen, eller jämföra prognosen i ögonblicksbilden med verkliga värden.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 593d6fa8efdecf1b64ef802e6861783d6f85489c
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186600"
---
# <a name="snapshots-overview-preview"></a>Översikt över ögonblicksbilder (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ögonblicksbilder låter organisationer redigera och spara information om sina kassapositioner och kassaprognoser vid en viss tidpunkt. Du kan jämföra ögonblicksbilden med faktiska ekonomiska värden, undersöka avvikelsen och använda den informationen för att förbättra kassaflödesprognoserna över tiden. Mer specifikt kan ögonblicksbilder kan användas på följande sätt:

- Spåra kassaposition och kassaprognoser över tid.
- Filtrera data för att visa en deluppsättning av juridiska personer som ögonblicksbilden skapades för.
- Redigera kassaposition och kassaprognos som genererats av systemet.
- Utföra en konsekvensanalys för att överväga optimistiska, pessimistiska och sannolika vyer av kassaflödet.
- Jämföra den faktiska ekonomiska prestandan med den prognos som sparas i ögonblicksbilden.

Du kan skapa en ögonblicksbild genom att välja **Ny ögonblicksbild** på fliken **Kassaposition** eller fliken **Kassaprognos** i arbetsytan **Kassaflödesprognoser**. När en ögonblicksbild har skapats kan inflödena och utflödena redigeras och sparas. Alla sparade ögonblicksbilder finns på fliken **Ögonblicksbilder**. Om du vill öppna en ögonblicksbild väljer du dess namn.

Du kan när som helst redigera kassainflöden och kassautflödena i ögonblicksbilder. När ett inflödesbelopp eller ett utflödesbelopp redigeras, fördelas det uppdaterade beloppet mot de likviditetskonton som gav det ursprungliga saldot. När du är klar med redigeringen av en ögonblicksbild väljer du **Spara** för att spara dina ändringar.

Om du vill jämföra flera ögonblicksbilder väljer du **Jämför ögonblicksbilder**. Du kan jämföra två ögonblicksbilder åt gången. Välj de två ögonblicksbilder som du vill jämföra och välj sedan **OK**. På sidan **Jämför ögonblicksbild** visas en jämförelse av de valda ögonblicksbilderna. Diagrammet i den övre delen av sidan visar en jämförelse av kassainflödena, kassautflödena och banksaldona i de överlappande perioderna mellan de två ögonblicksbilderna. I rutnätet i den nedre delen visas en detaljerad jämförelse av de två prognoserna för varje likviditetsbelopp. Kolumnen **Avvikelse** i rutnätet visar skillnaden mellan saldona i en period.

Om du vill jämföra faktiska ekonomiska resultat med en prognos som har sparats som en ögonblicksbild väljer du **Jämför med verkliga värden**. På sidan **Jämför ögonblicksbild** visas en jämförelse av de faktiska beloppen och prognosen. Diagrammet i den övre delen av sidan visar en jämförelse av kassainflödena, kassautflödena och banksaldona i de överlappande perioderna mellan de två ögonblicksbilderna. I rutnätet i den nedre delen visas en detaljerad jämförelse av faktiska saldon per period och det prognosticerade saldot för varje likviditetsbelopp. Kolumnen **Avvikelse** i rutnätet visar skillnaden mellan det faktiska saldot i en period och det prognosticerade saldot.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
