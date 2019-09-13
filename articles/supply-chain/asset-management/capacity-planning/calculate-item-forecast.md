---
title: Beräkna artikelprognos
description: I det här avsnittet beskrivs hur du beräknar artikelprognos i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: 9091ff7a394cd08b68e78c8f668d7cd962003e6d
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886780"
---
# <a name="calculate-item-forecast"></a>Beräkna artikelprognos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

På samma sätt som du kan göra beräkningar av kapacitetsbeläggning, som beskrivs i föregående avsnitt, kan du också göra artikelprognosberäkningar för

- Rader för underhållsschema  
- Arbetsorder som ännu inte har planerats  
- Schemalagda arbetsorder

Detta är användbart om du vill få en översikt över förväntad artikelförbrukning (reservdelar och andra artiklar som krävs för att slutföra arbetsorder) för en viss period. Beräkning av artikelprognos kan göras på alla tillgångar eller valda tillgångar. Du kan också göra en beräkning av aktiviteten underhållsstopp (**Alla aktiviteter för underhållsstopp** eller **Aktiva aktiviteter för underhållsstopp**) eller på en arbetsorderpool (**Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**).

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhållsstopp i listan > knappen **Artikelprognos**.

2. I dialogrutan **Beräkna artikelprognos** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**

3. Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i prognosberäkningen.

4. Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i prognosberäkningen.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerade artikelprognosraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på den funktionsplatsnivå som de är relaterade till.

6. Klicka på **OK** för att starta beräkningen.

7. I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna för åtgärdsfönstergrupper markeras i blått. Klicka på en knapp för att aktivera och inaktivera den.

8. Klicka på knappen **Visa dimensioner** om du vill visa produkt-, lagrings- eller spårningsdimensioner som hör till artiklarna. Markera relevanta kryssrutor och klicka på **OK**.

Bilden nedan visar en skärmbild av gränssnittet.

![Figur 1](media/02-capacity-planning.png)
