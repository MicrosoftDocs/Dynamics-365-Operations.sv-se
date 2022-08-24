---
title: Kassaapparatfunktioner för Norge
description: Denna artikel innehåller en översikt över kassaregisterfunktionerna som är tillgängliga för Norge i Microsoft Dynamics 365 Commerce samt riktlinjer för hur du konfigurerar funktionen.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 42eda805646dbb30b40528254a3137102e3075e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292747"
---
# <a name="cash-register-functionality-for-norway"></a>Kassaapparatfunktioner för Norge

[!include[banner](../includes/banner.md)]

Denna artikel innehåller en översikt över kassaapparatfunktioner för Norge i Dynamics 365 Commerce. Den innehåller även riktlinjer för att konfigurera funktionen. Funktionen innehåller följande delar:

- Vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner. Exempel inkluderar ett alternativ för att förhindra att en kopia av ett kvitto skrivs ut mer än en gång.
- Norgespecifika funktioner som digitala signaturer för försäljningstransaktioner.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Översikt över kassaapparatfunktioner för Norge

### <a name="common-pos-features"></a>Vanliga kassafunktioner

Mer information om kassafunktioner som är tillgängliga för kunder i alla länder eller regioner finns i [Hjälpresurser för Dynamics 365 Retail](../index.md).

Följande kassalokaliseringsfunktioner som tidigare implementerades och gjordes tillgängliga för kunder i alla länder eller regioner kan nu användas specifikt för Norge:

- **Skriva ut textfälten på kvittot i en stor teckenstorlek.** Du kan använda parametern **Teckenstorlekstorlek** i kvittoformatdesignern för att ange att stort teckenstorlek ska användas för ett fält i ett kvittoformat. (Stor teckenstorlek är ungefär dubbelt så stor som normal storlek.) Du kan exempelvis använda denna parameter för att skriva ut indikatorn ”kopia” på ett kvitto med stora bokstäver.
- **Registrera utskrift av kvittokopior i händelseloggen kassagranskning.** Du kan använda parametern **granska** i kassafunktionsprofilen för kopior av kvitton som ska skrivas ut och andra kassagranskningshändelser som ska registreras. Granskningshändelserna registreras i kanaldatabasen och i administrationen. Du kan visa granskningshändelser på sidan **granskningshändelser**.
- **Förhindra att en kopia av ett kvitto skrivs ut mer än en gång.** När parametern **granska** i kassafunktionsprofilen är aktiverad kan kassabehörigheten **Tillåt utskrift av kassakopior** kontrollera om kvittokopiorna kan skrivas ut. Det finns också ett alternativ för att förhindra att en kopia av ett kvitto skrivs ut mer än en gång.

Dessutom har följande kassafunktioner som implementerades för Norge gjorts tillgängliga för kunder i alla länder eller regioner:

- **Registrera ytterligare händelser i händelseloggen kassagranskning.** Om parametern **Granska** i kassafunktionalitetsprofilen är aktiverad, registreras följande händelser i kassarevisionshändelseloggen:

    - Priskontroller
    - Åsidosättning av moms
    - Korrigeringar av radkvantiteter
    - Rensa transaktioner från kanaldatabasen

### <a name="norway-specific-pos-features"></a>Norge-specifika kassafunktioner

Följande Norge-specifika kassafunktioner aktiveras när parametern **ISO-kod** i kassafunktionsprofilen ställs in till **No**:

#### <a name="digital-signing-of-sales-transactions"></a>Digital signering av försäljningstransaktioner

Alla försäljningstransaktioner är digitalt signerade. Signaturen skapas och registreras i kassatransaktionsjournalen samtidigt som transaktionen slutförs. Signaturen är även tillgänglig i journalen som exporteras för granskningsändamål.

Endast transaktioner för kontantförsäljning signeras. Nedan följer några exempel på transaktioner som inte kan signeras:

- Förskottsbetalningar (insättning på kundkonto)
- Förskottsbetalningar för försäljningsorder (insättning av kundorder)
- Utfärda ett presentkort
- Icke-försäljningstransaktioner (växelpost betalningsmedel och så vidare)

De data som signeras är en textsträng som består av följande datafält. Datafälten är åtskilda av semikolon.

1. Tidigare signatur för samma kassa (A noll \[**0**\] används för den första transaktionen.)
2. Transaktionsdatum
3. Transaktionstid
4. Sekventiellt, signerat transaktionsnummer
5. Transaktionsbelopp inklusive moms
6. Transaktionsbelopp exklusive moms

Den digitala signeringsprocessen använder en RSA 1024-bitarsnyckel som har en SHA-1 hash-funktion (RSA-SHA1-1024). Ett certifikat som installeras på Commerce Scale Unit används för signering. Intygets unika identifierare (certifikat) registreras tillsammans med signaturen.

Signaturen lagras i butiksdatabasen och huvudkontorsdatabasen tillsammans med transaktionsdata. Du kan se transaktionssignaturen, tillsammans med transaktionsdata som användes för att generera den, på snabbfliken **Räkenskapstransaktioner** på sidan **butikstransaktioner**.

#### <a name="receipts"></a>Inleveranser

Kvitton för Norge kan innehålla ytterligare information som har implementerats med hjälp av anpassade fält:

- **Kvittotitel** – Du kan lägga till ett fält i en layout för kvittoformat för att identifiera kvittotypen. Ett försäljningskvitto innehåller till exempel texten "Försäljningskvitto".
- **Underskriven transaktionslöpnummer** – Serienumret för en signerad transaktion kan visas på kvittot för att koppla ett utskrivet kvitto till en digital signatur i databasen.
- **Inleveranssummor** – Anpassade fält för inleveranssummor exkluderar icke-försäljningsbelopp från totala transaktionsbelopp. Belopp som inte är försäljningstransaktioner inkluderar belopp för följande åtgärder:

    - Förskottsbetalningar (insättning på kundkonto)
    - Förskottsbetalningar för försäljningsorder (insättning av kundorder)
    - Utfärda ett presentkort
    - Lägg till medel på ett presentkort

#### <a name="x-and-z-reports"></a>X- och Z-rapporter

Informationen som tas med i X- och Z-rapporterna baseras på Norges krav. **Totala kontantförsäljningsbelopp** inkluderar till exempel bara belopp för kontantförsäljningstransaktioner och exkluderar presentkortsåtgärder och förskottsbetalningar. Total kontantförsäljning visas också per artikelgrupp och betalningsmetod. Ackumulerad **total försäljning** och **returbelopp för totalsumma** underhålls och skrivs dessutom ut.

#### <a name="saf-t-cash-register-audit-file"></a>Verifieringsfil för SAF-T kassaapparat

Du kan exportera kassatransaktionsjournalen i det fördefinierade standardrevisionsfilen - moms (S DE-T) kassaregisterformatet. Verifieringsfilen innehåller information om organisationen, relevanta huvuddata (t.ex. artikelgrupper, artiklar och skattekoder), kassaförsäljningstransaktionsdata tillsammans med signaturer för dessa transaktioner, icke-försäljningshändelsedata och data om slutdatumsrapporter.

Verifieringsfilen kan exporteras i följande scenarier:

- Per butik
- Alla butiker
- Per terminal
- Alla terminaler

Du kan också skicka en rapport från en juridisk person på uppdrag av en annan juridisk person. I det här fallet måste du köra exporten från den juridiska personen som arbetar och ange den juridiska personen som ansvarar för rapporteringen som avsändare av rapporten.

Formatet för SAF-T kassaapparat implementeras i administration av [elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Konfigurera Commerce för Norge

Det här avsnittet beskriver inställningar som avser och rekommenderas för Norge. Mer information hittar du i [Hjälpresurser för Dynamics 365 Retail](../index.md).

Om du vill använda Norge-specifika funktioner måste du utföra följande uppgifter:

- Ange fältet **land/region** till **NOR** (Norge) i den primära adressen för den juridiska personen.
- Ange fältet **ISO-kod** till **NO** (Norge) i funktionsprofil för kassa för alla butiker som finns i Norge.

Du måste ange följande allmänna inställningar för Norge.

### <a name="set-up-the-legal-entity"></a>Ange den juridiska personen

Se till att namnet på den juridiska personen har angetts. Namnet skrivs ut på X- och Z-rapporter.

Dessutom, på snabbfliken **Bankkontoinformation** i fältet **Clearingnummer** anger du organisationsnummer.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Ställ in moms (VAT) per norska krav


Du måste skapa momskoder, momsgrupper och artikelmomsgrupper. Du måste även konfigurera momsinformation för produkter och tjänster. Mer information om hur du konfigurerar och använder moms finns i [Momsöversikt](../../finance/general-ledger/indirect-taxes-overview.md).

Du måste även ange momsgrupper och aktivera alternativet **Priser inkluderar moms** för butiker som finns i Norge.

### <a name="set-up-functionality-profiles"></a>Ställa in funktionsprofiler

Du måste aktivera granskning och konfigurera kvittonumrering.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Uppdatera kassabehörighetsgrupper och enskilda behörighetsinställningar för arbetare i butiken

Ange behörigheten **Tillåt utskrift av kvittokopia** till lämpligt värde:

- **Tillåt alltid** – operatören kan skriva ut en kopia av ett kvitto flera gånger.
- **Tillåt endast en gång** – operatören kan skriva ut en kopia av ett kvitto en gång.
- **Tillåt endast en gång och endast om HQ DB är tillgängligt** – Operatören kan skriva ut en kopia av ett kvitto endast en gång, och endast om HQ-databasen är tillgänglig genom Commerce Data Exchange: Realtidstjänst så att systemet kan kontrollera att inga kopior av kvittona har skrivits ut tidigare i någon butik.
- **Aldrig** – operatören kan inte skriva ut en kopia av ett kvitto.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton

På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout. Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel. Du kan ändra dem för att uppfylla dina krav.

| Språk-ID | Text                   | Text-ID |
|-------------|------------------------|---------|
| en-US       | Kvittorubrik          | 900011  |
| en-US       | År presentkort           | 900012  |
| en-US       | Totalt (försäljning)          | 900013  |
| en-US       | Total moms (försäljning)      | 900014  |
| en-US       | Totalt med moms (försäljning) | 900015  |
| en-US       | Momsbelopp (försäljning)     | 900016  |
| en-US       | ID för kontanttransaktion    | 900017  |

På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter. Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**.

| Namn                            | Typ    | Text-ID för rubrik |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Inleverans | 900011          |
| IsGiftCard                      | Inleverans | 900012          |
| SalesTotalExt                   | Inleverans | 900013          |
| TaxTotalExt                     | Inleverans | 900014          |
| TotalWithTaxExt                 | Inleverans | 900015          |
| AmountPerTaxExt                 | Inleverans | 900016          |
| CashTransactionSequentialNumber | Inleverans | 900017          |

> [!NOTE]
> Det är viktigt att du anger rätt anpassade fältnamn, så som listas i registret ovan. Om fel anpassat fältnamn saknas data i kvittona.

### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För alla obligatoriska kvittoformat ändrar du värdet på **Utskriftssätt** till **Skriv alltid ut** för kvittoformat.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i lämpliga kvittoavdelningar. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt.

1. Siduvud:

    - **Kvittotitel** – I det här fältet identifieras typen av inleverans.
    - **Kontanttransaktions-ID** – I det här fältet skrivs serienummer för den signerade kontanttransaktionen ut.

2. Rader:

    - **Är presentkort** – Det här fältet markerar kvittoraden som relaterad till åtgärden Utfärda presentkort eller Lägg till på presentkort.

3. Sidfot:

    - **Total (försäljning)** - Detta fält skriver ut kvittots totala kontanta försäljningsbelopp. Beloppet är exklusive skatt. Förskottsbetalningar och presentkortsåtgärder exkluderas.
    - **Momssumma (försäljning)** - Detta fält skriver ut kvittots totala momsbelopp för kontantförsäljning. Förskottsbetalningar och presentkortsåtgärder exkluderas.
    - **Summa med moms (försäljning)** - Detta fält skriver ut kvittots totala kontanta försäljningsbelopp. Beloppet är inklusive skatt. Förskottsbetalningar och presentkortsåtgärder exkluderas.
    - **Momsbelopp (försäljning)** - Detta fält skriver ut kvittots totala momsbelopp per momskod. Förskottsbetalningar och presentkortsåtgärder exkluderas.

Mer information om hur du arbetar med kvittoformat finns i [Ställ in och designa inleveransformat](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Konfigurera exportformatet SAF-T-kassaregister

Konfigurationen för SAF-T-kassaregister kan hämtas från Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Importera konfigurationer för elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Du måste hämta följande konfigurationer:

- **Butikskanal data.version.1** – datamodellkonfigurationen.
- **Butikskanal DMM data.version.1.14** – datamodellkonfigurationen.
- **NO SAF T kassa Register.version.1.20** – Formatkonfigurationen.

När du har importerat konfigurationerna på sidan **Commerce-parametrar** på fliken **Elektroniska dokument** i fältet **SAF-T kassaapparat exportformat**, välj namnet på formatkonfigurationen som importerades.

Du måste också mappa obligatoriska huvuddata till fördefinierade S DE-T-standardkoder. Mer information finns i dokumentationen för SAF-T-kassaregistret som tillhandahålls av den norska momsadministrationen. Om du vill skapa mappningen måste du konfigurera det nya fältet **SAF-T kassaregisterkod** på följande sidor:

- Artikelgrupper
- Betalningsmetoder
- Momskoder

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

Om du vill aktivera de norgespecifika funktionerna måste du konfigurera kanalkomponenter. Mer information finns i [Distributionsalternativ](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
