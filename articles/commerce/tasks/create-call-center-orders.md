---
title: " Skapa kundtjänstorder"
description: Den här artikeln går igenom en exempelprocedur där en kundtjänstanvändare söker upp en kund, skapar en ny beställning, söker efter en produkt och tar ut betalning från kunden i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228521"
---
# <a name="create-call-center-orders"></a> Skapa kundtjänstorder

[!include [banner](../includes/banner.md)]

Den här artikeln går igenom en exempelprocedur där en kundtjänstanvändare söker upp en kund, skapar en ny beställning, söker efter en produkt och tar ut betalning från kunden i Microsoft Dynamics 365 Commerce. I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig. 

## <a name="prerequisites"></a>Förutsättningar

Användaren som slutför proceduren måste användaren konfigureras som en kundtjänstanvändare. Om du vill kan Fabrikam halvårskatalog publiceras med minst en källkod.

### <a name="add-yourself-as-a-call-center-user"></a>Lägga till dig själv som kundtjänstanvändare

Följ dessa steg om du vill lägga till dig själv som kundtjänst.

1. I Commerce headquarters går du till **Butik och handel \> Kanaler \> Kundtjänster \> Alla kundtjänster**.
1. I fältet **Användare**, välj **Kanalanvändare**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Användar-ID** ange ditt användar-ID.
1. Ange sedan ett användarnamn i fältet **Namn**. Användarnamnet kan vara samma som användar-ID:t.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Gå till **Butik och handel \> Kanaler \> Kundtjänster \> Alla kundtjänster**.
1. Välj butikskanal-ID för kundtjänsten.
1. Bekräfta att alternativet **Aktivera slutförande av order** är inställt på **Ja**. Om alternativet inte visas kan du hoppa över det här steget.

## <a name="complete-the-example-call-center-procedure"></a>Slutför exemplet på kundtjänstproceduren

Slutför proceduren för kundtjänstexempel genom att följa dessa steg.

1. Gå till **Butik och handel \> Kunder \> Kundtjänst**.
1. På fliken **Kundsökning**, ange sökkriterierna för att hitta kunden. För den här exempelproceduren, skriv **Karen**.
1. Välj **Sök**. Dialogrutan **Kundsökning** visas och listar sökresultatet.
1. Välj kundposten för **Karen Berg** som har kundkontonumret **2001** och välj sedan **Välj**.
1. Välj **Ny försäljningsorder** i åtgärdsfönstret.
1. Till höger väljer du fliken **huvud**.
1. På snabbfliken **Leverans**, i fältet **Leveranssätt**, väljer du **99 standard**.

    ![Välja ett leveranssätt.](../media/Select_Mode_of_Delivery.png)

1. Till höger väljer du fliken **Rader**.
1. I avsnittet **Försäljningsorderrader**, på den nya raden för den nya försäljningslinjen, i **Artikelnummer** ange artikelnumret att söka efter. För den här proceduren skriver du **81327** och markerar sedan produkten i listrutan för att lägga till den på försäljningsordern.
1. I fältet **Kvantitet** anger du försäljningskvantiteten.
1. I fältet **Källkod** välj källkoden för katalogen. Om det inte finns några aktiva källkoder kan du hoppa över det här steget.
1. I åtgärdsfönstret, välj **Slutför** för att registrera kundbetalningen. Med den här åtgärden öppnas dialogrutan **Sammanfattning av försäljningsorder**, där det totala beloppet som förfaller visas. Åtgärden utlöser också beräkningen av eventuella avgifter, till exempel leverans och hantering, och visar dem i dialogrutan **Sammanfattning av försäljningsorder**.

    ![Knappen Slutför.](../media/Complete_button.png)

1. I dialogrutan **Sammanfattning av försäljningsorder** på snabbfliken **Betalningar**, välj **Lägg till** för att samla in betalningarna.

    ![Dialogrutan för sammanfattning av försäljningsorder.](../media/order_summary.png)

1. I dialogrutan **Ange kundbetalningsinformation** i fältet **Betalningsmetod**, välj betalningsmetod. För den här exempelproceduren, välj **Kontanter**.
1. I fältet **Betalningsbelopp**, ange betalningsbelopp. För det här exemplet anger **120,00**, som är lika med ordersaldot som visas i dialogrutan **Sammanfattning av försäljningsorder**. Genom att ange detta belopp kan du slutföra beställningen som fullbetald.
1. Välj **OK**.
1. Välj **skicka**.

## <a name="additional-resources"></a>Ytterligare resurser

[Anpassa transaktionsmeddelanden via e-post efter leveranssätt](../customize-email-delivery-mode.md)

[Ändra leveranssätt i POS](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
