---
title: Garantiavtal
description: I det här avsnittet beskrivs garantiavtal i Tillgångshantering.
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
ms.openlocfilehash: 8269b9f2084ddd0f69039044c29978ce7940270d5b569456f7a0bfca0a6f1f0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735313"
---
# <a name="warranty-agreements"></a>Garantiavtal

[!include [banner](../../includes/banner.md)]

 


I Tillgångshantering kan du ställa in garantivillkor som kan kopplas till en tillgång eller till en tillgångstyp. Garantivillkor skapas för en viss period. Garantin kan ställas in för att ge fullständig täckning eller deltäckning, och du kan ställa in villkor som är relaterade till timmar, utgifter och artiklar.

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