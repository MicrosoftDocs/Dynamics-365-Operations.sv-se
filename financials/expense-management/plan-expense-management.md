---
title: Konfigurera utgiftshantering
description: "Det här avsnittet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. I området Utgiftshantering kan du bland annat spara information om betalningsmetoder, reserekvisitioner, utgiftsrapporter och policyer."
author: KimANelson
manager: AnnBe
ms.date: 06/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: edd3d8ca760c1453ae7cf8d5ff2fdfdedbb022c4
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# <a name="configure-expense-management"></a>Konfigurera utgiftshantering

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. I området Utgiftshantering kan du bland annat spara information om betalningsmetoder, reserekvisitioner, utgiftsrapporter och policyer. 

Eftersom flera av besluten som du gör när du planerar konfigurationen för Utgiftshantering baseras på organisationens hierarki och ekonomiska struktur, måste du hänvisa till planläggningsdokumenten för dessa områden.

## <a name="intercompany-expenses"></a>Koncerninterna utgifter
När du aktiverar koncerninterna utgifter, kan du tillåta att juridiska personer och medarbetare ådrar utgifter på uppdrag av och inkasserar betalning från en annan juridisk person inom din organisation. En medarbetare i juridisk person A slutför till exempel ett projekt för juridisk person B. Om koncerninterna utgifter aktiveras kan medarbetaren spara en tidrapport till och får betalt av juridisk person, B. Om din organisation inte har flera juridiska personer behöver du inte aktivera koncerninterna utgifter. **Beslut:** Vill du aktivera koncerninterna utgifter?

## <a name="financial-management"></a>Ekonomisk styrning
Utgiftshantering är väl integrerad med ekonomisk hanteringen i din organisation. Många konfigurationer för utgiftshantering baseras på besluten du har tagit om organisationens ekonomi. Följande avsnitt beskrivs olika områden som kräver planering och beslut baserade på företagets ekonomiska beslut och till och anvisningar från ditt ledningsteam.

### <a name="per-diems"></a>Dagtraktamenten

Du måste definiera medarbetarens dagtraktamente som din organisation ger. Eftersom dagtraktamente vanligtvis används för utgifter som till exempel logi, måltider och andra tillfälliga utgifter, kan du skapa regler för dagtraktamenteavdragen som din organisation ger. Traktamentstariffer kan anges utifrån tid på året, resmål eller båda. När du skapar en traktamentsregel kan du ange att hålla inne en procentandel av traktamentstariffen om medarbetaren bjuds på måltider eller tjänster. Du kan också definiera traktamentsreglernas skikt för att ange lägsta och högsta antal timmar som dagtraktamentetariffen kan tillämpas på en arbetares resor. **Beslut:**

-   Standardregler för traktamente för de första och sista dagarna:
    -   Vad är minsta antal timmar som en medarbetare kan fordra för en dag och får fortfarande en dagtraktamente?
    -   Finns det en reducering av beloppet som tillhandahålls för måltider för första och sista dagen? Hur stor är i så fall reduktionens procentsats?
    -   Finns det en reducering av beloppet som tillhandahålls för hotell för första och sista dagen? Hur stor är i så fall reduktionens procentsats?
    -   Finns det en reducering av beloppet som tillhandahålls för andra utgifter för första och sista dagen? Hur stor är i så fall reduktionens procentsats?
-   Standardregler för traktamente:
    -   Finns det en procentuell reducering i dagtraktamentet för varje måltid om till exempel måltiden är kostnadsfri? Hur stor är i så fall reduktionens procentsats för varje måltid?
    -   Beräknas måltidsreduceringen per dag, per resa eller med antal måltider per dag?
    -   Ska traktamentsbeloppet avrundas normalt eller avrundas uppåt?
    -   Beräknas dagtraktamente på en 24-timmarsperiod eller på en kalenderdag?
-   Traktamentsregler baserade på plats:
    -   Varierar traktamentstariffen baserat på plats och vilka platser inkluderas?
    -   Om traktamentstarriffen varierar baserat på plats, vilken procentandel ges på varje plats för:
        -   måltider
        -   hotell
        -   övriga utgifter

### <a name="expense-management-journals-and-accounts"></a>Utgiftshanteringsjournaler och konton

Utgiftshantering kräver att du använder flera journaler och konton. Du måste bestämma om till exempel samma konto används för förskott och kreditkortstvister. **Beslut:**

-   I vilken redovisningsjournal bokförs godkända utgiftsrapporter.
-   Vilket konto används för förskott?
-   Ska förskott bokföras direkt?

### <a name="payment-methods"></a>Betalningsmetoder

När du beviljar medarbetare utlägg på uppdrag av ditt företag, måste du definiera de betalningsmetoder som medarbetare har behörighet att använda. Du kan till exempel tillåta att använda kontanter eller ett företagskort. Du kan även tillåta medarbetare att använda personliga kreditkort och sedan ersätta dem. Du måste göra följande beslut för varje betalningsmetod som du tillåter. **Beslut:**

-   Vilka betalningsmetoder är tillåtna?
-   Vem äger betalningsmetoden för utgifterna?
-   Finns det en motkontotyp? I så fall vilket?
-   Om det finns ett motkonto, vilket är kontot?
-   Om betalningsmetoden är kreditkort, ska betalningsmetoden användas endast med importerade transaktioner?

### <a name="expense-categories-and-shared-categories"></a>Utgiftskategorier och delade kategorier

När medarbetare skapar en utgiftsrapport måste varje utgift som de registrerar associeras med en utgiftskategori. Utgiftskategorier härleds från delade kategorier som kan delas mellan juridiska personer inom din organisation. Dessa kategorier kan också delas i redovisning och projekthantering beroende på hur din organisation har definierats. Bestäm om kategorierna som används i utgiftshanteringen endast används i utgifter eller om de ska delas mellan projektet och utgifter, baserat på definitionen av din organisation och med anvisningar från implementeringsteamet. Observera att dessa kategorier kan delas mellan projekt och utgifter eller projekt och produktion, men inte mellan utgifter och produktion. Du måste göra följande beslut för varje utgiftskategori. **Beslut:**

-   Vilken är utgiftskategorin? Till exempel, hotell, flyg eller körsträcka.
-   Kan denna utgiftskategori även användas i projekthantering och redovisning?
-   Vilken är utgiftstypen?
-   Vilken är standardbetalningsmetoden för utgiftskategorin?
-   Krävs att utgifter i denna kategori specificeras?
-   Vilket är huvudstandardkontot för utgiftskategorin?
-   Vilken är standardartikelmomsgruppen för utgiftskategorin?
-   Är ytterligare betalningsmetoder tillåtna för utgiftskategorin? I så fall vilka?
-   Finns det underkategorier i denna utgiftskategori? I så fall:
    -   Exkluderas någon av underkategorierna från momsåterbetalning?
    -   Vilken är underkategoriernas artikelmomsgrupp?

    Om denna utgiftskategori också används i projekthantering och redovisning, besvara de återstående frågorna. Annars är du klar med det här avsnittet.
-   Vilka kostnadskonton används för följande?
    -   Kostnad
    -   Löneallokering
    -   PIA - Kostnadsvärde
    -   Kostnad - Artikel
    -   PIA - Kostnadsvärde - Artikel
    -   Upplupen förlust
    -   PIA - upplupen förlust
-   Vilka intäktskonton används för följande?
    -   Fakturerade intäkter
    -   Upplupna intäkter - Försäljningsvärde
    -   PIA - Försäljningsvärde
    -   Upplupna intäkter - Produktion)
    -   PIA - Produktion
    -   Upplupna intäkter - Vinst
    -   PIA - Vinst
    -   Upplupen intäkt - Abonnemang
    -   PIA - abonnemang

 

### <a name="taxes"></a>Skatter

För utgiftsrelaterade skatter måste du bestämma vad som inkluderas eller aktiveras i utgiftsrapporter. **Beslut:**

-   Inkluderas moms i utgiftsbeloppen?
-   Ska momsåterbetalning aktiveras på utgifter?

Observera att om du under din planering av redovisningen bestämmer dig för att tillämpa moms för USA och använda skatteregler, vilket görs genom att växla fältet **Använd momsbeskattningsregler** till Ja, kan du inte aktivera momsåterbetalning på utgifter.

## <a name="policies"></a>Policyer
Du kan skapa utgiftsrapportpolicyer så att din organisation kan spara tid och pengar när medarbetarna gör utlägg å dess vägnar. Policyer garanterar att medarbetare håller budgeten, ger all information som krävs och spenderar pengar endast efter behov. Du måste ta följande beslut för varje utgiftsrapportpolicy och policy för utgiftsrapportgodkännande som du skapar. **Beslut:**

-   Vilket är namnet på policyn?
-   Vad gäller utgiftspolicyn för?
-   Om du tidigare bestämde att du vill aktivera koncerninterna utgifter, för vilka företag i organisationen gäller den här policyn?
-   När börjar principen gälla?
-   När upphör policyn?
-   Vilken är policyregeln?
-   Vilket är resultatet av policyregeln?





