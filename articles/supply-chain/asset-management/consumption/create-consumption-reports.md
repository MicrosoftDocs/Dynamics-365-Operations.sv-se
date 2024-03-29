---
title: Skapa förbrukningsrapporter
description: I denna artikel beskrivs hur du skapar förbrukningsrapporter i Tillgångshantering.
author: johanhoffmann
ms.date: 08/21/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 136d6248db8012e5870e0627ddbd3703aa63703b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852912"
---
# <a name="create-consumption-reports"></a>Skapa förbrukningsrapporter

[!include [banner](../../includes/banner.md)]

 

När du har skapat och bokfört förbrukningsregistreringar för arbetsorder i Tillgångshantering finns det två rapporter som kan visa information om förbrukningen.


## <a name="asset-consumption-report"></a>Rapport om tillgångsförbrukning

När du har bokfört förbrukning på arbetsorder kan du skriva ut en rapport över tillgångsförbrukning. I rapporten visas timmar, timkostnader, artikel kostnader och utgifter som har bokförts på tillgångar.

1. Klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsförbrukning**.

2. I dialogrutan **Tillgångsförbrukning** väljer du de parametrar och den detaljnivå som du vill visa genom att välja **Ja** på de relevanta växlingsknapparna och infoga en funktionsplatsnivå i avsnittet **Visa**.
    - Du kan använda fältet **Nivåer** för att indikera hur detaljerad tillgångsraderna ska vara gällande funktionsplatser. 
    
        Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångar för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
        
        Om du infogar siffran "0" i fältet **Nivåer** visas ett detaljerat resultat med alla tillgångar på alla de funktionsplatsnivåer som de är relaterade till. 
        
    - Välj **Ja** på växlingsknappen **Summa på alla undertillgångar** om du vill se summorna för varje undertillgång i rapporten.

3. Välj ett datumintervall i avsnittet **Datum**.

4. På snabbfliken **Destination** väljer du om du vill visa rapporten på skärmen, skriva ut den eller spara den som en fil eller ett e-postmeddelande.

5. Vid behov kan du välja specifika tillgångar som ska visas i rapporten. På snabbfliken **Poster som ska ingå** klickar du på **Filter** och lägger till de tillgångar som du vill inkludera i rapporten.

6. Klicka på **OK** för att generera rapporten.


## <a name="work-order-consumption-report"></a>Förbrukningsrapport för arbetsorder

När du har bokfört förbrukning på arbetsorder kan du skriva ut en rapport över arbetsorderförbrukning. I rapporten visas timmar, timkostnader, artikel kostnader och utgifter som har bokförts på arbetsorder.

1. Klicka på **Tillgångshantering** > **Rapporter** > **Arbetsorder** > **Arbetsorderförbrukning**.

2. I dialogrutan **Arbetsorderförbrukning** väljer du de parametrar som du vill inkludera i rapporten genom att välja **Ja** på de relevanta växlingsknapparna i avsnittet **Visa**.

3. Välj ett datumintervall i avsnittet **Datum**.

4. På snabbfliken **Destination** väljer du om du vill visa rapporten på skärmen, skriva ut den eller spara den som en fil eller ett e-postmeddelande.

5. Vid behov kan du välja specifika arbetsorder som ska visas i rapporten. På snabbfliken **Poster som ska ingå** klickar du på **Filter** och lägger till de arbetsorder som du vill inkludera i rapporten.

6. Klicka på **OK** för att generera rapporten.


>[!NOTE]
>Du kan också skapa en [arbetsorderrapport](../work-orders/work-order-report.md)som innehåller mer information om arbetsorder.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]