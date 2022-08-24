---
title: Fransk Intrastat
description: Det här ämnet innehåller information om Intrastat-deklaration i Frankrike.
author: AdamTrukawka
ms.date: 07/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 83af3cf304772085c5a6f0943ab5196fcc0208c9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287030"
---
# <a name="french-intrastat"></a>Fransk Intrastat

[!include[banner](../includes/banner.md)]

Företag i Frankrike som är registrerade för moms (VAT) och som handel med andra EU-länder måste deklarera utbytet av varor och tjänster till och från Frankrike. Declaration d'exchanges de biens (Declaration of Trade in Goods eller DEB) är en kombination av listan över försäljning inom EU och Intrastat-rapporten. Du måste skicka in den här rapporten varje månad för all inomeuropeisk försäljning av varor.

Du kan generera DEB-rapporten i något av två elektroniska textfilformat: SAISUNIC 330 eller INTRACOM-format.

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i SAISUNIC 330-format. Registret visar också rapportnivån i fältet. Fältet kan vara **4** (förenklat), **1** (fullständig) eller båda.

| **Fält**                   | **Rapportnivå** |
|-----------------------------|------------------|
| Referensperiod         | 4, 1              | 
| Antal deklarationer       | 4, 1              |
| Radnummer                 | 4, 1              |
| Landskod ISO (FR)       | 4, 1              | 
| Komplementskod          | 4, 1              | 
| Siren-nummer                | 4, 1              | 
| Moms kundkod        | 4, 1              | 
| Riktningskod              | 4, 1              |
| Transaktionstyp            | 4, 1              | 
| Ansvarsnivå            | 4, 1              |
| Artikelkod              | 1                | 
| Nationell NGP                | 1                | 
| Region (Avdelning)         | 1                |
| Typ av transaktion       | 1                | 
| Ursprungsland      | 1                | 
| Ursprungsland, importer | 1                | 
| Slutdestination, exporter | 1                | 
| Fakturavärde               | 4, 1              | 
| Statistiskt värde           | 1                |
| Nettovikt                  | 1                | 
| Ytterligare enheter            | 1                |
| Transportkod              | 1                | 

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i INTRACOM-format.
Registret visar också rapportnivån i fältet. Fältet kan vara **4** (förenklat), **1** (fullständig) eller båda.

| **Fält**                   | **Rapportnivå**   | 
|-----------------------------|--------------------|
| Kod                        | 4, 1               | 
| Antal deklarationer       | 4, 1               |
| Antal rader              | 4, 1               | 
| Siren                       | 4, 1               |
| Region (Avdelning)         | 1                  |          
| Transportkod              | 1                  |          
| Ursprungsland           | 1                  |            
| Typ av transaktion       | 1                  |             
| Fakturavärde               | 4, 1               |             
| Leveranssätt           | 1                  |           
| Transaktionstyp            | 4, 1               |            
| Ansvarsnivå            | 4, 1               |           
| Artikelkod              | 1                  |            
| Nationell NGP                | 1                  |            
| Nettovikt                  | 1                  |            
| Statistiskt värde           | 1                  |            
| Ytterligare enheter            | 1                  |            
| Ursprungsland, importer | 1                  |            
| Slutdestination, exporter | 1                  |            
| Moms kundkod        | 4, 1               |            
| Komplementskod          | 4, 1               |           
| Referensperiod         | 4, 1               |         

### <a name="set-up-intrastat"></a>Ställa in Intrastat

1.  I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationen:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat-INTRACOM (FR)
    - Intrastat SAISUNIC (FR)

    Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  I Dynamics 365 Finance, gå till **Skatt** > **Inställningar** >  **Utrikeshandeln** > **Utländska handelsparametrar** och följ dessa steg:

    1. På fliken **Intrastat** på snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)** eller **Intrastat SAISUNIC (FR)**.
    2. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
    3. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
    4. På snabbflikarna **Allmänt** i fältet **Transaktionskod**, välj koden som används för överföring av varor.
    5. I fältet **Kreditfaktura**, välj koden som används för retur av varor.
    6. I fältet **Ansvarsnivå för export**, ange detaljnivån för exportrapporten. Den nivå du väljer påverkar vilka rader som visas i rapporten. Mer information finns i tabellerna i början av detta ämne.

3. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**, välj ditt företag och följ stegen nedan:

    1. På snabbfliken **registreringsnummer** i fältet **NAF-kod** ange din NAF-kod. Mer information finns i [FR-00003 NAF-koder och Siret-nummer](tasks/fr-00003-naf-codes-siret-numbers.md).
    2. På snabbfliken **Utländsk handel och logistik** i avsnittet **Intrastat** ange fälten **momsregistreringsnummer för export** och **momsregistreringsnummer för import**.
    3. På **Momsregistrering** snabbfliken i **Momsregistreringsnummer** fältet, ange ditt företags momsregistreringsnummer.

4. Om du vill ange NAF-koder och momsregistreringsnummer för kunder går du till **Kundreskontra** > **Kunder** > **Alla kunder** och följer stegen nedan:

    1. Välj en kund.
    2. På snabbfliken **Faktura och leverans** i avsnittet **Moms** i fältet **Momsregistreringsnummer** ange kundens momsregistreringsnummer.
    3. På snabbfliken **Försäljningsdemografi** i fältet **Franskt Siret**, ange företagets Siret-nummer.
    4. I fältet **NAF-kod**, ange företagets NAF-kod.
    5. Upprepa de här stegen för andra kunder.

5. Om du vill ange NAF-koder och momsregistreringsnummer för leverantörer går du till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer** och följer stegen nedan:

    1. Välj en leverantör.
    2. På snabbfliken **Faktura och leverans** i avsnittet **Moms** i fältet **Momsregistreringsnummer** ange leverantörens momsregistreringsnummer.
    3. På snabbfliken **Inköpsdemografi** i fältet **Franskt Siret**, ange företagets Siret-nummer.
    4. I fältet **NAF-kod**, ange företagets NAF-kod.
    5. Upprepa de här stegen för andra leverantörer.

6. Gå till **Tax** > **Inställningar** > **Utländsk handel** > **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För franska Intrastat, välj **Statistikprocedur**, **Ursprungsstat**, **Ursprungsland/region**, **Leveransvillkor**, **Transport**, **Korrigering**, **Land/region**, **Ursprungsregion/destination**, **Riktning**, **Land/region för avsändare**, **Tillstånd för avsändare**, **Delstat**, **Transaktionskod** och **Vara**.

7. Gå till **Lagerstyrning** > **Inställningar** > **Lagerställe** > **Lagerställen**, välj ett lagerställe och följ sedan dessa steg:

    1. På snabbfliken **Adresser** väljer du **Lägg till** eller **Redifera**.
    2. I dialogrutan, i fältet **Ort** välj lagerställets ort. Delstatens ort används som en region för din DEB-rapport.

### <a name="ngp-codes"></a>NGP-koder

I DEB-rapporten består kodifieringen av produkter av följande element:

  - Den åttasiffriga CN8-kod som representerar EU-kodens tariff- och statistiktaxa.
  - Den ensiffriga nationella artikelkoden Nomenclature Générale des Produits (NGP) om tillämpligt.

Under 2021 gäller NGP endast tre typer av produkter:

  - Några produkter från kor, får och getter
  - Militär utrustning
  - Franska viner

 Du måste ställa in NGP-koderna och tilldela dem till relaterade produkter. Fältet **NGP** ställs sedan automatiskt in på sidan **Intrastat-journal**.

#### <a name="set-up-an-ngp-code"></a>Ställa in en NGP-kod

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **NGP-koder**.
2. I åtgärdsfönstret väljer du **Ny** för att skapa en NGP-kod.
3. I fältet **NGP** ange en ensiffrig kod.
4. I fältet **Beskrivning**, ange en beskrivning för koden.

#### <a name="assign-an-ngp-code-to-a-product"></a>Tilldela en NGP-kod till en produkt

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. I rutnätet väljer du en produkt.
3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **NGP** väljer du lämplig NGP-kod.

## <a name="intrastat-journal"></a>Intrastat-journal

Gå till **Moms** > **Deklarationer** > **Utländsk** **handel** > **Intrastat** för att hantera dina transaktioner som är tillämpliga på utrikeshandel med EU-länder. Mer information finns i [Intrastat, översikt](emea-intrastat.md).

Kolumnen **NGP** är specifik för Frankrike. Det visar NGP-koden för den produkten. Om NGP inte kan användas för en produkt visas **0** (noll). Du kan justera NGP-koden. Välj transaktionen och sedan på **Allmän** i avsnittet **Koder** i fältet **NGP** välj önskad NGP -kod.

### <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter, projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller destinationsregion (för utförsel) eller försändelse (vid införsel) kommer att överföras.

Eftersom DEB-rapporten är en kombination av listan över försäljning inom EU och Intrastat-rapporten, innehåller den även *trepartstransaktioner*, där en direktleverans görs från ett EU-land (part A) till ett annat EU-land (part C) och en fransk juridisk enhet (part B) är den mitt i trepartsaffären.

### <a name="generate-a-deb-intrastat-report"></a>Skapa DEB-rapport (Intrastat)

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
3. I dialogrutan **Intrastat-rapport** anger du följande fält.

    | Fält            | beskrivning                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Från-datum        | Välj startdatumet för rapporten.                                                                                               |
    | Till-datum          | Välj slutdatumet för rapporten.                                                                                                 |
    | Generera fil    | Ställ in det här alternativet till **Ja** om du vill generera en .txt-filen.                                                                                 |
    | Filnamn        | Ange namnet på .txt-filen för Intrastat-rapporten.                                                                          |
    | Generera rapport  | Ställ in det här alternativet till **Ja** om du vill generera en .xml-fil.                                                                                |
    | Rapportfilnamn | Ange önskat namn.                                                                                                            |
    | Bara korrigeringar | Ställ in det här alternativet till **ja** att bara rapportera rättelser. Ange **Nej** om du vill rapportera både normala transaktioner och korrigeringar.         |
    | Riktning        | Välj **Införsel** för en rapport om inomeuropeiska införslar. Välj **Utförsel** för en rapport om inomeuropeiska införslar. |

## <a name="example"></a>Exempel

Följande exempel visar hur du ställer in Franska Intrastat och skapar DEB-rapporten. Använd **DEMF** juridiska personen.

1. I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationsformat:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat-INTRACOM (FR)

2. Ställ in en transaktionskod i Finance:

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I fältet **Transaktionskod** ange **11**.
    4. I fältet **Namn** anger du **inköp eller försäljning**.
    5. Klicka på **Spara** i åtgärdsfönstret.

3.  Ställ in en produkthierarki:

    1. Gå till **Produktinformationshantering** > **Inställningar** > **Kategorier och attribut** > **Kategorihierarkier**.
    2. Välj **Intrastat** i rutnätet. I Åtgärdsfönstret, på fliken **kategorihierarki**, i gruppen **underhåll**, markerar du **redigera**.
    3. I åtgärdsfönstret klickar du på **Ny kategorinod**.
    4. I fältet **Namn** anger du **Autres Libournais**.
    5. I fältet **Kod** ange **2204 21 42**
    6. Klicka på **Spara** i åtgärdsfönstret.

4. Gå till **Moms** > **Inställningar** > **Utrikeshandeln** > **Utländska handelsparametrar** och följ dessa steg:

    1. På fliken **Intrastat** på fliken **Allmänt** i fältet **Transaktionskod**, välj **11**.
    2. På snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)**.
    3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
    4. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.

5. Ställa in en NGP-kod:

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **NGP-koder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I fältet **NGP** ange **8**.
    4. I fältet **Namn på beskrivning** ange **NGP 8**.
    5. Klicka på **Spara** i åtgärdsfönstret.

6. Tilldela en NGP-kod till en produkt:

    1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
    2. Välj **0001** i rutnätet.
    3. På snabbfliken **Utländsk handel** i fältet **NGP**, välj **8**.
    4. I fältet **Vara** välj **2204 21 42**.
    5. Klicka på **Spara** i åtgärdsfönstret.

7. Skapa en försäljningsorder som inkluderar den nya produkten:

    1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I dialogrutan **Skapa** **försäljning** **order** i avsnittet **Kund** i **Kund** **kontot**, välj **100001**.
    4. I avsnittet **Adress** i fältet **Leveransadress** välj plustecknet (**+**) för att skapa en adress.
    5. I dialogrutan **Ny adress** i fältet **Namn på beskrivning** ange **Tyskland**.
    6. I fältet **Land/region** välj **DEU**.
    7. Välj **OK**.
    8. I dialogrutan **Skapa försäljningsorder** välj **OK**.
    9. På snabbfliken **Försäljning** **orderrader** i fältet **Artikelnummer** välj **0001**.
    10. Klicka på **Spara** i åtgärdsfönstret.
    11. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
    12. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**. Du kan sedan välja **OK** för att bokföra fakturan.

8.  Skapa DEB-rapporten:

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**:
    2. I åtgärdsfönster. välj **Överför**.
    3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**. Välj sedan **OK**.
    4. Sortera transaktionerna efter fältet **Datum**. Den översta transaktionen är resultattransaktionen. Fältet **NGP** ställs automatiskt in.
    5. I åtgärdsfönstret väljer du **Utdata** &gt; **Rapport**.
    6. I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.
    7. Ställ in alternativet **Exportalternativ** ange **Generera fil** till **Ja**.
    8. I fältet **Filnamn** anger du ett namn som krävs.
    9. Välj **OK** och granska rapporten.

