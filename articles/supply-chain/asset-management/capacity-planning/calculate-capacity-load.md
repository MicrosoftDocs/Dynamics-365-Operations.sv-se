---
title: Beräkna kapacitetsbeläggning
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5015955338a4cbc2b51585d6297756f20dccee8b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437786"
---
# <a name="calculate-capacity-load"></a>Beräkna kapacitetsbeläggning

[!include [banner](../../includes/banner.md)]


I Tillgångshantering kan du beräkna kapacitetsbeläggningen på:

- rader för underhållsschema  
- arbetsorder som ännu inte har planerats  
- schemalagda arbetsorder

Detta är användbart om du vill få en översikt över förväntad kapacitetsbeläggning för en viss period. Beräkning av kapacitetsbeläggnin kan göras på alla tillgångar eller valda tillgångar. Du kan också utföra en beräkning av aktiviteter för underhållsstopp och arbetsorderpooler.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhåll i listan > knappen **Kapacitetsbeläggning**.

2. I dialogrutan **Beräkna kapacitetsbeläggning** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**

3. Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i beräkningen.

4. Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i beräkningen.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningsrader ska vara gällande funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
    
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på de funktionsplatsnivåer som de är relaterade till.

6. Klicka på **OK** för att starta beräkningen.

7. I **Gruppera efter...**-grupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. I bildrutan nedan markeras de valda knapparna **Gruppera efter** med blå färg. Klicka på en knapp för att aktivera och inaktivera den.

    ![Figur 1](media/01-capacity-planning.png)

>[!NOTE]
>Om du bara vill fokusera på kapacitetsplanering för schemalagda arbetsorder läser du i [Beräkna kapacitetsbeläggning på schemalagda arbetsorder](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]