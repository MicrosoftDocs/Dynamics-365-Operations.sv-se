---
title: Exempel på bearbeta kravbrev
description: I detta avsnitt finns ett exempel som visar processen med att skapa, skriva ut och bokföra kravbrev.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1b80532463d86dd59b867fca2ee24675396ce717
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826357"
---
# <a name="process-collection-letters-example"></a>Exempel på bearbeta kravbrev

[!include [banner](../../includes/banner.md)]

I detta avsnitt finns ett exempel som visar processen med att skapa, skriva ut och bokföra kravbrev. Exemplet baseras på alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** i Kredit och inkasso. Data används i USMF demoföretaget och en ny kund, US-045.

Till att börja med **Kundreskontra \> Kunder \> Alla kunder**, välj **Ny** och ange sedan nödvändig information för att skapa kund US-045.

När du avslutar följer du dessa steg.

1. Gå till **Kredit och inkasso \> Kravbrev \> Ställ in sekvensen för kravbrev** och ställa in sekvensen för samlingsbrevet som visas i följande tabell som tilldelas kundbokföringsprofilen.

|     Kravbrevskod      |     beskrivning                           |     Valuta      |     Huvudkonto        |     Avgift i valuta     |     Minimum över        |     Dagar block      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     Kravbrev 1         |     Andra notifieringen med avgift        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     Kravbrev 2         |     Andra notifieringen med avgift        |     USC           |     403150                |     20.00                 |     10,00                 |     3                 |
|     Grupp                    |     Sista notifieringen med avgift         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

I följande illustration visas den information som finns i registret på det sätt som den skulle visas på sidan **Kravbrev**. 

[![Ställ in en kravbrevsserie](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Nu måste du ställa in de två parametrar som krävs för det här exemplet.

2. Gå till **Kredit och inkasso \> Inställningar \> Parametrar för kundreskontra** och följ dessa steg:

    1. På fliken **Inkasso**, ange alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** till **Ja**.
    2. Se till att fältet **skapa kravbrev per** anges till **Kund**.

    [![Ställa in kundreskontraparametrar för kreditsamlingar](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**, välj **Ny** och gör följande steg:

    1. I fältet **kundkonto** välj **US-045**.
    2. I fältet **Fakturadatum**, ange **1/15/2021**.
    3. I fältet **Förfallodatum** anger du **1/16/2021**.
    4. På snabbfliken **Fakturarader** i fältet **Huvudkonto**, ange **401100**.
    5. I fältet **Enhetspris** ange **500.00**.
    6. Vald **bokföring**

    Du måste nu ange två kreditnotor för kunden.

4. Välj **Ny** och gör sedan följande:

    1. I fältet **kundkonto** välj **US-045**.
    2. I fältet **Fakturadatum**, ange **1/15/2021**.
    3. I fältet **Förfallodatum** anger du **1/16/2021**.
    4. På snabbfliken **Fakturarader** i fältet **Huvudkonto**, ange **401100**.
    5. I fältet **Enhetspris**, ange **-100,00**.
    6. Vald **bokföring**

5. Upprepa steg 4, men ange **-200,00** i fältet **Enhetspris**.
6. Gå till **Kundreskontra \> Kunder \> Alla kunder** och välj kund **US-045**. I åtgärdsfönstret väljer du sedan **Transaktioner \> Transaktioner** för att granska de kundtransaktioner som du publicerade tidigare.

    [![Granska bokförda kundtransaktioner](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Du måste nu skapa kravbrev för kunden US-045.

7. Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:

    1. Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.

        Som standard ska fältet **Kravbrev** anges till **Krav per kund**.

    2. I fältet **datum för kravbrevet**, ange **1/19/2021**.
    3. På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.
    4. Välj **OK**.
    5. Välj **OK** för att skapa kravbrevet.

8. Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och följa dessa steg:

    1. Observera att kravbrevkoden på både rubriken och transaktionsraderna är **Kravbrev 1**, eftersom det här kravbrevet är det första kravbrevet i sekvensen. (Om du vill visa transaktionsraderna måste du kanske välja snabbflik **transaktioner**.)

   [![Kontrollera att samma kravbrevskod visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. Klicka på **Bokföra** i åtgärdsfönstret.
    3. I fältet **Bokföringsdatum**, ange **1/19/2021**.

    Du måste nu skapa kravbrev igen för kunden US-045.

9. Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:

    1. Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.

        Som standard ska fältet **Kravbrev** anges till **Krav per kund**.

    2. I fältet **datum för kravbrevet**, ange **1/23/2021**.
    3. På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.
    4. Välj **OK**.
    5. Välj **OK** för att skapa kravbrevet.

10. Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och följa dessa steg:

    1. Lägg märke till att kravbrevskoden i rubriken **Kravbrev 1**. Koden på transaktionsraderna är dock **Kravbrev 2**.

   [![Kontrollerar att olika kravbrevskoder visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  Koderna skiljer sig åt eftersom alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** är **Ja**.

  2. Bokför inte detta kravbrevet.

11. Gå till **Kredit och inkasso \> Inställningar \> Parametrar för kundreskontra** och fliken **Inkasso**, ange **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** till **Nej**.

    [![Ställa in alternativet ignorera betalningar och kreditnotor när du beräknar kravbrevskod till Nej](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Du måste nu skapa kravbrev igen för kunden US-045.

12. Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:

    1. Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.

        Som standard ska fältet **Kravbrev** anges till **Krav per kund**.

    2. I fältet **datum för kravbrevet**, ange **1/23/2021**.
    3. På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.
    4. Välj **OK**.
    5. Välj **OK** för att skapa kravbrevet.

13. Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och märker att kravbrevkoden på både rubriken och transaktionsraderna är **Kravbrev 2**.

    [![Visa igen att samma kravbrevskod visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Samma kod visas på båda platserna eftersom alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** anges **Nej**.
