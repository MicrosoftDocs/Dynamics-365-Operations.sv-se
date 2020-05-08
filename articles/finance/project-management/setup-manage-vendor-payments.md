---
title: Ställa in och använda leverantörsbetalningar av typen Betala vid betalning
description: I det här avsnittet beskrivs hur du skapar villkor för betala vid betalning (PWP) så att du kan frisläppa leverantörsbetalningar för delbelopp baserat på kundbetalningar.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284123"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Ställa in och använda leverantörsbetalningar av typen Betala vid betalning

[!include [banner](../includes/banner.md)]

När du godkänner en leverantör till att arbeta som underleverantör, kan du hålla inne betalningen till leverantören tills du har betalats av kunden för projektet. För att stödja detta scenario, om du vill hålla inne en betalning till en leverantör, ställ in inköpsordern (PO) när du ställer in inköpsordern för leverantören.

Till exempel när en kund betalar ett belopp på en projektfaktura kan du frisläppa en del av eller hela beloppet för leverantörsfakturan. Du kan ställa in bet. vid bet.-villkor som anger om en leverantör betalas när du har fått en procentsats av den relaterade betalningen från kunden. Om du får delvis betalning från en kund, kan du manuellt frisläppa några av de relaterade leverantörsfakturorna för betalning.

I följande exempel beskrivs processen när bet. vid bet.-villkor används.

## <a name="example"></a>Exempel

Din organisation samtycker till att tillhandahålla en kund med 100 datorer som har installerad programvara till ett pris på 150,00 USD per dator. Du anställer sedan en leverantör för att förse dig med de datorer som har en installerad programvara. Enligt avtalet måste kunden godkänna datorns kvalitet innan den betalar din organisation. Organisationens policy är att hålla inne betalningen till leverantörer tills kunden har betalat dig. Därför ställer du in projektet så att det har en betala vid betalning-procentsats på 100 procent.

Leverantören skickar dig de 100 datorerna som har installerad programvara, tillsammans med en faktura på 10 000,00 USD. Eftersom bet. vid bet.-villkor har ställts in för projektet ska du inte betala leverantören vid mottagandet av datorerna. I stället skickar du datorerna till kunden, tillsammans med en faktura på 15 000,00. Kunden kontrollerar datorerna och godkänner hela beloppet på projektfakturan.

När du har tagit emot hela betalningen från kunden betalar du leverantören 10 000,00, hela beloppet för leverantörsfakturan.

## <a name="set-up-pwp-terms-for-a-project"></a>Ställ in bet. vid bet.-villkor för ett projekt

När du ställer in bet. vid bet.-villkor för ett projekt, måste du ange det minsta belopp som en kund måste betala för projektet innan du ska betala leverantören. Ingångsbeloppet beräknas automatiskt för kundfakturan för projektet. Följ dessa steg för att ställa in ingångsprocentsats för bet. vid bet.-villkor.

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.
2. Sök reda på och öppna det projekt som du vill ställa in bet. vid bet.-villkor för.
3. Klicka på **Lägg till rad** på snabbfliken, välj **Leverantörsavtal**.
3. Välj ett av följande alternativ i fältet **Kontokod**:

    - **Tabell** – Bet. vid bet.-villkoren gäller för en enskild leverantör.
    - **Grupp** – Bet. vid bet.-villkoren gäller för alla leverantörer inom en leverantörsgrupp.
    - **Alla** – Bet. vid bet.-villkoren gäller för alla leverantörer.

4. Om du valde **Tabell** eller **Grupp** i föregående steg väljer du i fältet **leverantör/leverantörsgrupp** den leverantör eller leverantörsgrupp som bet. vid bet.-villkoret gäller för. Om du valde **alla** i föregående steg kan fältet **leverantör/leverantörsgrupp** inte redigeras.
5. Om villkor för innehållet belopp till leverantör är inställda för leverantören väljer du i projektet i fältet **villkor för innehållet belopp till leverantör** regel-ID för villkor för innehållet belopp.
6. I fältet **ingångsprocentsats för bet. vid bet.** anger du ingångsprocentsatsen för projektet. Procentsatsen som du anger för projektet definierar minimibeloppet som kunden måste betala till dig innan du betalar leverantören.

## <a name="create-a-po-that-has-pwp-terms"></a>Skapa en inköpsorder som har bet. vid bet.-villkor

När du bokför en faktura från en leverantör och leverantören lyder under bet. vid bet.-villkor visas dessa villkor på inköpsorderraderna. Om du vill skapa ett inköpsorder som har bet. vid bet.-villkor följer du stegen nedan.

1. Gå till **Anskaffning och källa** \> **Inköpsorder** \> **Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret. Sedan i dialogrutan **skapa inköpsorder** anger du önskad information och väljer **OK**.

    Du kan också öppna ett befintligt inköpsorder på listsidan **Alla inköpsorder**.

4. På sidan **inköpsorder** på snabbfliken **inköpsorderrader** granska informationen på inköpsorderraden för leverantören. Alternativet **betala vid betalning** väljs automatiskt och värdet i fältet **ingångsprocentsats för bet. vid bet.** kopieras automatiskt från fältet **ingångsprocentsats för bet. vid bet.** på sidan **projekt**.
6. Om du inte vill använda bet. vid bet.-villkor för leverantören för en inköps order rad avmarkerar du alternativet **betala vid betalning**. I det här fallet återställs fältet **ingångsprocentsats för bet. vid bet.** för inköpsorderraden till 0 (noll).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Uppdatera en kundbetalning och betala till leverantören

När leverantören slutför arbetet ett projekt och du måste granska projektets status och kundfakturor för att bestämma om bet. vid bet.-villkoren har uppfyllts för projektet. Om bet. vid bet.-villkoren för leverantören har uppfyllts kan du bestämma vilka rader på leverantörsfakturan som ska betalas, baserat på kundbetalningarna för projektet. Om du bestämmer dig för att betala leverantören även om bet. vid bet.-villkor inte uppfyllts, kan du åsidosätta bet. vid bet.-villkor på sidan **Leverantörsfakturor med betala vid betalning**.

1. Gå till **projekthantering och redovisning** \> **förfrågningar och rapporter** \> **kvarhållandeförfrågningar** \> **Leverantörsfakturor med betala vid betalning**.
2. På sidan **Leverantörsfakturor med betala vid betalning** i sökfältet anger du värden för att söka efter den leverantörsfaktura som du vill granska och väljer sedan **Sök**.
3. På snabbfliken **leverantörsfakturarader**, välj de rader du vill ändra.
4. Om villkoren för **betala vid betalning** uppfylls för fakturaraden väljer du **Frisläpp leverantörsbetalning**. Alternativet **betala vid betalning** har avmarkerats och värdet för fältet **redo för betalning** ändras till **Ja**.
