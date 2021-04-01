---
title: Receptdesigner
description: Det här avsnittet beskriver hur du använder formeldesignern för att analysera och underhålla formler i en trädvy.
author: cvocph
manager: tfehr
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f14a536cd2860a290ac90469907ded5de26e1991
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246223"
---
# <a name="formula-designer"></a>Receptdesigner

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du använder formeldesignern för att analysera och underhålla formler i en trädvy.

När du öppnar sidan **Formeldesigner** sidan från sidan **Frisläppta produkter**, visade trädet i det vänstra fönstret en lista över samprodukter och komponenthierarkin för frisläppt produkt. Strukturen härleds från hierarkin för formler som är aktiva och godkända för den valda artikeln och dess komponenter, standardsiten för order för artikeln, samt fakturadatumet.

Klicka på **Inställningar** för att välja olika konfigureringar och ange vilken information som ska visas på raderna i trädstrukturen.

Klicka **Filter** för att ändra det initiala valet i vyn. Genom att ange visningsprincipen som **Vald/Aktiv** eller **Vald** kan du välja individuella formel- eller flödesversioner som ska användas i vyn. Du kan välja icke godkända och icke aktiva formelversioner att visa eller underhålla i formeldesignern.  

> [!NOTE]
> Om du öppnar sidan **Formeldesigner** från listsidan **Strukturlistor** visas inte flödesinformationen. För närvarande gäller valet av en formel- eller flödesversion alla instanser av formeldesignern.  

Följande avsnitt beskriver de funktioner som är tillgängliga i strukturlistedesignern.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analysera en formelstruktur med formeldesignern
Formeldesignern har två avsnitt:

-   En trädvy över formelstrukturen.
-   Detaljavsnittet som visar information om de valda data. När du väljer en nod i trädvyn, är snabbflikarna i detaljavsnittet uppdaterat baserat på den noden:
    -   **Information om formelrad** – Visar information om formelraden som valts i trädvyn.
    -   **Artikeldata** – Visar information om huvudartikeln eller den artikel som används i den valda noden. Du kan klicka på **Redigera frisläppt produkt** om du vill behålla den valda artikeln.
    -   **Formel** – Visar sidhuvudet för den formel som är relaterad till den valda noden.
    -   **Flöde** – Visar sidhuvudet för det flöde som är relaterat till den valda noden.
    -   **Flödesoperationer** – Visar en förhandsgranskning av operationerna för flödet. När en strukturlisterad (BOM) som tilldelas en viss operation är markerad, markeras operationen som **Komponent som behövs vid operationer**.

## <a name="select-a-formula-and-route"></a>Välj en formel och ett flöde
Filtret som används för formeln och flödet visas i formeldesignerns rubrik. Du kan ändra filtret, genom att använda dialogrutan **Filter**. I tabellen nedan beskrivs fälten i denna dialogruta.

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
<td>Du kan definiera aktiva produktdimensioner för huvudurvalet om vald slutprodukt är en produktmall. Observera att om du öppnar formeldesigner för en produkt som inte är en produktmall kan inga produktdimensioner väljas i dialogrutan <strong>Filter</strong>.</p></td>
</tr>
<tr class="even">
<td>Plats</td>
<td>Ändra den plats som komponentträdet visas för. Standardplatsen är standardlagerplatsen för den färdiga artikeln.</td>
</tr>
<tr class="odd">
<td>Visa princip</td>
<td><p>Välj den versionsvisningsprincip som gäller för den aktuella formelstrukturen och det aktuella flödet:</p>
<ul>
<li>När principen anges som <strong>Aktiv</strong> eller <strong>Vald/aktiv</strong> hittas giltig formel eller flödesversion för detta datum.</li>
<li>När principen anges som <strong>Vald/aktiv</strong> eller <strong>Vald</strong> kan du välja en formel- eller ruttversion genom att klicka på <strong>Formel</strong> &gt; <strong>Formelversioner</strong> eller <strong>Rutt</strong> &gt; <strong>Ruttversioner</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Versionsdatum</td>
<td>Ange versionsdatum för formel och flöde. Versionen identifierar vilken formelversion som används på ett visst datum, baserat på versionsdatumen i inställningen för formelversionen.</td>
</tr>
<tr class="odd">
<td>Från-kvantitet</td>
<td>Filtrera versionerna genom att välja från en viss &quot;från&quot;-kvantitet. Om du ställer in ett värde kan en annan formel och andra flödesversioner markeras.</td>
</tr>
<tr class="even">
<td>Visa bara giltiga</td>
<td>När du markerar kryssrutan visar trädstrukturen bara formelrader som har giltiga datum. Du kan högerklicka eller dubbelklicka en formelrad om du vill öppna sidan <strong>Redigera formelrad</strong>, där du kan visa formelradens giltighetsdatum.</td>
</tr>
</tbody>
</table>

När du använder formeldesignern för att granska eller redigera formler som består av en eller flera nivåer av fiktiva element, omfattar flödet som är kopplat till den översta artikeln vanligtvis hela formelhierarkin. För att förenkla översikten kan du låsa flödet på högsta nivån på skärmen genom att klicka på **Visa** &gt; **Lås flöde**. Om du vill låsa upp flödet, klicka på **Visa** &gt; **Lås upp flöde**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Lägg till och redigera formler och formelrader
Använd funktionerna **Strukturlisterader** eller **Formel** för att ändra formelraderna eller formeln. När du väljer en nod i trädet, bestämmer nodtypen vilka funktioner som är tillgängliga.

| Funktion                            | beskrivning                                                                                               | Nodtyp och -villkor |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Strukturlisterader &gt; Redigera                 | Öppna en dialogruta där du kan redigera attributen för formelrad.                                         | Den här funktionen finns bara när en nod för formelrad har valts. |
| Strukturlisterader &gt; Radera               | Ta bort en formelrad från den valda formeln.                                                          | Den här funktionen finns bara när en nod för formelrad har valt och formeln inte har låsts för redigering. |
| Strukturlisterader &gt; Lägg till före rad      | Öppna en dialogruta där du kan välja en produktvariant att inkludera före den valda formelraden.     | Den här funktionen finns bara när en nod för formelrad har valts. |
| Strukturlisterader &gt; Lägg till i komponentstrukturlista | Öppna en dialogruta där du kan välja en produktvariant att inkludera i slutet av den valda formeln.   | Den här funktionen finns bara när noden som har valts har en vald formel. Om denna funktion inte är tillgänglig kan en formelversion saknas för den valda artikelvarianten. I detta fall kan du klicka på **Formel** &gt; **Skapa version** för att skapa den saknade versionen för den valda noden. |
| Strukturlisterader &gt; Lägg till efter rad       | Öppna en dialogruta där du kan välja en produktvariant att inkludera efter den valda formelraden.      | Den här funktionen finns bara när en nod för formelrad har valts. |
| Formel &gt; Skapa version         | Skapa en ny formelversion eller formel för produktvarianten för den valda noden.                     | Den här funktionen finns bara när den valda noden för formelrad kopplas till en artikel som har produktionstypen **Strukturlista** eller **Formel** |
| Formel &gt; Beräkning            | Öppna en dialogruta där du kan köra kostnads- och försäljningprisberäkningen för den valda produktvarianten. | Den här funktionen finns bara när vald nod är relaterad till en formelversion. |
| Formel &gt; Kontroll                  | Validera och kontrollera den valda formeln.                                                                  | Den här funktionen finns bara när vald nod är relaterad till en formelversion. |

## <a name="configuring-the-tree-view"></a>Konfigurera trädvy
Klicka på **Inställningar** om du vill anpassa informationen som visas i trädvyn för formeldesignern.


| Fältgrupp |                                                                          beskrivning                                                                          |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Strukturlista     | Använd kryssrutorna för att välja de kriterier som visas i trädstrukturen. I formeldesignern visas det valda villkoret längst ned på båda flikarna. |
|    Flöde    |                                           Använd kryssrutorna för att välja de kriterier som visas för flödena.                                           |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]