---
title: Svenskt Intrastat
description: Detta ämnet innehåller information om Intrastatrapportering i Sverige.
author: andosip
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 404fb8dff1519aefb2f4af25eb95dfa6fce75b7c
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417092"
---
# <a name="swedish-intrastat"></a>Svenskt Intrastat

[!include[banner](../includes/banner.md)]

Sidan **Intrastat** används för att generera och rapportera information om handel mellan länder i EU. Den svenska Intrastatdeklarationen innehåller information om handel med varor för rapportering.

Följande fält finns inkluderade i den svenska Intrastatdeklarationen:

   - ISO-kod för partnerlandet
   - Transaktionskategori
   - Artikelkod
   - Ytterligare enhet
   - Vikt
   - Fakturabelopp

## <a name="set-up-intrastat"></a>Ställa in Intrastat

Importera den senaste versionen av följande ER-konfigurationer (Electronic Reporting; elektronisk rapportering):

   - Intrastat-modell
   - Intrastat-rapport
   - Intrastat (SE)

Mer information finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. I Microsoft Dynamics 365 Finance går du till **Moms** > **Inställningar** > **Utländska handelsparametrar**.
2. På fliken **Intrastat** > snabbfliken **Elektronisk rapportering** > fältet **Mappning av filformat** väljer du **Intrastat (SV)**.
3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
4. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
5. I fältet **Transaktionskod** väljer du transaktionskod för egenskapsöverföringar. Du använder den här koden för transaktioner som genererar faktiska eller planerade överlåtelser av egendom mot ersättning (ekonomisk eller annan). Du använder det även för korrigeringar. Företag i Sverige använder ensiffriga transaktionskoder.
6. I fältet **Kreditfaktura** väljer du transaktionskod för retur av varor. Den här koden används vid retur av varor när den ursprungliga transaktionen har registrerats under transaktionskoden. Företag i Sverige använder ensiffriga transaktionskoder.
7. På fliken **Egenskaper för land/region** i fältet **Land/region** anger alla länder eller regioner som ditt företag gör affärer med. I fältet **Typ av land/region** väljer du **EU** för samtliga länder som ingår i EU, detta så att landet visas i din Intrastatrapport.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Konfigurera produktparametrarna för Intrastatdeklarationen

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. I rutnätet väljer du en produkt.
3. På snabbfliken **Handel med utlandet** > avsnittet **Intrastat** > fältet **Vara** väljer du varukoden.
4. På snabbfliken **Hantera lager**, i fältet **Nettovikt**, anger du produktens vikt i kilo.
5. Gå till **Tax** > **Inställningar** > **Utländsk handel** > **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För svenskt Intrastat väljer du följande fält:

    - Artikel
    - Transaktionskategori
    - Riktning
    - Land/region
    - Korrigering
    - Faktura

## <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter, projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller destinationsregion (för utförsel) eller försändelse (vid införsel) kommer att överföras.

Du kan också ange transaktioner manuellt genom att välja **Ny** i åtgärdsfönstret.

### <a name="generate-an-intrastat-report"></a>Skapa Intrastat-rapport

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
3. I dialogrutan **Intrastat-rapport** anger du följande fält.

    | Fält            | beskrivning                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Från-datum        | Välj startdatumet för rapporten.                                                                                               |
    | Till-datum          | Välj slutdatumet för rapporten.                                                                                                 |
    | Generera fil    | Ange detta alternativ som **Ja** om du vill generera en .txt-fil för din Intrastatrapport.                                                       |
    | Filnamn        | Ange namnet på .txt-filen.                                                                                                    |
    | Generera rapport  | Ange detta alternativ som **Ja** om du vill generera en .xlsx-fil för din Intrastatrapport.                                                     |
    | Rapportfilnamn | Ange namnet på .xlsx-filen.                                                                                                   |
    | Riktning        | Välj **Införsel** för en rapport om inomeuropeiska införslar. Välj **Utförsel** för en rapport om inomeuropeiska införslar. |

4. Välj **OK** och granska rapporterna som genereras.

## <a name="example"></a>Exempel

I det här exemplet visas hur du bokför införsel och utförsel för Intrastat. Använd **DEMF** juridiska personen.

### <a name="preliminary-setup"></a>Preliminär inställning

1. Gå till **Organisationsadministration** > **Organisation** > **Juridiska personer** och välj den juridiska personen **DEMF**.
2. På snabbfliken **Adresser** väljer du **Redigera** och sedan, i fältet **Land/region**, väljer du **SWE (Sverige)**.
3. Importera den senaste versionen av följande ER-konfigurationer:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Skapa transaktionskoder

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Transaktion** **kod** ange **1**.
4. I fältet **Namn** anger du **Normala transaktioner**
5. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
2. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **1**.
3. På snabbfliken **Elektronisk rapportering** > fältet **Mappning av filformat** väljer du **Intrastat (SE)**.
4. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
5. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
6. På fliken **Egenskaper för land/region**, välj **Ny**.
7. I fältet **Part för land/region** välj **SWE**.
8. I fältet **Lands-/regiontyp**, väljer du **Lokal**.
9. I fältet **Land-/regionpart** väljer du **DEU** och sedan, i fältet **Land-/regiontyp**, väljer du **EU**.

### <a name="set-up-product-information"></a>Konfigurera produktinformation

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. Välj **D0001** i rutnätet.
3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **100 200 30**.
4. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **5**.
5. Klicka på **Spara** i åtgärdsfönstret.

### <a name="change-the-site-address"></a>Ändra platsens adress

1. Gå till **Lagerstyrning** > **Konfiguration** > **Distributionslager** > **Platser**.
2. Välj **1** i rutnätet.
3. På snabbfliken **Adresser** väljer du **Registrera**.
4. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **SWE**.
5. Välj **OK**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Skapa en försäljningsorder med en EU-kund

1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningsorder** på **Kund** i avsnitt **Kund** i fält **Kundkontot**, välj **DE-015**.
4. På snabbfliken **Allmänt** i avsnittet **Lagringsdimensioner** i fältet **Webbplats**, välj **1**.
5. I fältet **Lagerställe**, välj **11**.
6. Välj **OK**.
7. På fliken **Rader** > snabbfliken **Försäljningsorderrader** > fältet **Artikelnummer** väljer du **D0001**. I fältet **Kvantitet**, ange **10**.
8. På snabbfliken **Raddetaljer** på fliken **Handel med utlandet** ser du till att fälten **Transaktionskod** och **Vara** har ställts in automatiskt.
9. Klicka på **Spara** i åtgärdsfönstret.
10. I åtgärdsrutan på fliken **Faktura** i avsnittet **Generera**, klicka på **Faktura**.
11. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**.
12. Välj **OK** när du vill bokföra faktura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Överför transaktionen till Intrastatjournalen och granska resultatet

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**.
4. Välj **filter**.
5. I dialogrutan **Intrastat-filter**, fliken **Intervall**, välj den första raden och se till att **Fält** anges till **Datum**.
6. Välj aktuellt datum i fältet **Kriterier**.
7. Välj **OK** för att stänga dialogrutan **Intrastat-filter**.
8. Välj **OK** för att stänga dialogrutan **Intrastat (överför)** och granska resultatet. Raden representerar den försäljningsorder som du skapade tidigare.

    ![Intrastatjournalrader för försäljningsorder](media/swe_intrastat_journal_sales_order.png)

9. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Raddetaljer för försäljningsorder för Intrastatjournal](media/swe_intrastat_journal_sales_order_line_details.png)

10. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
11. I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.
12. I avsnittet **Export** **alternativet** ange **Generera fil** till **Ja**. I fältet **Filnamn** anger du sedan erforderligt namn.
13. Ange alternativet **Generera rapport** som **Ja**. I fältet **Rapportfilens namn** anger du sedan erforderligt namn.
14. I fältet **Riktning** väljer du **Utförsel**.
15. Välj **OK** och granska den rapport i .txt-format som genereras. Tabellen nedan visar värdena i exempelrapporten.

    | ISO-kod för partnerlandet | Transaktionskategori | Artikelkod | Ytterligare enhet | Vikt | Fakturabelopp |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Granska rapporten som genereras i Excel-format.

    ![Intrastat-rapport](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa inköpsorder**, i fältet **Leverantörskonto**, väljer du **DE-001**.
4. Välj **OK**.
5. I fliken **Rubrik**, på snabbfliken **Handel med** **utlandet**, bekräftar du att fältet **Transaktionskod** angetts som **1**.
6. På fliken **Rader** > snabbfliken **Inköpsorderrader** > fältet **Artikelnummer** väljer du **D0001**. I fältet **Kvantitet**, ange **6**.
7. I Åtgärdsfönstret > på fliken **Inköp** > i gruppen **Åtgärd** markerar du **Bekräfta**.
8. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
9. I åtgärdsfönstret väljer du **Standard från**. I fältet **Standardkvantiteter för rader** väljer du **Beställd kvantitet**. Välj sedan **OK**.
10. På snabbfliken **Sidhuvud i leverantörsfaktura** > avsnittet **Fakturaidentifiering** > fältet **Nummer** anger du **0001**.
11. Om du vill bokföra fakturan väljer du **Bokför** i åtgärdsfönstret.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Skapa en Intrastatdeklaration för införsel

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Leverantörsfaktura** som **Ja**.
4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

    ![Intrastatjournal för inköpsorder](media/swe_intrastat_journal_purchase_order.png)

5. Granska fliken **Allmänt** för inköpsordern.

    ![Raddetaljer för Intrastatjournal för inköpsorder](media/swe_intrastat_journal_purchase_order_line_details.png)

6. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
7. I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.
8. I avsnittet **Export** **alternativet** ange **Generera fil** till **Ja**. I fältet **Filnamn** anger du sedan erforderligt namn.
9. Ange alternativet **Generera rapport** som **Ja**. I fältet **Rapportfilens namn** anger du sedan erforderligt namn.
10. I fältet **Riktning** väljer du **Införsel**.
11. Välj **OK** och granska den rapport i .txt-format som genereras. Tabellen nedan visar värdena i exempelrapporten.

    | ISO-kod för partnerlandet | Transaktionskategori | Artikelkod | Ytterligare enhet | Vikt | Fakturabelopp |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Granska rapporten som genereras i Excel-format.

    ![Intrastatinförselsrapport](media/swe_intrastat_arrivals_report.png)
