---
title: Beräkna kapacitetsbeläggning
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning i Tillgångshantering.
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
ms.openlocfilehash: c6d15861492a46ddb1222db2210f8c751ed38cb3
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886803"
---
# <a name="calculate-capacity-load"></a>Beräkna kapacitetsbeläggning

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du beräkna kapacitetsbeläggningen på

- rader för underhållsschema  
- arbetsorder som ännu inte har planerats  
- schemalagda arbetsorder

Detta är användbart om du vill få en översikt över förväntad kapacitetsbeläggning för en viss period. Beräkning av kapacitetsbeläggnin kan göras på alla tillgångar eller valda tillgångar. Du kan också utföra en beräkning av aktiviteter för underhållsstopp och arbetsorderpooler.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhåll i listan > knappen **Kapacitetsbeläggning**.

2. I dialogrutan **Beräkna kapacitetsbeläggning** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**

3. Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i beräkningen.

4. Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i beräkningen.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningsrader ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på de funktionsplatsnivåer som de är relaterade till.

6. Klicka på **OK** för att starta beräkningen.

7. I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna för åtgärdsfönstergrupper markeras i blått. Klicka på en knapp för att aktivera och inaktivera den.

Bilden nedan visar en ett exempel på gränssnittet.

![Figur 1](media/01-capacity-planning.png)

>[!NOTE]
>Om du bara vill fokusera på kapacitetsplanering för schemalagda arbetsorder läser du i [Beräkna kapacitetsbeläggning på schemalagda arbetsorder](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).

