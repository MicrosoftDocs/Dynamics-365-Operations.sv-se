---
title: Moms beräknas inte, eller också är momsbeloppet noll
description: Detta avsnitt innehåller felsökningsinformation som kan vara till hjälp när momsbeloppet är 0 (noll) eller när moms inte beräknas.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7237980f8d330a7b3f5c966d5bd3fff0eda8b21a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685868"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>Moms beräknas inte, eller också är momsbeloppet noll

[!include [banner](../includes/banner.md)]

En transaktion kan ha ett radbelopp som inte är 0 (noll), men antingen beräknas inte momsbeloppet, också är det beräknade momsbeloppet 0. Felsök det här problemet genom att följa stegen i följande avsnitt.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Kontrollera att momskoderna har valts korrekt av transaktionen

Om transaktionen inte väljer de korrekta momskoderna – eller om den inte väljer några momskoder alls – beräknas inte momsen på den. Följ dessa steg i syfte att kontrollera att momskoderna har valts korrekt av transaktionen. 

1. På transaktionsraden, på snabbfliken **Radinformation**, i fliken **Inställningar**, i avsnittet **Moms** bekräftar du att rätt momsgrupper har valts i fälten för **Artikelgrupp för moms** samt **Momsgrupp**. Om rätt momsgrupper inte har valts, väljer du dem.

    [![Fält för Artikelgrupp för moms samt Momsgrupp.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Momsgrupper**.
3. Välj lämplig momsgrupp – i snabbfliken **Inställningar** noterar du sedan skattekoden i fältet **Momskod**.

    [![Sida för momsgrupper.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Artikelgrupper för moms**.
5. Välj lämplig momsgrupp och kontrollera sedan på snabbfliken **Inställningar** att skattekoden i fältet **Momskod** matchar skattekoden för momsgruppen.

    [![Sida för artikelmomsgrupper.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Om skattekoderna inte matchar uppdaterar du momskoden för en av grupperna.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Kontrollera att de valda momskoderna inte är undantagna och att de har korrekt skattesatsvärde

Om momskoderna är undantagna, eller om momssatsen är 0 (noll) blir momsberäkningen 0. Följ dessa steg för att fastställa om de valda momskoderna är undantagna, samt för att bekräfta att den korrekta momssatsen tillämpas på dem.

1. Gå till **Skatt** \> **Indirekta skatter** \> **Moms** \> **Momsgrupper**.
2. Välj lämplig momsgrupp och kontrollera sedan, i snabbfliken **Inställningar**, att kryssrutan **Undantagen** har rensats. Rensa om denna har markerats.

    [![Kryssrutan Undantagen på sidan Momsgrupper.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.
4. Välj lämplig momskod och kontrollera sedan att momssatsvärdet i fältet **Värde** inte är 0 (noll). Om det är 0 uppdaterar du fältet så att det får rätt momssats.

    [![Värdefält på värdesidan för moms.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Fastställ om noll är korrekt momsbelopp

I vissa scenarier är momsbeloppet 0 (noll) korrekt. Följ anvisningarna nedan och ta reda på om 0 är korrekt momsbelopp för transaktionen.

1. Gå till **Redovisning** \> **Inställningar för transaktionsregister** \> **Redovisningsparametrar**.
2. På fliken **Moms**, i fältet **Beräkningsmetod**, bekräftar du att **Summa** har valts.

    [![Fältet för beräkningsmetod på sidan Redovisningsparametrar.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.
4. Välj lämplig momskod, välj **Beräkning** \> **Marginalbas** och bekräfta att marginalbasen angetts som **Nettobelopp för fakturasaldo** eller **Fakturasumma inkl. andra momsbelopp**. Mer information finns i [Fakturasumma inkl. andra momsbelopp](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Om de korrekta värdena ställts in i steg 2 och 4 ska du avgöra om det totala beloppet för transaktionen är 0 (noll). Om totalbeloppet är 0 är ett momsbelopp på 0 det förväntade resultatet. Eftersom momsberäkningen baseras på det totala fakturasaldot och det beloppet inte är rad för rad, fördelas momsbeloppet 0 på varje rad efter momsberäkningen.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i de föregående avsnitten men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
