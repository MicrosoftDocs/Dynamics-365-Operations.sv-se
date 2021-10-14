---
title: Ställ in leverantörer, kunder och artiklar för koncernintern handel
description: Det här ämnet förklarar hur du ställer in leverantörer, kunder och artiklar för koncernintern handel
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 062b8fe956fef0f8172d26aac3df54b93e1941ef
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548531"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Ställ in leverantörer, kunder och artiklar för koncernintern handel

[!include [banner](../../includes/banner.md)]

För att förbereda din organisation för koncernintern handel måste du definiera de leverantörer och kunder med vilka du kommer att ha intern handel. Du måste sedan koppla dessa leverantörer och kunder till de artiklar som du ska köpa eller sälja.

1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**.
1. Välj den leverantör som ska definieras som en koncernintern leverantör.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Ange koncerninterna inställningsparametrar för leverantörskontot. Dessa parametrar inkluderar kundens juridiska person och konto, försäljningsorderpolicyer, inköpsorderpolicyer, värdekartläggning och inköpsavtal och policyer för försäljningsavtal. Du anger också om du vill använda grunddatavärden från leverantörskontot eller från kundkontot i den andra juridiska personen.
1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. På listsidan **Frisläppta produkter** väljer du de artiklar som ska tilldelas leverantören, så att artiklarna blir tillgängliga för koncernintern handel. För varje objekt, öppna **Information om frisläppt produkt**. På fliken **Inköp** på fältet **Leverantör** skriv leverantörsnumret.
1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund som ska definieras som en koncernintern kund.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Ange koncerninterna inställningsparametrar för kundkontot. Dessa parametrar inkluderar leverantörens juridiska person och konto, inköpsorderpolicyer, försäljningsorderpolicyer, värdekartläggning och försäljningsavtal och policyer för inköpsavtal. Du anger också om du vill använda grunddatavärden från kundkontot eller från leverantörskontot i den andra juridiska personen.
1. På sidan **Kunder** på snabbfliken **Faktura och leverans**, markera kryssrutan **Skapa koncerninterna returorder**. Markera kryssrutan Direktleverans om du vill att order ska **levereras direkt** till kunderna.

    > [!NOTE]
    > Om det finns vissa artiklar som din organisation har i lager och levererar till kunder kanske du inte vill skapa koncerninterna order automatiskt, oavsett om artikeln finns i lager. Avmarkera kryssrutan **Skapa koncerninterna returorder** om du vill inaktivera den automatiska genereringen av order för varor som du ibland kan ha på lager 

1. Om du vill tillåta att extra rader skapas indirekt på en försäljningsorder markerar du kryssrutan **Skapa indirekta orderrader**. En användare kan då lägga till rader i ursprungliga försäljningsordern från den koncerninterna försäljningsordern.

> [!WARNING]
> Om du tillåter indirekt skapande av orderrader tillåter du alla tillägg till den ursprungliga försäljningsordern från den koncerninterna försäljningsordern. Varje tillägg behandlas via kunden och läggs till på ordern och fakturan. Alla dokument som ingår i försäljningen skrivs dessutom ut och bokförs automatiskt. Användarna meddelas inte om tillägget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
