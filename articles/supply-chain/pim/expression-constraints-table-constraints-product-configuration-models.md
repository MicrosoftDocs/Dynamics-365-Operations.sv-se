---
title: "Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller."
description: "I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar. Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder. Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7aeb0438182fe177ac83580f03cbb547c79fd08a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Uttryckbegränsningar och tabellbegränsningar i produktkonfigurationsmodeller.

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du använder uttrycksbegränsningar och registerbegränsningar. Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder. Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar. 

Med begränsningar kontrolleras vilka attributvärden som du kan välja när du konfigurerar produkter för en försäljningsorder, försäljningsoffert, inköpsorder eller produktionsorder. Du kan använda uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar.

## <a name="what-are-expression-constraints"></a>Vad är uttrycksbegränsningar?
Uttrycksbegränsningar karakteriseras av ett uttryck som använder aritmetiska och booleska operatorer och funktioner. En uttrycksbegränsning skrivs för en viss komponent i en produktkonfigurationsmodell. Den kan inte återanvändas av eller delas med en annan komponent. Uttryckbegränsningarna för en komponent kan dock referera till attribut i komponentens delkomponenter.

## <a name="what-are-table-constraints"></a>Vad är registerbegränsningar?
Registerbegränsningar anger de kombinationer av värden som tillåts för attribut när du konfigurerar en produkt. Registerbegränsningdefinitioner kan användas i allmänhet. När du skapar en registerbegränsning för en komponent i en modell för produktkonfiguration, väljer du en registerbegränsningsdefinition. Om du vill skapa de tillåtna kombinationerna, lägger du till attribut för specifika typer till komponenterna. Varje attributtyp har ett visst värde.

### <a name="example-of-a-table-constraint"></a>Exempel på registerbegränsning.

I det här exemplet visas hur du kan begränsa konfigurationen för en högtalare till specifika kabinettfinish och framdelar. Den första tabellen visar storlekar och typer av kabinettfinish och framdelar som är allmänt tillgängliga för konfiguration. Du definierar värdena för attributtyperna **Kabinettfinish** och **Frontgaller**.

| Attributtyp | Värden                      |
|----------------|-----------------------------|
| Kabinettfinish | Svart ek, rosenträ, vitt |
| Frontgaller    | Svart, Metall, Vitt         |

Nästa tabell visar kombinationerna som definieras av registerbegränsningen i **Färg och finish**. Med hjälp av den här registerbegränsningen kan du konfigurera en högtalare, som har ekfinish och svart galler, en rosenträregisterbegränsning och ett vitt galler, osv.

| Slutför         | Galler                       |
|----------------|-----------------------------|
| Ek            | Svart                       |
| Rosenträ       | Vit                       |
| Vit          | Svart                       |
| Vit          | Vit                       |
| Svart          | Svart                       |
| Svart          | Metall                       | 

Du kan skapa systemdefinierade och användardefinierade registerbegränsningar. Mer information finns i [Systemdefinierade och användardefinierade registerbegränsningar](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Vilken syntax bör användas för att skriva begränsningar i ?
Du måste använda OML-syntaxen (Optimization Modeling Language) när du skriver begränsningar. Systemet använder Microsoft Solver Foundation-begränsning för att lösa begränsningarna.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>Ska jag använda registerbegränsningar eller uttrycksbegränsningar?
Du kan använda antingen uttrycksbegränsningar eller registerbegränsningar, beroende på hur du föredrar att skapa begränsningar. Du uppbyggnad en begränsning register som en vektor, medan en begränsning uttryck är ett enskilt utdrag. När du konfigurerar en produkt spelar det ingen roll vilken typ av begränsning som används. I följande exempel visas hur de två metoderna skiljer sig.  

När du konfigurerar en produkt, genom att använda följande begränsninginställningar, är dessa kombinationer tillåtna:

-   En produkt i färgen svart och i storlek 30 eller 50
-   En produkt i färgen röd och i storlek 20

### <a name="table-constraint-setup"></a>Registerbegränsningskonfiguration

| Färg | Storlek |
|-------|------|
| Svart | 30   |
| Svart | 50   |
| Röd   | 20   |

### <a name="expression-constraint-setup"></a>Inställning av uttrycksbegränsning

(Färg == "Svart" & (storlek == "30" | storlek == "50")) | (färg == "Rör" & storlek = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>Ska jag använda operatorer eller infixnotation när jag skriver uttrycksbegränsningar?
Du kan ange ett begränsningsuttryck, antingen genom att använda de tillgängliga prefixoperatorerna eller genom att använda infixnotation. För operatorerna **Min**, **Max**, och **Abs** kan du inte använda en infixnotation. Dessa operatorer inkluderas som standard i de flesta programspråk.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>Vilka operatorer eller infixnotationer kan jag använda när jag skriver uttrycksbegränsningar?
I följande tabeller visas operatorerna och infixnotationerna som du kan använda när du skriver en uttrycksbegränsning för en komponent i en produktkonfigurationsmodell. I exemplen i den första tabellen ser du hur du kan skriva ett uttryck genom att använda infixnotation eller operatorer.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operatör</th>
<th>Beskrivning</th>
<th>Syntax</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Medför</td>
<td>Detta gäller om det första villkoret är falskt, det andra villkoret är sant eller båda.</td>
<td>Medför[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Operatör:</strong> Implies[x != 0, y &gt;= 0]</li>
<li><strong>Infixnotation:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>Och</td>
<td>Detta gäller endast om alla villkor är sanna. Om antalet villkor är 0 (noll), ger det <strong>Sant</strong>.</td>
<td>And[args], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Operatör:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Infixnotation:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Eller</td>
<td>Detta gäller om något villkor är sant. Om antalet villkor är 0 (noll), ger det <strong>Falskt</strong>.</td>
<td>Or[args], infix: a | b | ... | z</td>
<td><ul>
<li><strong>Operatör:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Infixnotation:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plustecken</td>
<td>Detta summerar dess villkor. Om antalet villkor är 0 (noll), ger det <strong>0</strong>.</td>
<td>Plus[args], infix: a + b + ... + z</td>
<td><ul>
<li><strong>Operatör:</strong> Plus[x, y, 2] == z</li>
<li><strong>Infixnotation:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Minus</td>
<td>Detta upphäver dess argument. Detta måste ha exakt ett villkor.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Operatör:</strong> Minus[x] == y</li>
<li><strong>Infixnotation:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Detta tar absolutvärdet av dess villkor. Detta måste ha exakt ett villkor.</td>
<td>Abs [expr]</td>
<td><strong>Operatör:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Tider</td>
<td>Detta tar produkten av dess villkor. Om antalet villkor är 0 (noll), ger det <strong>1</strong>.</td>
<td>Times[args], infix: a * b * ... * z</td>
<td><ul>
<li><strong>Operatör:</strong> Times[x, y, 2] == z</li>
<li><strong>Infixnotation:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Effekt</td>
<td>Detta tar en exponential. Detta gäller exponentiering från höger till vänster. (Med andra ord är det rättighetsförenande.) Och därför är <strong>Power[a, b, c]</strong> det samma som <strong>Power[a, Power[b, c]].</strong> <strong>Effekt</strong> kan bara användas med en positiv konstant som exponent.</td>
<td>Power[args], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Operatör:</strong> Power[x, 2] == y</li>
<li><strong>Infixnotation:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Max.</td>
<td>Detta ger det största villkoret. Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</td>
<td>Maximal [args]</td>
<td><strong>Operatör:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min.</td>
<td>Detta ger det minsta villkoret. Om antalet villkor är 0 (noll), ger det <strong>Oändlighet</strong>.</td>
<td>Min[args]</td>
<td><strong>Operatör:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Inte</td>
<td>Detta producerar den logiska motsatsen av dess villkor. Detta måste ha exakt ett villkor.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Operatör:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Infixnotation:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Exemplen i följande tabell visar hur du skriver en infixnotation.

| Infixnotation    | beskrivning                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| x + y + z         | Tillägg                                                                                      |
| x \* y \* z       | Multiplikation                                                                                |
| x - y             | Binär subtraktion översätts liksom binär addition med negerad andra term. |
| x ^ y ^ z         | Högerassociativ exponentiering                                                   |
| !x                | Booleskt inte                                                                                   |
| x -: y            | Boolesk implikation                                                                           |
| §x | y | z         | Booleskt eller                                                                                    |
| x & y & z         | Booleskt och                                                                                   |
| x == y == z       | Likhet                                                                                      |
| x != y != z       | Distinkt                                                                                      |
| x &lt; y &lt; z   | Mindre än                                                                                     |
| x &gt; y &gt; z   | Större än                                                                                  |
| x &lt;= y &lt;= z | Mindre än eller lika med                                                                         |
| x &gt;= y &gt;= z | Större än eller lika med                                                                      |
| (x)               | Standardprioritet för åsidosättande av parenteser.                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Varför kan inte mina uttryckbegränsningar verifieras korrekt?
Du kan inte använda reserverade nyckelord som solvernamn för attribut, komponenter eller delkomponenter i produktkonfigurationsmodell. Följande lista innehåller de reserverade nyckelord som du inte kan använda:

-   Tak
-   Element
-   Lika
-   Våning
-   Om det 
-   Mindre
-   Större
-   Medför
-   Logg
-   Max.
-   Min.
-   Minus
-   Plustecken
-   Effekt
-   Tider
-   Fack
-   Modell
-   Beslut
-   Mål


<a name="see-also"></a>Se även
--------

[Skapa en uttrycksbegränsning (uppgiftsguide)(uppgifter/lägg-till-uttrycksbegränsning-produktkonfigurationsmodell.md)

[Lägg till en beräkning i en produktkonfigurationsmodell (uppgiftsguide)](tasks/add-calculation-product-configuration-model.md)




