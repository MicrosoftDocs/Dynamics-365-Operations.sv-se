---
title: Garantiavtal
description: I denna artikel beskrivs garantiavtal i Tillgångshantering.
author: johanhoffmann
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 32e5ba8bf87d7bcd30e7f1493540317764d347ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864039"
---
# <a name="warranty-agreements"></a>Garantiavtal

[!include [banner](../../includes/banner.md)]

 


I Tillgångshantering kan du konfigurera garantivillkor som kan kopplas till en tillgång eller till en tillgångstyp. Garantivillkor skapas för en viss period. Garantin kan ställas in för att ge fullständig täckning eller deltäckning, och du kan konfigurera villkor som är relaterade till timmar, utgifter och artiklar.

Det första steget är att skapa alla leverantörsgarantiavtal som du har för din utrustning. Du kopplar sedan garantiavtal till tillgångar eller tillgångstyper. Leverantörsgarantiavtal används endast i informationssyfte. Om leverantörsgaranti har ställts in för en tillgång kan du se garantiperioden för tillgången.

## <a name="create-a-warranty-agreement"></a>Skapa ett garantiavtal

Ett garantiavtal kan innehålla flera avtalsrader för att täcka garantin för arbetstid, utgifter och artiklar.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Tillgångar** \> **Garanti**.
2. Välj **Ny** för att skapa en produkt.
3. Ange ett garanti-ID i fältet **Garanti**. 
4. Ange en beskrivning i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **Tillgångar** antalet aktiva tillgångar som använder garantiavtalet.

5. På snabbfliken **garantirader** följer du stegen nedan för att lägga till rader som ska ingå i ett garantiavtal:

    1. Välj **Lägg till rad** om du vill lägga till ett nytt villkor i garantin. Ett sekventiellt nummer anges automatiskt i fältet **Rad**.
    2. Välj typen av garantiperiod i fältet **Period**.
    3. Ange ett värde i fältet **Intervall**. Det här fältet definierar antalet perioder som garantin ska gälla för.
    4. I fältet **Procent** anger du täckningsgraden för garantiraden. Procentsatsen anger hur mycket som företaget täcker.

![Sidan Garanti.](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]