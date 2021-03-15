---
title: Skapa förbrukningsrapporter
description: I det här avsnittet beskrivs hur du skapar förbrukningsrapporter i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e32924c71fd221caee4a7f413908120014ec8c5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022543"
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