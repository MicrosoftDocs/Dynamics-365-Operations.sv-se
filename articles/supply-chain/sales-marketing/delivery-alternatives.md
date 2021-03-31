---
title: Leveransalternativ
description: Försäljningsordertagare kan använda sidan Leveransalternativ för att upptäcka alternativa orderuppfyllelsealternativ.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 783307ea5cc764f4a04d069dfd7d614a4f63dd2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229265"
---
# <a name="delivery-alternatives"></a>Leveransalternativ

[!include [banner](../includes/banner.md)]

Försäljningsordertagare kan använda sidan **Leveransalternativ** för att upptäcka alternativa orderuppfyllelsealternativ.

Sidlayouten **Leveransalternativ** ger en bättre översikt över alla alternativ. Den gör även att ordertagare kan leta utanför det det aktuella företaget för orderuppfyllelsemöjligheter. De kan nu visa både koncerninterna affärsmöjligheter och affärsmöjligheter från externa leverantörer. Genom sorteringsalternativ per leveransdatum, kan försäljningsordertagare visa en intelligent lista med leveransalternativ. Dessutom hjälper parametrar dem att bättre hantera föreslagna leveranser. Eftersom transporttiden kan påverka leveransdatum, kan försäljningsordertagare utforska de olika transportvalen som transportföretag erbjuder. Eftersom detaljerad information visas för varje förslag kan ordertagare fatta välgrundade beslut direkt från sidan **leveransalternativ**.

## <a name="open-the-delivery-alternatives-page"></a>Öppna sidan leveransalternativ

Du kan öppna sidan **Leveransalternativ** från försäljningsorderraden.

1. Välj **Produkter och leverans \> Leveransalternativ**.
1. Välj **raddetaljer \> leverans \> leveransalternativ.**

Du kan också öppna sidan **leveransalternativ** genom att öppna arbetsytan **försäljningsorderbearbetning och förfrågan** och sedan klicka på **order och favoriter \> försenade orderrader \> leveransalternativ** **Obs!** Du kan endast öppna sidan **leveransalternativ** om båda följande villkor är uppfyllda:

- All obligatorisk försäljningsradinformation fylls i.
- Fältet **Leveransdatumkontroll** anges till ett värde som är annat än **ingen**.

## <a name="delivery-date-control-methods"></a>Kontrollmetoder för leveransdatum

Kontrollmetod för leveransdatum bestämmer hur systemet upprättar leveransdatum, hur leveransalternativ beräknas och vilken information som visas. Observera att leveransdatumkontroll beaktar kalendrar. Därför kan följande kalendrar påverka det förslagna inleveransdatumet: lagerställekalender, transportkalender, leverantörskalender och kundkalender. I följande tabell beskrivs respektive metod för leveransdatumkontroll.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Metod</strong></td>
<td><strong>Beskrivning</strong></td>
</tr>
<tr class="even">
<td><strong>None</strong></td>
<td><ul>
<li>Leveransalternativ för försäljningsrader stöds inte. Det här alternativet inaktiverar leveransdatumkontroll.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Produktionstid för försäljning</strong></td>
<td><ul>
<li>Leveransalternativ beräknas utifrån fördefinierad produktionstid för försäljning. Transportdagar beräknas baserat på leveranssätt.</li>
<li>Leveransalternativ inkluderar lagerställen som har lagerbehållning och tillgång-/efterfrågeorder.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>ATP</strong></td>
<td><ul>
<li>Leveransalternativ beräknas utifrån logiken disponibelt att lova (ATP). Aktuell tillgänglighet och förväntad framtida tillgänglighet kan användas. Transportdagar beräknas baserat på leveranssätt.</li>
<li>Leveransalternativ inkluderar lagerställen som har lagerbehållning och tillgång-/efterfrågeorder.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>ATP + utleveransmarginal</strong></td>
<td><ul>
<li>Leveransalternativ för beräknas för ATP-metoden men utleveransmarginalen tas med i beräkningen.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>Leveransalternativ beräknas utifrån logiken capable to promise (CTP). MPS-nedbrytningen används för att bestämma tillgänglighet. Observera att CTP åtminstone förskjuter leveransdatum till produktionstiden för försäljning. Transportdagar beräknas baserat på leveranssätt.</li>
<li>Leveransalternativ inkluderar förslag för följande lagerställen:
<ul>
<li>Aktuellt lagerställe</li>
<li>Standardlagerställe</li>
<li>Alla lagerställen som har tillgänglig lagerbehållning</li>
<li>Alla lagerställen som har leveransorder</li>
<li>Alla lagerställen som har aktiva strukturlisteversioner</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Visa information om leveransalternativ

Det här avsnittet innehåller information om leveransalternativ som finns på alla snabbflikar på sidan **leveransalternativ**.

### <a name="the-product-fasttab"></a>Snabbfliken produkt

Den här snabbfliken visar en sammanfattning av produkten och information om den aktuella försäljningsraden.

### <a name="the-delivery-alternatives-fasttab"></a>Snabbfliken leveransalternativ

Den här snabbfliken visar en lista med leveransalternativ som sorteras efter inleveransdatum. Du kan välja vilka alternativ som du vill basera förslagen på ovanför listan. Du kan också välja leveranssätt som bestämmer transportdagar. Följande alternativ är tillgängliga:

- **Inkludera andra produktvarianter** - det här alternativet är tillgängligt för produkter som har produktvarianter. Det innehåller leveransalternativ till andra varianter av produkten. Det här alternativet är inte tillgängligt för CTP.
- **Inkludera delkvantitet** - som standard inkluderas endast förslag som uppfyller hela kvantiteten på försäljningsraden. Välj detta alternativ om du vill inkludera förslag som bara delvis uppfyller orderraden. Det här alternativet är användbart när kunden begär ett tidigare leveransdatum och tar emot en delleverans.
- **Inkludera senare datum** - Som standard visas endast förslag som passar bättre (tidigare) än aktuellt datum på försäljningsraden. Välj det här alternativet om du vill inkludera senare datum. Det här alternativet kan vara användbart i situationer där andra parametrar än datumet har prioritet. En viss leverantör eller lagerställe kan exempelvis prioriteras.
- **Leveranssätt** - Välj föredraget leveranssätt för att optimera transporttiden och kostnader. Du kommer ommedelbart att se effekten av föreslagna leveransalternativ. Därför är det enkelt att jämföra alternativen.
- **Inkludera anskaffning** - när upphandling väljs föreslagna leverans alternativ innehåller alternativ för att anskaffa både från externa leverantörer och andra företag inom företaget (koncernintern). Alternativet **Inkludera anskaffning** stöds för för ATP och ATP + leveransdatumkontroll för utleveransmarginal. Anskaffningsalternativ från standardinköpsleverantören för produkten och alla godkända leverantörer för produkten ingår.
- Beräkningen baseras på inköpsproduktionstiden för externa leverantörer.
- För koncerninterna beaktar beräkningen vad som finns tillgängligt från källföretaget utifrån leveransdatumkontroll i företaget källa.
- **Leveranstypen** (relevant för inköp)
  - **Lager** - produkter levereras från lagerkälla till plats/lagerstället på försäljningsraden. De har levererats från detta lagerställe till kunden.
  - **Direktleverans** - produkter levereras direkt från lagerställets källa till kunden.

### <a name="the-availability-information-fasttab"></a>Snabbfliken Tillgänglighetsinformation

Information om denna snabbflik som rör den valda leveransalternativraden. Följande information visas beroende på Leveransdatumkontroll för försäljningsraden:

- **Produktionstid för försäljning**
  - **Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.
  - **Parametrar** - visar lagerenhet och produktionstid för försäljning.

- **ATP and ATP + Utleveransmarginal**
  - **Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.
  - **Parametrar** - visar lagerenhet och produktionstid för försäljning.
  - **Framtida tillgänglighet** – visar en grafisk representation av nuvarande och framtida tillgänglighet för den valda siten och lagerstället **alternativ leverans**. Om du klickar på kolumnerna i diagrammet får du mer detaljerad information om produktens framtida tillgänglighet. Bilden visar en lista över relevanta efterfråge- och leveransorder inom tidsgränsen för ATP.

- **CTP**
  - **Tillgänglig just nu** - visa den aktuella fysiska lagerbehållningen och tillgängligt fysiskt lager.
  - **Parametrar** - visar lagerenhet och produktionstid för försäljning.
  - **Nedbrytning** - visar leveransnedbrytning av den valda leveransen. Du kan använda **inställningar** för att ändra fälten och lagerdimensioner som ska visas i nedbrytningen.

### <a name="the-impact-of-selected-alternative-fasttab"></a>Snabbfliken Effekten av valt alternativ

Den här snabbfliken markerar effekten av valt alternativ. Om du klickar på **OK**, uppdateras försäljningsraden med de markerade värdena i markerade kolumner. Observera att, om kvantiteten på valt alternativ är mindre än kvantiteten på försäljningsraden har en leveransplan skapats och orderraden delas upp på två rader: en rad för den valda kvantiteten och en rad för den återstående kvantiteten. Du kan också uppdatera den kommersiella raden så att den matchar planens rader och påverkar priserna.

## <a name="additional-resources"></a>Ytterligare resurser

[Orderlöfte](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]