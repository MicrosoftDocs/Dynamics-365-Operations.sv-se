---
title: "Översikt över produktkonfigurationsmodeller"
description: "I den här artikeln definieras termer och begrepp som avser produktkonfigurationsmodeller. Med produktkonfigurationsmodeller kan du bygga en allmän produktstruktur som kan användas för att konfigurera många produktvarianter för en och samma produkt."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 64f0a9a44b97a9980f8d1b76ff158f1ac9cbc114
ms.openlocfilehash: 6b896c28f475a8f827a1db1b6dd684b6ec64e872
ms.contentlocale: sv-se
ms.lasthandoff: 11/15/2017

---

# <a name="product-configuration-models-overview"></a>Översikt över produktkonfigurationsmodeller

[!include[banner](../includes/banner.md)]


I den här artikeln definieras termer och begrepp som avser produktkonfigurationsmodeller. Med produktkonfigurationsmodeller kan du bygga en allmän produktstruktur som kan användas för att konfigurera många produktvarianter för en och samma produkt.

Modeller för produktkonfiguration skapas för att representera en struktur för den allmänna produkt. När du har ställt in en modell för produktkonfiguration kan du konfigurera en viss produktvariant som har en unik strukturlista (BOM) och ett unikt flöde. Modeller för produktkonfiguration använder både deklarativa begränsningar och absolut nödvändiga beräkningar för att hantera relationerna och begränsningarna mellan olika produktvarianter. Du kan konfigurera artiklar på försäljningsorder, försäljningsofferter, inköpsorder och tillverkningsorder. I tabellen nedan beskrivs de registerbegränsningsbaserade villkoren och koncepten.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Komponenter</td>
<td>Komponenterna är huvudbyggnadblocken av en modell för produktkonfiguration. Komponenter visas i en trädstruktur på sidan <strong>Detaljer för begränsningsbaserad produktkonfigurationsmodell</strong>. Komponenter kan innehålla följande element:
<ul>
<li>Attribut</li>
<li>Begränsningar</li>
<li>Beräkningar</li>
<li>Delkomponenter</li>
<li>Användarbehov</li>
<li>Strukturlisterader</li>
<li>Flödesoperationer</li>
</ul></td>
</tr>
<tr class="even">
<td>Attribut</td>
<td>Attribut beskriver alla funktioner för modellen för produktkonfiguration. Du kan använda attribut om du vill ange de funktioner som kan väljas, när en specifik produkt som konfigureras. Attribut används i begränsningar och villkor. När attribut skapas och läggs till en modell för produktkonfiguration, refereras till de relaterade attributtyperna. Ett standardvärde kan anges för ett attribut. Standardvärdet används i konfigurationanvändargränssnittet (UI), när modellen för produktkonfiguration konfigureras. Du kan ange att ett attribut är obligatoriskt, skrivskyddat, eller dolt.
<ul>
<li><strong>Obligatorisk</strong> – Ett värde måste anges för attribut, när produkten konfigureras.</li>
<li><strong>Skrivskyddad</strong> – Attributvärdet visas under en konfigurationssession, men kan inte ändras.</li>
<li><strong>Gömt</strong> – Attributvärdet ingår i begränsningar och kriterier, men visas inte under en konfigurationssession.</li>
</ul>
Du kan även ange ett villkor för attribut. Om villkoret uppfylls, måste ett värde angetts för obligatoriska attribut. Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration. Alla attribut som refereras i ett villkor, blir obligatorisk. Vi rekommenderar att du väljer attribut som är obligatoriska i fliken <strong>Attribut</strong>. Detta kan göra det enklare att identifiera obligatoriska attribut. Attributvärden är en viktig del av du vill återanvända konfigurationer. Attributvärden används för att fastställer om en konfiguration finns, som matchar val som en användare har gjort under en konfigurationssession.</td>
</tr>
<tr class="odd">
<td>Attributtyper</td>
<td>Attributtyper anger de uppsättning datatyper för attribut som används i en modell för produktkonfiguration. Följande attributtyper används:
<ul>
<li><strong>Heltal</strong> med eller utan ett intervall</li>
<li><strong>Decimal</strong></li>
<li><strong>Text</strong> med eller utan en fast lista</li>
<li><strong>Boolesk</strong></li>
</ul>
Om attributtypen är <strong>Booleskt</strong>, <strong>Heltal</strong> med ett intervall, eller <strong>Text</strong> med en fast lista är uppsättning värden tillgänglig när en modell för produktkonfiguration ställs in. <strong>Obs!</strong> Produktkonfigurationslösaren känner bara igen följande attributtyper: <strong>Booelskt</strong>, <strong>Text</strong> med en fast lista och <strong>Heltal</strong> med ett intervall. Därför kan endast dessa attributtyper användas i uttryckbegränsningar och villkor.</td>
</tr>
<tr class="even">
<td>Begränsningar</td>
<td>Begränsningar beskriver begränsningarna i produktmodellkonfigurationen. Begränsningar används för att garantera att endast giltiga värden väljs när en produkt konfigureras. Det kan antingen vara uttryckbegränsningar eller registret begränsningar:
<ul>
<li>Uttryckbegränsningar kan bara användas för komponenten att de är kopplat till. Uttryckbegränsningarna för en komponent kan referera till attribut i komponentens delkomponenter. Produktkonfigurationslösaren används för att lösa begränsningar, och du måste använda lösarens syntax när du skriver begränsningarna. Mer information finns på avsnittslänken om uttrycksbegränsningar och registerbegränsningar.</li>
<li>Registerbegränsningar måste definieras innan de kan användas på en komponent i en produktkonfigurationsmodell. Registerbegränsningar kan vara antingen användardefinierade eller systemdefinierade. En användardefinierad registerbegränsning är en sorts matris som kan användas för att beskriva uppsättningen kombinationer vilka definieras av attributtyper. Om till exempel högtalare tillverkas kan matrisen för en användardefinierad registerbegränsning ha kolumner för högtalarens finish och högtalargallret.</li>
</ul>
<strong>Exempel</strong> Högtalarna är tillgängliga i fyra varianter: Svart, Ek, och Rosenträ och Vitt. Högtalarna kan ha ett av tre främre galler: svart, metall eller vitt. Svart finish är tillgänglig för alla galler och andra ytbehandlingar begränsas till vissa galler. Följande tabell visar ett exempel på informationen som visas på fliken <strong>Tillåtna kombinationer</strong> på sidan <strong>Redigera registerbegränsning</strong>.
<table>
<thead>
<tr class="header">
<th>Kabinettfinish</th>
<th>Frontgaller</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Svart</td>
<td>Svart</td>
</tr>
<tr class="even">
<td>Svart</td>
<td>Metall</td>
</tr>
<tr class="odd">
<td>Svart</td>
<td>Vit</td>
</tr>
<tr class="even">
<td>Ek</td>
<td>Svart</td>
</tr>
<tr class="odd">
<td>Rosenträ</td>
<td>Vit</td>
</tr>
<tr class="even">
<td>Vit</td>
<td>Svart</td>
</tr>
<tr class="odd">
<td>Vit</td>
<td>Vit</td>
</tr>
</tbody>
</table>
En systemdefinierad registerbegränsning representerar en koppling mellan en attributtyp och ett fält i ett Finance and Operations-register. Systemdefinierade registerbegränsningar kopplar dynamiskt attributtypen till fältet. Länken gör att attributet i en produktkonfigurationsmodell återspeglar data i fältet i Finance and Operations-registret.</td>
</tr>
<tr class="odd">
<td>Beräkningar</td>
<td>Beräkningar representerar ett tillägg till begränsningar. Du kan använda en beräkning för att utföra aritmetiska operationer på attribut av typen <strong>Decimal</strong> och <strong>Heltal</strong>, eller logiska operationer som gäller attribut av typen <strong>Text</strong> med en fast lista eller <strong>Booleskt</strong>. En beräkning har ett målattribut som ska innehålla resultatet av beräkningsuttrycket. Du bygger beräkningsuttrycket med hjälp av uttrycksredigeraren.</td>
</tr>
<tr class="even">
<td>Delkomponenter</td>
<td>Delkomponenter återspeglar trädstrukturen för den modell som produktkonfiguration. Du kan använda delkomponenter för att skapa strukturen för modellen för produktkonfiguration. Delkomponenter refererar till befintliga komponenter. Därför främjar delkomponenter återanvändningen av komponenter i flera modeller för produktkonfiguration. På sidan <strong>Information för strukturlisterad</strong> för en delkomponent kan du välja ett annat värde för delkomponenten. Alternativt kan du välja ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in. Om du vill ta med en produkt som en komponent eller delkomponent måste du ange följande på sidan <strong>Skapa produkt</strong> när du skapar produkten:
<ul>
<li>Välj <strong>Artikel</strong> i fältet <strong>Produkttyp</strong>.</li>
<li>I fältet <strong>Delprodukttyp</strong> väljer du <strong>Produkthuvud</strong>.</li>
<li>I fältet <strong>Konfigurationsteknik</strong> väljer du <strong>Begränsningsbaserad konfiguration</strong>.</li>
</ul>
Du kan visa om en frisläppt produkt kan användas som en komponent eller delkomponent på fliken <strong>Allmänt</strong> på sidan <strong>Information om frisläppt produkt</strong>. Om <strong>Begränsningsbaserad konfiguration</strong> valts i fältet <strong>Konfigurationsteknik</strong> kan produkten användas som en komponent eller delkomponent. Du kan dölja delkomponenter så att de inte visas för användaren under en konfigurationssession. Attribut, delkomponenter och användarkrav, som gäller delkomponenten, döljs också.</td>
</tr>
<tr class="odd">
<td>Användarbehov</td>
<td>Användarkrav representerar en abstraktion mellan användarkrav och specifika komponenter och attribut. Du kan inte koppla ett användarkrav till en artikel. Till exempel en kund shoppar för ett hemmabiosystem. Försäljaren kanske ber om storleken på platsen där kund planerar att installera systemet, som bestämmer hur många watt krävs. I det här exemplet platsstorleken kan vara en användarkrav som hjälper bestämma lämpligt attributvärdet för en viss komponent. Du kan dölja användarkrav, så att de inte visas för användaren under en konfigurationssession. Attribut, delkomponenter och användarkrav, som gäller användarkrav, döljs också. Du kan ange ett villkor för att kontrollera om en användarkrav kan döljas. Du måste ange villkoret med hjälp av OML-syntaxen (Optimization Modeling Language).</td>
</tr>
<tr class="even">
<td>Strukturlisterader</td>
<td>Strukturlisterader representerar de enskilda materialen av komponenterna i modellen för produktkonfiguration. På sidan <strong>Information för strukturlisterad</strong> är alla artiklar tillgängliga för val. Ett villkor kan läggas till på strukturlisteraden, så att strukturlisteraderna som väljs för en viss produktvariant kan variera, baserat på användarens val när modellen för produktkonfiguration ställs in. Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration. På sidan <strong>Information för strukturlisterad</strong> kan du välja ett annat värde. Alternativt kan du koppla ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in.</td>
</tr>
<tr class="odd">
<td>Flödesoperationer</td>
<td>På sidan <strong>Flödesoperationsinformation</strong> kan du välja ett annat värde. Alternativt kan du koppla ett attribut som värdet väljs för när modellen för produktkonfiguration ställs in. Villkor skrivs som uttryckbegränsningar. Villkor är uttryck som måste uppfyllas för att attribut, strukturlisterader och flödesoperationer ska inkluderas i en modell för produktkonfiguration.</td>
</tr>
</tbody>
</table>






