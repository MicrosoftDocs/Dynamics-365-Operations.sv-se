---
title: Ställ in streckkodsmasker
description: Det här avsnittet beskriver hur du ställer in streckkodsmasktecken, streckkodsmasker och hur du tilldelar streckkodsmasker till streckkoder.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 5432741e7cdc21054d02bd24591deb307d096229
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969811"
---
# <a name="set-up-bar-code-masks"></a>Ställ in streckkodsmasker

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver hur du ställer in streckkodsmasktecken, streckkodsmasker och hur du tilldelar streckkodsmasker till streckkoder.

## <a name="set-up-bar-code-mask-characters"></a>Ställ in streckkodsmasktecken

Streckkodsmasker används för att skapa streckkoder och snabbt identifiera streckkoder som skannas till betalningsplatsen (POS). Masker består av tecken som fungerar som platshållare som anger formatet för streckkoder som ska skapas. Om du vill konfigurera en streckkodsmask måste du ställa in streckkodsmasktecken. Gå till **Butik och handel** &gt; **Lagerhantering** &gt; **Streckkoder och etiketter** &gt; **Streckodsinställningar**. Klicka på **Ny** om du vill skapa ett nytt streckkodsmasktecken. Masktecken kan skapas för att ange följande data i streckkoden.

| Fält            | beskrivning |
|------------------|-------------|
| Produkt          | Platshållare för produkt-ID. |
| Valfritt nummer       | Används för att ange ett tal som kommer att bli hårdkodade i streckkoder. |
| Kontrollsiffra      | Anger att streckkodsformatet i en streckkodsmask använder en kontrollsiffra för att bekräfta giltigheten hos en streckkod. |
| Sifferstorlek       | Anger storleken i en streckkod för produktvarianten som innehåller storlek. |
| Sifferfärg      | Anger färg i en streckkod för produktvarianten som innehåller färg. |
| Sifferformat      | Anger formatet i en streckkod för produktvarianten som innehåller ett format. |
| EAN-licenskod | Platshållare för EAN-licens utfärdad för EAN-licenskoder. |
| Pris            | Anger pris för prisinbäddade streckkoder. |
| Kvantitet         | Anger kvantiteten i kvantitet/slumpmässigt viktinbäddade streckkoder. |
| Medarbetare         | Anger streckkodssegment för anställningsnummer som ska användas för kassainloggning med streckkod. |
| Kund         | Anger kund-ID-segment. |
| Datapost       | *Ej implementerad.* |
| Rabattkod    | *Inaktuell* från Dynamics 365 for Retail version våren 2017. Tidigare: Anger en rabattkod för en streckkod som används för att lägga till en rabatt i en kassatransaktion. |
| Kupongkod      | Anger kupongkod för en streckkod som används för att lägga till en rabatt i en order. Detta ersatte rabattkoden. |
| Presentkort        | Anger ett presentkortsnummer när de utfärdar eller betalar med presentkort. |
| Förmånskort     | Lägger till en förmånskund till transaktionen och kan användas vid betalning av förmåner. |

## <a name="define-bar-code-masks"></a>Definiera streckkodsmasker

När du anger streckkodsmasktecken för nödvändiga streckkodsmasker, går du till **butik och handel** &gt; **lagerhantering** &gt; **streckkoder och etiketter** &gt; **streckkodsinställningsmask**. På den här sidan kan du definiera streckkodsmasker med tidigare angivna tecken. Dessa streckkodsmasker ska användas vid generering av streckkoder och även bidra till att identifiera streckkoder som skannas i POS.

1. Klicka på **Ny** om du vill skapa en ny streckkodsmask.
2. Ange värden i fälten **Mask-ID** och **beskrivning** och välj en streckkodsmask fältet **typ** .
3. I avsnittet **allmän** väljer du ett värde i fältet **Streckkodsstandard** och anger sedan streckkodsprefixet om ett sådant krävs.
4. I avsnittet **Streckkodsmasksegment** lägger ni till streckkodssegment som ska användas i streckkoden som ska skapas.

Exempelvis om du vill skapa en streckkodsmask med mask-ID för produkt, gör du följande:

1. Skapa en ny streckkodsmask och välj "Produkt".
2. Välj en streckkodsstandard, t.ex. "Kod 39".
3. Ange ett prefix som ska användas för att enkelt identifiera streckkoden. Till exempel "22".
4. Lägg till ett masksegment. Masksegmentet "Produkt" markeras.
5. Ange längden för produktsegment, till exempel "10". Längden ska matcha längden på ett produkt-ID som används ofta i butiken. Masken ska visas som en förhandsgranskning i avsnittet **allmän** under **Mask**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Tilldela streckkodsmasker till streckkoder

Streckkodsmasker måste tilldelas till streckkoder innan de kan användas. Gör följande för att tilldela streckkodsmasken till en streckkod:

1. Gå till **Organisationsadministration** &gt; **Inställningar** &gt; **Streckkoder**. Klicka på **Ny** för att skapa en ny streckkod.
2. Ange värden i fälten **Streckkod** **Inställning** och **Inställning**.
3. I avsnittet **allmänt** i fältet **streckkodstyp** väljer du "Kod 39". I fältet **Mask** **ID** väljer du masken "Produkt" som skapats tidigare.
4. Under **storlek**, anger du "12".
5. Klicka på **Spara**.

Streckkodsmasken kan nu användas för att skapa streckkoder för produkter. Stegen ovan är exempel på hur du skapar streckkodsmasker för produkter, men de visar också hur du kan skapa streckkodsmasker för alla andra streckkodstyper som stöds. Streckkodsmasker, typer och längd ska justeras för användning i din specifika miljö.
