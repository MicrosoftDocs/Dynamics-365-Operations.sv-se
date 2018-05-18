---
title: Konfigurera utgiftshantering
description: "Det här avsnittet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c87909d9eb3a4d717e0c40289353da0267a51f60
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="configure-expense-management"></a>Konfigurera utgiftshantering

[!include [banner](../includes/banner.md)]

Det här ämnet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations. I utgiftshanteraren kan du lagra information om betalsätt, reserekvisitioner, utgiftsrapporter, policyer och så vidare.

Eftersom flera av besluten som du gör när du planerar konfigurationen för Utgiftshantering baseras på organisationens hierarki och ekonomiska struktur, måste du hänvisa till planläggningsdokumenten för dessa områden.

## <a name="intercompany-expenses"></a>Koncerninterna utgifter

När du aktiverar företagsinterna utgifter tillåter du juridiska entiteter och medarbetare att ådra sig utgifter å en annan juridisk persons vägnar, samt att inhämta betalning från den juridiska anställningspersonen inom din organisation. En medarbetare inom Juridisk Person A slutför exempelvis ett projekt för Juridisk Person B, och projektet medför reserelaterade utgifter. Om företagsinterna utgifter har aktiverats kan medarbetaren därefter lämna in en utgiftsrapport som bokför utgiften hos Juridisk Person B, och utgiften måste sedan betalas av Juridisk Person A. Om din organisation inte har flera olika juridiska personer, behöver du inte aktivera företagsinterna utgifter.

**Beslut:** Vill du aktivera koncerninterna utgifter?

## <a name="financial-management"></a>Ekonomisk styrning

Utgiftshantering är väl integrerad med ekonomisk hanteringen i din organisation. Stora delar av dina inställningar för utgiftshantering baseras på de beslut som du har fattat angående din organisations finanser. Följande avsnitt beskriver de områden som kräver planering och beslut, vilket baseras på din organisations finansiella beslut samt vägledningen från ditt ledningsteam.

### <a name="per-diems"></a>Dagtraktamenten

Du måste definiera medarbetarens dagtraktamente som din organisation ger. Eftersom dagtraktamente vanligtvis används för utgifter som till exempel logi, måltider och andra tillfälliga utgifter, kan du skapa regler för dagtraktamenteavdragen som din organisation ger. traktamentsnivåerna kan baseras på årstid, resmål eller båda. När du skapar en traktamentsregel kan du ange att hålla inne en procentandel av traktamentstariffen om medarbetaren bjuds på måltider eller tjänster. Du kan också definiera traktamentsreglernas skikt för att ange lägsta och högsta antal timmar som dagtraktamentetariffen kan tillämpas på en arbetares resor.

**Beslut:**

- Standardregler för traktamente för de första och sista dagarna:

    - Vad är minsta antal timmar som en medarbetare kan fordra för en dag och får fortfarande en dagtraktamente?
    - Minskar det belopp som erbjuds för måltider under första och sista dagen? Vid minskning, till vilken procentsats sker minskningen?
    - Minskar det belopp som erbjuds för hotell under första och sista dagen? Vid minskning, till vilken procentsats sker minskningen?
    - Minskar det belopp som erbjuds för andra utgifter som uppstår under första och sista dagen? Vid minskning, till vilken procentsats sker minskningen?

- Standardregler för traktamente:

    - Finns det en procentuell reducering i dagtraktamentet för varje måltid om till exempel måltiden är kostnadsfri? Vid minskning, till vilken procentsats sker minskningen för respektive måltid?
    - Beräknas måltidsreduceringen per dag, per resa eller med antal måltider per dag?
    - Bör traktamentsbelopp avrundas på sedvanligt sätt, eller avrundas uppåt?
    - Beräknas dagtraktamente på en 24-timmarsperiod eller på en kalenderdag?

- Traktamentsregler baserade på plats:

    - Varierar traktamentsregler beroende på plats? Vilka platser är inkluderade i?
    - Om traktamentsnivåerna varierar efter plats och för varje enskild plats, vilket procentandelsbelopp erbjuds för följande utgiftstyper:

        - Måltider
        - Hotell
        - Andra kostnader

### <a name="expense-management-journals-and-accounts"></a>Utgiftshanteringsjournaler och konton

Utgiftshantering kräver att du använder flera journaler och konton. Du måste bestämma om till exempel samma konto används för förskott och kreditkortstvister.

**Beslut:**

- I vilken redovisningsjournal bokförs godkända utgiftsrapporter.
- Vilket konto används för förskott?
- Ska förskott bokföras direkt?

### <a name="payment-methods"></a>Betalningsmetoder

När du beviljar medarbetare utlägg på uppdrag av ditt företag, måste du definiera de betalningsmetoder som medarbetare har behörighet att använda. Du kan till exempel tillåta att använda kontanter eller ett företagskort. Du kan även tillåta medarbetare att använda personliga kreditkort och sedan ersätta dem. Du måste göra följande beslut för varje betalningsmetod som du tillåter.

**Beslut:**

- Vilka betalningsmetoder är tillåtna?
- Vem äger betalningsmetoden för utgifterna?
- Finns det en motkontotyp? Vid konto av förskjutningstyp, vilken typ?
- Om det finns ett motkonto, vilket är kontot?
- Om betalningsmetoden är kreditkort, ska betalningsmetoden användas endast med importerade transaktioner?

### <a name="expense-categories-and-shared-categories"></a>Utgiftskategorier och delade kategorier

När medarbetare skapar en utgiftsrapport måste varje utgift som de registrerar associeras med en utgiftskategori. Utgiftskategorier baseras på delade kategorier som kan delas över samtliga juridiska entiteter i din organisation. Dessa kategorier kan också delas inom projekthantering och redovisning, beroende på hur din organisation är utformad. Baserat på hur din organisation är utformat samt på vägledning från implementeringsteamet måste du avgöra huruvida kategorierna som används i utgiftshanteringen endast ska användas där, eller om de ska delas mellan projekthantering och redovisnings- och utgiftshantering. Observera att dessa kategorier kan delas mellan projekt och utgifter eller projekt och produktion, men inte mellan utgifter och produktion. Du måste göra följande beslut för varje utgiftskategori.

**Beslut:**

- Vilken är utgiftskategorin? Exemplen omfattar kategorier för flyg, hotell eller reseersättning.
- Kan utgiftskategorin även användas inom projekthantering och redovisning?
- Vilken är utgiftstypen?
- Vilken är standardbetalningsmetoden för utgiftskategorin?
- Måste utgifter i utgiftskategorin specificeras?
- Vilket är huvudstandardkontot för utgiftskategorin?
- Vilken är standardartikelmomsgruppen för utgiftskategorin?
- Är ytterligare betalningsmetoder tillåtna för utgiftskategorin? Om ytterligare betalsätt tillåts, vilka betalsätt?
- Finns det underkategorier i denna utgiftskategori? Om det finns underkategorier måste du också fatta följande beslut:

    - Exkluderas någon av underkategorierna från momsåterbetalning?
    - Vilken är underkategoriernas artikelmomsgrupp?

Om utgiftskategorin även används inom projekthantering och redovisning, besvara då följande frågor: Annars går du vidare till nästa avsnitt.

- Vilka kostnadskonton kommer att användas för följande utgifter?

    - Kostnad
    - Löneallokering
    - PIA - Kostnadsvärde
    - Kostnad - Artikel
    - PIA - Kostnadsvärde - Artikel
    - Upplupen förlust
    - PIA - upplupen förlust

- Vilka intäktskonton används för följande?

    - Fakturerade intäkter
    - Upplupna intäkter - Försäljningsvärde
    - PIA - Försäljningsvärde
    - Upplupna intäkter - Produktion)
    - PIA - Produktion
    - Upplupna intäkter - Vinst
    - PIA - Vinst
    - Upplupen intäkt - Abonnemang
    - PIA - abonnemang

### <a name="taxes"></a>Skatter

För utgiftsrelaterade skatter måste du bestämma vad som inkluderas eller aktiveras i utgiftsrapporter.

**Beslut:**

- Inkluderas moms i utgiftsbeloppen?
- Ska momsåterbetalning aktiveras på utgifter?

    > [!NOTE]
    > Du kan inte aktivera skatteåtervinning på utgifter om du valde att tillämpa amerikansk moms och att använda skatteregler när du planerade din redovisning. (För att använda amerikansk moms och skatteregler, ange alternativet **Applicera momsskatteregler** som **Ja**.)

## <a name="policies"></a>Policyer

Genom att skapa policyer för utgiftsrapporter kan du hjälpa din organisation att spara tid och pengar när medarbetarna ådrar sig utgifter å dess vägnar. Policyer hjälper till att säkerställa att medarbetarna håller sig inom budget, tillhandahåller all erforderlig information och endast spenderar pengar på nödvändigheter. Du måste ta följande beslut för varje utgiftsrapportpolicy och policy för utgiftsrapportgodkännande som du skapar.

**Beslut:**

- Vilket är namnet på policyn?
- Vad gäller utgiftspolicyn för?
- Om du tidigare har beslutat att aktivera företagsinterna utgifter, vilka företag inom din organisation omfattas då av denna policy?
- När börjar principen gälla?
- När upphör policyn?
- Vilken är policyregeln?
- Vilket är resultatet av policyregeln?

