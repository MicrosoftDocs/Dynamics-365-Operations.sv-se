---
title: Materiell ersättning i tillverkning
description: I denna artikel beskrivs hur du ersätter material under produktionsprocessen.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c2e6c9cc8ed85c8c60539b37fb6c51c96bc2872
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855990"
---
# <a name="material-substitution-in-manufacturing"></a>Materiell ersättning i tillverkning

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du ersätter material under produktionsprocessen. 

Det finns tre metoder för att ersätta material under produktionsprocessen:

-   Efter datum, när ett material ersätts med ett annat efter ett visst datum
-   Under huvudplanering, när ett material i ett recept ersätts med ett annat material, eftersom det är slut på lager
-   Under produktion, när ett oväntat material oväntat tar slut på lager och ersätts med ett annat material

## <a name="substituting-material-by-date"></a>Ersätta material efter datum
Beakta följande scenario: en maskin som ett företag tillverkar innehåller en komponent som kommer att utgå från leverantörens katalog inom två månader. Från sista giltighetsdatum och framåt kommer leverantören att erbjuda en ny komponent som kan ersätta den gamla komponenten. Från och till-giltighetsdatum kan ställas in på strukturlisterader. För det här exemplet konfigurerar att den gamla komponenten upphör genom att ange utgångsdatum i fältet **Till-datum**. Därefter ställer du in den nya ersättningsskomponenten i strukturlistan så att den är giltigt från dagen efter att den gamla komponenten har gått ut. För att göra detta anger du startdatum i fältet **Från-datum** .

## <a name="substituting-material-by-planning"></a>Ersätta material efter planering
Du kan bara ersätta material under planering när du använder recept, inte när du använder en strukturlista. Beakta följande scenario: Ett mattillverkningsföretag gör en sås från ett recept som har 20 ingredienser. En ingrediens i receptet kan ersättas av en av två andra ingredienser. Eftersom dessa två ingredienser är dyrare än den prioriterade ingrediensen, används endast ersättning om den prioriterade ingrediensen inte finns kvar på lager. Materialet som kan ersättas kallas A, medan de två material som kan ersätta den kallas B och C. Materialersättning genom planering kontrolleras av fältet **Planera grupp** och **Prioritet** på receptraderna. För det här exemplet skapar du receptrader för de tre materialen och associerar receptraderna med samma plangrupp. I inställningarna har receptraden för material A högsta prioritet (det lägsta numret), receptraden för material C har lägst prioritet, och receptraden för material B har en prioritet mellan prioriteten för de övriga två raderna. Om du har efterfrågan för den färdiga artikeln, bestämmer huvudplaneringen först om efterfrågan för material A kan mötas. Om efterfrågan inte kan mötas, tittar huvudplaneringen på material B och C i prioritetsordning. Om material B finns i lager ska det användas efter att en planerad batchorder har bekräftats för receptet. Om inget av materialen är tillgängligt, skapar huvudplaneringen en planerad order för material A. **Obs!** När du konfigurerar receptrader i en plangrupp anger du endast en kvantitet på materialet som har högst prioritet. Den här kvantiteten ska användas för att beräkna efterfrågan på allt material i planen, även de material som har lägre prioritet. Du kan inte ange olika kvantiteter på lågprioritetsartiklar i plangruppen.

## <a name="substituting-material-during-production"></a>Ersätta material under produktion
Beakta följande situationer: Ett del av metallplattan krävs för en svetsningsåtgärd. Under åtgärden informerar en lagerarbetare maskinoperatören om att plattan är slut på lager. Men det bestäms att plattan kan ersättas med en platta som är något tjockare. På så vis kan åtgärden slutföras. Material kan läggas till strukturlistan för en öppen produktionsorder. Om produktionsordern har status **Startad**, uppmanas användarna till att återuppskatta ordern när de lägger till en ny artikel i produktionsstrukturlistan. När materialet har lagts till, kan en ny plocklista skapas för den nya artikeln. Du behöver inte lägga till det nya materialet i produktionsstrukturlistan. I stället kan du lägga till den direkt i produktionplocklistan. Därefter när plocklistan bokförs, lägger systemet till materialet i produktionsstrukturlistan.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]