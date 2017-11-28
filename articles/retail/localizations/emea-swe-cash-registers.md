---
title: "Kassaapparater för Sverige"
description: "Det här avsnittet innehåller en översikt över kassaapparatfunktioner för Sverige."
author: EvgenyPopovMBS
manager: annbe
ms.date: 06/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailPosPermissionGroup, RetailFunctionalityProfile, RetailFormLayout, RetailHardwareProfile, RetailFiscalPrinterConfigTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Retail, Operations, Core
ms.search.region: Sweden
ms.search.industry: retail
ms.author: epopov
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c68d84ea0297d954eaf62d36b98b2e305e6be50e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---
# <a name="cash-registers-for-sweden"></a>Kassaapparater för Sverige

Det här avsnittet innehåller en översikt över kassaapparatfunktioner för Sverige i Microsoft Dynamics 365 for Retail. Den innehåller även riktlinjer för att ställa in funktionen. Funktionen innehåller följande delar:

- Vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner som ett alternativ för att förhindra försäljning och returer från att slås samman i ett butikskvitto
- Sverige-specifika funktioner, t.ex. ytterligare räknare i dagliga kassarapporter
- Ett exempel för att integrera 365 Dynamics for Retail POS med Sverige-specifika kvittoskrivarenhet som kallas kontrollenheter.

## <a name="overview-of-cash-register-functionality-for-sweden"></a>Översikt över kassaapparatfunktioner för Sverige 

### <a name="common-pos-features"></a>Vanliga kassafunktioner

Mer information om vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner finns i [Microsoft Dynamics 365 Retail, dokumentation](../index.md).

Dessutom har följande kassafunktioner som implementerades för Sverige gjorts tillgängliga för kunder i alla länder eller regioner:

- **Förbjuda försäljning och returer från att slås samman i ett butikskvitto.** När du anger parametern **förbjuda blandning av försäljning och returer i ett kvitto** i kassafunktionsprofilen till **Ja**, kommer Cloud POS och Modern POS inte låta användarna skapa en transaktion som innehåller både positiva och negativa rader.
- **Skriva ut textfälten på kvittot i en stor teckenstorlek.** Du kan använda parametern **Teckenstorlekstorlek** i kvittoformatdesignern för att ange att stort teckenstorlek ska användas för ett fält i ett kvittoformat. (Stor teckenstorlek är ungefär dubbelt så stor som normal storlek.) Du kan exempelvis använda denna parameter för att skriva ut indikatorn ”kopia” på ett kvitto med stora bokstäver.
- **Registrera utskrift av kvittokopior i händelseloggen kassagranskning.** Du kan använda parametern **granska** i kassafunktionsprofilen för utskrift av kvittokopior och andra kassagranskningshändelser som ska registreras. Granskningshändelserna registreras i kanaldatabasen och i butiksadministrationen. Du kan visa granskningshändelser på sidan **granskningshändelser**.
- **Förhindra att en kopia av ett kvitto skrivs ut mer än en gång.** När parametern **granska** i kassafunktionsprofilen är aktiverad kan kassabehörigheten **Tillåt utskrift av kassakopior** kontrollera om kvittokopiorna kan skrivas ut. Det finns också ett alternativ för att förhindra att en kopia av ett kvitto skrivs ut mer än en gång. 

### <a name="sweden-specific-pos-features"></a>Sverige-specifika kassafunktioner

Följande Sverige-specifika kassafunktioner aktiveras när parametern **ISO-kod** i kassafunktionsprofilen ställs in till **SE**:

- Extra räknare i daglga kassarapporter som X- och Z-rapporter:

    - Antal kvittokopior och totalt belopp
    - Momsbelopp per momssats
    - Totala kvantiteter för artiklar och tjänster som säljs
    - Total försäljning exklusive och inklusive moms
    - Totalförsäljning, returer och netto

- En kanalrapport för **elektronisk journal (Sverige)** som listar användningshändelser i kassan, till exempel försäljning, returer, kvittokopior, kassalådöppningar och prisåsidosättningar.

    > [!NOTE]
    > För närvarande kan rapporten **elektronisk journal (Sverige)** inte exporteras eller skrivas ut. Men funktionen för export och utskrift av rapportenkommer att läggas till senare.

### <a name="integration-of-retail-pos-with-control-units"></a>Integrering med kontrollenheter i Retail POS

Retail inkluderar ett exempel för att integrera kassa med Sverige-specifika kvittoskrivarenhet som kallas kontrollenheter. Det antas att en enhet är fysiskt ansluten till maskinvarustationerna som kassan är kopplad till. Provet implementeras i källkoden för kassan, maskinvarustationen och Commerce Runtime-tillägg och är tillgänglig i Retail software development kit (SDK). Provet innehåller följande funktioner:

- Försäljning, returer och kvittokopior registreras automatiskt i en kontrollenhet som är ansluten till maskinvarustationen som är kopplad till kassan.
- Kontrollkoden och tillverkningsnumret för kontrollenheten för en registrerad transaktion fångas in från kontrollenheten och sparas i transaktionen. (Denna data kallas också _räkenskapsdata_.) Räkenskapsdata kan visas sdian **Butikstransaktioner** i Retail.
- Anpassade fält för kontrollkoden och tillverkningsnumret för kontrollenheten kan läggas till ett kvittoformat så att du kan skriva ut räkenskapsdata för transaktionen på ett kvitto.
- Räkenskapsdata för en transaktion skrivs ut på kanalrapporten **elektronisk journal (Sverige)**.
- Om ett fel inträffar vid registrering av en transaktion i styrenheten förblir räkenskapsdata för transaktionen tomt. I det här fallet går det inte att starta en ny transaktion och det går inte att stänga det aktuella skiftet. Operatören ombeds att försöka registrera den oregistrerade transaktionen igen i styrenheten. Om det andra försöket misslyckas hoppar operatören över registreringen, under förutsättning att han eller hon har en särskild behörighet. Om operatören hoppar över registreringen av en transaktion i styrenheten, sparas informationen om händelsen i transaktionen i stället för räkenskapsdata.

> [!NOTE]
> För närvarande stöder inte styrenhetens integrationsprov kundorder. Men ett prov som stöder kundorder kommer att bli tillgängligt senare.

Mer information om styrenhetens integrationsprov finns i [Guiden för provanvändning](../dev-itpro/retail-sdk/retail-sdk-control-unit-sample.md).

## <a name="setting-up-retail-for-sweden"></a>Konfigurera Retail för Sverige

Det här avsnittet beskriver inställningar för Retails som avser och rekommenderas för Sverige. Mer information om hur du ställer in Retail finns i [Microsoft Dynamics 365 for Retail - dokumentation](../index.md).

Om du vill använda Sverige-specifika funktioner för Retail måste du utföra följande uppgifter:

- Ange fältet **land/region** till **SWE** (Sverige) i den primära adressen för den juridiska personen.
- Ange fältet **ISO-kod** till **SE** (Sverige) i funktionsprofil för kassa för alla butiker som finns i Sverige.

Sverige-specifika inställningar kan delas in i två grupper:

- Allmänna inställningar
- Styrenhet - specifika inställningar

### <a name="general-settings"></a>Allmänna inställningar

Du måste ange följande allmänna inställningar för Sverige.

1. Ange följande parametrar för moms (VAT) enligt svenska krav:

    - Momskoder
    - Momsgrupper
    - Artikelmomsgrupper
    - Momsinställningar i artiklar (artikelmomsgrupper för försäljning)

    Mer information om hur du ställer in och använder moms i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, och i Retail finns i [Momsöversikt](../../financials/general-ledger/indirect-taxes-overview.md).

2. På sidan **Alla butiker** uppdaterar du butiksinformation. Du måste speciellt ställa in följande parametrar:
    
    - I fältet **momsgrupp** anger du en momsgrupp som ska användas för försäljning till butikskund.
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
    
        - Lägger till minst i följande fält på **rader**-delen av kvittolayouten: **artikelnamn**, **kvantitet**, och **totalpris inkl. moms**.

        - Lägg till minst följande fält till **Sidfot**-delen på kvittolayouten:

            - Momsfält så att momsbeloppen för varje momssats skrivs ut. Lägg till exempel till fälten **skatte-Id**, **momsprocent**, och **Momsbelopp** till en rad i layouten.
            - Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut. Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.

6. På sidan **Konfiguration av kanalrapporter** anger du rapporten **elektronisk journal (Sverige)**. I fältet **behörighetsgrupper** väljer du kassabehörighetsgrupper som får köra rapporten.

### <a name="control-unitspecific-settings"></a>Styrenhet - specifika inställningar

Du måste du ange följande inställningar för att aktivera [integrationsprovet](../dev-itpro/retail-sdk/retail-sdk-control-unit-sample.md) så att Retail POS är integrerat med kontrollenheter för Sverige.

1. Skapa räkenskapsregisterkonfigurationer och tilldela dem till maskinvaruprofiler:

    1. På sidan **Räkenskapsregisterkonfigurationer** skapar du en ny konfigurationspost för räkenskapsregister. Ange namnet och beskrivningen på konfigurationen.
    2. Fyll i konfigurationens innehåll. För detta prov är en konfiguration en XML-fil som skapar mappningen mellan momskoder och en styrenhets momsgrupper. Du kan koppla upp till fyra momskoder. I följande exempel på en konfiguration, **VAT10** och **VAT20** representerar momskoder som måste mappas.

        ``` xml
        <UnitConfiguration>
            <TaxMapping>
                <Tax taxCode="VAT10" controlUnitTaxId="1"/>
                <Tax taxCode="VAT20" controlUnitTaxId="2"/>
            </TaxMapping>
        </UnitConfiguration>
        ```
        
        Du kan också exportera en provkonfiguration genom att klicka på **Exportera provkonfiguration** i åtgärdsfönstret.

    3. På sidan **maskinvaruprofiler** markerar du maskinvaruprofilen på den maskinvarustation som kassan är sammankopplad med och kontrollenheten som den är ansluten till. På snabbfliken **räkenskapsregister** anger du följande fält:

        - I fältet **räkenskapsregister** väljer du **tredje parts drivrutin**.
        - I fältet **konfiguration**, markerar du namnet på räkenskapsregisterkonfigurationen som du har skapat.

2. Konfigurera anpassade fält för kvittolayouter så att kontrollkoden och tillverkningsnumret för kontrollenheten skrivs ut på kvittona:

    1. På sidan **Språktext** kan du lägga till två poster efter texten i fältet för anpassad kvittolayout. Ange språk-ID för rubrikerna i de motsvarande fälten (t.ex. **sv-se**), text-ID (exempelvis **900001** och **900002**), och texten (exempelvis **kontrollkod** och **kontroll-ID för enheten**).
    2. På sidan **Anpassade fält** kan du lägga till två poster för fältet för anpassad kvittolayout. I fältet **Typ**, välj **Kvitto**. Ange namn och beskrivningar för fälten för anpassad kvittolayout:

        - Kontrollkod:

            - **Namn:****FiscalRegisterControlCode**
            - **Beskrivning av text-ID:** text-ID som du angav för kodfältet kontrollen (**900001** i föregående exempel)
            
        - Tillverkningsnummer för kontrollenheten:

            - **Namn:****FiscalRegisterId**
            - **Beskrivning av text-ID:** text-ID som du angav för fältet kontrollenhets-ID (**900002** i föregående exempel)
            
    3. För försäljningskvittoformat, kvittorformatdesignern i avsnittet **sidfot** på kvittolayouten, lägger du till fälten för de angivna rubrikerna (**kontrollkod** och **kontrollenhets-ID** i föregående exempel).

3. Uppdatera kassabehörighetsgrupper och enskilda behörighetsinställningar för arbetare i butiken. Om du vill tillåta att arbetare som tilldelats behörighetsgruppen hoppar över räkenskapsregister markerar du kryssrutan **Tillåt hoppa över räkenskapsregister**.

