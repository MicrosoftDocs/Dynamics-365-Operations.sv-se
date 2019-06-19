---
title: Omvänd moms
description: Det här avsnittet beskriver hur du ställer in omvänd moms (VAT) för europeiska länder och Saudiarabien.
author: epodkolz
manager: AnnBe
ms.date: 04/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 26f7f3f11408cac387c58a5345b566ac50ed426f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571177"
---
# <a name="reverse-charge-vat"></a>Omvänd moms


[!include [banner](../includes/banner.md)]


Det här avsnittet beskriver en allmän metod för att ställa in omvänd moms (VAT) för Saudiarabien och europeiska länder.

Omvänd moms är ett skatteschema som har ansvaret för redovisning och rapportering av moms från säljaren till köparen av varor eller tjänster. Därför rapporterar mottagaren av varor eller tjänster både utgående moms (i rollen som säljare) och ingående moms (i rollen som inköpare) i deras momsrapport.

I vissa länder används omvänt momsschema endast för vissa varor eller tjänster och det finns ytterligare villkor eller tröskelvärden för försäljningsbelopp. I andra länder eller region beror ansvaret för momsbetalning på status för leverantören och köparen. Om köparen är skyldig att betala moms anges detta klart på fakturan som leverantören utfärdar. Fakturan måste t.ex. innehålla orden ”omvänd moms” och ange vilka befattningar som är under omvänt momsschema. 

Du måste utföra följande inställningar om du vill använda omvänd moms.

## <a name="set-up-sales-tax-codes"></a>Ställ in momskoder
Vi rekommenderar att du använder olika momskoder för försäljning och inköp.

<table>
<body>
<tr>
<td><strong>Momskoder för försäljning</strong></td>
<td>Skapa en momskod för försäljningsoperationer med omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momskoder</strong>).
</td>
</tr>
<tr>
<td><strong>Momskoder för inköp</strong></td>
<td><p>Skapa positiva och negativa momskoder för omvänd moms för inköp (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momskoder</strong>).</p>
<ol>
<li>Skapa en momskod som har ett positivt värde.</li>
<li>Skapa en momskod som har ett negativt värde. Ange alternativet <strong>Tillåt negativ momsprocent</strong> till <strong>Ja</strong>.
Den måste tilldela denna negativa momskod till en artikelmomsgrupp, och därefter tilldelar du artikelmomsgruppen till de artiklar som omvänd moms tillämpas för.</li>
</ol>
<p>Mer information om &quot;Ange momsgrupper och artikelmomsgrupper&quot; finns i nästa avsnitt.</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Ställ in momsgrupper och artikelmomsgrupper
Vi rekommenderar att du använder olika momsgrupper för försäljning och inköp.

<table>
<tr>
<td><strong>Momsgrupper för försäljning</strong></td>
<td>Skapa en momsgrupp för försäljningsoperationer som har omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momsgrupper</strong>). På fliken <strong>inställningar</strong>, inkludera momskoden för omvänd moms i den här gruppen. Markera kryssrutorna <strong>undanta</strong> och <strong>omvänd moms</strong> för momskoden.</td>
</tr>
<tr>
<td><strong>Momsgrupper för inköp</strong></td>
<td>Skapa en momsgrupp för inköpsoperationer som har omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momsgrupper</strong>). På fliken <strong>inställningar</strong>, inkluderar du både positiva och negativa momskoder i den här gruppen. Markera kryssrutan <strong>omvänd moms</strong> för momskoden som har ett negativt värde.</td>
</tr>
<tr>
<td><strong>Artikelmomsgrupper</strong></td>
<td>Skapa eller uppdatera artikelmomsgrupp med momskoder som har ett negativt värde (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Artikelmomsgrupper</strong>). Du måste tilldela standardartikelmomsgruppen till produkterna och kategoriera som är föremål för omvänd moms.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Ställ in information för omvända momsgrupper
På sidan omvänd momsartikelgrupper **Artikelgrupper för återfört tillägg** (**Moms** &gt; **Inställningar** &gt; **Moms** &gt; **Artikelgrupper för återfört tillägg**), kan du definiera grupper av produkter eller tjänster, eller enskilda produkter eller tjänster som omvänd moms kan tillämpas på. Definiera listan med artiklar, artikelgrupper och kategorier för försäljning och inköp för varje artikelgrupp för omvänd moms.

## <a name="set-up-reverse-charge-rules"></a>Ställ in regler för omvänd moms
På sidan **Regler för återfört tillägg** (**Skatt** &gt; **Inställningar** &gt; **Moms** &gt; **Regler för återfört tillägg**), kan du definiera tillämpningsreglerna för inköp och försäljning. Du kan konfigurera en uppställning med regler för omvänd moms. För varje regel anger du följande fält:

- **Dokumenttyp** – Välj **inköpsorder**, **leverantörsfakturajournal**, **försäljningsorder**, **fritextfaktura**, **Kundfakturajournal**, och/eller **leverantörsfakturan**.
- **Partnerns land/regions-typ** – Välj **lokal**, **EU**, eller **utländsk**. Alternativt om regeln kan kopplas till alla handelspartner oavsett land eller region för adressen kan du välja **alla**.
- **Lokal leveransadress** – Markera den här kryssrutan om du vill använda regeln för leveranser inom samma land eller region. Den här kryssrutan kan inte väljas för dokumenttyperna **leverantörsfakturajournal** och **Kundfakturajournal**.
- **Artikelgrupp för omvänd moms** – Välj den grupp som regeln kan tillämpas på.
- **Tröskelbelopp** – används endast i schemat för omvänd moms till en faktura om värdet på artiklarna eller tjänsterna som ingår i artikelgruppen för omvänd moms överskrider den gräns som du anger här.

Du kan även använda fälten **giltighetsdatum** och **förfallodatum** för att anger perioden då regeln ska gälla.

Du kan också ange om ett meddelande visas och dokumentraden uppdateras med momsgrupp för omvänd moms om villkoret för den dokumentraden uppfylls. Följande alternativ är tillgängliga:

- **Ingen** – dokumentraden uppdateras inte.
- **Fråga** – ett meddelande visas som bekräftar att omvänd moms kan användas.
- **Ange** – dokumentraden uppdateras utan meddelande.

## <a name="set-up-default-parameters"></a>Ställ in standardparametrar
Om du vill aktivera funktionen för återföring av moms på sidan **allmänna redovisningsparametrar** på fliken **omvänd moms** anger du alternativet **aktivera omvänd moms** till **Ja**. I fälten **Momsgrupp för inköpsorder** och **Momsgrupp för försäljningsorder** väljer du standardmomsgrupper. När villkoren för omvänd moms uppfylls kommer försäljnings- eller inköpsordern att uppdateras med de här momsgrupperna.

## <a name="reverse-charge-on-a-sales-invoice"></a>Omvänd moms på en försäljningsfaktura
För försäljningen under schema för omvänd moms debiterar inte säljaren moms. Istället indikerar fakturan både artiklarna för vilka momsen ska återföras och det totala beloppet för den återförda momsen noteras på fakturan.

När en försäljningsfaktura bokförs med omvänd momstransaktion har kryssrutorna **Momsskuld** momsriktning och nollmom och **omvänd moms** markerats.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Omvänd moms på en inköpsfaktura
För inköpare under schemat omvänd moms agerar inköparen som tar emot fakturan som har omvänd moms som en köpare och säljare för redovisningsändamål.

När en inköpsfaktura med omvänd moms bokförs, skapas två momstransaktioner. En transaktion har skatteriktningen **Momsfordran**. Den andra transaktionen har skatteriktningen **Momsskuld** och kryssrutan **omvänd moms** är markerad.

I följande skärmbild har en transaktion riktningen **Momsfordran** och den andra transaktionen har riktningen **Momsskuld**. 

![Bokförd moms](media/apac-sau-posted-sales-tax.png)
