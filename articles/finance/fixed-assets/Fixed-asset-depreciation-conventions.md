---
title: Avskrivningspraxis för anläggningstillgångar
description: Den här ämnet beskriver avskrivningspraxis för anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd0153b5d735e1d565b67db6c66c854ff738509c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969213"
---
# <a name="fixed-asset-depreciation-conventions"></a>Avskrivningspraxis för anläggningstillgångar

[!include [banner](../includes/banner.md)]

Den här ämnet beskriver avskrivningspraxis för anläggningstillgångar. Avskrivningspraxis används för att bestämma när och hur avskrivning beräknas för både året när anläggningstillgången anskaffades och året när anläggningstillgången avyttrades.

Avskrivningspraxis kan tilldelas till inställningen för en räkenskapsbok för anläggningstillgångsgrupp. Om du vill visa eller tilldela avskrivningspraxis väljer du **Anläggningstillgångsgrupper** i inställningsområdet för anläggningstillgångar. Välj knappen **Böcker**. I det här fallet används avskrivningspraxis som tilldelas som standardvärden när räkenskapsbok för anläggningstillgångsgrupp skapas. Avskrivningspraxis kan också ställas in för individuella anläggningstillgångar. För att göra detta väljer du **Böcker** i inställningsområdet för anläggningstillgångar och väljer sedan knappen **Anläggningstillgångsgrupper**.

| Avskrivningspraxis   | Beskrivning |
|---------------------------|-------------|
| Ingen                      | Tillgångarna börjar skrivas av datumet <strong>Satt i tjänst</strong>. |
| Halvår                 | Du kan dra av ett halvårs avskrivning för både det första året och det sista året som du skrev av egendomen. Du kan dra ett helt års avskrivning för andra år under återställningsperioden. |
| Hel månad                | Tillgångar som har datumet <strong>Tas i drift</strong> som inträffar vid något tillfälle under månadsstarten för avskrivning för den första dagen i den månaden. För avskrivningar anses tillgångar vara pensionerade den sista dagen i föregående månad. Den specifika dagen i månaden då den blev tillbakadragen beaktas inte. |
| Mellankvartal               | Om du vill beräkna dina avskrivningsavdrag för året då egendomen tas i drift multiplicerar du avskrivningen för ett helt år med procentsatsen för det kvartal när egendomen tas i drift, enligt tabellen nedan.<table><thead><tr><th>Kvartal</th><th>Procentsats</th></tr></thead><tbody><tr><td>Förnamn</td><td>87,5</td></tr><tr><td>Andra</td><td>62,5</td></tr><tr><td>Tredje</td><td>37,5</td></tr><tr><td>Fjärde</td><td>12.5</td></tr></tbody></table>En halv fjärdedel av avskrivningarna tas i det kvartal då tillgången avyttrades (eller det kvartal då den avskrivs helt). |
| Mitt i månaden (första i månaden)  | Tillgångar som har datum för <strong>Tas i drift</strong> den första delen av månaden (dagar 1 till 15) börjar skriva av den första dagen i månaden för datumet <strong>Tas i drift</strong>. Tillgångar som har datum för <strong>Tas i drift</strong> den andra delen av månaden (dagar 16 till månadens slut) börjar skriva av den första dagen i månaden efter datumet <strong>Tas i drift</strong>. Tillgångar som skulle dras tillbaka under första delen av månaden (dag 1 till 15) betraktas som tillbakadragna för avskrivningssyfte den sista dagen i föregående månad. Tillgångar som skulle dras tillbaka under andra hälften av månaden (dagar 16 till månadens slut) betraktas som tillbakadragna för avskrivningssyfte den sista dagen i månaden för tillbakadragandet. |
| Mitt i månaden (15:e i månaden) | Om du vill beräkna dina avskrivningsavdrag för året när du använder egendomen, multiplicera avskrivningen för ett helt år med en kvot. Täljaren (översta talet) i denna kvot är antalet fullständiga månader under det år som egendomen är i tjänst plus 1/2 eller (0,5). Nämnaren (understa numret) är 12. Om du avyttrar egendomen före utgången av din återställningsperiod använder du samma metod för att beräkna dina avskrivningsavdrag för året för dispositionen. |
| Halvår (start på året) | Tillgångar som har ett <strong>Tas i drift</strong>-datum i den första hälften av året börjar skriva av den första dagen på året (hela år). Tillgångar som har ett <strong>Tas i drift</strong>-datum i den andra hälften av året börjar skriva av i mitten på året. |
| Halvår (nästa år)     | Tillgångar som har ett <strong>Tas i drift</strong>-datum i den första hälften av året börjar skriva av den första dagen på året (hela år). Tillgångar som har ett <strong>Tas i drift</strong>-datum i den andra hälften av året börjar skriva av den första dagen nästa år. Tillgångar som skulle dras tillbaka under första delen av året betraktas som tillbakadragna för avskrivningssyfte den sista dagen i föregående år. All avskrivning som bokförs för innevarande år måste återföras eller justeras. Tillgångar som skulle dras tillbaka under andra halvan av året anses indragna för avskrivning den sista dagen på året för tillbakadragandet. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]