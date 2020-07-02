---
title: Lägg till rekommendationer på transaktionsskärmen
description: Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 760e6e093dbe0ba6b2781f90af7fbb614c492b93
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454589"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Lägg till rekommendationer på transaktionsskärmen

[!include [banner](includes/banner.md)]


Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Commerce. Mer information om produktrekommendationer finns i [produktrekommendationerna i kassadokumentationen](product.md).


Du kan visa produktrekommendationer på din kassaenhet när du använder Handel . Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern. 

## <a name="open-layout-designer"></a>Öppna layoutdesignern

1. Navigera till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.
2. Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i. Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet **F2CP16:9M**.
3. Hitta och markera önskad post i listan. Markera exempelvis **Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M**.
4. Klicka på **Layoutdesigner**.
5. Följ instruktionerna för att starta layoutdesignern. När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.
6. När du loggar in visas en sida som liknar den nedanstående. Layouten är olika beroende på de anpassningar som gjorts för din butik.


    [![Layoutdesigner](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Välj ett visningsalternativ

Det finns två konfigurationsalternativ tillgängliga. Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna. De två alternativen är:

- Rekommendationer visas alltid.
- Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.

### <a name="make-recommendations-always-visible"></a>Gör så att rekommendationer alltid visas


1. Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.


    [![Höjden på detaljområdet för transaktionsrader har reducerats](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen. Ändra storlek på kontrollen så att den passar in i utrymmet.

    [![Rekommendationskontroll som läggs till i layouten](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Klick på **X** för att spara och stänga layoutdesignern.
4. I Handel, gå till **Butik och handel** &gt; **Butiks- och handels-IT** &gt; **Distributionsschema**.
5. I listan väljer du **1090 Registers**.
6. Klicka på **Kör nu**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Lägg till en rekommendationsflik i knappsatsen till höger på skärmen

1. Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.

2. Klicka på **anpassa**.

    [![Anpassning - dialogrutan flikkontroll](./media/pic-5.png)](./media/pic-5.png)

3. Klicka på **Ny flik**.
4. Hitta den nya fliken som du just skapade. Du kan behöva rulla nedåt.
5. I listrutan **Innehåll** väljer du **Rekommenderade produkter**.

    [![Välja rekommenderade produkter i fältet Innehåll](./media/pic-6.png)](./media/pic-6.png)

6. I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.
7. I fältet **Bild** väljer du den bild du vill visa i fliken.
8. Klicka på **OK**. Den nya fliken visas i knappsatsen.
9. Klick på **X** för att spara och stänga layoutdesignern.
10. I Handel, gå till **Butik och handel** &gt; **Butiks- och handels-IT** &gt; **Distributionsschema**.
11. I listan väljer du **1090 Registers**.
12. Klicka på **Kör nu**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)
