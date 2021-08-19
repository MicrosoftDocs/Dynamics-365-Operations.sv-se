---
title: Kvalitetsassociationer
description: I detta ämne beskrivs hur du kan använda kvalitetsassociationer i Microsoft Dynamics 365 Supply Chain Management för att automatiskt generera kvalitetsorder som hör till dina försäljnings-, inköps- och produktionsprocesser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0705af8f8c40db82e412f294f45f704b7a628c1ced679cef25ce77d49642feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724854"
---
# <a name="quality-associations"></a>Kvalitetsassociationer

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du kan använda kvalitetsassociationer i Microsoft Dynamics 365 Supply Chain Management för att automatiskt generera kvalitetsorder som hör till dina försäljnings-, inköps- och produktionsprocesser.

En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:

- Transaktionshändelsen
- Uppsättningen med tester som måste utföras på artiklarna
- Godtagbar kvalitetsnivå (AQL)
- Samplingsplanen

Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder. En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.

## <a name="working-with-quality-associations"></a>Arbeta med kvalitetsassociationer

Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.

Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder. Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess. Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras. Beroende på hur körningsplanen har ställts in kan själva utlösarprocessen spärras när det finns en öppen kvalitetsorder. Efterföljande processer, såsom inköpsorderfakturering, kan också spärras.

> [!NOTE]
> Även om det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utfärdas. Beroende på inställningen för fältet **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden. Mer information finns i [Artikelsampling för kvalitetshantering](quality-item-sampling.md).

För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och de villkor som en kvalitetsorder genereras för. Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person. En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.

Om du vill arbeta med kvalitetsassociationer går du till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsassociationer**. Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i respektive affärsprocess. För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.

<table>
<thead>
<tr>
<th>Referenstyp</th>
<th>Händelsetyp</th>
<th>Körning</th>
<th>Händelsespärr</th>
<th>Dokumentreferens</th>
</tr>
</thead>
<tbody>
<tr>
<td>Lager</td>
<td>Inte tillämpligt</td>
<td>Inte tillämpligt</td>
<td>Ingen</td>
<td>Alla</td>
</tr>
<tr>
<td rowspan="7">Försäljning</td>
<td rowspan="4">Plockningsprocess har schemalagts</td>
<td rowspan="4">Före</td>
<td>Ingen</td>
<td rowspan="22">Specifikt ID, Grupp eller Alla</td>
</tr>
<tr>
<td>Plockningsprocess</td>
</tr>
<tr>
<td>Följesedel</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Följesedel</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Följesedel</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="15">Inköp</td>
<td rowspan="7">Inleveranslista</td>
<td rowspan="4">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Inleveranslista</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Registrering</td>
<td rowspan="3">Inte tillämpligt</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="5">Produktinleverans</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="2">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="8">Produktion</td>
<td rowspan="3">Registrering</td>
<td rowspan="3">Inte tillämpligt</td>
<td>Ingen</td>
<td rowspan="12">Alla</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="5">Rapportera som färdig</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="2">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="4">Karantän</td>
<td rowspan="3">Rapportera som färdig</td>
<td rowspan="2">Före</td>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td>Efter</td>
<td>Slut</td>
</tr>
<tr>
<td>Slut</td>
<td>Före</td>
<td>Slut</td>
</tr>
<tr>
<td rowspan="3">Flödesoperation</td>
<td rowspan="3">Rapportera som färdig</td>
<td rowspan="2">Före</td>
<td>None</td>
<td rowspan="3">Specifikt ID, Grupp eller Alla samt Specifik resurs, Grupp eller Alla</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Efter</td>
<td>None</td>
</tr>
<tr>
<td rowspan="3">Produktion av samprodukt</td>
<td>Registrering</td>
<td>Inte aktuellt</td>
<td rowspan="3">None</td>
<td rowspan="3">Allt</td>
</tr>
<tr>
<td rowspan="2">Rapportera som färdig</td>
<td>Före</td>
</tr>
<tr>
<td>Efter</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Funktionen *Kvalitetshantering för lagerprocesser* tillsätter funktioner för bearbetning av kvalitetsorder för produktion där fältet **Händelsetyp** är inställt på *Rapportera som färdig* och fältet **Körning** inställt på *Efter*, samt för köp där fältet **Händelsetyp** är inställt på *Registrering*. Mer information finns i [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).

Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Typ av process</th>
<th>När kvalitetsorder kan genereras automatiskt</th>
<th>När kvalitetsorder kan genereras om det krävs destruktivt test</th>
<th>Villkorsinformation</th>
<th>Information om manuell generering</th>
</tr>
</thead>
<tbody>
<tr>
<td>Inköpsorder</td>
<td>Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</td>
<td>Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</td>
<td>Behovet av en kvalitetsorder kan återspegla en specifik, artikel eller leverantör, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Karantänorder</td>
<td>Före eller efter att karantänordern rapporteras som färdig eller avslutad</td>
<td>Kvalitetsorder som kräver destruktiva tester kan inte genereras. Det antas att funktionen för karantänorder hanterar dispositionen av materialet som förstörs.</td>
<td>Behovet av en kvalitetsorder kan återspegla en specifik, artikel eller leverantör, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Försäljningsorder</td>
<td>Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</td>
<td>I ett obestämt steg</td>
<td>Behovet av en kvalitetsorder kan återspegla en specifik plats, artikel eller kund, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Produktionsorder</td>
<td>Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</td>
<td>Efter att den fullständiga kvantiteten för produktionsordern rapporteras</td>
<td>Behovet av en kvalitetsorder kan återspegla en specifik plats eller artikel, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Produktionsorder som har en flödesoperation</td>
<td>Före eller efter att rapporten är färdig för en åtgärd</td>
<td>Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</td>
<td>Behovet av en kvalitetsorder kan återspegla en specifik plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Lager</td>
<td>En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</td>
<td></td>
<td></td>
<td>En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet. Fysisk lagerbehållning krävs.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exempel på automatisk generering av kvalitetsorder

### <a name="purchasing"></a>Inköp

I inköp, om du ställer in fältet **händelsetyp** till *produktinleverans* och fältet **körning** till *efter* på sidan **kvalitetsassociationer**, får du följande resultat:

- Om alternativet **per uppdaterad kvantitet** är inställt på *Ja*, genereras en kvalitetsorder för varje inleverans mot inköpsordern, baserat på inlevererad kvantitet och inställningar i artikelsampling. Varje gång en kvantitet inlevereras mot inköpsordern genereras nya kvalitetsorder utifrån den nylevererade kvantiteten.
- Om alternativet **per uppdaterad kvantitet** är inställt på *Nej*, genereras en kvalitetsorder för första inleveransen mot inköpsordern, baserat på inlevererad kvantitet. Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna. Kvalitetsorder genereras inte för efterföljande inleveranser mot inköpsordern.

### <a name="production"></a>Produktion

I produktion, om du ställer in fältet **händelsetyp** till *Rapportera som slutförd* och fältet **körning** till *efter* på sidan **kvalitetsassociationer**, får du följande resultat:

- Om alternativet **per uppdaterad kvantitet** är inställt på *Ja*, genereras en kvalitetsorder för varje slutförd kvantitet och inställningar i artikelsampling. Varje gång en kvantitet rapporteras som slutförd mot produktionsorden genereras nya kvalitetsorder utifrån den nyligen avslutade kvantiteten. Denna generations logik är förenlig med inköp.
- Om alternativet **Per uppdaterad kvantitet** anges till *Nej*, genereras en kvalitetsorder första gången som en kvantitet rapporteras som färdig, baserat på den färdiga kvantiteten. Dessutom skapas en eller flera kvalitetsorder utifrån den återstående kvantiteten, beroende på spårningsdimensionerna av artikelsampling. Kvalitetsorder genereras inte för senare färdiga kvantiteter.

<table>
<thead>
<tr>
<th>Kvantitetsspecifikation</th>
<th>Per uppdaterad kvantitet</th>
<th>Per spårningsdimension</th>
<th>Resultat</th>
</tr>
</thead>
<tbody>
<tr>
<td>Procent: 10 %</td>
<td>Ja</td>
<td>
<p>Batchnummer: Nej</p>
<p>Serienummer: Nej</p>
</td>
<td>
<p>Orderkvantitet: 100</p>
<ol>
<li>Rapportera som slutförd för 30
<ul>
<li>Kvalitetsorder 1 för 3 (10 % av 30)</li>
</ul>
</li>
<li>Rapportera som slutförd för 70
<ul>
<li>Kvalitetsorder 2 för 7 (10 % av det resterande orderkvantiteten, vilket i det här fallet är lika med 70)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Fast kvantitet: 1</td>
<td>Nr</td>
<td>
<p>Batchnummer: Nej</p>
<p>Serienummer: Nej</p>
</td>
<td>Orderkvantitet: 100
<ol>
<li>Rapportera som slutförd för 30
<ul>
<li>Kvalitetsorder 1 för 1 (för den första kvantiteten som rapporteras som färdig, som har ett fast värde på 1)</li>
<li>Kvalitetsorder 2 för 1 (för den återstående kvantiteten som fortfarande har ett fast värde på 1)</li>
</ul>
</li>
<li>Rapportera som slutförd för 10
<ul>
<li>Inga kvalitetsorder skapas.</li>
</ul>
</li>
<li>Rapportera som slutförd för 60
<ul>
<li>Inga kvalitetsorder skapas.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Fast kvantitet: 1</td>
<td>Ja</td>
<td>
<p>Batch-nummer: Ja</p>
<p>Serienummer: Ja</p>
</td>
<td>
<p>Orderkvantitet: 10</p>
<ol>
<li>Rapportera som färdig för 3:1 för batchnummer b1, serienummer s1; 1 för batchnummer b2, serienummer s2; samt 1 för batchnummer b3, serienummer s3
<ul>
<li>Kvalitetsorder 1 för 1 av batchnummer b1, serienummer s1</li>
<li>Kvalitetsorder 2 för 1 av batchnummer b2, serienummer s2</li>
<li>Kvalitetsorder 3 för 1 av batchnummer b3, serienummer s3</li>
</ul>
</li>
<li>Rapportera som färdig för 2:1 för batchnummer b4, serienummer s4; och 1 för batchnummer b5, serienummer s5
<ul>
<li>Kvalitetsorder 4 för 1 av batchnummer b4, serienummer s4</li>
<li>Kvalitetsorder 5 för 1 av batchnummer b5, serienummer s5</li>
</ul>
</li>
</ol>
<p><strong>Obs!</strong> batchen kan återanvändas.</p>
</td>
</tr>
<tr>
<td>Fast kvantitet: 2</td>
<td>Nr</td>
<td>
<p>Batch-nummer: Ja</p>
<p>Serienummer: Ja</p>
</td>
<td>
<p>Orderkvantitet: 10</p>
<ol>
<li>Rapportera som färdig för 4:1 för batchnummer b1, serienummer s1; 1 för batchnummer b2, serienummer s2; 1 för batchnummer b3, serienummer s3; samt 1 för batchnummer b4, serienummer s4
<ul>
<li>Kvalitetsorder 1 för 1 av batchnummer b1, serienummer s1</li>
<li>Kvalitetsorder 2 för 1 av batchnummer b2, serienummer s2</li>
<li>Kvalitetsorder 3 för 1 av batchnummer b3, serienummer s3</li>
<li>Kvalitetsorder 4 för 1 av batchnummer b4, serienummer s4</li>
</ul>
<ul>
<li>Kvalitetsorder 5 för 2, utan referens till ett batch- och ett serienummer</li>
</ul>
</li>
<li>Rapportera som färdig för 6:1 för batchnummer b5, serienummer s5; 1 för batchnummer b6, serienummer s6; 1 för batchnummer b7, serienummer s7; 1 för batchnummer b8, serienummer s8; 1 för batchnummer b9, serienummer s9; och 1 för batchnummer b10, serienummer s10
<ul>
<li>Inga kvalitetsorder skapas.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshanteringsprocesser](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
