---
title: Åtgärdssökning
description: I artikeln beskrivs funktionen åtgärdssökning i Microsoft Dynamics 365 for Finance and Operations. Funktionen för åtgärdssökning hjälper dig att hitta och köra åtgärder på en sida.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 960c715c487fbda5d93630327f07380e6d8fbd3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547041"
---
# <a name="action-search"></a>Åtgärdssökning

[!include [banner](../includes/banner.md)]

I artikeln beskrivs funktionen åtgärdssökning i Microsoft Dynamics 365 for Finance and Operations. Funktionen för åtgärdssökning hjälper dig att hitta och köra åtgärder på en sida.

## <a name="introduction"></a>Introduktion

Sidorna i Microsoft Dynamics 365 for Finance and Operations visar främst kommandon i åtgärdsfönster, både det vanliga åtgärdsfönstret som visas högst upp på en sida och verktygsfälten som visas på olika delar av sidan. I tidigare versioner fanns funktionen Tangenttips, som snabbt gav dig åtkomst till valfri knapp i ett åtgärdsfönster genom att trycka på ALT och en serie bokstäver.

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)

I den aktuella versionen av Finance and Operations har tangenttipsen emellertid ersatts av funktionen för åtgärdssökning. Den här nya funktionen kan du snabbt söka efter och kör en knapp från synliga rutan Åtgärd.

## <a name="using-action-search"></a>Med hjälp av action sök

För att använda åtgärden sökfunktionen, följ dessa steg.

1. I åtgärdsrutan, klicka i **sökfältet** . ( **åtgärden sökfältet** innehåller en förstoringsglaset).
2. Skriv hela eller en del av namnet på den knapp som du vill köra. Du kan också söka genom att använda ord från knappens "sökväg". (Mer information finns i nästa avsnitt i den här artikeln.) Vanligtvis visas en knapp längst upp i resultatlistan när du har skrivit två till fyra tecken.
3. Hitta och köra i resultatlistan (genom att använda din mus eller tangentbord).

När du kör, fokus återgår till din senaste position på sidan, så att du kan fortsätta att arbeta.

[![fält-för-åtgärdssökning](./media/action-search-field.png)](./media/action-search-field.png)

Du kan också starta åtgärden sökning, genom att pressa Ctrl+/- eller Alt+Q. Tryck på kortkommandot igen för att återgå till din senaste position på sidan.

## <a name="understanding-the-results-list"></a>Förstå resultaten förteckning

I Finance and Operations måste du ofta veta både på plats och samband för en knapp för att förstå syftet med den. Därför visas ytterligare information för varje artikel i resultatlistan, information som hjälper dig att förstå exakt vilka knappar som visas i listan. I synnerhet "sökväg" på knappen visas. Den här sökvägen kan inkludera etiketter av följande UI-beståndsdelar:

- Rutan åtgärd flik
- Knappgrupp
- Knappen meny (om knappen är placerad inuti en meny-knapp)
- Menyn separator (om knappen är placerad inuti en namngiven grupp inuti en meny-knapp)
- Grupp eller flik på sidan (t.ex. namnet på en snabbfliken)

Exempelvis du maskinskrev **tot** i **sökfältet** och granskar nu resultat listan. Den första posten, för en knapp vid namn **Summor**, markeras. Knappsökvägen för **Försäljningsorder** &gt; **Visa** visas också. **Försäljningsorder**-delen av sökvägen motsvarar fliken **Försäljningsorder** i åtgärdsfönstret, och **Visa**-delen i sökvägen motsvarar **Visa** gruppen på fliken. Dessutom informerar sökvägen till knappen **Totalrabatt** (**Sälj** &gt; **Beräkna**) dig om att den här knappen finns i gruppen **Beräkna** på fliken **Sälj** i åtgärdsfönstret. Därför kan den här informationen hjälpa dig att förstå exakt vilken knapp som utlöses av sökåtgärden (om du väljer knappen i resultatlistan).

[![fält-för-åtgärdssökning-med-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

I föregående exempel visade åtgärdsökningen resultat från det vanliga åtgärdsfönstret överst på sidan. Men action sök visar också resultaten från synligt verktygsfält som finns på andra ställen på sidan. Låt oss till exempel säga att du söker efter knappen **Lagerbehållning** som finns på snabbfliken **Försäljningsorderrader**. I det här fallet kommer knappsökvägen i resultatlistan (**Försäljningsorderrader** &gt; **Lager** &gt; **Visa**) att informera dig om att den här knappen finns under rubriken **Visa** på menyknappen **Lager** på snabbfliken **Försäljningsorderrader**.

[![lagerbehållning](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Åtgärd söka vs. navigation sökningen

Medan åtgärdssökningen är avsedd att hitta och köra åtgärder på en sida, finns en separat sökmekanism för att söka och navigera till sidor i Finance and Operations. Mer information om funktionen finns i artikeln [Navigeringssökning](navigation-search.md).