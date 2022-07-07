---
title: Beräkna kapacitetsbeläggning
description: I denna artikel beskrivs hur du beräknar kapacitetsbeläggning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 95d1e38db8e4658a57f36139836264b87d525e61
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016142"
---
# <a name="calculate-capacity-load"></a>Beräkna kapacitetsbeläggning

[!include [banner](../../includes/banner.md)]


I Tillgångshantering kan du beräkna kapacitetsbeläggningen på:

- rader för underhållsschema  
- arbetsorder som ännu inte har planerats  
- schemalagda arbetsorder

Detta är användbart om du vill få en översikt över förväntad kapacitetsbeläggning för en viss period. Beräkning av kapacitetsbeläggnin kan göras på alla tillgångar eller valda tillgångar. Du kan också utföra en beräkning av aktiviteter för underhållsstopp och arbetsorderpooler.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Kapacitetsbeläggning** eller **Tillgångshantering** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arebtsorderpool i listan > **Kapacitetsbeläggning** eller **Tillgångshantering** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhåll i listan > knappen > **Kapacitetsbeläggning**.

2. I dialogrutan **Beräkna kapacitetsbeläggning** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**

3. Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i beräkningen.

4. Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i beräkningen.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningsrader ska vara gällande funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
    
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på de funktionsplatsnivåer som de är relaterade till.

6. Klicka på **OK** för att starta beräkningen.

7. I **Gruppera efter...**-grupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. I bildrutan nedan markeras de valda knapparna **Gruppera efter** med blå färg. Klicka på en knapp för att aktivera och inaktivera den.

    ![Figur 1.](media/01-capacity-planning.png)

>[!NOTE]
>Om du bara vill fokusera på kapacitetsplanering för schemalagda arbetsorder läser du i [Beräkna kapacitetsbeläggning på schemalagda arbetsorder](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]