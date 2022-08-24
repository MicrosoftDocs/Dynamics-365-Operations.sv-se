---
title: Intrastat för Polen
description: Detta ämne innehåller information om Intrastatrapportering i Polen.
author: AdamTrukawka
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 473581fa4f3f1e8cac06d5748f28116e6615215e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281655"
---
# <a name="polish-intrastat"></a>Intrastat för Polen

[!include[banner](../includes/banner.md)]

Sidan **Intrastat** används för att generera och rapportera information om handel mellan länder i EU. Den polska Intrastatdeklarationen innehåller information om handel med varor för rapportering.

Följande fält finns inkluderade i den polska Intrastatdeklarationen: Alla fält är inkluderade vid införsel och utförsel utom **RodzajTransportu** (transportläget) och **KrajPochodzenia** (ursprungslandet eller ursprungsområdet) som inte tas med i utförsel, samt **IdKontrahenta** (kundens utländska momsnummer) som inte ingår i införseln.

| Fältnamn | Beskrivning |
|-------------------------|-------------------------|
| Deklaracja-data | Det datum då dokumentet skapas. |
| Miesiac | Referensmånaden för deklarationen. |
| Rok | Referensåret för deklarationen. |
| Numer | Deklarationsnumret i referensperioden. |
| Wersja | Versionsnumret för deklarationen. |
| NrWlasny | Deklarationsidentifieraren. Värdet genereras automatiskt. |
| Typ | Rapportens riktning.</br><li>För införsel trycks "P".</li><li>För utförsel trycks "W".</li> |
| Rodzaj | Deklarationstypen. Värdet anger huruvida rapporten är den ursprungliga deklarationen eller en korrigeringsdeklaration. |
| UC | Enhetskoden som Intrastat-deklarationen adresseras till. Värdet anges i fältet **Momsregistreringsnummer** i avsnittet **Moms** på fliken **Agent** på sidan **Utländska handelsparametrar**. |
| Nazwa | Företagets namn. |
| Miejscowosc, UlicaNumer, KodPocztowy | Den fullständiga adressen för den juridiska personen. |
| Nip | Det polska momsregistreringsnumret. |
| Regon | Det polska statistiska ID-numret (företagsnummer). |
| LacznaWartoscFaktur | Summan av fakturavärdena. |
| LacznaWartoscStatystyczna | Summan av statistiska värden. |
| LacznaLiczbaPozycji | Totalt antal varuartiklar. |
| PozId | Löpnummer för en given varuartikel. |
| OpisTowaru | Varunamnet. |
| KrajPochodzeniaWysylki | Internationella standardiseringsorganisationens (ISO) kod för motpartens land eller region. |
| WarunkiDostawy | Intrastat-koden för leveransvillkoren. |
| RodzajTransakcji | Koden som anger transaktionens karaktär. Polska företag använder tvåsiffriga transaktionskoder. |
| KodTowarowy | Den åttasiffriga varukoden enligt kombinerad nomenklatur. |
| RodzajTransportu | Intrastat-koden för transportsättet. |
| KrajPochodzenia | ISO-koden för landet eller regionen där varorna framställdes eller tillverkades. |
| MasaNetto | Nettovikten i hela kilo. |
| IloscUzupelniajacaJm | Kvantiteten i kompletterande måttenhet i heltal. |
| WartoscFaktury | Fakturavärdet för alla transaktioner som ingår i en artikel. |
| WartoscStatystyczna | Statistiskt värde. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | För- och efternamn, telefonnummer, faxnummer och e-postadress för den person som skickar deklarationen. |
| IdKontrahenta | Kundens utländska momsnummer i en EU-medlemsstat. |


## <a name="set-up-intrastat"></a>Ställa in Intrastat

Från den globala databasen importerar du de senaste versionerna av följande ER-konfigurationer (elektronisk rapportering):

   - Intrastat-modell
   - Intrastat-rapport
   - Intrastat (PL)

Mer information finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Konfigurera ett momsregistreringsnummer och ett företagsnummer för företaget

### <a name="create-registration-types-for-company-codes"></a>Skapa registreringstyper för företagskoder

Du måste skapa två registreringstyper för företagskoder: en för momsregistreringsnummer (NIP-kod) och en för företagsnummer (Regon-kod).

1. Gå till **Organisationsadministration** > **Global adressbok** > **Registreringstyper** > **Registreringstyper**.
2. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för momsregistreringsnumret.
3. I dialogrutan **Ange detaljer för registreringstyp** > fältet **Namn** anger du ett namn för den nya registreringstypen. Ange exempelvis **NIP**.
4. I fältet **Land/region** välj **POL**.
5. Markera **Skapa**.
6. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för företagsnumret.
7. I dialogrutan **Ange detaljer för registreringstyp** > fältet **Namn** anger du ett namn för den nya registreringstypen. Ange till exempel **Regon**.
8. I fältet **Land/region** välj **POL**.
9. Markera **Skapa**.

### <a name="match-the-registration-types-with-registration-categories"></a>Matcha registreringstyper med registreringskategorier

1. Gå till **Organisationsadministration** > **Global adressbok** > **Registreringstyper** > **Registreringskategorier**.
2. I åtgärdsfönstret väljer du **Ny** om du vill skapa en länk mellan varje registreringstyp som du skapat och en registreringskategori.

    - Välj registreringskategorin **Momsregistreringsnummer** för momsregistreringsnumrets registreringstyp (NIP-koden).
    - Välj registreringskategorin **Företags-ID (COID)** för företagsnumrets registreringstyp (Regon-kod).

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Konfigurera ett momsregistreringsnummer och ett företagsnummer för företaget

1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
2. I rutnätet väljer du ditt företag.
3. Välj **Registrerigns-ID:n** i åtgärdsfönstret.
4. På snabbfliken **Registrerings-ID** väljer du **Lägg till**.
5. I fältet **Registreringstyp** väljer du en av de registreringstyper som du skapade tidigare.
6. Ange företagets momsregistreringsnummer (NIP-kod) eller företagsnummer (Regon-kod) beroende på vilken registreringstyp du valde i det föregående steget.
7. Upprepa steg 4 till 6 för den andra registreringstyp som du skapade tidigare.

## <a name="set-up-a-company-address"></a>Konfigurera en företagsadress

1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
2. I rutnätet väljer du ditt företag.
3. På fliken **Adresser** väljer du **Registrera**.
4. I dialogrutan **Redigera adress** > fältet **Postnummer** väljer du ditt företags postnummer.
5. Ange adressen i fältet **Gatuadress**.
6. I fältet **Ort** väljer du din stad.

## <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** > **Konfiguration** > **Parametrar för utrikeshandel**.
2. På fliken **Intrastat** > snabbfliken **Elektronisk rapportering** > fältet **Mappning av filformat** väljer du **Intrastat (PL)**.
3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
4. På snabbfliken **Artikelkodhierarki** i fältet **Kategorihierarki**, välj **Intrastat**.
5. I fältet **Transaktionskod** väljer du transaktionskod för egenskapsöverföringar. Du använder den här koden för transaktioner som genererar faktiska eller planerade överlåtelser av egendom mot ersättning (ekonomisk eller annan). Du använder det även för korrigeringar. Företag i Polen använder tvåsiffriga transaktionskoder.
6. I fältet **Kreditfaktura** väljer du transaktionskod för retur av varor.
7. På fliken **Egenskaper för land/region** i fältet **Land/region** anger alla länder eller regioner som ditt företag gör affärer med. Välj **EU** i fältet **Lands-/regiontyp** för respektive land som är EU-medlemstat, så att landet visas i din Intrastat-rapport. För Polen väljer du **Inrikes** i fältet för **Lands-/regiontyp**.
8. På fliken **Agent** tab > snabbfliken **Agent** > avsnittet **Moms** > fältet **Momsregistreringsnummer** anger du **420000** för att ange den enhetskod som Intrastat-deklarationen adresserats till.
9. På fliken **Kontakt** anger du namn, telefonnummer, faxnummer och e-postadress för den person som skickar in deklarationen.
10. På fliken **Nummerserier** > i fältet **Nummerseriekod** för referensen **XML-filnummer** anger du ett icke-kontinuerlig nummerserie med maximalt nio tecken. Detta fält används för att automatiskt generera ett värde för fältet **Deklarationsidentifierare** i Intrastat-rapporten.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Konfigurera produktparametrar för Intrastatdeklarationen

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta produkter**.
2. I rutnätet väljer du en produkt.
3. På snabbfliken **Handel med utlandet** > avsnittet **Intrastat** > fältet **Vara** väljer du varukoden. Namnet på varan skrivs ut i fältet **Beskrivning av varor** i Intrastat-rapporten.
4. I avsnittet **Ursprung**, i **fältet Land/region**, väljer du produktens urpsrungsland eller ursprungsregion.
5. På snabbfliken **Hantera lager**, i fältet **Nettovikt**, anger du produktens vikt i kilo.

## <a name="set-up-compression-of-intrastat"></a>Ställ in komprimering av Intrastat

-   Gå till **Tax** > **Inställningar** > **Utländsk handel** > **Komprimering av Intrastat** och välj de fält som ska jämföras när Intrastat-information sammanfattas. För polskt Intrastat, välj följande fält:

    - Artikel
    - Transaktionskategori
    - Ursprungsland/region
    - Transport
    - Leveransvillkor
    - Avsändarens land/region
    - Land/region
    - Korrigering
    - Momsregistreringsnummer
    - Riktning
    - Faktura

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Konfigurera transportmetod och leveransvillkor

1.  Konfigurera transportkoder.

    1. Gå till **Moms** > **Inställningar** > **handel med utlandet** > **Transportmetod**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. Ange en unik kod i fältet **Transport**. Polska företag använder ensiffriga transportkoder.

2.  Konfigurera Intrastatkoder för leveranssätt.

    1. Gå till **Anskaffning och källa** > **Inställningar** > **Fördelning** > **Leveransvillkor**.
    2. Välj en uppsättning leveransvillkor i rutnätet.
    3. Ange din unika kod på snabbfliken **Allmänt** i fältet **Intrastatkod**.

## <a name="intrastat-transfer"></a>Intrastat-överföring

På sidan **Intrastat** kan du välja **Överför** om du vill överföra information om inomeuropeisk handel automatiskt från dina försäljningsorder, fritextfakturor, inköpsorder, leverantörsfakturor, inleveranser av leverantörsprodukter, projektfakturor och överföringsorder. Endast dokument som har ett EU-land som land eller region för destination eller försändelse kommer att överföras.

Du kan också ange transaktioner manuellt genom att välja **Ny** i åtgärdsfönstret.

### <a name="generate-an-intrastat-report"></a>Skapa Intrastat-rapport

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. I åtgärdsfönstret väljer du **Utdata** &gt; **Rapport**.
3. I dialogrutan **Intrastat-rapport** anger du följande fält.

    | Fält | Beskrivning |
    |-------------------------|-------------------------|
    | Från-datum | Välj startdatumet för rapporten. |
    | Generera fil | Ange detta alternativ som **Ja** om du vill generera en .xml-fil för din Intrastatrapport. |
    | Filnamn | Ange namnet på .xml-filen. |
    | Generera rapport | Ange detta alternativ som **Ja** om du vill generera en .xlsx-fil för din Intrastatrapport. |
    | Rapportfilnamn | Ange namnet på .xlsx-filen. |
    | Riktning | Välj **Införsel** för en rapport om inomeuropeiska införslar.</br>Välj **Utförsel** för en rapport om inomeuropeiska införslar. |
    | Deklarationsidentifierare | Dokument-ID genereras automatiskt och kan uppdateras. |
    | Deklarationstyp | Välj **Deklaration** för en ursprunglig deklaration.</br>Välj **Deklarationskorrigering – ersättning** för en korrigeringsdeklaration som är tänkt att helt ersätta en befintlig, tidigare inlämnad ursprunglig deklaration eller korrigeringsdeklaration. |
    | Ort för skapande av dokument | Ange det värde som ska skrivas ut i fältet **Miejscowosc** i Intrastat-deklarationen. |
    | Datum för skapande av dokument | Ange det värde som ska skrivas ut i fältet **Deklaracja Data** i Intrastat-deklarationen. |
    | Dokumentnr | Ange det värde som ska skrivas ut i fältet **Numer** i Intrastat-deklarationen. |
    | Dokumentversion | Ange det värde som ska skrivas ut i fältet **Wersja** i Intrastat-deklarationen. |

4. Välj **OK** och granska rapporterna som genereras.

## <a name="example"></a>Exempel

I det här exemplet visas hur du bokför införsel och utförsel för Intrastat med hjälp av den juridiska personen **DEMF**.

### <a name="preliminary-setup"></a>Preliminär inställning

Importera den senaste versionen av följande ER-konfigurationer:

   - Intrastat-modell
   - Intrastat-rapport
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Konfigurera en företagsadress

1. Gå till **Organisationsadministration** > **Global adressbok** > **Adresser** > **Inställning av adress**.
2. På fliken **Ort** väljer du **Ny**.
3. I fältet **Land/region** välj **POL**.
4. I fältet **Ort** anger du **Warszawa**.
5. På fliken **Postnummer** väljer du **Ny**.
6. I fältet **Land/region** välj **POL**.
7. I fältet **Ort** väljer du **Warszawa**.
8. I fältet **Postnummer** anger du **00-844**.
9. Gå till **Organisationsadministration** > **Organisation** > **Juridiska personer** och välj den juridiska personen **DEMF**.
10. På snabbfliken **Adresser** väljer du **Registrera**.
11. I fältet **Land/region** välj **POL**.
12. I fältet **Postnummer** väljer du **31-111**.
13. I fältet **Gatuadress** anger du **Statystyczna 22/1**.
14. I fältet **Ort** väljer du **Warszawa**.
15. Välj **OK**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Konfigurera ett momsregistreringsnummer och en företagskod för företaget

### <a name="create-registration-types-for-company-codes"></a>Skapa registreringstyper för företagskoder

1. Gå till **Organisationsadministration** > **Global adressbok** > **Registreringstyper** > **Registreringstyper**.
2. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för momsregistreringsnumret (NIP-koden).
3. I dialogrutan **Ange detaljer för registreringstyp**, i fältet **Namn**, anger du **NIP**.
4. I fältet **Land/region** välj **POL**.
5. Markera **Skapa**.
6. I åtgärdsfönstret väljer du **Ny** för att skapa en registreringstyp för företagsnumret (Regon-kod).
7. I dialogrutan **Ange detaljer för registreringstyp**, i fältet **Namn**, anger du **Regon**.
8. I fältet **Land/region** välj **POL**.
9. Markera **Skapa**.

### <a name="match-the-registration-types-with-registration-categories"></a>Matcha registreringstyper med registreringskategorier

1. Gå till **Organisationsadministration** > **Global adressbok** > **Registreringstyper** > **Registreringskategorier**.
2. I åtgärdsfönstret väljer du **Ny** om du vill skapa en länk mellan varje registreringstyp som du skapat och en registreringskategori.

    - För registreringstyp **NIP** väljer du registreringskategori **Momsregistreringsnummer**.
    - För registreringstyp **Regon** väljer du registreringskategori **Företags-ID (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Konfigurera ett momsregistreringsnummer och ett företagsnummer för företaget

1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
2. Välj **DEMF** i rutnätet.
3. Välj **Registrerigns-ID:n** i åtgärdsfönstret.
4. På snabbfliken **Registrerings-ID** väljer du **Lägg till**.
5. I fältet **Registreringstyp** väljer du **NIP**.
6. I fältet **Registreringsnummer** anger du **1234567890**.
7. Markera **Lägg till**.
8. I fältet **Registreringstyp** väljer du **Regon**.
9. I fältet **Registreringsnummer** anger du **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Konfigurera nummerseriekod

1. Gå till **Organisationsadministrering** > **Nummerserier** > **Nummerserier**.
2. I åtgärdsfönstret, på fliken **Nummerserie**, i gruppen **Ny**, väljer du **Nummerserie**.
3. I snabbfliken **Identifiering**, i fältet **Nummerseriekod**, anger du **XML\_fil**.
4. På snabbfliken **Omfångsparametrar**, i fältet **Omfång**, väljer du **Företag**.
5. I fältet **Företag** väljer du **DEMF**.
6. I snabbfliken **Segment**, i fältet **Längd** tillhörande segmentet **Alfanumeriskt**, anger du **4**.
7. På snabbfliken **Allmänt**, i avsnittet **Inställningar**, anger du alternativet **Löpande** som **Nej**.
8. I avsnittet **Nummerallokering**, i fältet **Störst**, anger du **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar

1. Gå till **Moms** > **Inställningar** > **Utländsk handel** > **Utländska handelsparametrar**.
2. På fliken **Intrastat** på snabbfliken **Allmänt** i fältet **Transaktion** **kod** välj **11**.
3. På snabbfliken **Elektronisk rapportering**, i fältet **Mappning av filformat**, väljer du **Intrastat (PL)**.
4. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport**.
5. På snabbfliken **Artikelkodhierarki** bekräftar du att fältet **Kategorihierarki** är inställt på **Intrastat**.
6. På fliken **Egenskaper för land/region**, välj **Ny**.
7. I fältet **Part för land/region** välj **POL**. I fältet **Lands-/regiontyp** väljer du sedan **Inrikes**.
8. I fältet **Part för land/region** välj **DEU**. I fältet **Lands-/regiontyp** väljer du sedan **EU**.
9. På fliken **Agent** > snabbfliken **Agent** > avsnittet **Moms** > fältet **Momsregistreringsnummer** anger du **420000**.
10. På fliken **Kontakt** i fältet **Namn** anger du **Manish Chopra**.
11. I fältet **Telefon** anger du **425-555-5068**.
12. I fältet **Faxnummer** anger du **425-555-5049**.
13. I fältet **E-postadress** anger du **manishc@contoso.com**.
14. På fliken **Nummerserier**, i fältet **Nummerseriekod** för referensen **XML-filnummer**, väljer du **XML\_fil**.

### <a name="set-up-product-information"></a>Konfigurera produktinformation

1. Gå till **Produktinformationshantering** > **Produkter** > **Frisläppta** **produkter**.
2. Välj **D0001** i rutnätet.
3. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **100 200 30**.
4. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **2**.
5. Klicka på **Spara** i åtgärdsfönstret.
6. Välj **D0003** i rutnätet.
7. På snabbfliken **Utländsk handel** i avsnittet **Intrastat** i fältet **Artikel**, välj **100 200 30**.
8. I avsnittet **Ursprung** i fältet **land/region**, välj **DEU**.
9. På snabbfliken **Hantera lager** i avsnittet **Viktmått** i fältet **Nettovikt**, ange **5**.
10. Klicka på **Spara** i åtgärdsfönstret.

### <a name="change-the-site-address"></a>Ändra platsens adress

1. Gå till **Lagerstyrning** > **Konfiguration** > **Distributionslager** > **Platser**.
2. Välj **1** i rutnätet.
3. På snabbfliken **Adresser** väljer du **Registrera**.
4. I dialogrutan **Redigera adress**, i fältet **Land/region**, väljer du **POL**.
5. Välj **OK**.

### <a name="set-up-a-transport-method"></a>Konfigurera en transportmetod

1. Skapa en transportmetod.

    1. Gå till **Moms** > **Inställningar** > **handel med utlandet** > **Transportmetod**.
    2. Klicka på **Ny** i åtgärdsfönstret.
    3. I fältet **Transport** anger du **3**.
    4. I fältet **Beskrivning** anger du **Vägtransport**.

2. Tilldela den nya transportmetoden till en leveransmetod. På det här sättet konfigurerar du de standardvärden som används för transportmetoden när motsvarande leveranssätt väljs.

    1. Gå till **Anskaffning och källa** > **Inställningar** > **Fördelning** > **Leveranssätt**.
    2. Välj **10** i rutnätet.
    3. På snabbfliken **Utländsk handel** i fältet **Transport**, välj **3**.

3. Välj standardleveranssätt för en kund.

    1. Gå till **Kundreskontra** > **Kunder** > **Alla kunder**.
    2. Välj **DE-016** i rutnätet.
    3. På snabbfliken **Faktura och leverans**, i fältet **Leveranssätt**, väljer du **10**.

4. Välj standardleveranssätt för en leverantör.

    1. Gå till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer**.
    2. Välj **DE-001** i rutnätet.
    3. På snabbfliken **Faktura och leverans**, i fältet **Leveranssätt**, väljer du **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Konfigurera koder för leveransvillkor

1. Konfigurera en Intrastat-kod för leveransvillkoren.

    1. Gå till **Anskaffning och källa** > **Inställningar** > **Fördelning** > **Leveransvillkor**.
    2. Välj **CIF** i rutnätet.
    3. På snabbfliken **Allmänt**, i fältet **Intrastatkod**, väljer du **CIF**.

2. Välj standardleveransvillkor för en kund.

    1. Gå till **Kundreskontra** > **Kunder** > **Alla kunder**.
    2. Välj **DE-016** i rutnätet.
    3. På snabbfliken **Faktura och leverans**, i fältet **Leveransvillkor**, väljer du **CIF**.

3. Välj standardleveransvillkor för en leverantör.

    1. Gå till **Leverantörsreskontra** > **Leverantörer** > **Alla leverantörer**.
    2. Välj **DE-001** i rutnätet.
    3. På snabbfliken **Faktura och leverans**, i fältet **Leveransvillkor**, väljer du **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Bekräfta momsregistreringsnummerkod för EU-kund

1. Gå till **Kundreskontra** > **Kunder** > **Alla kunder**.
2. Välj **DE-016** i rutnätet.
3. Ppå snabbfliken **Faktura och leverans**, i avsnittet **Moms**, bekräftar du att fältet **Momsregistreringsnummer** har angivits som **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Skapa en försäljningsorder med en EU-kund

1. Gå till **Leverantörsreskontra** > **Order** > **Alla försäljningsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa försäljningsorder** på **Kund** i avsnitt **Kund** i fält **Kundkontot**, välj **DE-016**.
4. På snabbfliken **Allmänt** i avsnittet **Lagringsdimensioner** i fältet **Webbplats**, välj **1**.
5. I fältet **Lagerställe**, välj **11**.
6. På fliken **Adress** bekräftar du att fältet **Adress** angivits som **Teichgasse 12, Kiel, 24103, DEU**, detta eftersom kunden är hemmahörande i Tyskland.
7. Välj **OK**.
8. På fliken **Rubrik**, på snabbfliken **Leverans**, bekräftar du att fältet **Leveransvillkor** är angivet som **CIF** samt att fältet **Leveranssätt** har angivits som **10**.
9. På fliken **Rader** > snabbfliken **Försäljningsorderrader** > fältet **Artikelnummer** väljer du **D0001**. I fältet **Kvantitet**, ange **8**.
10. På snabbfliken **Raddetaljer**, på fliken **Handel med utlandet**, bekräftar du att fältet **Transaktionskod** är angivet som **11**, att fältet **Vara** är angivet som **100 200 30**, samt att fältet **Ursprungsland/-region** är angivet som **POL**.
11. Klicka på **Spara** i åtgärdsfönstret.
12. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
13. I dialogrutan **Bokföring av faktura** på snabbfliken **Parametrar** i avsnittet **Parameter** i fältet **Kvantitet**, välj **Alla**.
14. I snabbfliken **Inställningar**, i fältet **Försäljningsdatum**, väljer du **2021-10-18** (18 oktober 2021).
15. Välj **OK** när du vill bokföra faktura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Överför transaktionen till Intrastatjournalen och granska resultatet

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överför)** i avsnittet **Parametrar** ange alternativet **Kundfaktura** till **Ja**.
4. Välj **filter**.
5. I dialogrutan **Intrastat-filter**, på fliken **Intervall**, väljer du den första raden och bekräftar att fältet **Fält** angetts som **Datum**.
6. Välj aktuellt datum i fältet **Kriterier**.
7. Välj **OK** för att stänga dialogrutan **Intrastat-filter**.
8. Välj **OK** för att stänga dialogrutan **Intrastat (överför)** och granska resultatet. Raden representerar den försäljningsorder som du skapade tidigare.

    ![Rad som representerar försäljningsordern på Intrastat-sidan](media/intrastat_pl_1.png)

9. Markera transaktionsraden och välj fliken **Allmänt** för att se fler detaljer.

    ![Försäljningsorderdetaljer på fliken Allmänt på Intrastat-sidan](media/intrastat_pl_2.png)

10. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
11. I dialogrutan **Intrastatrapport** > snabbfliken **Parametrar** > i avsnittet **Datum** > fältet **Från datum** väljer du aktuell månads första dag.
12. I avsnittet **Export** **alternativet** ange **Generera fil** till **Ja**. I fältet **Filnamn** anger du sedan erforderligt namn.
13. Ange alternativet **Generera rapport** som **Ja**. I fältet **Rapportfilens namn** anger du sedan erforderligt namn.
14. I fältet **Riktning** väljer du **Utförsel**.
15. I avsnittet **Mappning av filformat** bekräftar du att fältet **Deklarationstyp** har angetts som **Deklaration**.
16. I fältet **Ort för dokumentframställande** anger du **Krakow**.
17. I fältet **Datum för dokumentframställande** väljer du **2021-10-19** (19 oktober 2021).
18. I fältet **Dokumentnr.** anger du **11**.
19. I fältet **Dokumentversion** anger du **22**.
20. Välj **OK** och granska rapporten i XML-format som genereras. Tabellen nedan visar värdena i exempelrapporten.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Fältnamn</strong></p>
    </td>
    <td>
    <p><strong>Fältbeskrivning</strong></p>
    </td>
    <td>
    <p><strong>Värde</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Information om dokumentet</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja-data</p>
    </td>
    <td>
    <p>Det datum då dokumentet skapades.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Den ort där dokumentet skapades.</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Totalt antal artiklar.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Totalt statistiskt värde.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Det totala fakturavärdet.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Enhetskoden.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Deklarationstypen.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Dokumentversionen.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Dokumentnumret.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>Referensmånaden.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>Referensåret.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>Rapportens riktning.</p>
    </td>
    <td>
    <p>U</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>Deklarationsidentifieraren.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Information om företaget</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>Den ort där företaget finns.</p>
    </td>
    <td>
    <p>Warszawa</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>Företagets Regon-kod.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Företagets NIP-kod.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Företagets postnummer.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Den gata där företaget finns.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Företagets namn.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Information om varan</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Statistiskt värde.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Fakturavärdet.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Nettomassan.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>Kundens momsnummer.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Artikelkoden.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Transaktionskoden.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Leveranssättet.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Koden för landet eller regionen där utförsel/destination finns.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>En beskrivning av varorna.</p>
    </td>
    <td>
    <p>Maskinvara</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Artikelnummer.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Kontaktinformation</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-post</p>
    </td>
    <td>
    <p>Insändarens e-postadress.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Insändarens faxnummer.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Insändarens telefonnummer.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Insändarens namn.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Granska rapporten som genereras i Excel-format.

    ![Intrastatrapport rörande utförsel](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I dialogrutan **Skapa inköpsorder**, i fältet **Leverantörskonto**, väljer du **DE-001**.
4. I fältet **Anläggning** väljer du **1**.
5. I fältet **Lagerställe** väljer du **11**.
6. Välj **OK**.
7. På fliken **Sidhuvud**, på snabbfliken **Leverans**, bekräftar du att fältet **Leveransvillkor** är angivet som **10** samt att fältet **Leveransvillkor** har angivits som **CIF**.
8. På fliken **Rader** > snabbfliken **Inköpsorderrader** > fältet **Artikelnummer** väljer du **D0003**. I fältet **Kvantitet**, ange **6**.
9. På snabbfliken **Raddetaljer**, på fliken **Handel med utlandet**, bekräftar du att **Transaktionskod** har angetts till **11**, att fältet **Transport** angetts som **3**, att fältet **Vara** har angetts som **100 200 30**, samt att fältet **Ursprungsland/-region** angetts som **DEU**.
10. I Åtgärdsfönstret > på fliken **Inköp** > i gruppen **Åtgärd** markerar du **Bekräfta**.
11. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
12. I åtgärdsfältet väljer du **Standard från** innan du i fältet **Standardkvantitet för rader** väljer du **Beställd kvantitet**. Välj sedan **OK**.
13. På snabbfliken **Sidhuvud i leverantörsfaktura** > avsnittet **Fakturaidentifiering** > fältet **Nummer** anger du **00010**.
14. I avsnittet **Fakturadatum**, i fältet **Fakturadatum**, väljer du aktuellt datum. Detta datum används vid Intrastat-överföring.
15. I fältet **Datum för dokumenterhållande** väljer du **2021-10-18** (18 oktober 2021).
16. Om du vill bokföra fakturan väljer du **Bokför** i åtgärdsfönstret.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Skapa en Intrastatdeklaration för införsel

1. Gå till **Moms** > **Deklarationer** > **Utländsk handel** > **Intrastat**.
2. Klicka på **Överför** i åtgärdsfönstret.
3. I dialogrutan **Intrastat (överföring)** anger du alternativet **Leverantörsfaktura** som **Ja**.
4. Välj **OK** för att överföra transaktionerna, och granska sedan Intrastatjournalen.

    ![Rad som representerar inköpsordern på Intrastat-sidan](media/intrastat_pl_4.png)

5. Granska informationen på fliken **Allmänt** för inköpsordern.

    ![Inköpsorderdetaljer på fliken Allmänt på Intrastat-sidan](media/intrastat_pl_5.png)

6. I åtgärdsfönstret väljer du **Utdata** > **Rapport**.
7. I dialogrutan **Intrastatrapport** > snabbfliken **Parametrar** > i avsnittet **Datum** > fältet **Från datum** väljer du aktuell månads första dag.
8. I avsnittet **Export** **alternativet** ange **Generera fil** till **Ja**. I fältet **Filnamn** anger du sedan erforderligt namn.
9. Ange alternativet **Generera rapport** som **Ja**. I fältet **Rapportfilens namn** anger du sedan erforderligt namn.
10. I fältet **Riktning** väljer du **Införsel**.
11. I avsnittet **Mappning av filformat** bekräftar du att fältet **Deklarationstyp** har angetts som **Deklaration**.
12. I fältet **Ort för dokumentframställande** anger du **Krakow**.
13. I fältet **Datum för dokumentframställande** väljer du **2021-10-19** (19 oktober 2021).
14. I fältet **Dokumentnr.** anger du **11**.
15. I fältet **Dokumentversion** anger du **22**.
16. Välj **OK** och granska rapporten i XML-format som genereras. Tabellen nedan visar värdena i exempelrapporten.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Fältnamn</strong></p>
    </td>
    <td>
    <p><strong>Fältbeskrivning</strong></p>
    </td>
    <td>
    <p><strong>Värde</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Information om dokumentet</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja-data</p>
    </td>
    <td>
    <p>Det datum då dokumentet skapades.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Den ort där dokumentet skapades.</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Totalt antal artiklar.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Totalt statistiskt värde.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Det totala fakturavärdet.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Enhetskoden.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Deklarationstypen.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Dokumentversionen.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Dokumentnumret.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>Referensmånaden.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>Referensåret.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>Rapportens riktning.</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>Deklarationsidentifieraren.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Information om företaget</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>Den ort där företaget finns.</p>
    </td>
    <td>
    <p>Warszawa</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>Företagets Regon-kod.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Företagets NIP-kod.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Företagets postnummer.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Den gata där företaget finns.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Företagets namn.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Information om varan</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Statistiskt värde.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Fakturavärdet.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Nettomassan.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>Koden för ursprungslandet eller -regionen.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>Kod för transportsätt.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Artikelkoden.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Transaktionskoden.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Leveranssättet.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Koden för landet eller regionen där utförsel/destination finns.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>En beskrivning av varorna.</p>
    </td>
    <td>
    <p>Maskinvara</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Artikelnummer.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Kontaktinformation</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-post</p>
    </td>
    <td>
    <p>Insändarens e-postadress.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Insändarens faxnummer.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Insändarens telefonnummer.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Insändarens namn.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Granska rapporten som genereras i Excel-format.

    ![Intrastatrapport för införslar](media/intrastat_pl_6.png)
