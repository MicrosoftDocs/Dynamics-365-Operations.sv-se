---
title: Abonnemangsförsäljningspriser
description: När du skapar ett abonnemang hämtas försäljningspriset från inställningarna för försäljningspris som skapats i formuläret Försäljningspris (abonnemang).
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b4b02af0a535e67818751c437482c3663524474
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817423"
---
# <a name="subscription-sales-prices"></a>Abonnemangsförsäljningspriser   

[!include [banner](../includes/banner.md)]


När du skapar ett abonnemang hämtas försäljningspriset från inställningarna för försäljningspris som skapats i formuläret **Försäljningspris (abonnemang)**.

I formuläret **Försäljningspris (abonnemang)** kan du skapa försäljningspriser för ett visst abonnemang, eller också kan du skapa försäljningspriser som har ett bredare tillämpningsområde. Om du ska kunna tillämpa ett försäljningspris på ett abonnemang måste periodkoden och valutan för abonnemanget måste vara identisk med periodkoden och försäljningsprisets valuta.

Om periodkoden och valutan är identiska för både abonnemang och försäljningspris väljs försäljningspriser för abonnemanget utifrån de prioriteringar som listas i följande tabell. En tom cell i tabellen indikerar tomt fält och X anger ett värde som är lika med värdet i abonnemanget som transaktionen genererats från.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Prioritet </p></th>
<th><p><strong>Kategori</strong></p></th>
<th><p><strong>Projekt-ID</strong></p></th>
<th><p><strong>Abonnemang</strong></p></th>
<th><p><strong>Försäljningsvaluta</strong></p></th>
<th><p><strong>Periodkod</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


När en abonnemangsavgift skapas väljs försäljningspriset med högst detaljnivå (enligt uppgifterna i tabellen ovan) som försäljningspris för abonnemanget.

## <a name="update-and-index-subscription-sales-prices"></a>Uppdatera och indexera abonnemangsförsäljningspriser

Du kan uppdatera försäljningspriset för abonnemanget genom att uppdatera baspris eller index. Du kan uppdatera med en procentsats eller till ett nytt värde.

## <a name="subscription-fee-sales-prices"></a>Försäljningspriser för abonnemangsavgift

När du skapar en abonnemangsavgift baseras försäljningspriset på abonnemangets inställda försäljningspris. Du kan använda baspriset från prisinställningarna från abonnemanget eller så kan du skapa indexerade försäljningspriser.

## <a name="example"></a>Exempel

Du vill skapa ett försäljningspris för abonnemang på 500 EUR för det nya projektet 9030. I formuläret **försäljningspris (abonnemang)** kan du skapa en försäljningsprisrad enligt tabellen nedan.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Giltig från</p></th>
<th><p>Kategori</p></th>
<th><p>Project</p></th>
<th><p>Abonnemang</p></th>
<th><p>Periodkod</p></th>
<th><p>Försäljningsvaluta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2006-08-28</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Månad</p></td>
<td><p>Euro</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Observera att fälten **Kategori** och **Abonnemang** är tomma.

Du skapar sedan följande abonnemang:

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Serviceabonnemang</p></th>
<th><p>Project</p></th>
<th><p>Abonnemangsgrupp</p></th>
<th><p>Kategori</p></th>
<th><p>Valuta</p></th>
<th><p>Periodkod</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Ab1</p></td>
<td><p>AbKat1</p></td>
<td><p>Euro</p></td>
<td><p>Månatligen</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Ab1</p></td>
<td><p>AbKat2</p></td>
<td><p>Euro</p></td>
<td><p>Månatligen</p></td>
</tr>
</tbody>
</table>


Nu skapar du abonnemangsavgifter för båda abonnemangen i abonnemangsgruppen Ab1:

1.  Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.

2.  I formuläret **abonnemangsgrupper** klickar du på **funktion**\>**Skapa abonnemangsavgift**.

3.  På formuläret **Skapa abonnemangsavgift** ange lämplig information i fälten i formuläret. Mer information finns i [Skapa transaktioner för abonnemangsavgifter](create-subscription-fee-transactions.md).

Abonnemangsavgifter med försäljningspriset 500 EUR skapas för båda abonnemangen som visas i följande tabell.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Projektdatum</p></th>
<th><p>Serviceabonnemang</p></th>
<th><p>Project</p></th>
<th><p>Kategori</p></th>
<th><p>Startdatum</p></th>
<th><p>Slutdatum</p></th>
<th><p>Försäljningsvaluta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2006-08-28</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>AbKat1</p></td>
<td><p>2007-01-01</p></td>
<td><p>2007-03-31</p></td>
<td><p>Euro</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>2006-08-28</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>AbKat2</p></td>
<td><p>2007-01-01</p></td>
<td><p>2007-03-31</p></td>
<td><p>Euro</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Senare beslutar du dig för att du vill ange försäljningspriser för kategorin AbKat1 för projekt 9030. Därför skapar du en ny försäljningsprisrad med försäljningspriset EUR 550 för kombinationen projekt 9030 och avgiftskategori AbKat1. Det finns nu två abonnemangsprisrader för projekt 9030 enligt följande tabell.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Giltig från</p></th>
<th><p>Kategori</p></th>
<th><p>Project</p></th>
<th><p>Abonnemang</p></th>
<th><p>Periodkod</p></th>
<th><p>Valuta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2007-08-28</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Månad</p></td>
<td><p>Euro</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>2007-08-28</p></td>
<td><p>AbKat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Månad</p></td>
<td><p>Euro</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Du upprepar proceduren ovan och skapar abonnemangsavgifter för båda abonnemangen i abonnemangsgruppen Ab1. Följande tabell visar de transaktioner som skapas för varje abonnemang som är kopplat till abonnemangsgruppen:

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Projektdatum</p></th>
<th><p>Abonnemang</p></th>
<th><p>Project</p></th>
<th><p>Kategori</p></th>
<th><p>Startdatum</p></th>
<th><p>Slutdatum</p></th>
<th><p>Försäljningsvaluta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2007-07-28</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>AbKat1</p></td>
<td><p>2008-01-01</p></td>
<td><p>2008-03-31</p></td>
<td><p>Euro</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>2008-07-28</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>AbKat2</p></td>
<td><p>2008-01-01</p></td>
<td><p>2008-03-31</p></td>
<td><p>Euro</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


I den första transaktionen för abonnemang 00020\_135, kommer försäljningspriset på 550 EUR från det abonnemangsförsäljningspris som skapats för den specifika kombinationen av projekt och kategori. I den andra transaktionen för abonnemang 00021\_135, används försäljningspriset 500 EUR som projektets abonnemangsförsäljningspris eftersom inget pris skapats för kombinationen av projekt 9030 och kategori AbKat2.

## <a name="see-also"></a>Se även

[Uppdatera och indexera abonnemangsförsäljningspriser](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]