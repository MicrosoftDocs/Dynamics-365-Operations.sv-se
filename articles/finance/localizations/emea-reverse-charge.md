---
title: Mekanism för omvänd moms för moms/GST-schema
description: Det här avsnittet beskriver hur du ställer in omvänd moms (VAT) för europeiska länder, Saudiarabien och Singapore.
author: epodkolz
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 46b26fc1c0c45be894e226080a5aa9d5ae48b595
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006001"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Mekanism för omvänd moms för moms/GST-schema

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs ett allmänt tillvägagångssätt för att ställa in funktioner för omvänd moms för länder/regioner som har moms- eller GST-scheman.
                                                                                 
Land/regiontillgänglighet för funktionen hanteras av följande funktioner på arbetsytan **Funktionshantering**.

| Funktion                                              | Land/region                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ingen specifik funktion                                | Österrike </br>Belgien </br>Bulgarien </br>Kroatien </br>Cypern </br>Tjeckien </br>Danmark  </br>Estland  </br>Finland  </br>Frankrike  </br>Tyskland  </br>Ungern  </br>Island  </br>Irland  </br>Italien  </br>Lettland  </br>Liechtenstein  </br>Litauen  </br>Luxemburg  </br>Nederländerna  </br>Norge Polen </br>Portugal </br>Rumänien  </br>Saudiarabien </br>Singapore  </br>Slovakien  </br>Slovenien  </br>Spanien  </br>Sverige  </br>Schweiz  </br>Storbritannien  </br>Förenade Arabemiraten |
| Omvänd moms för ytterligare länder            | Bahrain  </br>Kuwait  </br>Oman  </br>Qatar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Aktivera mekanismen för omvänd moms för moms/GST-schema | Alla andra länder/regioner utom:  </br>Brasilien  </br>Indien  </br>Ryssland                                                                                                                                                                                                                                                                                                                                                                                         |
 
 Mer information finns i [Aktivera mekanismen för omvänd moms för moms/GST-schema](#enable-reverse-charge) senare i det här avsnittet.

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

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Ställ in momsgrupper och artikelmomsgrupper
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

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Ställ in artikelgrupper för omvänd moms
På sidan omvänd momsartikelgrupper **Artikelgrupper för återfört tillägg** (**Moms** &gt; **Inställningar** &gt; **Moms** &gt; **Artikelgrupper för återfört tillägg**), kan du definiera grupper av produkter eller tjänster, eller enskilda produkter eller tjänster som omvänd moms kan tillämpas på. Definiera listan med artiklar, artikelgrupper och kategorier för försäljning och inköp för varje artikelgrupp för omvänd moms.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Ställ in regler för omvänd moms
På sidan **Regler för återfört tillägg** (**Skatt** &gt; **Inställningar** &gt; **Moms** &gt; **Regler för återfört tillägg**), kan du definiera tillämpningsreglerna för inköp och försäljning. Du kan konfigurera en uppställning med regler för omvänd moms. För varje regel anger du följande fält:

- **Dokumenttyp** – Välj **inköpsorder**, **leverantörsfakturajournal**, **försäljningsorder**, **fritextfaktura**, **Kundfakturajournal**, och/eller **leverantörsfakturan**.
- **Partnerns land/regions-typ** – Välj **lokal**, **EU**, **GCC** eller **utländsk**. Alternativt om regeln kan kopplas till alla handelspartner oavsett land eller region för adressen kan du välja **alla**.
- **Lokal leveransadress** – Markera den här kryssrutan om du vill använda regeln för leveranser inom samma land eller region. Den här kryssrutan kan inte väljas för dokumenttyperna **leverantörsfakturajournal** och **Kundfakturajournal**.
- **Artikelgrupp för omvänd moms** – Välj den grupp som regeln kan tillämpas på.
- **Tröskelbelopp** – används endast i schemat för omvänd moms till en faktura om värdet på artiklarna eller tjänsterna som ingår i artikelgruppen för omvänd moms överskrider den gräns som du anger här.

Du kan även använda fälten **giltighetsdatum** och **förfallodatum** för att anger perioden då regeln ska gälla.

Du kan också ange om ett meddelande visas och dokumentraden uppdateras med momsgrupp för omvänd moms om villkoret för den dokumentraden uppfylls. Följande alternativ är tillgängliga:

- **Ingen** – dokumentraden uppdateras inte.
- **Fråga** – ett meddelande visas som bekräftar att omvänd moms kan användas.
- **Ange** – dokumentraden uppdateras utan meddelande.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Ange egenskaper för land/region
Sidan **Utländska handelsparametrar** (**skatt** &gt; **inställningar** &gt; **moms** &gt; **utländsk handel** &gt; **parametrar för utländsk handel**) på fliken **egenskaper för land/region** ange land/region för aktuell juridisk person till *lokal*. Ange **typ av land/region** för EU-länder/EU-regioner som deltar i EU-handel med den aktuella juridiska personen till *EU*. Ange **typ av land/region** för GCC-länder/regioner som deltar i GCC-handel med den aktuella juridiska personen till *GCC*.

## <a name="set-up-default-parameters"></a>Ställ in standardparametrar
Om du vill aktivera funktionen för återföring av moms på sidan **allmänna redovisningsparametrar** på fliken **omvänd moms** anger du alternativet **aktivera omvänd moms** till **Ja**. I fälten **Momsgrupp för inköpsorder** och **Momsgrupp för försäljningsorder** väljer du standardmomsgrupper. När villkoren för omvänd moms uppfylls kommer försäljnings- eller inköpsordern att uppdateras med de här momsgrupperna.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Omvänd moms på en försäljningsfaktura
För försäljningen under schema för omvänd moms debiterar inte säljaren moms. Istället indikerar fakturan både artiklarna för vilka momsen ska återföras och det totala beloppet för den återförda momsen noteras på fakturan.

När en försäljningsfaktura bokförs med omvänd momstransaktion har kryssrutorna **Momsskuld** momsriktning och nollmoms och **omvänd moms** och **momsbefrielse** markerade.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Omvänd moms på en inköpsfaktura
För inköpare under schemat omvänd moms agerar inköparen som tar emot fakturan som har omvänd moms som en köpare och säljare för redovisningsändamål.

När en inköpsfaktura med omvänd moms bokförs, skapas två momstransaktioner. En transaktion har skatteriktningen **Momsfordran**. Den andra transaktionen har skatteriktningen **Momsskuld** och kryssrutan **omvänd moms** är markerad.

I följande skärmbild har en transaktion riktningen **Momsfordran** och den andra transaktionen har riktningen **Momsskuld**. 

![Bokförd moms](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Aktivera funktionen mekanism för omvänd moms för moms/GST-schema
På arbetsytan **Funktionshantering** söker du reda på funktionen och väljer **Aktivera**.

När du har aktiverat funktionen är fliken **Omvänd moms** tillgänglig i alla juridiska personer. Aktivera funktionen för omvänd moms för en juridisk person genom att ställa in alternativet **Aktivera omvänd moms** som **Ja**.

Följande sidor och menyobjekt som är relaterade till funktionsinställningar är tillgängliga:
 - **Artikelgrupper för omvänd moms** (**Skatt** > **Inställning** > **Moms** > **Artikelgrupper för omvänd moms**). Mer information finns i avsnittet [Ställ in artikelgrupper för omvänd moms](#reverse-charge-item-group).
 - **Regler för omvänd moms** (**Skatt** > **Inställning** > **Moms** > **Regler för omvänd moms**). Se [Ställa in regler för omvänd moms](#reverse-charge-rules).
 - **Utländska handelsparametrar** (**Skatt** > **Inställning** > **Moms** > **Utlandshandel** > **Utländska handelsparametrar**). Se [Ställa in egenskaper för land/region](#Set-up-Country/region-properties).

Kryssrutan **Omvänd moms** finns på sidorna **Momsgrupp** och **Bokförd moms**. Mer information finns i avsnitten [Ställ in momsgrupper och artikelmomsgrupper](#sales-tax-item-sales-tax-groups), [Omvänd moms på en försäljningsfaktura](#reverse-charge-sale) och [Omvänd moms på en inköpsfaktura](#reverse-charge-purchase).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]