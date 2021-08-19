---
title: Fransk Intrastat
description: Det här ämnet innehåller information om Intrastat-deklaration i Frankrike.
author: andosip
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: d38169d73caf93a0f81e832293916c9e54855a1848fe6ab409a670a4bf707b7c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713146"
---
# <a name="french-intrastat"></a>Fransk Intrastat

[!include[banner](../includes/banner.md)]

Företag i Frankrike som är registrerade för moms (VAT) och som handel med andra EU-länder måste deklarera utbytet av varor och tjänster till och från Frankrike. Declaration d'exchanges de biens (Declaration of Trade in Goods eller DEB) är en kombination av listan över försäljning inom EU och Intrastat-rapporten. Du måste skicka in den här rapporten varje månad för all inomeuropeisk försäljning av varor.

Du kan generera DEB-rapporten i något av två elektroniska textfilformat: SAISUNIC 330 eller INTRACOM-format.

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i SAISUNIC 330-format.

| **Fält**                   | **Rapportnivå**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (förenklad)** | **1 (full)** |
| Referensperiod         | X                  | X            |
| Antal deklarationer       | X                  | X            |
| Radnummer                 | X                  | X            |
| Landskod ISO (FR)       | X                  | X            |
| Komplementskod          | X                  | X            |
| Siren-nummer                | X                  | X            |
| Moms kundkod        | X                  | X            |
| Riktningskod              | X                  | X            |
| Transaktionstyp            | X                  | X            |
| Ansvarsnivå            | X                  | X            |
| Artikelkod              |                    | X            |
| Nationell NGP                |                    | X            |
| Region (Avdelning)         |                    | X            |
| Typ av transaktion       |                    | X            |
| Ursprungsland      |                    | X            |
| Ursprungsland, importer |                    | X            |
| Slutdestination, exporter |                    | X            |
| Fakturavärde               | X                  | X            |
| Statistiskt värde           |                    | X            |
| Nettovikt                  |                    | X            |
| Ytterligare enheter            |                    | X            |
| Transportkod              |                    | X            |

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i INTRACOM-format.

| **Fält**                   | **Rapportnivå**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (förenklad)** | **1 (full)** |
| Kod                        | X                  | X            |
| Antal deklarationer       | X                  | X            |
| Antal rader              | X                  | X            |
| Siren                       | X                  | X            |
| Region (Avdelning)         |                    | X            |
| Transportkod              |                    | X            |
| Ursprungsland           |                    | X            |
| Typ av transaktion       |                    | X            |
| Fakturavärde               | X                  | X            |
| Leveranssätt           |                    | X            |
| Transaktionstyp            | X                  | X            |
| Ansvarsnivå            | X                  | X            |
| Artikelkod              |                    | X            |
| Nationell NGP                |                    | X            |
| Nettovikt                  |                    | X            |
| Statistiskt värde           |                    | X            |
| Ytterligare enheter            |                    | X            |
| Ursprungsland, importer |                    | X            |
| Slutdestination, exporter |                    | X            |
| Moms kundkod        | X                  | X            |
| Komplementskod          | X                  | X            |
| Referensperiod         | X                  | X            |

### <a name="set-up-intrastat"></a>Ställa in Intrastat

1.  I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationen:

-   Intrastat-modell

-   Intrastat-rapport

-   Intrastat-INTRACOM (FR)

-   Intrastat SAISUNIC (FR)

Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  I Dynamics 365 Finance, gå till **Skatt** &gt; **Inställningar** &gt; **Utrikeshandeln** &gt; **Utländska handelsparametrar**, och följ dessa steg:

    1.  På fliken **Intrastat** på snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)** eller **Intrastat SAISUNIC (FR)**.

    2.  I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.

    3.  På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.

    4.  På snabbflikarna **Allmänt** i fältet **Transaktionskod**, välj koden som används för överföring av varor.

    5.  I fältet **Kreditfaktura**, välj koden som används för retur av varor.

    6.  I fältet **Ansvarsnivå för export**, ange detaljnivån för exportrapporten. Den nivå du väljer påverkar vilka rader som visas i rapporten. Mer information finns i tabellerna i början av detta ämne.

3.  Gå till **Organisationsadministration** &gt; **Organisationer** &gt; **Juridiska personer**, välj ditt företag och följ stegen nedan:

    1.  På snabbfliken **registreringsnummer** i fältet **NAF-kod** ange din NAF-kod. Mer information finns i [FR-00003 NAF-koder och Siret-nummer](tasks/fr-00003-naf-codes-siret-numbers.md).

    2.  På snabbfliken **Utländsk handel och logistik** i avsnittet **Intrastat** ange fälten **momsregistreringsnummer för export** och **momsregistreringsnummer för import**.

    3.  På **Momsregistrering** snabbfliken i **Momsregistreringsnummer** fältet, ange ditt företags momsregistreringsnummer.

4.  Om du vill ange NAF-koder och momsregistreringsnummer för kunder går du till **Kundreskontra** &gt; **Kunder** &gt; **Alla kunder** och följer stegen nedan:

    1.  Välj en kund.

    2.  På snabbfliken **Faktura och leverans** i avsnittet **Moms** i fältet **Momsregistreringsnummer** ange kundens momsregistreringsnummer.

    3.  På snabbfliken **Försäljningsdemografi** i fältet **Franskt Siret**, ange företagets Siret-nummer.

    4.  I fältet **NAF-kod**, ange företagets NAF-kod.

    5.  Upprepa de här stegen för andra kunder.

5.  Om du vill ange NAF-koder och momsregistreringsnummer för leverantörer går du till **Leverantörsreskontra** &gt; **Leverantörer** &gt; **Alla leverantörer** och följer stegen nedan:

    1.  Välj en leverantör.

    2.  På snabbfliken **Faktura och leverans** i avsnittet **Moms** i fältet **Momsregistreringsnummer** ange leverantörens momsregistreringsnummer.

    3.  På snabbfliken **Inköpsdemografi** i fältet **Franskt Siret**, ange företagets Siret-nummer.

    4.  I fältet **NAF-kod**, ange företagets NAF-kod.

    5.  Upprepa de här stegen för andra leverantörer.

6.  Gå till **Skatt** &gt; **Inställningar** &gt; **Utländsk handel** &gt; **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För franska Intrastat, välj **Statistikprocedur**, **Ursprungsstat**, **Ursprungsland/region**, **Leveransvillkor**, **Transport**, **Korrigering**, **Land/region**, **Ursprungsregion/destination**, **Riktning**, **Land/region för avsändare**, **Tillstånd för avsändare**, **Delstat**, **Transaktionskod** och **Vara**.

7.  Gå till **Lagerstyrning** &gt; **Inställningar** &gt; **Lagerställe** &gt; **Lagerställen**, välj ett lagerställe och följ sedan dessa steg:

    1.  På snabbfliken **Adresser** väljer du **Lägg till** eller **Redifera**.

    2.  I dialogrutan, i fältet **Ort** välj lagerställets ort. Delstatens ort används som en region för din DEB-rapport.

### <a name="ngp-codes"></a>NGP-koder

I DEB-rapporten består kodifieringen av produkter av följande element:

1.  Den åttasiffriga CN8-kod som representerar EU-kodens tariff- och statistiktaxa.

2.  Den ensiffriga nationella artikelkoden Nomenclature Générale des Produits (NGP) om tillämpligt.

Under 2021 gäller NGP endast tre typer av produkter:

-   Några produkter från kor, får och getter

-   Militär utrustning

-   Franska viner

Du måste ställa in NGP-koderna och tilldela dem till relaterade produkter. Fältet **NGP** ställs sedan automatiskt in på sidan **Intrastat-journal**.

#### <a name="set-up-an-ngp-code"></a>Ställa in en NGP-kod

1.  Gå till **Moms** &gt; **Inställningar** &gt; **Utländsk handel** &gt; **NGP-koder**.

2.  I åtgärdsfönstret väljer du **Ny** för att skapa en NGP-kod.

3.  I fältet **NGP** ange en ensiffrig kod.

4.  I fältet **Beskrivning**, ange en beskrivning för koden.

#### <a name="assign-an-ngp-code-to-a-product"></a>Tilldela en NGP-kod till en produkt

1.  Gå till **Produktinformationshantering** &gt; **Produkter** &gt; **Frisläppta produkter**.

2.  I rutnätet väljer du en produkt.

3.  På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **NGP** väljer du lämplig NGP-kod.

## <a name="intrastat-journal"></a>Intrastat-journal

Gå till **Moms** &gt; **Deklarationer** &gt; **Utländsk** **handel** &gt; **Intrastat** för att hantera dina transaktioner som är tillämpliga på utrikeshandel med EU-länder. Mer information finns i [Intrastat, översikt](emea-intrastat.md).

Kolumnen **NGP** är specifik för Frankrike. Det visar NGP-koden för den produkten. Om NGP inte kan användas för en produkt visas **0** (noll). Du kan justera NGP-koden. Välj transaktionen och sedan på **Allmän** i avsnittet **Koder** i fältet **NGP** välj önskad NGP -kod.

### <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter, projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller destinationsregion (för utförsel) eller försändelse (vid införsel) kommer att överföras.

Eftersom DEB-rapporten är en kombination av listan över försäljning inom EU och Intrastat-rapporten, innehåller den även *trepartstransaktioner*, där en direktleverans görs från ett EU-land (part A) till ett annat EU-land (part C) och en fransk juridisk enhet (part B) är den mitt i trepartsaffären.

### <a name="generate-a-deb-intrastat-report"></a>Skapa DEB-rapport (Intrastat)

1.  Gå till **Moms** &gt; **Deklarationer** &gt; **Utländsk handel** &gt; **Intrastat**.

2.  I åtgärdsfönstret väljer du **Utdata** &gt; **Rapport**.

3.  I dialogrutan **Intrastat-rapport** anger du följande fält.

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

Följande exempel visar hur du ställer in och arbetar med NGP-koder. Använd **DEMF** juridiska personen.

1.  I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationsformat:

-   Intrastat-modell

-   Intrastat-rapport

-   Intrastat-INTRACOM (FR)

2.  Ställ in en transaktionskod i Finance:

    1.  Gå till **Moms** &gt; **Inställningar** &gt; **Utländsk handel** &gt; **Transaktionskoder**.

    2.  Klicka på **Ny** i åtgärdsfönstret.

    3.  I fältet **Transaktionskod** ange **11**.

    4.  I fältet **Namn** anger du **inköp eller försäljning**.

    5.  Klicka på **Spara** i åtgärdsfönstret.

3.  Ställ in en produkthierarki:

    1.  Gå till **Produktinformationshantering** &gt; **Inställningar** &gt; **Kategorier och attribut** &gt; **Kategorihierarkier**.

    2.  Välj **Intrastat** i rutnätet. I Åtgärdsfönstret, på fliken **kategorihierarki**, i gruppen **underhåll**, markerar du **redigera**.

    3.  I åtgärdsfönstret klickar du på **Ny kategorinod**.

    4.  I fältet **Namn** anger du **Autres Libournais**.

    5.  I fältet **Kod** ange **2204 21 42**

    6.  Klicka på **Spara** i åtgärdsfönstret.

4.  Gå till **Skatt** &gt; **Inställningar** &gt; **Utrikeshandeln** &gt; **Utländska handelsparametrar** och följ dessa steg:

    1.  På fliken **Intrastat** på fliken **Allmänt** i fältet **Transaktionskod**, välj **11**.

    2.  På snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)**.

    3.  I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.

    4.  På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.

5.  Ställa in en NGP-kod:

    1.  Gå till **Moms** &gt; **Inställningar** &gt; **Utländsk handel** &gt; **NGP-koder**.

    2.  Klicka på **Ny** i åtgärdsfönstret.

    3.  I fältet **NGP** ange **8**.

    4.  I fältet **Namn på beskrivning** ange **NGP 8**.

    5.  Klicka på **Spara** i åtgärdsfönstret.

6.  Tilldela en NGP-kod till en produkt:

    1.  Gå till **Produktinformationshantering** &gt; **Produkter** &gt; **Frisläppta produkter**.

    2.  Välj **0001** i rutnätet.

    3.  På snabbfliken **Utländsk handel** i fältet **NGP**, välj **8**.

    4.  I fältet **Vara** välj **2204 21 42**.

    5.  Klicka på **Spara** i åtgärdsfönstret.

7.  Skapa en försäljningsorder som inkluderar den nya produkten:

    1.  Gå till **Kundreskontra** &gt; **Order** &gt; **Alla försäljningsorder**.

    2.  Klicka på **Ny** i åtgärdsfönstret.

    3.  I dialogrutan **Skapa** **försäljning** **order** i avsnittet **Kund** i **Kund** **kontot**, välj **100001**.

    4.  I avsnittet **Adress** i fältet **Leveransadress** välj plustecknet (**+**) för att skapa en adress.

    5.  I dialogrutan **Ny adress** i fältet **Namn på beskrivning** ange **Tyskland**.

    6.  I fältet **Land/region** välj **DEU**.

    7.  Välj **OK**.

    8.  I dialogrutan **Skapa försäljningsorder** välj **OK**.

    9.  På snabbfliken **Försäljning** **orderrader** i fältet **Artikelnummer** välj **0001**.

    10. Klicka på **Spara** i åtgärdsfönstret.

    11. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.

    12. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**. Du kan sedan välja **OK** för att bokföra fakturan.

8.  Skapa DEB-rapporten:

    1.  Gå till **Moms** &gt; **Deklarationer** &gt; **Utländsk handel** &gt; **Intrastat**:

    2.  I åtgärdsfönster. välj **Överför**.

    3.  I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**. Välj sedan **OK**.

    4.  Sortera transaktionerna efter fältet **Datum**. Den översta transaktionen är resultattransaktionen. Fältet **NGP** ställs automatiskt in.

    5.  I åtgärdsfönstret väljer du **Utdata** &gt; **Rapport**.

    6.  I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.

    7.  Ställ in alternativet **Exportalternativ** ange **Generera fil** till **Ja**.

    8.  I fältet **Filnamn** anger du ett namn som krävs.

    9.  Välj **OK** och granska rapporten.

