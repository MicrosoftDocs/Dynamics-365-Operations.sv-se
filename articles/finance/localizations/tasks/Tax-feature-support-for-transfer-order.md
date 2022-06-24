---
title: Momsfunktionstöd för överföringsorder
description: Det här ämnet innehåller information om det nya momsfunktionen som stöder överföringsorder genom att använda tjänsten för momsberäkning.
author: Kai-Cloud
ms.date: 10/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 281ee90b7cae2d24d37d0684ad9975118560bb3e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869993"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Momsfunktionstöd för överföringsorder

[!include [banner](../../includes/banner.md)]

Det här ämnet ger information om momsberäkning och bokföringsintegrering i överföringsorder. Med hjälp av den här funktionen kan du ställa in momsberäkning och bokföring i överföringsorder för lageröverföringar. Inom EU behandlas lageröverföringar inomeuropeisk anskaffning och anskaffning inomeuropeisk moms.

Om du vill konfigurera och använda denna funktion måste du utföra tre huvudsteg:

1. **RCS-inställning:** I Regulatory Configuration Service, ställ in momsfunktionen, momskoder och tillämplighet för momskoder för bestämning av momskod i överföringsorder.
2. **Dynamics 365 Finance-konfiguration:** I Finance, aktivera funktionen **Moms i överföringsorder**, konfigurera momsberäkningstjänstens parametrar för lager och konfigurera grundläggande momsparametrar.
3. **Lagerinställningar:** Ställ in lagerkonfigurationen för överföringsordertransaktioner.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Ställa in RCS för moms- och överföringsordertransaktioner

Följ dessa steg för att ställa in momsen som ingår i en överföringsorder. I exemplet som visas här är överföringsordern från Nederländerna till Belgien.

1. På sidan **Momsfunktioner**, på fliken **Versioner**, välj versionen av utkastfunktionen och välj sedan **Redigera**.

2. På sidan **Inställning av momsfunktioner** på fliken **Momskoder**, välj **Lägg till** för att skapa nya momskoder. I det här exemplet skapas tre momskoder: **NL-undantagen**, **BE-RC-21** och **BE-RC+21**.

    - När en överföringsorder levereras från ett lagerställe i Nederländerna används den momsbefriade momskoden (**NL-undantagen**) använd.
      
        Skapa momskoden **NL-undantagen**.
        1. Välj **Lägg till**, ange **NL-undantag** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Ange **Är undantagen** till **Ja** i avsnittet **Allmänt**.
        6. I fältet **Momsbefrielsekod** ange **EC**.

    - När en överföringsorder tas emot på ett belgiskt lagerställe används omvänd momsmekanism med hjälp av momskoderna **BE-RC-21** och **BE-RC+21**.
        
        Skapa momskoden **BE-RC-21**.      
        1. Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Ange **-21** i fältet **Momssats**.
        6. Ange **Är återförd avgift** till **Ja** i avsnittet **Allmänt**.
        7. Välj **Spara**.
        
        Skapa momskoden **BE-RC+21**.
        1. Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.
        2. Välj **Efter nettobelopp** i fältet **Momskomponent**.
        3. Välj **Spara**.
        4. Välj **Lägg till** i tabellen **Kurs**.
        5. Ange **21** i fältet **Momssats**.
        6. Välj **Spara**.

3. Definiera momsgrupp.
    1. Markera **Hantera kolumner** och markera sedan radfältet **Momsgrupp**.
    2. Välj **->** och välj sedan **OK**.
    3. Välj **Lägg till** för att lägga till en momsgrupp.
    4. I kolumnen **Momsgrupp** anger du **AR-EU** och väljer sedan momskoden **NL-Momsbefrielse**.
    5. Välj **Lägg till** för att lägga till en momsgrupp.
    6. I kolumnen **Momsgrupp**, ange **RC-VAT** och välj sedan **BE-RC-21** och **BE-RC+21** momskoderna.
4. Definiera artikelmomsgrupp.
    1. Markera **Hantera kolumner** och markera sedan radfältet **Artikelmomsgrupp**.
    2. Välj **->** och välj sedan **OK**.
    3. Välj **Lägg till** för att lägga till en artikelmomsgrupp.
    4. Ange **FULL** kolumnen **Artikelmomsgrupp**. Välj momskoderna **BE-RC-21**, **BE-RC+21** och **NL-Momsbefrielse**.
5. Definiera tillämplighet för momsgruppen.

    1. Markera **Hantera kolumner** och välj sedan kolumner som ska användas för att bygga tillämplighetsregler.

        > [!NOTE]
        > Se till att du lägger till kolumnerna **Affärsprocess** och **Momsriktningar**. Båda kolumnerna är nödvändiga för funktionen för moms i överföringsorder.

    2. Lägg tillämplighetsregler. Lämna inte fältet **Momsgrupp** tomt.
        
        Lägg till en ny regel för överföringsorderförsändelse.
        1. Välj **Lägg till** i tabellen **Tillämplighetsregler**.
        2. I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.
        3. I fältet **Sänd från land/region**, ange **NLD**.
        4. I fältet **Sänd till land/region**, ange **BEL**.
        5. I fältet **Momsriktning**, välj **Utgång** för att göra regeln tillämplig för överföring av orderförsändelse.
        6. I fältet **Momsgrupp**, välj **AR-EU**.
        
        Lägg till en annan regel för inleverans av överföringsorder.
        
        1. Välj **Lägg till** i tabellen **Tillämplighetsregler**.
        2. I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.
        3. I fältet **Sänd från land/region**, ange **NLD**.
        4. I fältet **Sänd till land/region**, ange **BEL**.
        5. I fältet **Momsriktning**, välj **Ingång** för att göra regeln tillämplig för inleverans av överföringsorder.
        6. I fältet **Momsgrupp**, välj **RC-VAT**.

6. Definiera tillämplighet för artikelmomsgruppen.

    1. Markera **Hantera kolumner** och välj sedan kolumner som ska användas för att bygga tillämplighetsregler.
    2. Lägg tillämplighetsregler. Lämna inte fältet **Artikelmomsgrupp** tomt.
        
        Lägg till en ny regel för överföringsorderförsändelse och kvitto.
        1. På sidan **Lägg till**, välj **Lägg till**.
        2. I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.
        3. I fältet **Artikelmomsgrupp**, välj **FULL**.
7. Slutför och publicera den nya versionen av skattefunktionen.


## <a name="set-up-finance-for-transfer-order-transactions"></a>Ställa in Finance för moms- och överföringsordertransaktioner

Följ dessa steg för att aktivera och ställa in skatter för överföringsorder.

1. I Finance, gå till **Arbetsytor** > **Funktionshantering**.
2. I listan, hitta och välj funktionen **Moms i överföringsorder** och välj sedan **Aktivera nu** för att aktivera den.

    > [!IMPORTANT]
    > Funktionen **Moms i överföringsorder** är helt beroende av momberäkningstjänst. Det kan därför endast aktiveras när du har installerat momberäkningstjänst.

    ![Moms i överföringsfunktionen.](../media/image7.png)

3. Aktivera momberäkningstjänst och välj affärsprocessen **Lager**.

    > [!IMPORTANT]
    > Du måste genomföra det här steget för varje juridisk person i Finance där du vill att momberäkningstjänsten och momsfunktionerna i överföringsorder ska vara tillgängliga.

    1. Gå till **Moms** > **Inställningar** > **Momsinställning** > **Parametrar för momsberäkning**.
    2. I fälten **Affärsprocess**, välj **Lager**.

4. Kontrollera att omvänd avgiftsmekanism har ställts in. Gå till **Redovisning** \> **Inställning** \> **Parametrar** och sedan på **Omvänd debitering**, kontrollera att alternativet **Aktivera omvänd moms** anges **Ja**.

    ![Aktivera alternativet för återfört tillägg.](../media/image9.png)

5. Kontrollera att de relaterade momskoderna, momsgrupperna, artikelmomsgrupperna och momsregistreringsnumren har ställts in i Finance enligt momsberäkningstjänstens riktlinjer.
6. Ställ in ett mellanliggande transitkonto. Detta steg är endast nödvändigt när den skatt som tillämpas på en överföringsorder, inte gäller för en momsbefriad eller återförd avgiftsmekanism.

    1. Gå till **Moms** > **Inställningar** > **Moms** > **Redovisningsbokföringsgrupper**.
    2. I fältet **mellanliggande transit**, välj redovisningskonto.

       ![Ställa in ett mellanliggande transitkonto.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Ställ in grundläggande inventering för moms- och överföringsordertransaktioner

Följ dessa steg om du vill ställa in grundläggande lager för att aktivera överföringsordertransaktioner.

1. Skapa från- och leveransplatser för dina lagerställen i olika länder eller regioner och lägg till den primära adressen för respektive webbplats.

    1. Gå till **Lagerstyrning** > **Konfiguration** > **Distributionslager** > **Platser**.
    2. Välj **Ny** för att skapa den webbplats som du tilldelar till ett lager senare.
    3. Upprepa steg 2 för alla andra siter som du måste skapa.

    > [!NOTE]
    > En av de webbplatser som du skapar ska få namnet **Transit**. Senare tilldelar du den här siten till transitlagret så att momsrelaterade lagerverifikationer kan bokföras i "skeppa" och "ta emot"-transaktioner för överföringsorder. Adressen till transitplatsen är inte relevant för momsberäkningen. Därför kan du lämna det tomt.

    ![Konfigurera in webbplatser.](../media/image11.png)

2. Skapa leverans-, transit- och leverans till lagerställen. All adressinformation som finns i ett lagerställe åsidosätter siteadressen vid momsberäkningen.

    1. Gå till **Lagerstyrning** > **Inställningar** > **Lagerställe** > **Lagerställen**.
    2. Välj **Ny** för att skapa ett lager och tilldela det till motsvarande webbplats.
    3. Upprepa steg 2 om du vill skapa ett lagerställe för respektive webbplats efter behov.

       ![Konfigurera lagerställen.](../media/image12.png)

    > [!NOTE]
    > För ett lagerställe för leverans från måste ett transitlager väljas i fältet **Transitlagerställe** för överföringsordertransaktioner.
    >
    > ![Välja ett transitlager.](../media/image13.png)

3. Kontrollera att konfiguration av lagerbokföring har ställts in för överföringsordertransaktioner.

    1. Gå till **Lagerhantering** > **Inställningar** > **Bokföring** > **Bokföring**.
    2. Kontrollera på fliken **Lager**, verifiera att ett huvudbokskonto är konfigurerat för båda bokföring av **lagerutleverans** och **lagerinleverans**.

        ![Konfigurera in bokföring av lagerutleverans och lagerinleverans.](../media/image14.png)

    3. Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern skuld**.

        ![Konfigurera in bokföring av enhetsintern reskontra.](../media/image15.png)

    4. Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern fordran**.

        ![Ställa in bokföring av enhetsintern reskontra.](../media/image16.png)
        
        
  [!INCLUDE[footer-include](../../../includes/footer-banner.md)]
