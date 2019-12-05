---
title: Artikeln har använts
description: I det här avsnittet beskrivs hur du får en översikt över var en artikel används i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 476b01a4bae34a271203f34481ff18042783d4df
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811273"
---
# <a name="item-where-used"></a>Artikeln har använts

[!include [banner](../../includes/banner.md)]

 

Du kan göra en beräkning för en viss artikel för att få en översikt över var i Tillgångshantering artikeln har använts. Resultaten visar i vilket sammanhang artikeln har använts under dess livstid. Sidan **Artikel där den används** kan öppnas från huvudmenyn för hantering av tillgångar och kan även öppnas från följande sidor:

- [Tillgångsstrukturer](../objects/object-BOM.md)

- [Reservdelar för standardtyp av tillgång](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Underhållsprognoser](../work-orders/maintenance-forecasts.md)

- [Anskaffning](../work-orders/procurement.md)

- [Inköp för arbetsorder](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Göra en beräkning av artikel-där-den-används

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Artikel där den används**, eller välj knappen **Artikel där den används** på en av sidorna som nämns ovan.

2. I dialogrutan **Artikel där den används** välj den artikel som du vill göra beräkningen för i fältet **Artikelnummer**.

3. Du kan använda fältet **Nivå** för att indikera hur detaljerade artikelraderna ska vara gällande funktionsplatser. 

    Om du till exempel infogar numret "1" i fältet och har en funktionsplatsstruktur med flera nivåer, så visas alla artikelrader för en funktionsplats på den översta nivån. Därför kan relationen/kvantiteten på en rad läggas till från funktionsplatserna på en lägre nivå. 
    
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla artikelrader på alla de funktionsplatsnivåer som de är relaterade till.

4. Välj "Ja" i avsnittet **Inkludera** på växlingsknapparna som du vill inkludera i beräkningen.

5. Klicka på **OK** för att starta beräkningen.

6. På fliken **Artikel där den används**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

7. Om du vill visa relaterade dimensioner för artikeln klickar du på **Visa dimensioner** och väljer de dimensioner som ska visas.

## <a name="example"></a>Exempel

I skärmbilden nedan visas ett exempel på en beräkning av artikel-där-den-används för artikelnummer "1000".

![Exempel på artikel där beräkningen används](media/12-controlling-and-reporting.png)

