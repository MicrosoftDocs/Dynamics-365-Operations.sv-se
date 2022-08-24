---
ms.openlocfilehash: 31ff361280cda94d475507bab148267ee5638318
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281524"
---
# <a name="cash-register-functionality-for-sweden"></a>Kassaapparatfunktioner för Sverige
---

titel: Kassaapparatfunktioner för Sverige [!include [banner](../includes/banner.md)]
beskrivning: Den här artikeln innehåller en översikt över kassaapparatfunktioner för Sverige.

författare: EvgenyPopovMBS Den här artikeln innehåller en översikt över kassaapparatfunktioner för Sverige i Dynamics 365 Commerce. Den innehåller även riktlinjer för att konfigurera funktionen. Funktionen innehåller följande delar: ms.date: 12/02/2019

ms.topic: artikel
- Vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner som ett alternativ för att förhindra försäljning och returer från att slås samman i ett butikskvitto ms.prod: 
- Sverige-specifika funktioner, t.ex. ytterligare räknare i dagliga kassarapporter ms.technology: 
- Ett exempel för att integrera kassa med Sverige-specifika kvittoskrivarenheter som kallas kontrollenheter.
publik: programanvändare

ms.reviewer: josaw
## <a name="overview-of-cash-register-functionality-for-sweden"></a>Översikt över kassaapparatfunktioner för Sverige
ms.search.region: Sverige

ms.author: josaw
### <a name="common-pos-features"></a>Vanliga kassafunktioner
ms.search.validFrom: 2017-06-30

ms.dyn365.ops.version: juli 2017 uppdatering För mer information om vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner finns i [Commerce-startsida](../index.md).
ms.search.industry: detaljhandel

ms.search.form: RetailPosPermissionGroup, RetailFunctionalityProfile, RetailFormLayout, RetailHardwareProfile, RetailFiscalPrinterConfigTable Dessutom har följande kassafunktioner som implementerats för Sverige gjorts tillgängliga för kunder i alla länder eller regioner:

---
- **Förbjuda försäljning och returer från att slås samman i ett kvitto.** När du anger parametern **förbjuda blandning av försäljning och returer i ett kvitto** i kassafunktionsprofilen till **Ja**, kommer Cloud POS och Modern POS inte låta användarna skapa en transaktion som innehåller både positiva och negativa rader.

- **Skriva ut textfälten på kvittot i en stor teckenstorlek.** Du kan använda parametern **Teckenstorlekstorlek** i kvittoformatdesignern för att ange att stort teckenstorlek ska användas för ett fält i ett kvittoformat. (Stor teckenstorlek är ungefär dubbelt så stor som normal storlek.) Du kan exempelvis använda denna parameter för att skriva ut indikatorn ”kopia” på ett kvitto med stora bokstäver.
    
- **Registrera utskrift av kvittokopior i händelseloggen kassagranskning.** Du kan använda parametern **granska** i kassafunktionsprofilen för utskrift av kvittokopior och andra kassagranskningshändelser som ska registreras. Granskningshändelserna registreras i kanaldatabasen och i administrationen. Du kan visa granskningshändelser på sidan **granskningshändelser**.

- **Förhindra att en kopia av ett kvitto skrivs ut mer än en gång.** När parametern **granska** i kassafunktionsprofilen är aktiverad kan kassabehörigheten **Tillåt utskrift av kassakopior** kontrollera om kvittokopiorna kan skrivas ut. Det finns också ett alternativ för att förhindra att en kopia av ett kvitto skrivs ut mer än en gång.



### <a name="sweden-specific-pos-features"></a>Sverige-specifika kassafunktioner
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

Följande Sverige-specifika kassafunktioner aktiveras när parametern **ISO-kod** i kassafunktionsprofilen ställs in till **SE**:

- Extra räknare i daglga kassarapporter som X- och Z-rapporter:

    - Antal kvittokopior och totalt belopp
    - Momsbelopp per momssats
    - Totala kvantiteter för artiklar och tjänster som säljs
    - Total försäljning exklusive och inklusive skatt
    - Totalförsäljning, returer och netto

- En kanalrapport för **elektronisk journal (Sverige)** som listar användningshändelser i POS, till exempel försäljning, returer, kvittokopior, kassalådöppningar och prisåsidosättningar.

    > [!NOTE]
    > För närvarande kan rapporten **elektronisk journal (Sverige)** inte exporteras eller skrivas ut. Men funktionen för export och utskrift av rapportenkommer att läggas till senare.

### <a name="integration-of-retail-pos-with-control-units"></a>Integrering med kontrollenheter i Retail POS


   # <a name="retail-1006-and-earlier"></a>[Retail 10.0.6 och tidigare](#tab/retail-10-0-6)

  Mer information om integrationen med styrenheter som är tillgängliga i återförsäljarversioner till och med Retail 10.0.6 finns i [exempel för POS-integrering med styrenheter för Sverige (äldre).](./retail-sdk-control-unit-sample.md#overview-of-integration-with-control-units). 


   # <a name="retail-1007-and-later"></a>[Retail 10.0.7 och senare](#tab/retail-10-0-7)

  Mer information om styrenhetens integrationsprov finns i [Exempel på integration av kontrollenhet för Sverige](./emea-swe-fi-sample.md).

---


## <a name="setting-up-commerce-for-sweden"></a>Konfigurera Commerce för Sverige

Det här avsnittet beskriver inställningar som avser och rekommenderas för Sverige. Mer information finns i [Startsida för Commerce](../index.md).

Om du vill använda Sverige-specifika funktioner måste du utföra följande uppgifter:

- Ange fältet **land/region** till **SWE** (Sverige) i den primära adressen för den juridiska personen.
- Ange fältet **ISO-kod** till **SE** (Sverige) i funktionsprofil för kassa för alla butiker som finns i Sverige.

Sverige-specifika inställningar kan delas in i två grupper:

- Allmänna inställningar
- Styrenhet – specifika inställningar

### <a name="general-settings"></a>Allmänna inställningar

Du måste ange följande allmänna inställningar för Sverige.

1. Ange följande parametrar för skatt (VAT) enligt svenska krav:

    - Momskoder
    - Momsgrupper
    - Artikelmomsgrupper
    - Momsinställningar i artiklar (artikelmomsgrupper för försäljning)

    Mer information om hur du ställer in och använder moms finns i [Momsöversikt](../../finance/general-ledger/indirect-taxes-overview.md).


2. På sidan **Alla butiker** uppdaterar du butiksinformation. Du måste speciellt ställa in följande parametrar:

    - I fältet **Momsgrupp** anger du en momsgrupp som ska användas för försäljning till standardkund.
    - Markera kryssrutan **Moms ingår i priserna**.
    - Ange fältet **Butiksnamn** till att inkludera företagets namn. Den här ändringen hjälper till att garantera att företagsnamnet visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagsnamnet på layouten av försäljningskvittot i fritt format.
    - Ange fältet **Skatteidentifieringsnummer (TIN)** så att det inkluderar företagets identifieringnummer. Den här ändringen hjälper till att garantera att företagets identifieringnummer visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagets identifieringnummer på försäljningskvittot i fritt format.

3. Ställa in kassafunktionsprofiler:

    - På snabbfliken **funktioner** markerar du kryssrutorna **Granskning** och **Förhindra att försäljning och returer blandas på ett kvitto**.
    - På snabbfliken **Kvittonumrering** anger du kvittonumrering. Skapa eller uppdatera poster för kvittotransaktionstyperna **försäljning** och **returer**. Ange formaten så att endast innehåller numeriska tecken. Avmarkera kryssrutan **oberoende sekvens** i båda posterna.

4. Uppdatera kassabehörighetsgrupper och enskilda behörighetsinställningar för arbetare i butiken. Ange behörigheten **Tillåt utskrift av kvittokopia** till lämpligt värde:

    - **Tillåt alltid** – operatören kan skriva ut en kopia av ett kvitto flera gånger.
    - **Tillåt endast en gång** – operatören kan skriva ut en kopia av ett kvitto en gång.
    - **Tillåt endast en gång och endast om HQ DB är tillgängligt** – operatören kan skriva ut en kopia av ett kvitto bara en gång och endast om huvudkontorets databas är tillgänglig via Realtidstjänst så att systemet kan kontrollera att inga kopior av kvittona har skrivits ut tidigare i någon butik.
    - **Aldrig** – operatören kan inte skriva ut en kopia av ett kvitto.

5. Gör nödvändiga ändringar i kvittoformat för försäljningskvitton:

    - Ändra värdet i fältet **Utskriftssätt** till **Skriv alltid ut** för kvittoformatet.
    - Gör följande ändringar i Layoutdesigner för kvitto:

        - Lägg till minst följande fält till **Rubrik**-delen på kvittolayouten:

            - Fälten **Butiksnamn** och **momsidentifieringsnummer** så att företagsnamnet och identitetnumret är utskrivna kvitton. Alternativt kan du kan lägga till företagsnamn och identitetsnummer på layouten i fritt format.
            - Fälten **Butiksadress**, **datum**, **Tid, 24 h**, **kvittonummer**, och **registreringsnummer**.
            - Fältet **Skriv ut meddelande på nytt** så att indikatorn ”kopia” skrivs ut på kvittokopior. Ange fältet **Teckenstorlek** för fältet **Skriv ut meddelande på nytt** till **Stor**.

        - Lägger till minst i följande fält på **rader**-delen av kvittolayouten: **artikelnamn**, **kvantitet**, och **totalpris inkl. skatt**.
        - Lägg till minst följande fält till **Sidfot**-delen på kvittolayouten:

            - Momsfält så att momsbeloppen för varje momssats skrivs ut. Lägg till exempel till fälten **skatte-Id**, **momsprocent**, och **Momsbelopp** till en rad i layouten.
            - Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut. Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.

6. På sidan **Konfiguration av kanalrapporter** anger du rapporten **elektronisk journal (Sverige)**. I fältet **behörighetsgrupper** väljer du kassabehörighetsgrupper som får köra rapporten.

### <a name="control-unitspecific-settings"></a>Styrenhet – specifika inställningar

   # <a name="retail-1006-and-earlier"></a>[Retail 10.0.6 och tidigare](#tab/retail-10-0-6)

  Mer information om inställning och konfiguration av integrationen med styrenheter som är tillgängliga i återförsäljarversioner till och med Retail 10.0.6 finns i [exempel för POS-integrering med styrenheter för Sverige (äldre)](./retail-sdk-control-unit-sample.md#setting-up-integration-with-control-units). 

   # <a name="retail-1007-and-later"></a>[Retail 10.0.7 och senare](#tab/retail-10-0-7)

  Mer information om inställning och konfiguration av styrenhetens integrationsprov finns i [Exempel på integration av kontrollenhet för Sverige](./emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

---
