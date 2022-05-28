---
title: Bokföra införsel och utförsel för Intrastat
description: I detta ämne ges ett exempel på hur du bokför införsel och utförsel för Intrastat.
author: anasyash
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4ab4402740d199043519773b18732bdde9a0fb2f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724795"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Bokföra införsel och utförsel för Intrastat

[!include [banner](../includes/banner.md)]

I detta ämne ges ett exempel på hur du bokför införsel och utförsel för Intrastat. I exemplet används den juridiska personen **ITCO**.

## <a name="setup"></a>Ställ in

1. Importera den senaste versionen av följande ER-konfigurationer (Electronic Reporting; elektronisk rapportering):

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat (IT)

    Mer information finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. I Microsoft Dynamics 365 Finance definierar du följande nummersekvenser som löpande: **Gene\_397**, **Acco\_16403**, **Gene\_407** och **PUR\_EU**.

    1. Gå till **Organisationsadministrering** > **Nummersekvenser** > **Nummersekvenser**.
    2. Välj en av nummerseriekoderna i rutnätet.
    3. I åtgärdsfönstret väljer du **Redigera**.
    4. På snabbfliken **Allmänt** i avsnittet **Inställningar** anger du alternativet **Löpande** som **Ja**.
    5. Klicka på **Spara** i åtgärdsfönstret.

3. Ange en adress för lagerställe.

    1. Gå till **Lagerstyrning** &gt; **Inställningar** &gt; **Lagerställe** &gt; **Lagerställen**.
    2. Välj lagerställe **11** i listan.
    3. På snabbfliken **Adress** väljer du **Lägg till**.
    4. I dialogrutan **Ny** **adress**, i fältet **Namn** **eller** **beskrivning**, anger du **Primär**.
    5. I fältet **Land/region** väljer du **ITA (Italien)**.
    6. I fältet **Ort** väljer du **Aprilia**.
    7. Välj **OK**.

4. Ställ in transaktionskoder.

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Transaktionskoder**.
    2. Välj **Ny** och konfigurera sedan en transaktionskod för överföring av egenskap.

        - I fältet **Transaktionskod** ange **1**.
        - I fältet **Namn** anger du **Överföra egenskap**.

    3. Välj **Ny** och konfigurera sedan en transaktionskod för returer.

        - I fältet **Transaktion** **kod** ange **2**.
        - I fältet **Namn** anger du **retur av varor**.

5.  Konfigurera utländska handelsparametrar.

    1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
    2. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **1**.
    3. I fältet **Kreditfaktura** välj **2**.
    4. I fältet **Rapporteringsperiod för försäljningsperiod** väljer du **Månad**.
    5. I fältet **Rapporteringsperiod för inköp** väljer du **Månad**.
    6. På snabbfliken **Elektronisk rapportering** > fältet **Mappning av filformat** väljer du **Intrastat (IT)**.
    7. I fältet **Mappning av rapportformat** väljer du **Intrastatrapport**.
    8. På snabbfliken **Varukodhierarki** i fältet **Kategorihierarki** väljer du **Intrastat**.
    9. På snabbfliken **Statistiskt värde** anger du alternativet **Skriv ut och exportera statistiska data** som **Ja**.
    10. Kontrollera att följande rader finns på fliken **Egenskaper för land/region**.

        | **Part/land/region** | **Intrastat-kod** | **Valuta** | **Lands-/regiontyp** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Lokal                |
        | SMR                      | SM                 | EUR          | Special - inrikes        |

    11. I verktygsfältet väljer du **Ny** för att skapa följande rad:

        | **Part/land/region** | **Intrastat-kod** | **Valuta** | **Lands-/regiontyp** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | EU                      |

6. Konfigurera momsregistreringsnummer.

    1. Gå till **Moms** > **Inställningar** > **Moms** > **Momsregistreringsnummer**.
    2. I åtgärdsfönstret väljer du **Ny** för att skapa följande rader.

        | **Land/region** | **Momsregistreringsnummer** | **Företagsnamn** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | UE-LEVERANTÖR        |
        | DNK                | DK0987654321          | Kund-ER      |

7. Ange leverantörens adress.

    1. Gå till **Leverantörsreskontra** &gt; **Leverantörer** &gt; **Alla leverantörer**.
    2. I rutnätet väljer du **UE-leverantör**.
    3. På snabbfliken **Adresser** väljer du **Lägg till**.
    4. I dialogrutan **Ny adress**, i fältet **Namn eller beskrivning**, anger du **Tyskland**.
    5. I fältet **Land/region** välj **DEU**.
    6. Skapa en ny adress genom att välja **OK**.
    7. På snabbfliken **Faktura och leverans**, i avsnittet **Moms**, i fältet **Momsregistreringsnummer**, väljer du **Alla** och sedan **DE1234567890**.
    8. Klicka på **Spara** i åtgärdsfönstret.

8. Ange kundadresser.

    1. Gå till **Kundreskontra** > **Kunder** > **Alla kunder**.
    2. Välj **ITCO-000001** i rutnätet.
    3. På snabbfliken **Adresser** väljer du **Registrera**.
    4. I dialogrutan **Ny adress**, i fältet **Namn eller beskrivning**, anger du **San Marino**.
    5. I fältet **Land/region** välj **SMR**.
    6. Skapa en ny adress genom att välja **OK**.
    7. i snabbfliken **Faktura och leverans** > avsnittet **Faktura** > fältet **Fakturabelopp** väljer du **ITCO-000001**.
    8. I fältet **Nummerseriegrupp** väljer du **IT\_VENDOM**.
    9. Välj **Spara** i åtgärdsfönstret och stäng sidan.
    10. På sidan **Alla kunder** väljer du **ITCO-000002** i rutnätet.
    11. På snabbfliken **Adresser** väljer du **Lägg till**.
    12. I dialogrutan **Ny adress**, i fältet **Namn eller beskrivning**, anger du **Danmark**.
    13. I fältet **Land/region** välj **DNK**.
    14. Skapa en ny adress genom att välja **OK**.
    15. På snabbfliken **Försäljningsdemografi**, i fältet **Valuta**, väljer du **DKK**.
    16. På snabbfliken **Faktura och leverans** > avsnittet **Moms** > fältet **Momsgrupp** väljer du **IT\_PUREU**.
    17. I fältet **Momsregistreringsnummer** väljer du **Alla** och sedan **DK0987654321**.
    18. Klicka på **Spara** i åtgärdsfönstret.

9. Ställ in kategorihierarkin.

    1. Gå till **Produktinformationshantering** > **Inställningar** > **Kategorier och attribut** > **Kategorihierarkier**.
    2. Välj **Intrastat** i rutnätet.
    3. I åtgärdsfönstret klickar du på **Ny kategorinod**.
    4. I fältet **Namn** anger du **Tjänst**.
    5. I fältet **Kod** anger du **123456**.
    6. Klicka på **Spara** i åtgärdsfönstret.

10. Ställ in produkter.

    1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
    2. Välj **ITEM** i rutnätet.
    3. På snabbfliken **Inköp** > avsnittet **Administration** > fältet **Leverantör** väljer du **ITCO-000001**.
    4. På snabbfliken **Handel med utlandet** > avsnittet **Intrastat** > fältet **Vara** väljer du **\[100 200 30\] Högtalare**.
    5. I avsnittet **Ursprung** i fältet **land/region**, välj **DEU**.
    6. I fältet **Delstat/provins** väljer du **BE**.
    7. På snabbfliken **Hantera lager** > avsnittet **Nettomått** > fältet **Nettovikt** anger du **5**.
    8. Klicka på **Spara** i åtgärdsfönstret.
    9. På sidan **Frisläppta produkter** väljer du **Serviceartikel** i rutnätet.
    10. På snabbfliken **Handel med utlandet** > avsnittet **Intrastat** > fältet **Vara** väljer du **\[123456\] Tjänst**.
    11. Klicka på **Spara** i åtgärdsfönstret.

11. Konfigurera transpormedtoder.

    1. Gå till **Moms** > **Inställningar** > **handel med utlandet** > **Transportmetod**.
    2. I åtgärdsfönstret väljer du **Ny** för att skapa följande transportmetoder:

        | **Transport** | **Beskrivning** |
        |---------------|-----------------|
        | 1             | Vägtransport            |
        | 2             | Flyg             |

12. Konfigurera ett leveranssätt.

    1. Gå till **Anskaffning och källa** > **Inställningar** > **Fördelning** > **Leveranssätt**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I fältet **Leveranssätt** anger du **1**.
    4. I fältet **Beskrivning** anger du **Lastbil**.
    5. På snabbfliken **Handel med utlandet**, i fältet **Transport**, väljer du **1 Vägtransport**.
    6. Klicka på **Spara** i åtgärdsfönstret.

13. Konfigurera leveransvillkor.

    1. Gå till **Leverantörsreskontra** > **Inställningar** > **Leveransvillkor**.
    2. Välj **CFR** i listan.
    3. På snabbfliken **Allmänt**, i fältet **Intrastatkod**, väljer du **1**.

## <a name="post-arrivals-for-intrastat"></a>Bokföra införsel för Intrastat

### <a name="purchase-goods-by-using-a-purchase-order"></a>Köpa varor genom att använda en inköpsorder

Den här delen av exemplet visar hur du använder en inköpsorder för att köpa in varor (artiklar) från EU-länder.

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2.  Klicka på **Ny** i åtgärdsfönstret.
3.  I dialogrutan **Skapa inköpsorder**, i fältet **Leverantörskonto**, väljer du **UE-leverantör**.
4.  På snabbfliken **Administration**, i fältet **Språk**, väljer du **it**.
5.  Välj **OK**.
6.  I vyn **Sidhuvud**, på snabbfliken **Handel med** **utlandet**, bekräftar du att fältet **Transaktionskod** angetts som **1**.
7.  Kontrollera att fältet **Ursprungs-/destinationsland** har ställts in på **RM**.
8.  På snabbfliken **Leverans** > avsnittet **Leverans** > fältet **Leveranssätt** väljer du **1**.
9.  I fältet **Leveranssätt** väljer du **CFR**.
10. I vyn **Rader** > snabbfliken **Rader för inköpsorder** > fältet **Artikelnummer** väljer du **Artikel**.
11. I fltet **Site**, välj **1**.
12. I fältet **Lagerställe**, välj **11**.
13. I fältet **Kvantitet**, ange **10**.
14. I fältet **Enhetspris** ange **100**.
15. På fliken **Inställningar** > i avsnittet **Moms** > fältet **Artikelmomsgrupp** väljer du **22%EU**.
16. I Åtgärdsfönstret > på fliken **Inköp** > i gruppen **Åtgärd** markerar du **Bekräfta**.
17. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
18. I åtgärdsfönstret väljer du **Standard från**.
19. I fältet **Standardkvantitet för rader** väljer du först **Betälld kvantitet** och väljer sedan **OK**.
20. På snabbfliken **Sidhuvud i leverantörsfaktura** > avsnittet **Fakturaidentifiering** > fältet **Nummer** anger du **0001**.
21. I avsnittet **Fakturadatum** > fältet **Fakturadatum** väljer du **7/9/2021**.
22. Om du vill bokföra fakturan väljer du **Bokför** i åtgärdsfönstret.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Inköpstjänster genom att använda en leverantörsfaktura

Denna del av exemplet visar hur du använder en leverantörsfaktura för att köpa in tjänster från EU-länder.

1. Gå till **Leverantörsreskontra** > **Fakturor** > **Faktureringsjournalnvoice journal**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Namn** väljer du **VEND\_EUINV**.
4. Klicka på **Rader** i åtgärdsrutan.
5. I fältet **Datum** anger du **7/9/2021**.
6. I fältet **Kontotyp** väljer du **Leverantör**.
7. I fältet **Konto** väljer du **UE-leverantör**.
8. I fältet **Fakturadatum** väljer du **7/9/2021**.
9. I fältet **Faktura** anger du **ITA-0004**.
10. I fältet **Kredit** anger du **120000**.
11. I fältet **Motkontotyp** väljer du **Redovisning**.
12. I fältet **Motkonto** anger du **110130**.
13. I fältet **Momsgrupp** väljer du **IT\_PUREU**.
14. I fältet **Artikelmomsgrupp** väljer du **22%EU**.
15. På fliken **Handel med utlandet** följer du dessa steg:

    1. I fältet **Transaktionskod** väljer du **1**.
    2. I fältet **Transport** väljer du **2 Flyg**.
    3. I fältet **Vara** väljer du **\[123456\] Tjänst**.
    4. I fältet **Land/region** välj **ITA**.
    5. I fältet **Delstat/provins** väljer du **LAZ**.
    6. I fältet **Ursprungsland/destination** väljer du **LT**.


16. Klicka på **Bokföra** i åtgärdsfönstret.
17. Skapa en Intrastatdeklaration för införsel.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Leverantörsfaktura** som **Ja**.
    4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

   ![Sidan Intrastatjournal, fliken Översikt.](media/ita_intrastat_journal_vendor_invoice.png)

18. Granska fliken **Allmänt** för inköpsordern.

    ![Raddetaljer för Intrastatjournal för inköpsorder](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Granska fliken **Allmänt** för leverantörsordern.

    ![Raddetaljer för Intrastatjournal för leverantörsorder](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Generera Intrastatrapport för införsel.

    1. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
    2. I dialogrutan **Intrastatrapport** > avsnittet **Datum** > fältet **Från-datum** väljer du **7/1/2021**.
    3. I fältet **Till-datum** väljer du **7/31/2021**.
    4. I avsnittet **Exportalternativ** anger du alternativen **Genrera fil** och **Generera rapport** som **Ja**.
    5. I fältet **Filnamn** anger du **Införselsfil**.
    6. I fältet **Namn på rapportfil** anger du **Införselsrapport**.
    7. I fältet **Riktning** väljer du **Införsel**.
    8. I fältet **Referensnummer** anger du **123456**.
    9. Välj **OK** för att generera Intrastatrapporten och Intrastatfilen och granska dem.

    Illustrationen nedan visar ett exempel på en Intrastatrapport.

    ![Intrastatinförselsrapport.](media/ita_intrastat_arrivals_report.png)

    Illustrationen nedan visar ett exempel på en Intrastatfil.

    ![Intrastatinförselsfil.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Bokföra utförsel för Intrastat

### <a name="sell-goods-by-using-a-sales-order"></a>Sälja varor genom att använda en försäljningsorder

Denna del av exemplet visar hur du använder en försäljningsorder för att sälja varor (artiklar) till EU-länder.

1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** väljer du **ITCO-000002**.
4. Välj **OK**.
5. I vyn **Rubrik** > snabbfliken **Leverans** > avsnittet **Div. leveransinfo** > fältet **Leveranssätt** väljer du **1 Lastbil**.
6. I fältet **Leveranssätt** väljer du **CFR**.
7. På vyn **Rader** > snabbfliken **Försäljningsorderrader** > fältet **Artikelnummer** väljer du **ARTIKEL**.
8. I fältet **Kvantitet**, ange **50**.
9. I fltet **Site**, välj **1**.
10. I fältet **Lagerställe**, välj **11**.
11. I fältet **Enhetspris** ange **250**.
12. På snabbfliken **Raddetaljer** > fliken **Inställningar** > avsnittet **Moms** > fältet **Artikelmomsgrupp** väljer du **22%EU**.
13. Klicka på **Spara** i åtgärdsfönstret.
14. I åtgärdsfönstret > fliken **Faktura** > gruppen **Generera** väljer du **Faktura** om du vill skapa fakturan för ordern.
15. I dialogrutan **Bokföring av faktura** > snabbfliken **Parametrar** > avsnittet **Parameter** > fältet **Kvantitet** väljer du **Alla**.
16. På snabbfliken **Inställningar**, i fältet **Fakturadatum** väljer du **7/9/2021**.
17. Välj **OK**.
18. Granska raderna i Intrastatjournalen.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Kundfaktura** som **Ja**.
    4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen. Kreditfakturatransaktionen markeras som en korrigering och har negativt fakturabelopp.

        ![Journalsida för Intrastat](media/ita_intrastat_journal_sales_order.png)

        ![Raddetaljer för försäljningsorder för Intrastatjournal](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Returnera varor med en kreditfaktura

Denna del av exemplet visar hur du använder en kreditfaktura för att returnera varor (artiklar) från EU-länder.

1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** väljer du **ITCO-000002**.
4. Välj **OK**.
5. I vyn **Rubrik** > snabbfliken **Leverans** > avsnittet **Div. leveransinfo** > fältet **Leveranssätt** väljer du **1 Lastbil**.
6. I fältet **Leveranssätt** väljer du **CFR**.
7. På snabbfliken **Handel med utlandet**, i fältet **Transaktionskod**, väljer du **2**.
8. På fliken **Rader** > snabbfliken **Försäljningsorderrader** > fältet **Artikelnummer** väljer du **ARTIKEL**.
9. I fältet **Kvantitet** anger du **-10**.
10. I fltet **Site**, välj **1**.
11. I fältet **Lagerställe**, välj **11**.
12. I fältet **Enhetspris** ange **250**.
13. På snabbfliken **Raddetaljer** > fliken **Inställningar** > avsnittet **Moms** > fältet **Artikelmomsgrupp** väljer du **22%EU**.
14. I avsnittet **Returnerad order**, i fältet **ID för returparti**, väljer du det parti som du tidigare skapat.
15. Klicka på **Spara** i åtgärdsfönstret.
16. I åtgärdsfönstret > fliken **Faktura** > gruppen **Generera** väljer du **Faktura** om du vill skapa fakturan för ordern.
17. På snabbfliken **Parametrar** > avsnittet **Parameter** > fältet **Kvantitet** väljer du **Alla**.
18. I dialogrutan **Bokföring av faktura** > snabbfliken **Inställningar** > fältet **Fakturadatum** väljer du **7/9/2021**.
19. Välj **OK** när du vill bokföra faktura.
20. Granska raderna i Intrastatjournalen.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Kundfaktura** som **Ja**.
    4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen. Kreditfakturatransaktionen markeras som en korrigering och har negativt fakturabelopp.

    ![Kreditfaktura för Intrastatjournal](media/ita_intrastat_journal_credit_note.png)

    ![Raddetaljer för kreditfaktura för Intrastatjournal](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Sälj varor till San Marino genom att använda en försäljningsorder

Denna del av exemplet visar hur du använder en försäljningsorder för att köpa varor (artiklar) till San Marino.

1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** väljer du **ITCO-000001**.
4. Välj **OK**.
5. I vyn **Rubrik** > snabbfliken **Leverans** > avsnittet **Div. leveransinfo** > fältet **Leveranssätt** väljer du **1**.
6. I fältet **Leveranssätt** väljer du **CFR**.
7. På fliken **Rader** > snabbfliken **Försäljningsorderrader** > fältet **Artikelnummer** väljer du **ARTIKEL**.
8. I fältet **Kvantitet**, ange **30**.
9. I fltet **Site**, välj **1**.
10. I fältet **Lagerställe**, välj **11**.
11. I fältet **Enhetspris** ange **200**.
12. Klicka på **Spara** i åtgärdsfönstret.
13. I åtgärdsfönstret > fliken **Faktura** > gruppen **Generera** väljer du **Faktura** om du vill skapa fakturan för ordern.
14. På snabbfliken **Parametrar** > avsnittet **Parameter** > fältet **Kvantitet** väljer du **Alla**.
15. I dialogrutan **Bokföring av faktura** > snabbfliken **Inställningar** > fältet **Fakturadatum** väljer du **7/9/2021**.
16. Välj **OK** när du vill bokföra faktura.
17. Granska raderna i Intrastatjournalen.

    1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
    2. Klicka på **Överför** i åtgärdsfönstret.
    3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Kundfaktura** som **Ja**.
    4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

   ![Intrastatjournal för San Marino](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Raddetaljer för Intrastatjournal för San Marino](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Skapa en Intrastatdeklaration för utförsel.

    1. Gå till **Moms** &gt; **Deklarationer** &gt; **Utländsk handel** &gt; **Intrastat**.
    2. I åtgärdsfönstret väljer du **Utdata** &gt; **Rapport**.
    3. I dialogrutan **Intrastatrapport** > avsnittet **Datum** > fältet **Från-datum** väljer du **7/1/2021**.
    4. I fältet **Till-datum** väljer du **7/31/2021**.
    5. I avsnittet **Exportalternativ** anger du alternativen **Genrera fil** och **Generera rapport** som **Ja**.
    6. I fältet **Filnamn** anger du **Utförselsfil**.
    7. I fältet **Namn på rapportfil** anger du **Utförselsrapport**.
    8. I fältet **Riktning** väljer du **Utförsel**.
    9. I fältet **Referensnummer** anger du **98754**.
    10. Välj **OK** för att generera Intrastatrapporten och Intrastatfilen.

        Illustrationen nedan visar ett exempel på en utskriven Intrastatrapport.

        ![Intrastat-rapport](media/ita_intrastat_report_for_dispatches.png)

        Illustrationen nedan visar ett exempel på en utskriven Intrastatfil.

        ![Intrastatfil för utförsel](media/ita_intrastat_file_for_dispatches.png)
