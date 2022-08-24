---
title: Tysk Intrastat
description: Det här ämnet innehåller information om Intrastat-deklaration i Tyskland.
author: AdamTrukawka
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: ae978b28098d92d84415c29bbe76157144f862d8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269447"
---
# <a name="german-intrastat"></a>Tysk Intrastat

[!include [banner](../includes/banner.md)]

Sidan **Intrastat** används för att generera och rapportera information om handel mellan länder i EU. Den tyska Intrastat-deklarationen innehåller information om handel med varor för rapportering. Rapporten formateras enligt de tyska myndigheternas riktlinjer som visas på formatsidan [6.2 för fildeklarationer i formatsidan INSTAT/XML](https://www-idev.destatis.de/idev/doc/intra_en/hilfe6_2.html). 

I följande tabell visas fälten som ingår i den tyska Intrastat-deklarationen.

| Fält | Utförsel | Införsel |
|-------------------------|-------------------------|-------------------------|
| Referensperiod | X | X |
| Riktningskod | X | X |
| Valuta för Intrastat-deklarationen</br>**Obs!** Denna valuta är <em>redovisningsvalutan</em>. | X | X |
| Artikelkod | X | X |
| Artikelnamn | X | X |
| Kod för fyllnadsenhet | X | X |
| Försändelse-/destinationsstat | X | X |
| Nettovikt | X | X |
| Kompletterande enheter | X | X |
| Ursprungsland |  | X |
| Fakturabelopp | X |  |
| Statistiskt värde | X | X |
| Typ av transaktioner | X | X |
| Transportlägen | X | X |
| Regionkod</br>**Notering:**</br><ul></br><li>Om landet eller regionen där ursprunget är Tyskland, och fakturan gäller för utförsel, visas en Intrastat-kod för ursprungsstat.</li></br><li>Om landet eller regionen där ursprunget inte är Tyskland, och fakturan gäller för utförsel, visas kod **99**. </li></br><li>Om fakturan är för införsel visas en Intrastat-kod för staten.</li></br></ul> | X | X |
| Portkod för Port/Flygplats/Inland | X | X |
| Leveransvillkor | X | X |


## <a name="set-up-intrastat"></a>Ställa in Intrastat

1. Ställ in företagets koder.

    1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
    2. På snabbfliken **Utländsk handel och logistik** i avsnittet **Identifiering** i fältet **DVR** ange ID för utbytesavtal. Detta ID inkluderas i rapporten.
    3. I fältet **momsregistreringsnummer för export** ange ditt företags momsnummer för export.
    4. I fältet **momsregistreringsnummer för import** ange ditt företags momsnummer för import.
    5. Ange i fältet **Intrastat-kod** den Intrastat-kod som tilldelas den juridiska personen.
    6. På **Momsregistrering** snabbfliken i **Momsregistreringsnummer** fältet, ange ditt företags momsregistreringsnummer.

    > [!NOTE]
    > Om du genererar en Intrastat-rapport för koncernbolag anger du i fältet **Momsregistreringsnummer** momsregistreringsnumret för ditt moderbolag.

2. I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationen.

    - Intrastat-modell
    - Intrastat-rapport
    - INSTAT-XML
    - INSTAT XML (DE)

3. Konfigurera utländska handelsparametrar:

    1. I Dynamics 365 Finance går du till **Skatt** > **Inställningar** > **Utländska handelsparametrar**.
    2. På fliken **Intrastat** på snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat XML (DE)**.
    3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
    4. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
    5. I fältet **Transaktionskod** väljer du transaktionskod för egenskapsöverföringar. Du använder den här koden för transaktioner som producerar faktiska eller planerade överlåtelser av egendom mot ersättning (ekonomisk eller annan). Du använder det även för korrigeringar.
    6. I fältet **Kreditfaktura** väljer du transaktionskod för retur av varor.
    7. Välj kontaktperson för Intrastat-rapporten i fältet **Arbetare**. Alternativt kan du på fliken **Kontakt** ange eller välja värden i fälten **Namn**, **Telefon**, **Fax**, **E-post**, och **Internet-adress**. Dessa fält är inkluderade i rapporten.
    8. Välj Intrastat-utfärdare i fältet **utfärdare**.
    9. Gå till **Skatt** > **Indirekt moms** > **Moms** > **Skattemyndigheter** och ange följande information för Intrastat-myndigheten som du valde i föregående steg:

       - Myndighets-ID
       - Adress
       - Kontaktinformation

    10. På fliken **Egenskaper för land/region** i fältet **Land/region** anger alla länder eller regioner som ditt företag gör affärer med. För varje land eller region i fältet **Typ av land/region** väljer du **EU**, så att landet eller regionen visas i din Intrastat-rapport.

4. Ställa in regionskoder.

    1. Gå till **Organisationsadministration** > **Global adressbok** > **Adresser** > **Inställning av adress**.
    2. På fliken **Delstat/region** i fältet **Land/region**, välj **DEU** och välj **Tillämpa filter**.
    3. Välj tillståndet i rutnätet. Sedan **Intrastat-kod** field, ange den unika Intrastat-koden.

5. Ställ in ursprungsadressen för en produkt.

    1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
    2. I rutnätet väljer du en produkt.
    3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Ursprungsland**, välj **DEU**.

6. Gå till **Tax** > **Inställningar** > **Utländsk handel** > **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För tysk Intrastat, välj följande fält:

    - Artikel
    - Land/region
    - Korrigering
    - Riktning
    - Leveransvillkor
    - Faktura
    - Ursprungsland/-region
    - Lastningsplats
    - Avsändarens land/region
    - Avsändarens stat
    - Statistikprocedur
    - Transaktionskategori
    - Transport
    - Momsregistreringsnummer

### <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter **,** projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller destinationsregion (för utförsel) eller försändelse (vid införsel) kommer att överföras.

Du kan också ange transaktioner manuellt genom att välja **Ny** i åtgärdsfönstret.

### <a name="generate-an-intrastat-report"></a>Skapa Intrastat-rapport

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
3. I dialogrutan **Intrastat-rapport** anger du följande fält.

    | Fält | beskrivning |
    |-------------------------|-------------------------|
    | Från-datum | Välj startdatumet för rapporten. |
    | Till-datum | Välj slutdatumet för rapporten. |
    | Generera fil | Ställ in det här alternativet till **Ja** om du vill generera en .xml-fil. |
    | Filnamn | Lämna det här fältet tomt. Filnamnet genereras automatiskt och består av värdet av **&lt;envelopeId&gt;** XML-tagg plus filnamnstillägget **.xml**.</br>Värdet **&lt;envelopeId&gt;** är en sammanfogning av följande element i denna ordning:</br><ol type="1"></br><li>Värdet på tagget **&lt;interchangeAgreementId&gt;**</li></br><li>Ett bindestreck (-)</li></br><li>Värdet på fliken **&lt;referencePeriod in YYYYMM&gt;**</li></br><li>Ett bindestreck (-)</li></br><li>Värdet på fliken **&lt;Envelope/DateTime/date in YYYYMMDD&gt;**</li></br><li>Ett bindestreck (-)</li></br><li>Värdet på fliken **&lt;Envelope/DateTime/time in hhmm&gt;**</li></br></ol> |
    | Riktning | <ul></br><li>Välj **Införsel** för en rapport om inomeuropeiska införslar.</li></br><li>Välj **Utförsel** för en rapport om inomeuropeiska införslar.</li></br><li>Välj **Båda** för att rapportera om både ankomster och avsändningar.</li></br></ul> |
    | Skatteregistreringsnummer | Ange det registreringsnummer som ska användas för att generera avsändarens ID-kod, om numret skiljer sig från det juridiska personens momsregistreringsnummer. |


## <a name="example"></a>Exempel

I det här exemplet visas hur du bokför införsel och utförsel för Intrastat. Använd **DEMF** juridiska personen.

1. I [LCS](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner de senaste versionerna av följande ER-konfigurationer för Intrastat-deklarationsformatet:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat XML
    - Intrastat XML (DE)

2. Skapa transaktionskoder.

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I fältet **Transaktion** **kod** ange **21**.
    4. I fältet **Namn** anger du **retur av varor**.
    5. Klicka på **Spara** i åtgärdsfönstret.

3. Ställ in myndighetens identifieringsnummer.

    1. Gå till **Skatt** > **Indirekta skatter** > **Moms** > **Skattemyndigheter**.
    2. Välj **TA**.
    3. I fältet **Myndighetsidentifiering** ange **123**.

4. Ställa in regionskoder.

    1. Gå till **Organisationsadministration** > **Global adressbok** > **Adresser** > **Inställning av adress**.
    2. På fliken **Delstat/region** i fältet **Land/region**, välj **DEU** och välj **Tillämpa filter**.
    3. Välj i rutnätet **BE** och ange sedan **Intrastat-kod** ange **11**.
    4. Klicka på **Spara** i åtgärdsfönstret.

5. Konfigurera utländska handelsparametrar.

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
    2. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **11**.
    3. I fältet **Kreditfaktura** välj **21**.
    4. I fältet **Myndighet**, välj **TA**.
    5. På snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **INSTAT XML (DE)**.
    6. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
    7. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
    8. På fliken **Egenskaper för land/region**, välj **Ny**.
    9. I fältet **Part för land/region** välj **FRA**.
    10. I fältet **Lands-/regiontyp**, välj **EU**.

6. Tilldela en artikelkod till en produkt och ange produktens ursprung. Fälten **Artikelkod**, **Ursprungsland/region** och **Ursprungsstat** ställs sedan in automatiskt på försäljningsorder och inköpsorder när du väljer produkten.

    1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
    2. Välj **D0001** i rutnätet.
    3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **920 20 34**.
    4. I avsnittet **Ursprung** i fältet **land/region**, välj **DEU**.
    5. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **12**.
    6. Klicka på **Spara** i åtgärdsfönstret.

7. Tilldela transport till ett leveranssätt. Transportkoden ställs sedan automatiskt in för order när du väljer leveranssätt.

    1. Gå till **Anskaffning och källa** > **Inställningar** > **Fördelning** > **Leveranssätt**.
    2. Välj i listan **10**.
    3. På snabbfliken **Utländsk handel** i fältet **Transport**, välj **01**.

8. Skapa en försäljningsorder med en EU-kund.

    1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I dialogrutan **Skapa försäljningsorder** på **Kund** i avsnitt **Kund** i fält **Kundkontot**, välj **DE-012**.
    4. På snabbfliken **Allmänt** i avsnittet **Lagringsdimensioner** i fältet **Webbplats**, välj **1**.
    5. I fältet **Lagerställe**, välj **11**.
    6. Välj **OK**.
    7. På fliken **Rubrik** på snabbfliken **Utländsk handel** i fältet **Port**, välj **53**.
    8. På fältet **Statistisk procedur**, välj **31710**.
    9.  På fliken **Rader** på snabbfliken **Försäljningsorder** **rader** i fältet **Artikelnummer**, välj **D0001**. I fältet **Kvantitet**, ange **10**.
    10. På snabbfliken **Raddetaljer**, på fliken **Utländsk handel** kontrollerar du att fälten **Transaktionskod**, **Transport**, **Artikel** och **Ursprungsland/-region** ställts in automatiskt.
    11. Klicka på **Spara** i åtgärdsfönstret.
    12. I åtgärdsrutan på fliken **Faktura** i avsnittet **Generera**, klicka på **Faktura**.
    13. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**.
    14. Välj **OK** när du vill bokföra faktura.

9.  Överför transaktionen till Intrastat-journalen och granska resultatet.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**.
    4. Välj **filter**.
    5. I dialogrutan **Intrastat-filter**, fliken **Intervall**, välj den första raden och se till att **Fält** anges till **Datum**.
    6. Välj aktuellt datum i fältet **Kriterier**.
    7. Välj **OK** för att stänga dialogrutan **Intrastat-filter**.
    8. Välj **OK** för att stänga dialogrutan **Intrastat (överför)** och granska resultatet. Raden representerar den försäljningsorder som du skapade tidigare.

        ![Rad som representerar försäljningsordern på Intrastat-sidan](media/intrastat_deu_1.png)

10. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Försäljningsorderdetaljer på fliken Allmänt på Intrastat-sidan](media/intrastat_deu_2.png)

11. Skapa en kreditfaktura mot en försäljningsorder.

    1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I dialogrutan **Skapa försäljningsorder** på **Kund** i avsnitt **Kund** i fält **Kundkontot**, välj **DE-012**.
    4. På snabbfliken **Allmänt** i avsnittet **Lagringsdimensioner** i fältet **Webbplats**, välj **1**.
    5. I fältet **Lagerställe**, välj **11**.
    6. På fliken **Rubrik** på snabbfliken **Utländsk handel** i fältet **Port**, välj **53**.
    7. På fältet **Statistisk procedur**, välj **31710**.
    8. På fliken **Rader** på snabbfliken **Försäljningsorder** **rader** i fältet **Artikelnummer**, välj **D0001**. I fältet **Kvantitet**, ange **-2**.
    9. På snabbfliken **Radinformation** på fliken **Utländsk handel** i fältet **Transaktionskod**, välj **21**.
    10. Kontrollera att fälten **Transport**, **Artikel** och **Ursprungsland/-region** ställs in automatiskt.
    11. Klicka på **Spara** i åtgärdsfönstret.
    12. I åtgärdsrutan på fliken **Faktura** i avsnittet **Generera**, klicka på **Faktura**.
    13. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**.
    14. Välj **OK** när du vill bokföra faktura.

12. Överför transaktionen till Intrastat-journalen och granska resultatet.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**.
    4. Välj **OK** för att stänga dialogrutan **Intrastat (överför)** och granska resultatet. En ny rad där fält **Riktning** anges till **Införsel** har lagts till.            
        Den här raden representerar den fysiska returen av varor.

        ![Rad för fysisk retur av varor på Intrastat-sidan](media/intrastat_deu_3.png)

13. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Information om fysisk retur av varor på fliken Allmänt på Intrastat-sidan](media/intrastat_deu_4.png)

14. Skapa en korrigering med hjälp av en försäljningsorder:

    1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I dialogrutan **Skapa försäljningsorder** på **Kund** i avsnitt **Kund** i fält **Kundkontot**, välj **DE-012**.
    4. På snabbfliken **Allmänt** i avsnittet **Lagringsdimensioner** i fältet **Webbplats**, välj **1**.
    5. I fältet **Lagerställe**, välj **11**.
    6. På fliken **Rubrik** på snabbfliken **Utländsk handel** i fältet **Port**, välj **53**.
    7. På fältet **Statistisk procedur**, välj **31710**.
    8. På fliken **Rader** på snabbfliken **Försäljningsorder** **rader** i fältet **Artikelnummer**, välj **D0001**. I fältet **Kvantitet**, ange **-3**.
    9. På snabbfliken **Radinformation** på fliken **Utländsk handel** i fältet **Transaktionskod**, välj **11**.
    10. Kontrollera att fälten **Transport**, **Artikel** och **Ursprungsland/-region** ställs in automatiskt.
    11. Klicka på **Spara** i åtgärdsfönstret.
    12. Se till att fältet **Transaktionskategori** anges 11.
    13. I åtgärdsrutan på fliken **Faktura** i avsnittet **Generera**, klicka på **Faktura**.
    14. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**.
    15. Välj **OK** när du vill bokföra faktura.

15. Överför transaktionen till Intrastat-journalen och granska resultatet:

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**.
    4. Välj **OK** för att stänga dialogrutan **Intrastat (överför)** och granska resultatet. En ny rad där en bockmarkering visas i kolumnen **Korrigering** har lagts till.

        ![Rad för korrigeringen på Intrastat-sidan](media/intrastat_deu_5.png)

16. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Detaljer om korrigeringen på fliken Allmänt på Intrastat-sidan](media/intrastat_deu_6.png)

17. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
18. I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.
19. I avsnittet **Export** **alternativet** ange **Generera fil** till **Ja**.
20. I fältet **Filnamn** anger du ett namn som krävs.
21. Välj **OK** och granska rapporten som genereras. Tabellen nedan visar värdena i exempelrapporten.

    | **Namn**                  | **Försäljningsfaktura**  |   **Korrigering**   | **Kreditfaktura** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | D                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Talare            | Talare            | Talare         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

