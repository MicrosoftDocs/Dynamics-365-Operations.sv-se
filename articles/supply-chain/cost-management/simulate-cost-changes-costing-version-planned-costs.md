---
title: Simulera kostnadsändringar med hjälp av en kostnadsversion för planerade kostnader
description: Det här avsnittet innehåller en beskrivning av hur du kan simulera effekterna av kostnadsändringar för en tillverkad artikels beräknade kostnader med hjälp av en separat kostnadsversion för planerade kostnader.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 053709cb7a4ffb30e1e4968096ea4df5e67242e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011832"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Simulera kostnadsändringar med hjälp av en kostnadsversion för planerade kostnader

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du kan simulera effekterna av kostnadsändringar för en tillverkad artikels beräknade kostnader med hjälp av en separat kostnadsversion för planerade kostnader.

Du kan simulera effekterna av kostnadsändringar för en tillverkad artikels beräknade kostnader med hjälp av en separat kostnadsversion för planerade kostnader. Använd den separata kostnadsversionen för att registrera väntande kostnadsposter som återspeglar stegvisa kostnadsändringar och för att beräkna kostnadens inverkan på tillverkade artiklar. Tack vare att reservprincipen för aktiva kostnader används i strukturlisteberäkningarna behöver enbart de stegvisa kostnadsändringarna registreras.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Riktlinjer för definiering av simuleringen av kostnadsversionen
Använd följande riktlinjer när du definierar kostnadsversionen för simuleringar:

-   Tilldela en kostnadstyp för **Planerade kostnader**.
-   Tilldela en meningsfull identifierare för kostnadsversionen såsom **Simulering**.
-   Kontrollera att innehållet inkluderar kostnadsposter.
-   Tillåt registrering av kostnadsposter. Spärra inte registreringen av väntande kostnader.
-   Tillåt registrering av kostnadsposter för alla siter. Genom att specificera en webbplats begränsas registreringen av kostnadsposter till den angivna webbplatsen.
-   Förhindra att pågående kostnader aktiveras. Enbart väntande kostnader behöver registreras för kostnadsposter i simuleringen av kostnadsversionen.
-   Ange inte något fråndatum. Ett beräkningsdatum anges för varje strukturlisteberäkning som använder kostnadsversionen för simulering.
-   Ange en reservprincip för **För tillfället aktiva**. Reservprincipen tillåter registrering av stegvisa kostnadsändringar i simuleringssyfte, men använder de för tillfället aktiva kostnaderna som källa för alla andra kostnadsposter. Det förutsätts att alla för tillfället aktiva kostnader finns för alla andra kostnadsposter.
-   Ange en kostnadsprismodell för **Självkostnad för version**, men begränsa inte beräkningar. Simuleringar kan till exempel även utnyttja en kostnadsprismodell med **Beräkningsgrupp för strukturlista** för att ange källan till kostnadsbidragen för inköpta artiklar.
-   Ange ett nedbrytningsläge med **Flera nivåer**, men begränsa inte beräkningar. Simuleringar kan använda andra nedbrytningslägen.

## <a name="costing-versions"></a>Kostnadsredovisningsversioner
Följande scenarier visar hur du använder en kostnadsversion för att simulera kostnadsändringars inverkan. Innan du registrerar en simulerad kostnadsändring måste du ta bort väntande kostnadsposter i simuleringsversionen så att du har en ren utgångspunkt. Använd sidan **Artikelpris** när du vill visa och ta bort väntande kostnadsposter som hör till artikelpriserna och kostnadskategoripriserna.

-   Simulera kostnadsändringen för en inköpt artikel. Kostnadsändringen kan till exempel återspegla en förväntad ökning eller minskning av kostnaderna för viktiga inköpta material. Du definierar olika kostnader för en inköpt artikel genom att använda sidan **Artikelpris** där du registrerar en väntande kostnadspost i simuleringsversionen.
-   Simulera kostnadsändringen för en kostnadskategori. Kostnadsändringen kan till exempel återspegla en förväntad ökning eller minskning i arbetskostnader eller i timkostnader för verksamhetsresurser. Du definierar olika kostnader för en kostnadskategori genom att använda sidan **Kostnadskategoripris** där du registrerar en väntande kostnadspost i simuleringsversionen.
-   Simulera kostnadsändringen i en beräkningsformel för indirekt kostnad. Kostnadsändringen kan till exempel återspegla en förväntad ökning eller minskning av tillverkningsomkostnader. Du definierar ändringen av en beräkningsformel för indirekt kostnad genom att använda sidan **Inställningar för kostnadsredovisning** där du registrerar en väntande kostnadspost i simuleringsversionen och kontrollerar och sparar ändringen.

När du har registrerat de simulerade kostnadsändringarna ska du beräkna kostnaderna för de tillverkade artiklar som påverkas av kostnadsändringen. Använd sidan **Beräkning** för simuleringsversionen och identifiera de valda tillverkade artiklarna som påverkas av kostnadsändringarna. Strukturlisteberäkningarna gäller för alla tillverkade artiklar såvida du inte väljer särskilda artiklar. Du kan också använda alternativet för strukturlisteberäkning för uppdateringar av typen var-använd. Visa artikelkostnadsposterna i simuleringsversionen om du vill analysera hur de simulerade kostnadsändringarna påverkar kostnaderna för de valda tillverkade artiklarna. Använd sidorna **Artikelpris** och **Beräkna artikelkostnad** för att visa och analysera kostnaderna.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]