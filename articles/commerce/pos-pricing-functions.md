---
title: Prissättningsfunktioner i kassa
description: I den här artikeln beskrivs olika pris- och rabattfunktioner i Microsoft Dynamics 365 Commerce kassa (POS).
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 92bbc3b81b889f106dc113528afbdc37d1106ff3
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294138"
---
# <a name="pricing-functions-in-pos"></a>Prissättningsfunktioner i kassa

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I den här artikeln beskrivs olika pris- och rabattfunktioner i Microsoft Dynamics 365 Commerce kassa (POS).

Kassa appen Dynamics 365 Commerce tillhandahåller rika funktioner som gör det möjligt för arbetare i första linjen att utföra butikshandel. I följande tabell visas de pris- och rabattfunktioner som för tillfället är tillgängliga i programmet.

| Funktion                       | POS-åtgärder |
|--------------------------------|----------------|
| Visa priser                    | [Priskontroll](#price-check) |
| Visa rabatter                 | [Visa alla rabatter](#view-all-discounts)<br>[Visa tillgängliga rabatter](#view-available-discounts) |
| Åsidosätt priser                | [Åsidosätt pris](#price-override) |
| Tillämpa eller ta bort rabatter      | [Radrabattbelopp](#line-discount-amount)<br>[Radrabatt i procent](#line-discount-percent)<br>[Totalt rabattbelopp](#total-discount-amount)<br>[Total rabatt i procent](#total-discount-percent)<br>[Ta bort systemrabatter från transaktion](#remove-system-discounts-from-transaction)<br>[Tillämpa systemrabatter igen](#reapply-system-discounts) |
| Tillämpa eller ta bort kuponger        | [Lägg till kupongkod](#add-coupon-code)<br>[Ta bort kupongkod](#remove-coupon-code) |
| Beräkna priser och rabatter | [Omberäkna](#recalculate) |

För information om hur de föregående operationerna kan konfigureras i kassaprogrammet och om de stöder offlineläge, se [Verksamhet för online- och offlinekassor (POS)](pos-operations.md).

## <a name="price-check"></a>Priskontroll

Åtgärden **Priskontroll** gör det möjligt för kassaanvändare att slå upp förkonfigurerade priser för en specifik produkt.

## <a name="view-all-discounts"></a>Visa alla rabatter

Åtgärden **Visa alla rabatter** gör det möjligt för kassaanvändare att leta upp alla effektiva kampanjer som för närvarande körs i butikskanalen. I åtgärden visas alla rabatter som matchar något av följande villkor:

- Prisgruppen för rabatten matchar butikens prisgrupp.
- Rabattens prisgrupp mappas till ett anknytning eller förmånsprogram.
- Rabattens prisgrupp mappas till en katalog som är kopplad till butiken.

Åtgärden **Visa alla rabatter** visar endast rabatter som inte konkurrerar med någon av de tillämpade rabatterna. På så sätt säkerställs att om en säljare informerar en kund om en rabatt och kunden vidtar den åtgärd som krävs (t.ex. kunden köper ytterligare en artikel för att få 10 procents rabatt) används rabatten på transaktionen. Kupongbaserade rabatter visas enbart om parametern **Använd utan kupongkod** är aktiverad.

I operationen **Visa alla rabatter** kan kassaanvändare söka efter rabatter efter namn och beskrivning och de kan filtrera rabatterna baserat på om de kräver en kupong.

## <a name="view-available-discounts"></a>Visa tillgängliga rabatter

Med åtgärden **Visa tillgängliga rabatter** kan kassaanvändare visa alla rabatter som kan användas på en vald rad i en transaktion eller för hela transaktionen. Rabatterna som gäller för en vald rad omfattar rabatter som redan har tillämpats och rabatter som inte har tillämpats ännu men kan användas (till exempel blandade och kombinationsrabatter som kräver ytterligare artiklar). Om en tillämplig rabatt är kopplad till en kupong där parametern **Använd utan kupongkod** är aktiverad kan kassaanvändaren också använda funktionen **Använd kupong** i denna åtgärd för att lösa in kupongen direkt, utan att behöva ange eller skanna några kupongkoder eller streckkoder.

## <a name="price-override"></a>Åsidosätt pris

Med åtgärden **Prisåsidosättning** kan kassaanvändare åsidosätta försäljningspriset för en produkt i en transaktion. Den här åtgärden fungerar bara för produkter som är konfigurerade för att tillåta prisåsidosättningar.

## <a name="line-discount-amount"></a>Radrabattbelopp

Med åtgärdem **Radrabattbelopp** kan kassaanvändare ange ett rabattbelopp för en radartikel i en transaktion. Den här åtgärden gäller bara för artiklar som kan ha rabatt och följer värdet **Maximalt radrabattbelopp** som har angetts i kassabehörighetsgruppen för användaren.

## <a name="line-discount-percent"></a>Radrabatt i procent

Med åtgärdem **Radrabattprocent** kan kassaanvändare ange ett rabattprocent för en radartikel i en transaktion. Den här åtgärden gäller bara för artiklar som kan ha rabatt och följer värdet **Maximalt radrabattprocent** som har angetts i kassabehörighetsgruppen för användaren.

## <a name="total-discount-amount"></a>Totalt rabattbelopp

Med åtgärdem **Totalt rabattbelopp** kan kassaanvändare ange ett rabattbelopp för en transaktion. Den här åtgärden gäller bara för artiklar som kan ha rabatt och följer värdet **Högsta totala rabattbelopp** som har angetts i kassabehörighetsgruppen för användaren. Om det angivna rabattbeloppet överskrider det maximala totala rabattbeloppet spärras åtgärden och inget flöde för behörighetsåsidosättning utlöses. För närvarande kan ett totalt rabattbelopp inte tillämpas på en vagn som har en mix av försäljningsartiklar och returartiklar.

## <a name="total-discount-percent"></a>Total rabatt i procent

Med åtgärdem **Total rabattprocent** kan kassaanvändare ange ett rabattprocent för en transaktion. Den här åtgärden gäller bara för artiklar som kan ha rabatt och följer värdet **Maximal total rabattprocent** som har angetts i kassabehörighetsgruppen för användaren. Om den angivna rabattprocenten överskrider den maximala totala rabattprocent spärras åtgärden och inget flöde för behörighetsåsidosättning utlöses. För närvarande kan en totalt rabattprocent inte tillämpas på en vagn som har en mix av försäljningsartiklar och returartiklar.

## <a name="remove-system-discounts-from-transaction"></a>Ta bort systemrabatter från transaktion

Åtgärden **Ta bort systemrabatter från transaktion** gör det möjligt för kassaanvändare att rensa alla tillämpade systemrabatter (inklusive kupongbaserade rabatter) från en transaktion. När åtgärden har utförts börjar prissättningsmotorn utelämna systemrabatter från rabattberäkningsområdet. Åtgärden **Ta bort systemrabatter från transaktion** tar inte bort manuella rabatter.

## <a name="reapply-system-discounts"></a>Tillämpa systemrabatter igen

Åtgärden **Tillämpa systemrabatter igen** gör det möjligt för kassaanvändare att åter tillämpa systemberäknade rabatter på en transaktion om rabatterna togs bort med hjälp av **Ta bort systemrabatter från transaktion**. När åtgärden har utförts börjar prissättningsmotorn inkludera systemrabatter i rabattberäkningsområdet.

## <a name="add-coupon-code"></a>Lägg till kupongkod

Åtgärden **Lägg till kupongkod** gör det möjligt för kassaanvändare att lägga till en kupong till en transaktion genom att ange en kupongkod. Alternativt kan kassaanvändare skanna en kupongstreckkod eller ange den genom att använda det numeriska tangentbordet på skärmen **Transaktioner**.

## <a name="remove-coupon-code"></a>Ta bort kupongkod

Åtgärden **Ta bort kupongkod** gör det möjligt för kassaanvändare att välja och ta bort en eller flera kuponger som för närvarande tillämpas på en transaktion.

## <a name="recalculate"></a>Omberäkna

Med åtgärden **Omberäkna** kan kassaanvändare initiera prissättningsberäkningar vid behov. Åtgärden är obligatorisk när prislås och/eller försenad prisberäkning aktiveras och kassaanvändaren vill omberäkna priser och rabatter efter kundvagn- eller orderändringar. Åtgärden **Omberäkning** räknar alltid om hela ordern. Den kan inte användas för att beräkna om valda försäljningsrader. Om du vill använda manuella rabatter på en låst försäljningsrad i kassa måste kassaanvändarna först använda åtgärden **Omberäkna** för att låsa upp alla försäljningsrader.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
