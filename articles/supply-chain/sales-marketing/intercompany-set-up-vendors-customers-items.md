---
title: Ställ in leverantörer, kunder och artiklar för koncernintern handel
description: Denna artikel förklarar hur du konfigurerar leverantörer, kunder och artiklar för koncernintern handel
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4c928435a4e66832b09dbc805664934cfb1236be
ms.sourcegitcommit: b666289f5113d0a3fa2220fe337d5aacf07cbd92
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2022
ms.locfileid: "8945767"
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
1. När du är klar med att konfigurera de koncerninterna parametrarna stänger du sidan **Koncernintern** för att återgå till den valda kundinformationen.
1. Visa snabbfliken **Diverse detaljer** och ange **Skapa koncerninterna order** som *Ja*. Om du dessutom vill att order ska levereras direkt till kunderna anger du **Direktleverans** som *Ja*.

    > [!NOTE]
    > Om det finns vissa artiklar som din organisation har i lager och levererar till kunder kanske du inte vill skapa koncerninterna order automatiskt, oavsett om artikeln finns i lager. Om du vill inaktivera den automatiska genereringen av order för artiklar som du ibland kanske har på lager anger du **Skapa koncerninterna order** som *Nej*.

1. Om du vill tillåta att extra rader skapas indirekt på en försäljningsorder anger du **Skapa indirekta orderrader** som *Ja*. En användare kan då lägga till rader i ursprungliga försäljningsordern från den koncerninterna försäljningsordern.

> [!WARNING]
> Om du tillåter indirekt skapande av orderrader tillåter du alla tillägg till den ursprungliga försäljningsordern från den koncerninterna försäljningsordern. Varje tillägg behandlas via kunden och läggs till på ordern och fakturan. Alla dokument som ingår i försäljningen skrivs dessutom ut och bokförs automatiskt. Användarna meddelas inte om tillägget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
