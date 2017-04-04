---
title: "Ställ in streckkodsmasker"
description: "Det här avsnittet beskrivs hur du ställer in streckkodsmasktecken, masker för streckkoder och maskerar tilldela streckkod till streckkoder."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Ställ in streckkodsmasker

Det här avsnittet beskrivs hur du ställer in streckkodsmasktecken, masker för streckkoder och maskerar tilldela streckkod till streckkoder.

<a name="set-up-bar-code-mask-characters"></a>Ställ in streckkodsmasktecken
-------------------------------

Streckkodsmasker används för att skapa streckkoder och snabbt identifiera streckkoder som skannas till försäljningsstället (PO). Masker består av tecken som fungerar som platshållare som anger formatet för streckkoder som ska skapas. Om du vill konfigurera en streckkodsmask måste du ställa in streckkodsmasktecken. Gå till **butik och handel**&gt;**lagerhantering**&gt;**streckkoder och etiketter**&gt;**tecken Mask**. Klicka på **New** att skapa streckkodsmasktecken. Masktecken kan skapas för att ange följande data i streckkoden.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | Platshållare för produkt-ID.                                                                                     |
| **Any number**       | Används för att ange ett tal som är hårddiskar kodats i streckkoder.                                                  |
| **Check digit**      | Anger att streckkodsformat i en streckkodsmask används en kontrollsiffra för att bekräfta giltigheten hos en streckkod. |
| **Size digit**       | Anger storleken i en streckkod för produktvarianten som innehåller storlek.                                 |
| **Color digit**      | Anger färgen på en streckkod för produktvarianten som innehåller färg.                               |
| **Style digit**      | Anger formatet på en streckkod för produktvarianten som innehåller en formatmall.                             |
| **EAN license code** | Platshållare för EAN-licens utfärdad för EAN licenskoder.                                                       |
| **Pris**            | Visar pris pris inbäddade streckkoder.                                                                   |
| **Quantity**         | Anger kvantiteten i antal slumpmässigt vikt inbäddad streckkoder.                                                |
| **Employee**         | Anger streckkod segmentet anställningsnummer för streckkod POS-inloggning.                                  |
| **Customer**         | Anger ID kundsegment.                                                                                  |
| **Inmatning av data**       | *Har inte implementerats ännu.*                                                                                          |
| **Discount code**    | Anger en rabattkod för en streckkod som används för att lägga till en rabatt i en mittpunkt försäljningstransaktionen             |
| **Presentkort**        | Anger presentkortsnummer när de utfärdar eller betala med presentkort.                                               |
| **Loyalty card**     | Lägger till en förmånskund har använt i transaktionen och kan användas vid betalning av förmåner.                             |

## <a name="define-bar-code-masks"></a>Definiera streckkodsmasker
När du anger streckkodsmasktecken för nödvändiga streckkodsmasker, går du till **butik och handel**&gt;**lagerhantering**&gt;**streckkoder och etiketter**&gt;**Streckkodsinställningar mask**. På den här sidan kan du definiera streckkodsmasker med tidigare angivna tecken. Dessa streckkod masker ska användas vid generering av streckkoder och även bidra till att identifiera streckkoder skannas i KASSAN.

1.  Klicka på **New** du skapar en ny streckkodsmasken.
2.  Ange värden i den **Mask-ID för** och **beskrivning** fält och välj en streckkodsmask den **typ** fältet.
3.  I den **allmänna** och välj ett värde i den **Streckkodsstandard** fält och sedan ange prefixet streckkod om en sådan krävs.
4.  I den **Streckkodsmasksegment** avsnitt, lägga till streckkod segment som ska användas i streckkoden ska skapas.

Exempelvis om du vill skapa en streckkodsmask mask-ID för produkt, gör du följande:

1.  Skapa en ny streckkodsmask och välj "Produkt".
2.  Välj en streckkod standard, till exempel kod 39' '.
3.  Ange ett prefix som ska användas för att enkelt identifiera streckkoden. Exempelvis "22".
4.  Lägg till ett segment i masken. Segmentet "Product" masken markeras.
5.  Ange längden för produkten segment, till exempel "10". Längden ska matcha längden på ett produkt-ID som ofta används i butiken. Masken ska visas som en förhandsgranskning i den **allmänna** enligt avsnitt **Mask**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Tilldela streckkoder streckkodsmasker
Streckkodsmasker måste tilldelas streckkoder innan de kan användas. Fortsätter med exemplet ovan streckkodsmasken tilldelas en streckkod, gör du så här:

1.  Gå till **Organisationsadministration**&gt;**inställningar**&gt;**streckkoder**. Klicka på **New** du skapar en ny streckkod.
2.  Ange värden i de **streckkod****inställningar** och ** inställningar ** fält.
3.  I den **allmänna** avsnitt i den **streckkodstyp** väljer "Kod 39". I den **Mask****ID** väljer du skapade masken "Produkt".
4.  Under **storlek**, ange "12".
5.  Click **Save**.

Streckkodsmasken kan nu användas för att skapa streckkoder för produkter. De visar också skapa streckkodsmasker för någon av andra stöds Streckkodstyper stegen ovan är exempel på hur du kan skapa streckkodsmasker för produkter. Streckkodsmasker, typer och längd skall justeras för användning i din miljö.


