---
title: Sammansatta datatyper som stöds för elektroniska rapporteringsformler
description: Detta ämne ger information om de sammansatta datatyper som stöds i elektroniska rapporteringsformler (ER-formler).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc3fbe695d79eb0ec9796d471c4d2bb0bb7ab99d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869327"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Sammansatta datatyper som stöds för elektroniska rapporteringsformler

[!include [banner](../includes/banner.md)]

Detta ämne ger information om de sammansatta datatyper som stöds i [elektroniska rapporteringsuttryck (ER-uttryck)](general-electronic-reporting.md). Sammansatta datatyper är [klass](#class), [behållare](#container), [post](#record), [postlista](#record-list) och [objekt](#object).

## <a name="class"></a><a name="class"></a>Klass

Datatypen *klass* avser en offentlig programklass. I ER representeras den som en [*post*](#record) som innehåller ett separat fält för samtliga offentliga metoder för den refererade klassen. När anropet för metoden är parametriserat måste du även ange de argument som krävs för lämpliga typer i ett ER-uttryck som är konfigurerat för att anropa metoden.

I komponenterna för ER-mappning och -format kan du lägga till datakällan **Klass**, som presenteras som en datakälla och som returnerar ett värde för typen *klass*. Denna datakälla visar offentliga metoder för den klass som kan anropas vid körning.

> [!NOTE]
> Det är bara metoder som returnerar ett värde som kan anropas från ER-uttryck.
>
> Det är bara metoder med intervallet noll till åtta argument som kan anropas från ER-uttryck.

Standardvärdet för en *klass* är **null**.

I följande bild anges hur datakällan **System information(xInfo)** för typen **Klass** läggs till i syfte att skapa instansen för programklassen **xInfo** och anropa dess **productName()**-metod i syfte att erhålla namnet på aktuellt program. Namnet på det aktuella programmet hämtas i samband med körning genom körning av den `xInfo.productName`-bindning som konfigurerats för fältet **Programvarunamn (SoftwareName)** i ER-datamodellen. Denna bindning kallas `productName()`-metoden för den **xInfo**-programklass som representeras i aktuell modellmappning som datakällan **System information(xInfo)**.

[![Konfigurera en Klass-datakälla i ER-modellmappningsdesignern.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

Följande bild visar hur ER-formatet är konfigurerat för att placera det angivna programnamnet i genererade dokument. Fältet **Programvarunamn (SoftwareName)** i använd datamodell var bundet till den **Sträng**-komponent kapslats under XML-elementet **softwareUsed** för ER-formatet. I så fall placeras namnet på det aktuella programmet vid körning i XML-elementet **softwareUsed** för ett genererat dokument i XML-format.

[![Konfigurera strukturen för ett elektroniskt utgående dokument i ER-formatdesignern.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Behållare

Datatypen *behållare* innehåller binärt innehåll. Ett värde för *behållare* kan användas för att överföra specifik information från lagring till ett genererat dokument. Inom ER-ramverket används denna datatyp ofta för att placera medieinnehåll som t.ex. en företagslogotyp i genererade dokument.

> [!NOTE]
> Även om alla mediaobjekt kan representeras som ett *behållar* värde representerar inte alla *behållar*-värden en medieartikel. Om du konfigurerar ett ER-format så att det använder en *behållare* för att placera en bild i genererade dokument, men den refererade *behållaren* inte returnerar medieinnehåll, kan ett undantag som liknar följande exempel visas: "Ett fel uppstod i samband med körning av kod: Binär (objekt), metoden constructFromContainer anropad med ogiltiga parametrar."

Standardvärdet för en *behållare* är **null**.

I följande bild visas hur fältet **Bitmap (bild)** av typen *Behållare* är knutet till datamodellfältet **Logo** av typen **Behållare** i modellmappningen **Försäljningsfaktura**. Med den här bindningen blir företagslogotypen tillgänglig för alla ER-format som har utformats för rotdefinitionen **SalesInvoice** och som använder denna modellmappning vid körning.

[![Binda ett fält av behållartyp i ER-modellmappningsdesignern.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Registrera

En *post* är en samling namngivna fält som vart och ett är kopplat till ett värde av antingen en [primitiv](er-formula-supported-data-types-primitive.md) datatyp eller en sammansatt datatyp. Vanligtvis används en *post* för att representera en enda post i en postlista. I det här fallet representerar varje artikel enskilda fält, metoder och relationer.

Standardvärdet för en *post* är **tom**.

> [!NOTE]
> När du får värdet för ett fält med en tom *post* returneras standardvärdet för lämplig datatyp.

En *post* erhålles med hjälp av följande funktioner:

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Mer information om omvandlingen av *post* värden finns i [Lista över ER-funktioner i listkategorin](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Postlista

En *postlista* är en lista över artiklar av typen *post*. En *postlista* används vanligtvis för att representera listan med poster som har hämtats från en databastabell.

Som standard ges åtkomst sekventiellt till poster i en *postlista*. Du kan komma åt en specifik post genom att använda funktionen [INDEX](er-functions-list-index.md) och ange *heltals* index.

Standardvärdet för en *postlista* är **tom**. Du kan använda funktionen [SEMPTY](er-functions-list-isempty.md) för att utvärdera om en *postlista* är tom.

> [!NOTE]
> Om en *postlista* är tom kommer alla försök att hämta ett fältvärde för en *post* i densamma att förorsaka ett undantag i samband med körning. Information om hur du kan förhindra undantag av det här slaget i samband med körning finns i [Beaktanden i samband med tomma listor](er-components-inspections.md#i9).

En *postlista* kan initieras med hjälp av följande funktioner:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Mer information om omvandlingen av värden för *postlistor* finns i [Lista över ER-funktioner i listkategorin](er-functions-category-list.md). För information om hur du presenterar artiklar i en *postlista*, fyller dessa med programdata och sedan använder denna data för att generera affärsdokument, se [Designa en ny ER-lösning för att skriva ut en anpassad rapport](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Objekt

Ett *objekt* avser en godkänd instans av en *klass*. Normalt *initieras* ett objekt i källkoden. Det överförs sedan till en ER-modellmappning och ger information om körningskontexten.

Standardvärdet för ett *objekt* är **null**.

I följande bild visas hur datakällan **ReportDataContract** av typen *Objekt* läggs till för att överföra information om en genererad faktura från källkoden till modellmappningen **Projektfaktura**. Fakturainstanstexten skickas till exempel som en del av körningskontexten. Denna text tas från källkoden vid körning genom körning av den `ReportDataContract.parmInvoiceInstanceText`-bindning som konfigurerats för fältet **Anteckning** i ER-datamodellen. Denna bindning kallas för `parmInvoiceInstanceText()`-etoden för den **PSAProjInvoiceContract**-programklass som finns representerad i aktuell modellmappning som datakällan **ReportDataContract**.

[![Konfigurera en objektdatakälla i ER-modellmappningsdesignern.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Mer information om hur du vidarebefordrar detaljer från körningskontexten från källkod till den ER-lösning som köls [Ta fram programartefakter för att anropa designad rapport](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Formelspråk i elektronisk rapportering](er-formula-language.md)
- [Primitiva datatyper som stöds](er-formula-supported-data-types-primitive.md)
