---
title: Funktionen strukturlistedesigner
description: "Det här avsnittet ger en beskrivning av hur du kan använda sidan för strukturlistan för att designa och arbeta med trädstrukturer för strukturlistor (BOMs). Du kan klicka på Inställningar för att välja olika konfigureringar och ange vilken information som ska visas på raderna i trädstrukturen."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-08 21 - 09 - 22
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 2c98039c9fa8179408394f9f66b9fca0f8cad3fe
ms.lasthandoff: 03/29/2017


---

# <a name="bom-designer-functionality"></a>Funktionen strukturlistedesigner

Det här avsnittet ger en beskrivning av hur du kan använda sidan för strukturlistan för att designa och arbeta med trädstrukturer för strukturlistor (BOMs). Du kan klicka på Inställningar för att välja olika konfigureringar och ange vilken information som ska visas på raderna i trädstrukturen.

När du öppnar sidan **Strukturlistedesigner** från sidan **Frisläppta produkter**, visar den hierarkin med strukturlistor som är aktiva och godkända för den valda artikeln, standardorderplatsen för artikeln och aktuellt datum.  

Klicka **Filter** för att ändra det initiala valet i vyn. Genom att ange visningprincipen till **Valda/aktiva eller valda** kan du välja individuella strukturliste- eller flödesversioner som ska användas i vyn. Du kan välja icke godkända och icke aktiva strukturlisteversioner att visa eller underhålla i strukturlistedesignern.  

**Obs!** Om du öppnar strukturlistedesignern från listsidan, **Strukturlistor** visas inte flödesinformationen. För närvarande är valet av en strukturlista eller flödesversion en egenskap i strukturlistan och flödesversionen och gäller alla instanser av strukturlistedesignern.  

Följande avsnitt beskriver de funktioner som är tillgängliga för de olika flikarna i strukturlistedesignern.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Analysera en strukturlistestruktur genom att använda strukturlistedesignern
Strukturlistedesignern har två avsnitt:

-   Trädvy av strukturlistestruktur.
-   Detaljavsnittet som visar information om de valda data. När du väljer en nod i trädvyn, är snabbflikarna i detaljavsnittet uppdaterat baserat på den noden:
    -   **Information för strukturlisterad** – Visar information om strukturlisteraden som valts i trädvyn.
    -   **Artikeldata** – Visar information om huvudartikeln eller en artikel som används i den valda noden. Du kan klicka på **Redigera frisläppt produkt** om du vill behålla den valda artikeln.
    -   **Strukturlista** - Visar sidhuvudet i strukturlistan som är relaterade till den valda noden.
    -   **Flöde** - Visar sidhuvudet i flödet som är relaterade till den valda noden.
    -   **Flödesoperationer** – Visar en förhandsgranskning av operationerna för flödet. När en strukturlisterad, som tilldelas en viss operation, är markerad markeras operationen som **Komponenter måste anges vid operationer**.

## <a name="selecting-a-bom-and-route"></a>Välj en strukturlista och ett flöde
Filtret som används för strukturlistan och flödet, visas i strukturlistedesignern. Du kan ändra filtret, genom att använda dialogrutan **Filter**. I tabellen nedan beskrivs fälten i denna dialogruta.

<table>
<thead>
<tr class="header">
<th>Fält</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produktdimensioner</td>
<td>Om den valda färdiga produkten är en produktmall, kan du definiera de aktiva produktdimensionerna för huvudavsnittet.<strong>Obs!</strong> Om du öppnar strukturlistedesignern för en produkt som inte är en produktmall, kan inga produktdimensioner markeras i dialogrutan <strong>Filter</strong> .</td>
</tr>
<tr class="even">
<td>Plats</td>
<td>Ändra den plats som strukturlistaträdet visas för. Standardplatsen är standardlagerplatsen för den färdiga artikeln.</td>
</tr>
<tr class="odd">
<td>Visa princip</td>
<td>Välj den versionsvisningsprincip som gäller för den aktuella strukturlistans struktur och det aktuella flödet:
<ul>
<li>När principer anges till <strong> Aktiva eller Valda/aktiva</strong> hittas den giltiga strukturliste- eller flödesversionen för detta datum.</li>
<li>När principerna har angetts som <strong>Vald/aktiv eller Vald</strong> så kan du välja en strukturlisteversion eller flödesversion genom att klicka på <strong>Strukturlista</strong> &gt; <strong>Strukturlisteversioner</strong> eller <strong>Flöde</strong> &gt; <strong>Flödesversioner</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Versionsdatum</td>
<td>Ange versionsdatum för strukturlistan och flödet. Versionen identifierar vilken strukturlisteversion som används på ett visst datum, vilket bestäms av versionsdatumen i inställningen för strukturlisteversionen.</td>
</tr>
<tr class="odd">
<td>Från-kvantitet</td>
<td>Filtrera versionerna genom att välja från en viss kvantitet. Om du ställer in ett värde, kan en annan strukturlista och flödesversioner markeras.</td>
</tr>
<tr class="even">
<td>Visa bara giltiga</td>
<td>När du markerar kryssrutan visar trädstrukturen bara strukturlisterader som har giltiga datum. Du kan högerklicka på strukturlisteraden om du vill öppna <strong>Redigera strukturlisterad</strong> där du kan visa strukturlisteradens giltighetsdatum.</td>
</tr>
</tbody>
</table>

När du använder strukturlistedesignern för att granska eller redigera strukturlistor som består av en eller flera nivåer av fiktiva element, omfattar flödet som är kopplat till den översta artikeln, vanligtvis den färdiga strukturlistans hierarki. För att förenkla översikten kan du låsa flödet på högsta nivån på skärmen genom att klicka på **Visa** &gt; **Lås flöde**. Om du vill låsa upp flödet, klicka på **Visa** &gt; **Lås upp flöde**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Lägga till och redigera strukturlistor och strukturlisterader
Använd funktionerna **Strukturlisterader **eller **Strukturlista** för att ändra strukturlisteraderna eller strukturlistan. När du väljer en nod i trädet, bestämmer typen av nod vilka funktioner som är tillgängliga.

| Funktion                            | beskrivning                                                                                               | Nodtyp och -villkor                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Strukturlisterader &gt; Redigera                 | Öppna en dialogruta där du kan redigera strukturlisteradattributen.                                             | Den här funktionen finns bara, när en strukturlisteradnod har valts.                                                                                                                                                                                                                                   |
| Strukturlisterader &gt; Radera               | Ta bort den strukturlisteraden från den valda strukturlistan.                                                                  | Den här funktionen finns bara, när en strukturlisteradnod och strukturlistan inte är låst för redigering.                                                                                                                                                                                             |
| Strukturlisterader &gt; Lägg till före rad      | Öppna en dialogruta där du kan välja en produktvariant att inkludera innan den valda strukturlisteraden.         | Den här funktionen finns bara, när en strukturlisteradnod har valts.                                                                                                                                                                                                                                   |
| Strukturlisterader &gt; Lägg till i komponentstrukturlista | Öppna en dialogruta där du kan välja en produktvariant att inkludera på slutet av den valda strukturlisteraden.       | Den här funktionen finns bara, när noden som har valts har en vald strukturlisterad. Om denna funktion inte är tillgänglig, kan en strukturlisteversion saknas för den valda artikelvarianten. I detta fall kan du klicka på **Strukturlista** &gt; **Skapa version** för att skapa den saknade versionen för den valda noden. |
| Strukturlisterader &gt; Lägg till efter rad       | Öppna en dialogruta där du kan välja en produktvariant att inkludera efter den valda strukturlisteraden.          | Den här funktionen finns bara, när en strukturlisteradnod har valts.                                                                                                                                                                                                                                   |
| Strukturlista &gt; Skapa version             | Skapa en ny strukturlisteversion eller strukturlista för produktvarianten för den valda noden.                             | Den här funktionen finns bara när strukturlisteradnoden, som väljs är kopplad till en artikel som har en produktionstyp av **Strukturlista** eller **Formel**                                                                                                                                                  |
| Strukturlista &gt; Beräkning                | Öppna en dialogruta där du kan köra kostnads- och försäljningprisberäkningen för den valda produktvarianten. | Den här funktionen finns bara, när noden som har valts är relaterad till en strukturlisteversion.                                                                                                                                                                                                         |
| Strukturlista &gt; Kontrollera                      | Validera och kontrollera den valda strukturlistan.                                                                      | Den här funktionen finns bara, när noden som har valts är relaterad till en strukturlisteversion.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Konfigurera trädvy
Klicka på **Inställningar** om du vill anpassa informationen som visas i trädvyn i strukturlistedesignern.

| Fältgrupp | Beskrivning                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Strukturlista         | Använd kryssrutorna för att välja de kriterier som visas i trädstrukturen. I designverktyget visas det valda villkoret längst ned på båda flikarna. |
| Rutt       | Använd kryssrutorna för att välja de kriterier som visas för flödena.                                                                                    |




