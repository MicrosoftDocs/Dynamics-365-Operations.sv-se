---
title: Fransk Intrastat
description: Det här ämnet innehåller information om Intrastat-deklaration i Frankrike.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831816"
---
# <a name="french-intrastat"></a>Fransk Intrastat

[!include[banner](../includes/banner.md)]

Företag i Frankrike som är registrerade för moms (VAT) och som handel med andra EU-länder måste deklarera utbytet av varor och tjänster till och från Frankrike. Declaration d'exchanges de biens (Declaration of Trade in Goods eller DEB) är en kombination av listan över försäljning inom EU och Intrastat-rapporten. Du måste skicka in den här rapporten varje månad för all inomeuropeisk försäljning av varor.

Du kan generera DEB-rapporten i något av två elektroniska textfilformat: SAISUNIC 330 eller INTRACOM-format.

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i SAISUNIC 330-format. Registret visar också rapportnivåerna i varje fält. Ett fält kan ha följande rapportnivåer:

- **4** – Momsdeklaration.
- **1** – Statistiskt svar.
- **5** – Statistiskt svar på leverans och momsdeklaration och gemensam fyllning.

| Fält                       | Rapportnivåer |
|-----------------------------|---------------|
| Referensperiod         | 4, 1, 5       |
| Antal deklarationer       | 4, 1, 5       |
| Radnummer                 | 4, 1, 5       |
| Landskod ISO (FR)       | 4, 1, 5       |
| Komplementskod          | 4, 1, 5       |
| Siren-nummer                | 4, 1, 5       |
| Moms kundkod        | 4, 1, 5       |
| Riktningskod              | 4, 1, 5       |
| Transaktionstyp            | 4, 1, 5       |
| Ansvarsnivå            | 4, 1, 5       |
| Artikelkod              | 1, 5          |
| Nationell NGP                | 1, 5          |
| Region (Avdelning)         | 1, 5          |
| Typ av transaktion       | 1, 5          |
| Ursprungsland      | 1, 5          |
| Ursprungsland, importer | 1, 5          |
| Slutdestination, exporter | 1, 5          |
| Fakturavärde               | 4, 1, 5       |
| Statistiskt värde           | 1, 5          |
| Nettovikt                  | 1, 5          |
| Ytterligare enheter            | 1, 5          |
| Transportkod              | 1, 5          |

Följande tabell visar de fält som är inkluderade i den franska Intrastat-deklarationen i INTRACOM-format. Registret visar också rapportnivåerna i varje fält. Ett fält kan ha följande rapportnivåer:

- **4** – Momsdeklaration.
- **1** – Statistiskt svar.
- **5** – Statistiskt svar på leverans och momsdeklaration och gemensam fyllning.

| Fält                       | Rapportnivåer |
|-----------------------------|---------------|
| Riktningskod              | 4, 1, 5       |
| Antal deklarationer       | 4, 1, 5       |
| Antal rader              | 4, 1, 5       |
| Siren                       | 4, 1, 5       |
| Region (Avdelning)         | 1, 5          |
| Transportkod              | 1, 5          |
| Ursprungsland           | 1, 5          |
| Typ av transaktion       | 1, 5          |
| Fakturavärde               | 4, 1, 5       |
| Leveranssätt           | 1, 5          |
| Transaktionstyp            | 4, 1, 5       |
| Ansvarsnivå            | 4, 1, 5       |
| Artikelkod              | 1, 5          |
| Nationell NGP                | 1, 5          |
| Nettovikt                  | 1, 5          |
| Statistiskt värde           | 1, 5          |
| Ytterligare enheter            | 1, 5          |
| Ursprungsland, importer | 1, 5          |
| Slutdestination, exporter | 1, 5          |
| Moms kundkod        | 4, 1, 5       |
| Komplementskod          | 4, 1, 5       |
| Referensperiod         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Ställa in Intrastat

- I [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationen:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat-INTRACOM (FR)
    - Intrastat SAISUNIC (FR)

    Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-vat-ids"></a>Skapa moms-ID

#### <a name="set-up-vat-codes-for-your-company"></a>Skapa momskoder för ditt företag

1. Gå till **Skatt** \> **Inställningar** \> **Moms** \> **Momsregistreringsnummer**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Land/region** välj **FRA**.
4. I fältet **momsregistreringsnummer** ange ditt företags momsnummernyckel.
5. Gå till **Organisationsadministration** \> **Organisationer** \> **Juridiska personer**, välj ditt företag.
6. På snabbfliken **Utländsk handel och logistik** i avsnittet **Intrastat** ange fälten **momsregistreringsnummer för export** och **momsregistreringsnummer för import** till koden du skapade i steg 4.
7. På **Momsregistrering** snabbfliken i **Momsregistreringsnummer** fältet, ange ditt företags momsregistreringsnummer.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Ställ in momsregistreringsnummer för handelspartner

##### <a name="create-a-registration-type-for-the-company-code"></a>Skapa en registreringstyp för företagskoden

Du måste skapa typer av momsregistreringsnummer för alla länder eller regioner som ditt företag gör affärer med.

1. Gå till **Organisationsadministration** \> **Global adressbok** \> **Registreringstyper** \> **Registreringstyper**.
2. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för momsregistreringsnumret.
3. I dialogrutan **Ange detaljer för registreringstyp** i fältet **Namn** anger du ett namn för den nya registreringstypen. Ange exempelvis **VAT ID**.
4. I fältet **Land/region** välj ett land eller region för handelspartnern.
5. Markera **Skapa**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Matcha registreringstyp med registreringskategori

1. Gå till **Organisationsadministration** \> **Global adressbok** \> **Registreringstyper** \> **Registreringskategorier**.
2. I åtgärdsfönstret väljer du **Ny** om du vill skapa en länk mellan en registreringstyp och en registreringskategori.
3. Välj registreringskategorin **Momsregistreringsnummer** för momsregistreringsnumrets registreringstyp.
4. Upprepa steg 2 och 3 för de andra registreringstyperna som du har skapat för de länder eller regioner som ditt företag gör affärer med.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Ställ in momsnumret för en handelspartner

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. I rutnätet väljer du en kund.
3. I åtgärdsfönstret, på fliken **Kund** i gruppen **Registrering**, markerar du **Registrerings-ID**.
4. På snabbfliken **Registrerings-ID** väljer du **Lägg till** för att skapa ett registrerings-ID.
5. I fältet **Registreringstyp** väljer du den registreringstyp som du skapade för företagskoden.
6. I fältet **Registreringsnummer** anger du företagets momsnummer.
7. Välj **Spara** i åtgärdsfönstret och stäng sidan.

Mer information finns i [Registrera ID](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **Utländska handelsparametrar**.
2. På fliken **Intrastat** på snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)** eller **Intrastat SAISUNIC (FR)**.
3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
4. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
5. På snabbflikarna **Allmänt** i fältet **Transaktionskod**, välj koden som används för överföring av varor.
6. I fältet **Kreditfaktura**, välj koden som används för retur av varor.
7. Välj namnet på kontaktpersonen i fältet **Arbetare**.
8. På fliken **Kontakt**, lägg till information om kontaktpersonen:

    - I fältet **Telefon** ange kontaktpersonens telefonnummer.
    - I fältet **Fax** ange kontaktpersonens faxnummer.

9. På fliken **Egenskaper för land/region** i fältet **Land/region** anger alla länder eller regioner som ditt företag gör affärer med. Välj **EU** i fältet **Lands-/regiontyp** för respektive land som är EU-medlemstat, så att landet visas i din Intrastat-rapport. För Frankrike väljer du **Inrikes** i fältet för **Lands-/regiontyp**.

### <a name="set-up-compression-of-intrastat"></a>Ställ in komprimering av Intrastat

- Gå till **Skatt** \> **Inställningar** \> **Utländsk handel** \> **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För fransk Intrastat, välj följande fält:
 
    - Statistikprocedur
    - Ursprungsland/region
    - Transport
    - Korrigering
    - Land/region
    - Region för ursprung/destination
    - Riktning
    - Avsändarens land/region
    - Transaktionskategori
    - Artikel

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Konfigurera produktparametrar för Intrastatdeklarationen

1. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.
2. I rutnätet väljer du en produkt.
3. På snabbfliken **Handel med utlandet** i avsnittet **Intrastat** fältet **Vara** väljer du varukoden. Namnet på varan skrivs ut i fältet **Beskrivning av varor** i Intrastat-rapporten.
4. I avsnittet **Ursprung**, i **fältet Land/region**, väljer du produktens urpsrungsland eller ursprungsregion.
5. På snabbfliken **Hantera lager**, i fältet **Nettovikt**, anger du produktens vikt i kilo.

### <a name="ngp-codes"></a>NGP-koder

I DEB-rapporten består kodifieringen av produkter av följande element:

- Den åttasiffriga CN8-kod som representerar EU-kodens tariff- och statistiktaxa.
- Den ensiffriga nationella artikelkoden Nomenclature Générale des Produits (NGP) om tillämpligt.

Under 2022 gäller NGP endast tre typer av produkter:

- Några produkter från kor, får och getter
- Militär utrustning
- Franska viner

Du måste ställa in NGP-koderna och tilldela dem till relaterade produkter. Fältet **NGP** ställs sedan automatiskt in på sidan **Intrastat-journal**.

#### <a name="set-up-an-ngp-code"></a>Ställa in en NGP-kod

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **NGP-koder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **NGP** ange en ensiffrig kod.
4. I fältet **Beskrivning**, ange en beskrivning för koden.

#### <a name="assign-an-ngp-code-to-a-product"></a>Tilldela en NGP-kod till en produkt

1. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.
2. I rutnätet väljer du en produkt.
3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **NGP** väljer du lämplig NGP-kod.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Konfigurera lagerställeparametrar för Intrastatdeklarationen

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Lagerställen**.
2. Välj ett lagerställe och markera sedan **Lägg till** eller på snabbfliken, välj **Lägg till** eller **Redigera**.
3. I dialogrutan, i fältet **Ort** välj lagerställets ort. Delstatens ort eller provins används som en region för din DEB-rapport.

### <a name="set-up-the-transport-method"></a>Konfigurera en transportmetod

1. Gå till **Moms** \> **Inställningar** \> **Handel med utlandet** \> **Transportmetod**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. Ange en unik kod i fältet **Transport**. Företag i Frankrike använder ensiffriga transportkoder.

### <a name="intrastat-journal"></a>Intrastat-journal

Gå till **Moms** \> **Deklarationer** \> **Utländsk handel** \> **Intrastat** för att hantera dina transaktioner som är tillämpliga på utrikeshandel med EU-länder. Mer information finns i [Intrastat, översikt](emea-intrastat.md).

Kolumnen **NGP** är specifik för Frankrike och visar NGP-koden för produkten. Om NGP inte kan användas för en produkt visas **0** (noll). För att justera NGP-koden, välj transaktionen och sedan på **Allmän** i avsnittet **Koder** i fältet **NGP** välj önskad NGP -kod.

#### <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter, projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller destinationsregion (för utförsel) eller försändelse (vid införsel) kommer att överföras.

Eftersom DEB-rapporten är en kombination av listan över försäljning inom EU och Intrastat-rapporten, innehåller den även *trepartstransaktioner*, där en direktleverans görs från ett EU-land (part A) till ett annat EU-land (part C) och en fransk juridisk enhet (part B) är den mitt i trepartsaffären.

#### <a name="generate-a-deb-intrastat-report"></a>Skapa DEB-rapport (Intrastat)

1. Gå till **Moms** \> **Deklarationer** \> **Utländsk handel** \> **Intrastat**.
2. I åtgärdsfönstret väljer du **Utdata** \> **Rapport**.
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

4. Välj **OK** för att stänga dialogrutan **Intrastat-rapport**.
5. I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Parametrar** i fältet **Rapportnivå** väljer du rapportnivå. Rapportnivån kan vara **1 – statistiskt svar**, **4 – momsdeklaration** eller **5 – statistiskt svar på leverans och momsdeklaration**.

## <a name="example"></a>Exempel

Följande exempel visar hur du ställer in Franska Intrastat och skapar DEB-rapporten. Använd **DEMF** juridiska personen.

### <a name="preliminary-setup"></a>Preliminär inställning

1. I [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), i det delade tillgångsbiblioteket, ladda ner den senaste versionen av följande konfigurationer för elektronisk rapportering (ER) för Intrastat-deklarationsformat:

    - Intrastat-modell
    - Intrastat-rapport
    - Intrastat-INTRACOM (FR)

2. Ställ in en produkthierarki:

    1. Gå till **Produktinformationshantering** \> **Inställningar** \> **Kategorier och attribut** \> **Kategorihierarkier**.
    2. Välj **Intrastat** i rutnätet.
    3. I Åtgärdsfönstret, på fliken **kategorihierarki**, i gruppen **underhåll**, markerar du **redigera**.
    4. I åtgärdsfönstret klickar du på **Ny kategorinod**.
    5. I fältet **Namn** anger du **Autres Libournais**.
    6. I fältet **Kod** ange **2204 21 42**.
    7. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-vat-ids"></a>Skapa moms-ID

#### <a name="set-up-vat-codes-for-your-company"></a>Skapa momskoder för ditt företag

1. Gå till **Skatt** \> **Inställningar** \> **Moms** \> **Momsregistreringsnummer**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Land/region** välj **FRA**.
4. I fältet **Momsregistreringsnummer** ange **MS123456**.
5. Gå till **Organisationsadministration** \> **Organisationer** \> **Juridiska personer** och välj **DEMF**.
6. På snabbfliken **Utländsk handel och logistik** i avsnittet **Intrastat** ange fälten **momsregistreringsnummer för export** och **momsregistreringsnummer för import** till koden du skapade i steg 4.
7. På snabbfliken **Momsregistrering** i fältet **Momsregistreringsnummer** ange **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Ställ in momsregistreringsnummer för handelspartner

##### <a name="create-a-registration-type-for-the-company-code"></a>Skapa en registreringstyp för företagskoden

1. Gå till **Organisationsadministration** \> **Global adressbok** \> **Registreringstyper** \> **Registreringstyper**.
2. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för momsregistreringsnumret.
3. I dialogrutan **Ange detaljer för registreringstyp**, i fältet **Namn**, anger du **momsregistreringsnummer**.
4. I fältet **Land/region** välj **DEU**.
5. Markera **Skapa**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Matcha registreringstyp med registreringskategori

1. Gå till **Organisationsadministration** \> **Global adressbok** \> **Registreringstyper** \> **Registreringskategorier**.
2. I åtgärdsfönstret väljer du **Ny** om du vill skapa en länk mellan en registreringstyp och en registreringskategori.
3. För registreringstyp **momsregistreringsnummer** för landet **DEU** välj registreringstyp **momsregistreringsnummer**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Ange kundens momsregistreringsnummer

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. Välj **DE-016** i rutnätet.
3. I åtgärdsfönstret, på fliken **Kund** i gruppen **Registrering**, markerar du **Registrerings-ID**.
4. På snabbfliken **Registrerings-ID** väljer du **Lägg till** för att skapa ett registrerings-ID.
5. I fältet **Registreringstyp** väljer du **momsregistreringsnummer**.
6. I fältet **Registreringsnummer** anger du **DE9012**.
7. Välj **Spara** i åtgärdsfönstret och stäng sidan.
8. På snabbfliken **Faktura och leverans** i avsnittet **Moms** i fältet **Momsregistreringsnummer**, välj **DE9012**.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **Utländska handelsparametrar**.
2. På fliken **Intrastat** på fliken **Allmänt** i fältet **Transaktionskod**, välj **11**.
3. På snabbfliken **Elektronisk rapportering** i fältet **Mappning av filformat**, välj **Intrastat INTRACOM (FR)**.
4. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
5. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
6. I fältet **medarbetare** välj en post.
7. På fliken **Kontakt** i fältet **Telefon** ange kontaktpersonens telefonnummer
8. I fältet **Fax** ange kontaktens faxnummer.

### <a name="create-ngp-code"></a>Skapa en NGP-kod

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **NGP-koder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **NGP** ange **8**.
4. I fältet **Namn på beskrivning** ange **NGP 8**.
5. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-product-information"></a>Konfigurera produktinformation

1. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.
2. Välj **D0001** i rutnätet.
3. På snabbfliken **Handel med utlandet** i avsnittet **Intrastat** i fältet **NGP** väljer du **8**.
4. I fältet **Vara** välj **2204 21 42**.
5. I avsnittet **Ursprung** i fältet **land/region**, välj **FRA**.
6. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **2**.
7. Välj **Spara** i åtgärdsfönstret och stäng sidan.
8. Välj **D0003** i rutnätet.
9. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **100 200 30**.
10. I avsnittet **Ursprung** i fältet **land/region**, välj **DEU**.
11. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **5**.
12. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-regime-codes"></a>Ställa in användningskoder

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **Statistikprocedur**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. På fältet **Statistisk procedur**, ange **21**.
4. I fältet **Text 1** ange **användningskod 21**.

### <a name="change-the-site-address"></a>Ändra platsens adress

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Webbplats**.
2. Välj **1** i rutnätet.
3. På snabbfliken **Adresser** väljer du **Registrera**.
4. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **FRA**.
5. Välj **OK**.
6. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Lagerställen**, välj ett lagerställe.
7. På snabbfliken **Adresser** väljer du **Lägg till**.
8. I dialogrutan **ny adress**, i fältet **Land/region**, väljer du **FRA**.
9. I fältet **Ort** väljer du **Bordeaux**.
10. Välj **OK** för att stänga dialogrutan.

### <a name="set-up-a-transport-method"></a>Konfigurera en transportmetod

1. Gå till **Moms** \> **Inställningar** \> **Handel med utlandet** \> **Transportmetod**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Transport** anger du **3**.
4. I fältet **Beskrivning** anger du **Vägtransport**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Tilldela transportläge till ett leveranssätt

1. Gå till **Anskaffning och källa** \> **Inställningar** \> **Fördelning** \> **Leveranssätt**.
2. Välj **50** i rutnätet.
3. På snabbfliken **Utländsk handel** i fältet **Transport**, välj **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Skapa en försäljningsorder med en EU-kund som inkluderar den nya produkten

1. Gå till **Kundreskontra** \> **Order** \> **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningorder** i avsnittet **Kund** i fältet **Kundkonto** välj **DE-016**.
4. I avsnittet **Adress** i fältet **Leveransadress** välj plustecknet (**+**) för att skapa en adress.
5. I dialogrutan **Ny adress** i fältet **Namn på beskrivning** ange **Tyskland**.
6. I fältet **Land/region** välj **DEU**.
7. Välj **OK**.
8. I dialogrutan **Skapa försäljningsorder** välj **OK**.
9. På snabbfliken **Försäljningsorderrader** i fältet **Artikelnummer** välj **0001**.
10. På snabbfliken **Radinformation** på fliken **Utländsk handel** i fältet **Statistikprocedur**, välj **21**.
11. I fältet **Ursprungsstat** väljer du **AL**.
12. Klicka på **Spara** i åtgärdsfönstret.
13. På fliken **Rubrik** på snabbfliken **Leverans** i fältet **Leveranssätt** se till att **50** är vald.
14. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
15. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**. Du kan sedan välja **OK** för att bokföra fakturan.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Överför transaktionen till Intrastatjournalen och granska resultatet

1. Gå till **Moms** \> **Deklarationer** \> **Utländsk handel** \> **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**. Välj sedan **OK**.
4. Sortera transaktionerna efter fältet **Datum**. Den översta transaktionen är resultattransaktionen.

    ![Rad som representerar försäljningsordern på Intrastat-sidan.](media/intrastat_fr_1.png)

5. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Försäljningsorderdetaljer på fliken Allmänt på Intrastat-sidan.](media/intrastat_fr_2.png)

6. I åtgärdsfönstret väljer du **Utdata** \> **Rapport**.
7. I dialogrutan **Intrastat-rapport** på snabbfliken **Parametrar** i avsnittet **Datum** välj månad för försäljningsordern du skapade.
8. Ställ in alternativet **Exportalternativ** ange **Generera fil** till **Ja**.
9. I fältet **Filnamn** anger du ett namn som krävs.
10. Välj **OK** för att stänga dialogrutan **Intrastat-rapport**.
11. I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Parametrar** i fältet **Rapportnivå**, välj **5 – statistiskt svar på leverans och momsdeklaration** och granska rapporten.

    ![Intrastat Intracom-rapport rörande utförsel.](media/intrastat_fr_3.png)

12. Granska den genererade Excel-rapporten.

    ![Intrastatrapport rörande utförsel.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
