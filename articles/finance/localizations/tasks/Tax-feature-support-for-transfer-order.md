---
title: Momsfunktionens stöd för överföringsorder
description: Det här ämnet innehåller information om det nya momsfunktionen som stöder överföringsorder genom att använda tjänsten för momsberäkning.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b97eca8c2d4fe9f71c3cd8f1e40a3bbb7ee4879
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348426"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Momsfunktionens stöd för överföringsorder

[!include [banner](../../includes/banner.md)]

Det här ämnet ger information om momsberäkning och bokföringsintegrering i överföringsorder. Med hjälp av den här funktionen kan du ställa in momsberäkning och bokföring i överföringsorder för lageröverföringar. Inom EU behandlas lageröverföringar inomeuropeisk anskaffning och anskaffning inomeuropeisk moms.

Om du vill konfigurera och använda denna funktion måste du utföra tre huvudsteg:

1. **RCS-inställning:** I Regulatory Configuration Service, ställ in momsfunktionen, momskoder och tillämplighet för momskoder för bestämning av momskod i överföringsorder.
2. **Ekonomiska inställningar:** I Microsoft Dynamics 365 Finance, aktivera funktionen **Moms i överföringsordning**, ställa in skattetjänstparametrar för lager och ställa in huvudsakliga momsparametrar.
3. **Lagerinställningar:** Ställ in lagerkonfigurationen för överföringsordertransaktioner.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Ställa in RCS för moms- och överföringsordertransaktioner

Följ dessa steg för att ställa in momsen som ingår i en överföringsorder. I exemplet som visas här är överföringsordern från Nederländerna till Belgien.

1. På sidan **Momsfunktioner**, på fliken **Versioner**, välj versionen av utkastfunktionen och välj sedan **Redigera**.

    ![Välja Redigera.](../media/tax-feature-support-01.png)

2. På sidan **Inställning av momsfunktioner** på fliken **Momskoder**, välj **Lägg till** för att skapa nya momskoder. I det här exemplet skapas tre momskoder: **NL-undantagen**, **BE-RC-21** och **BE-RC+21**.

    - När en överföringsorder levereras från ett lagerställe i Nederländerna används den momsbefriade momskoden (**NL-undantagen**) använd.
      
        Skapa momskoden **NL-undantagen**.
        1. Välj **Lägg till**, ange **NL-undantag** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Växla **Är undantagen** till **Ja** i avsnittet **Allmänt**.

        ![NL-undantagen momskod.](../media/tax-feature-support-02.png)

    - När en överföringsorder tas emot på ett belgiskt lagerställe används omvänd momsmekanism med hjälp av momskoderna **BE-RC-21** och **BE-RC+21**.
        
        Skapa momskoden **BE-RC-21**.      
        1. Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Ange **-21** i fältet **Momssats**.
        6. Växla **Är återförd avgift** till **Ja** i avsnittet **Allmänt**.
        7. Välj **Spara**.

        ![BE-RC-21-momskod för omvänd moms.](../media/tax-feature-support-03.png)
        
        Skapa momskoden **BE-RC+21**.
        1. Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Ange **21** i fältet **Momssats**.
        6. Välj **Spara**.

        ![BE-RC+21-momskod för omvänd moms.](../media/tax-feature-support-04.png)

3. Definiera tillämplighet för momskoderna.

    1. Markera **Hantera kolumner** och välj sedan kolumner som ska användas för att bygga tillämplighetsregler.

        > [!NOTE]
        > Se till att du lägger till kolumnerna **Affärsprocess** och **Momsriktningar**. Båda kolumnerna är nödvändiga för funktionen för moms i överföringsorder.

    2. Lägg tillämplighetsregler. Lämna inte fälten **Momskoder**, **Momsgrupp** och **Artikelmomsgrupp** tomma.
        
        Lägg till en ny regel för överföringsorderförsändelse.
        1. Välj **Lägg till** i tabellen **Tillämplighetsregler**.
        2. I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.
        3. I fältet **Sänd från land/region**, ange **NLD**.
        4. I fältet **Sänd till land/region**, ange **BEL**.
        5. I fältet **Momsriktning**, välj **Utgång** för att göra regeln tillämplig för överföring av orderförsändelse.
        6. I fältet **Momskoder**, välj **NL-undantag**.
        7. I fältet **Momsgrupp** och **Artikelmomsgrupp**, ange den relaterade momsgruppen och artikelns momsgrupp som definieras i ditt Finance-system.
        
        Lägg till en annan regel för inleverans av överföringsorder.
        1. Välj **Lägg till** i tabellen **Tillämplighetsregler**.
        2. I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.
        3. I fältet **Sänd från land/region**, ange **NLD**.
        4. I fältet **Sänd till land/region**, ange **BEL**.
        5. I fältet **Momsriktning**, välj **Ingång** för att göra regeln tillämplig för inleverans av överföringsorder.
        6. I fältet **Momskoder**, välj **BE-RC+21** och **BE-RC-21**.
        7. I fältet **Momsgrupp** och **Artikelmomsgrupp**, ange den relaterade momsgruppen och artikelns momsgrupp som definieras i ditt Finance-system.

        ![Tillämplighetsregler.](../media/image5.png)

4. Slutför och publicera den nya versionen av skattefunktionen.

    [![Ändra status för den nya versionen.](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>Ställa in Finance för moms- och överföringsordertransaktioner

Följ dessa steg för att aktivera och ställa in skatter för överföringsorder.

1. I Finance, gå till **Arbetsytor** \> **Funktionshantering**.
2. I listan, hitta och välj funktionen **Moms i överföringsorder** och välj sedan **Aktivera nu** för att aktivera den.

    > [!IMPORTANT]
    > Funktionen **Moms i överföringsorder** är helt beroende av momstjänst. Det kan därför endast aktiveras när du har installerat skattetjänsten.

    ![Moms i överföringsfunktionen.](../media/image7.png)

3. Aktivera skattetjänsten och välj affärsprocessen **Lager**.

    > [!IMPORTANT]
    > Du måste genomföra det här steget för varje juridisk person i Finance där du vill att momstjänsten och momsfunktionerna i överföringsorder ska vara tillgängliga.

    1. Gå till **Moms** \> **Inställningar** \> **Momskonfiguration** \> **Installation av momstjänst**.
    2. I fälten **Affärsprocess**, välj **Lager**.

    ![Ställa in affärsprocessfältet.](../media/image8.png)

4. Kontrollera att omvänd avgiftsmekanism har ställts in. Gå till **Redovisning** \> **Inställning** \> **Parametrar** och sedan på **Omvänd debitering**, kontrollera att alternativet **Aktivera omvänd moms** anges **Ja**.

    ![Aktivera alternativet för återfört tillägg.](../media/image9.png)

5. Kontrollera att de relaterade momskoderna, momsgrupperna, artikelmomsgrupperna och momsregistreringsnumren har ställts in i Finance enligt momstjänstens riktlinjer.
6. Ställ in ett mellanliggande transitkonto. Detta steg är endast nödvändigt när den skatt som tillämpas på en överföringsorder, inte gäller för en momsbefriad eller återförd avgiftsmekanism.

    1. Gå till **Moms** \> **Inställningar** \> **Moms** \> **Redovisningsbokföringsgrupper**.
    2. I fältet **mellanliggande transit**, välj redovisningskonto.

    ![Ställa in ett mellanliggande transitkonto.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Ställ in grundläggande inventering för moms- och överföringsordertransaktioner

Följ dessa steg om du vill ställa in grundläggande lager för att aktivera överföringsordertransaktioner.

1. Skapa från- och leveransplatser för dina lagerställen i olika länder eller regioner och lägg till den primära adressen för respektive webbplats.

    1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Webbplats**.
    2. Välj **Ny** för att skapa den webbplats som du tilldelar till ett lager senare.
    3. Upprepa steg 2 för alla andra siter som du måste skapa.

    > [!NOTE]
    > En av de webbplatser som du skapar ska få namnet **Transit**. Senare tilldelar du den här siten till transitlagret så att momsrelaterade lagerverifikationer kan bokföras i "skeppa" och "ta emot"-transaktioner för överföringsorder. Adressen till transitplatsen är inte relevant för momsberäkningen. Därför kan du lämna det tomt.

    ![Konfigurera in webbplatser.](../media/image11.png)

2. Skapa leverans-, transit- och leverans till lagerställen. All adressinformation som finns i ett lagerställe åsidosätter siteadressen vid momsberäkningen.

    1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Lagerställen**.
    2. Välj **Ny** för att skapa ett lager och tilldela det till motsvarande webbplats.
    3. Upprepa steg 2 om du vill skapa ett lagerställe för respektive webbplats efter behov.

    ![Konfigurera lagerställen.](../media/image12.png)

    > [!NOTE]
    > För ett lagerställe för leverans från måste ett transitlager väljas i fältet **Transitlagerställe** för överföringsordertransaktioner.
    >
    > ![Välja ett transitlager.](../media/image13.png)

3. Kontrollera att konfiguration av lagerbokföring har ställts in för överföringsordertransaktioner.

    1. Gå till **Lagerhantering** \> **Inställningar** \> **Bokföring** \> **Bokföring**.
    2. Kontrollera på fliken **Lager**, verifiera att ett huvudbokskonto är konfigurerat för båda bokföring av **lagerutleverans** och **lagerinleverans**.

        ![Konfigurera in bokföring av lagerutleverans och lagerinleverans.](../media/image14.png)

    3. Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern skuld**.

        ![Konfigurera in bokföring av enhetsintern reskontra.](../media/image15.png)

    4. Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern fordran**.

        ![Ställa in bokföring av enhetsintern reskontra.](../media/image16.png)
