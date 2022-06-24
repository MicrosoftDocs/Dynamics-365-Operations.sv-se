---
title: Beräkna artikelprognos
description: I denna artikel beskrivs hur du beräknar artikelprognos i Tillgångshantering.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d0552c38ddc31ad6322e9e2e0f2c2c722c045f4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870912"
---
# <a name="calculate-item-forecast"></a>Beräkna artikelprognos

[!include [banner](../../includes/banner.md)]

 

På samma sätt som du kan göra beräkningar av kapacitetsbeläggning, som beskrivs i föregående avsnitt, kan du också göra artikelprognosberäkningar för:

- rader för underhållsschema  
- arbetsorder som ännu inte har planerats  
- schemalagda arbetsorder

Detta är användbart om du vill få en översikt över förväntad artikelförbrukning (reservdelar och andra artiklar som krävs för att slutföra arbetsorder) för en viss period. Beräkning av artikelprognos kan göras på alla tillgångar eller valda tillgångar. Du kan också göra en beräkning av aktiviteten underhållsstopp (**Alla aktiviteter för underhållsstopp** eller **Aktiva aktiviteter för underhållsstopp**) eller på en arbetsorderpool (**Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**).

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhållsstopp i listan > knappen **Artikelprognos**.

2. I dialogrutan **Beräkna artikelprognos** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**

3. Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i prognosberäkningen.

4. Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i prognosberäkningen.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerade artikelprognosraderna ska vara gällande funktionsplatser. 

      Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
  
      Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på den funktionsplatsnivå som de är relaterade till.

6. Klicka på **OK** för att starta beräkningen.

7. I **Gruppera efter...**-grupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. I bildrutan nedan markeras de valda knapparna **Gruppera efter** med blå färg. Klicka på en knapp för att aktivera och inaktivera den.

8. Klicka på knappen **Visa dimensioner** om du vill visa produkt-, lagrings- eller spårningsdimensioner som hör till artiklarna. Markera relevanta kryssrutor och klicka på **OK**.

![Figur 1.](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]