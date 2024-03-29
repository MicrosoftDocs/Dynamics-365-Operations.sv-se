---
title: Kostnadskontroll för tillgångsfel
description: I denna artikel förklaras kostnadskontroll för tillgångsfel i Tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 553b89a43b656669b7730b19898f3a5d81a3873a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889676"
---
# <a name="asset-fault-cost-control"></a>Kostnadskontroll för tillgångsfel

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering kan du beräkna kostnader för tillgångsfelregistreringar att få en översikt över de faktiska kostnaderna jämfört. Faktiska kostnader baseras på bokförda transaktioner. Datumet är feldatumet då symptomen registrerades.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Kostnadskontroll för tillgångsfel**.

2. I dialogrutan **Kostnadskontroll för tillgångsfel** väljer du en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen om det behövs.

4. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla kostnadskontrollrader för tillgångsfel för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
    
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader för tillgångsfel på alla funktionsplatsnivåer som de är relaterade till.

6. Om du vill begränsa sökningen kan du välja specifika tillgångar, feldatum och felorsaker på snabbfliken **Poster som ska ingå**.

7. Klicka på **OK** för att starta beräkningen.

8. Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

## <a name="example"></a>Exempel

Det här exemplet visar en kostnadskontrollberäkning för tillgångsfel.

- I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen. 
- I fältet **Faktisk kostnad** visas bokförda kostnader för arbetsorder. 
- I fältet **Utfästa kostnader** visas det totala kostnaderna som ditt företag är förpliktigat att utföra i relation till arbetsorder.

    ![Figur 1.](media/05-controlling-and-reporting.png)

För information om hur du konfigurerar fel, se artikeln [Felhantering](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]