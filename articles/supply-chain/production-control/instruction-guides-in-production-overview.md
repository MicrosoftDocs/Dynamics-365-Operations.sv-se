---
title: Tillhandahålla guider för mixad verklighet för arbetare i produktion
description: I det här avsnittet beskrivs hur du integrerar modulen för produktionshantering i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides.
author: cabeln
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 3e69f9007b6605a07c6bec189b596d36a26f6222
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007225"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Tillhandahålla guider för mixad verklighet för arbetare i produktion

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Arbetare i produktionsprocesser kommer att ha nytta av relevanta instruktioner som ges vid rätt tid inom ramen för deras arbete. *Instruktionerna* gäller i flera arbetsdomäner, t.ex. sammansättning, service, åtgärder, certifiering och säkerhet. I alla dessa grundläggande affärsfunktioner kan de pågående utbildningsinstruktionerna hjälpa medarbetarna att utföra mer och arbeta bättre.

## <a name="introduction"></a>Introduktion

Du kan ange instruktioner på olika sätt. Ett effektivt system som levereras utanför kartongen använder [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

Dynamics 365 Guides kan hjälpa dina anställda med praktisk utbildning. Du kan definiera standardiserade processer med steg-för-steg-instruktioner som vägleder dina medarbetare till de verktyg och delar de behöver och visa anställda hur de kan använda verktygen i verkliga arbetssituationer.

Du kan koppla layoutstöd till olika aspekter av produktionsstyrningen inklusive:

- [Resurser](#resources)
- [Resursgrupper](#resource-groups)
- [Frisläppta produkter](#released-products)
- [Formler](#formulas)
- [Formelversioner](#formula-versions)
- [Strukturlista](#bom)
- [Strukturlisteversioner](#bom-versions)
- [Rutter](#routes)
- [Flödesversioner](#route-versions)
- [Flödesoperationsrelation](#route-operation-relations)

> [!NOTE]
> Du kan också koppla guider med tillgångshantering. För mer information om det alternativet, se [Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

När en medarbetare i första ledet väljer ett jobb på verkstadsgolvet med hjälp av Supply Chain Management kan medarbetaren se [relevanta handböcker](#logic) på jobbkortet. När arbetaren väljer en viss guide visas en QR-kod för denna guide på skärmen. Arbetaren använder sedan sin HoloLens för att skanna QR-koden, som startar guider och visar de instruktioner som krävs.

Följande underavsnitt beskriver några utvalda scenarier där företag över branscher kan se störst värde när man använder guider för att presentera tillverkningsinstruktioner.

### <a name="assembly"></a>Sammansättning

![Använda guider i monteringsuppgifter](media/instruction-guides-hero-assembly.png "Använda guider i serviceuppgifter")

Instruktioner i monteringsoperationer visar arbetare vilka verktyg och delar de behöver och hur de ska användas i realtidssituationer.

Produktionschefer kan t.ex. skapa och tilldela guider för [produktionsflöden](routes-operations.md), [operationsrelationer](routes-operations.md#operation-relations) eller [strukturlistor](bill-of-material-bom.md). Medarbetarna kommer att hitta de relevanta instruktionerna om respektive operationserfarenhet på verkstadsgolvet.

### <a name="service"></a>Service

![Använda guider i serviceuppgifter](media/instruction-guides-hero-service.png "Använda guider i serviceuppgifter")

Utrusta tekniker med guidade instruktioner på arbetsplatsen, vilket eliminerar behovet av att schemalägga ytterligare besök.

Serviceansvariga kan till exempel tilldela guider till specifika [produkter](../../commerce/product.md) som går igenom rutinerna för kvalitetsbedömning.

### <a name="quality"></a>Kvalitet

![Använda guider i kvalitetssäkringsuppgifter](media/instruction-guides-hero-quality.png "Använda guider i kvalitetssäkringsuppgifter")

Lansering av nya processer och bättre överensstämmelse genom att göra medarbetarnas kunskaper i ett repeterbart verktyg.

Kvalitetssäkringsansvariga kan tilldela guider till [produkter](../../commerce/product.md) som går igenom rutinerna för kvalitetsbedömning.

### <a name="certifications"></a>Intyg

![Använda guider för uppgifter som rör certifiering](media/instruction-guides-hero-certification.png "Använda guider för uppgifter som rör certifiering")

Se till att alla medarbetare uppfyller höga standarder genom att snabbt identifiera vem som behöver hjälp och var.

### <a name="safety"></a>Säkerhet

![Använda guider i instruktioner om arbetssäkerhet](media/instruction-guides-hero-safety.png "Använda guider i instruktioner om arbetssäkerhet")

Ge instruktioner för hur du ska gå igenom de farliga procedurerna i stort innan du försöker göra det i den fysiska miljön. Med en blandad verklighet kan medarbetarna uppleva farliga procedurer i princip.

Produktionschefer kan tillhandahålla dedikerade hanteringsinstruktioner för hantering av farliga material och ömtåliga genom att tilldela instruktioner till [produktartiklar](../../commerce/product.md), [flöden](routes-operations.md) och [operationer](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Komma igång med instruktioner och guider

Om du vill aktivera instruktioner i produktionsprocesser tillhandahåller Supply Chain Management en medföljande integration i Dynamics 365 Guides. En licensierad och installerad appinstans av Guides krävs för att skapa, underhålla och tilldela instruktioner till produktion och arbete i mixad verklighet.

### <a name="prerequisites"></a>Förutsättningar

För att du ska kunna använda den här funktionen måste systemet innehålla följande:

- Dynamics 365 Supply Chain Management version 10.0.15 eller senare
- [Dubbelriktad skrivning](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) för Supply Chain Management-appar.
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 eller senare

### <a name="turn-on-the-feature"></a>Aktivera en funktion

Om du vill göra funktionen tillgänglig i systemet måste du aktivera dess konfigurationsnycklar. Du behöver bara göra detta en gång. För att göra detta måste en administratör göra följande:

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Expandera avsnittet **Mixad verklighet** och markera kryssrutan **Guide för mixad verklighet**.
1. Expandera avsnittet **Produktionshantering** och markera kryssrutan **Produktionsinstruktioner**.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Konfigurera hur guider visas på verkstadsgolvet

Om du vill konfigurera hur guider visas verkstadsgolvet går du till konfiguration **Mixad verklighet \> Dynamics 365 Guides \> Konfigurera integration av guider**.

![Konfigurera integrering av guide för tillverkning](media/instruction-guides-configure-integration.png "Konfigurera integrering av guide för tillverkning")

Ange följande fält.

- **Microsoft Dataverse URL** - Ange den URL till Microsoft Dataverse-miljön där du skapar Guides. Formatet är "contoso.crm4.dynamics.com", där den första delen av webbadressen vanligtvis namnges efter din organisation (t.ex. "contoso."), den andra delen är specifik för din miljös dataområde (t.ex. "CRM4.") och den sista delen är domänen (t.ex. "dynamics.com"). Ett sätt att hitta rätt URL är att gå till [home.dynamics.com](https://home.dynamics.com/) och sedan öppna appen Guides. När Guides öppnas visas URL:en i adressfältet i webbläsaren (endast bas-URL:en, som bör likna föregående exempel). Det här värdet används för att skapa adresser för guider och de kommer att kodas till QR-koderna."
- **Storlek på QR** - Ange storleken på den återgivna QR-koden. Vi rekommenderar att du väljer en storlek som kommer att fylla större delen av skärmen, men inte mer. Normalt *15* är ett bra värde.
- **Korrigeringsnivå för QR-kod** - Ange granularitet för QR-koden. Högre granularitet kan öka kodens tillförlitlighet, men **QR-kodens storlek** måste vara stor nog för att ge den detaljnivå som krävs för den valda korrigeringsnivån.

> [!TIP]
> - Värden för QR-koder som är för stora för din bildskärm tar lite längre tid att återge och sedan skalas de ned så att de passar din bildskärm. De ger ingen förmån.
> - De QR-kodstorlekar som är för små kan minska möjligheten HoloLens att läsa koden korrekt i vissa miljöer.
> - Vi rekommenderar att du testar inställningarna för varje enhet som ska visa QR-koder för HoloLens-användarna. Välj inställningar som ger tillräcklig läsbarhet i din arbetsmiljö.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Få en översikt över alla tilldelningar i guidetilldelningar

Använd sidan **Alla guider** för att visa en lista över alla tillgängliga guider i din organisation och alla tilldelningar till produktionsprocesserna och resurserna. Om du vill öppna den går du till **Mixad verklighet \> Guider \> Alla guider**. Listan högst upp visar alla tillgängliga guider och du kan använda fältet här för att filtrera listan. Listan längst ned visar alla guider tilldelningar och innehåller ett verktygsfält för hantering av dem.

![Hantera guider](media/instruction-guides-allguides.png "Hantera guider")

I följande avsnitt beskrivs de typer av objekt som du kan tilldela guider till. Varje tilldelad guide innehåller instruktioner som automatiskt kopplas till respektive produktionsjobb och blir tillgängliga i verktygsgolvet.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Associera en guider till en resurs

Lägg till en guide till en [resurs](operations-resources.md) för att erbjuda guiden i samband med relevanta produktionsjobb.

### <a name="typical-scenario-using-resources"></a>Vanligt scenario med resurser

Du kan till exempel lägga till en guide med generella maskin säkerhets- eller hanteringsinstruktioner på en resurs av typen maskin. Sedan kommer guiden att vara tillgänglig på alla jobb som utförs på datorn.

### <a name="add-a-guide-to-a-resource"></a>Lägg till en guider till en resurs

Lägg till en guider till en resurs:

1. Gå till **Produktionsstyrning \> Inställningar \> Resurser \> Resurser**.
1. Välj den resurs som du vill tilldela en guide till i listrutan.
1. Expandera snabbfliken **Associerade guider**.
1. Välj **Lägg till** från verktygsfältet **Associerade guider**. En ny rad läggs till i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela. Om du har ett stort antal guider kan du filtrera listan för att hitta den som du söker efter.
    ![Hantera guider](media/instruction-guides-allguides.png "Hantera guider")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Associera en guider till en resursgrupp

Du kan lägga till en guide i [resursgrupper](tasks/define-discrete-manufacturing-resource-group.md) om du använder dem för att hantera grupper av maskiner, produktionsrader eller arbetsceller.

### <a name="typical-scenarios-using-resource-groups"></a>Vanligt scenario med resursgrupper

**Exempel 1:** du har definierat en resursgrupp för flera maskiner av samma modell. I stället för att tilldela relevant guide för hanteringsinstruktioner för maskinmodellen till varje relevant resurs, kan du i stället tilldela guiden till den resursgrupp som återspeglar den maskinmodellen.

**Exempel 2:** du har definierat en resursgrupp för en arbetsgrupp som innehåller olika maskiner och du har en guide som innehåller allmänna instruktioner för hur du ska underhålla arbetsgruppen. Guiden gäller alla produktionsaktiviteter i den här arbetsgruppen.

### <a name="add-a-guide-to-a-resource-group"></a>Lägg till en guide till en resursgrupp

För att lägga till en guide till en resursgrupp:

1. Gå till **Produktionsstyrning \> Inställningar \> Resurser \> Resursgrupper**.
1. Välj den resursgrupp som du vill tilldela en guide till i listrutan.
1. Expandera snabbfliken **Associerade guider**.
1. Välj **Lägg till** från verktygsfältet **Associerade guider**. En ny rad läggs till i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela. Om du har ett stort antal guider kan du filtrera listan för att hitta den som du söker efter.
    ![Lägg till en guide till en resursgrupp](media/instruction-guides-resourcegroup.png "Lägg till en guide till en resursgrupp")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Associera en guide till en frisläppt produkt

Du kan lägga till en guide för alla [frisläppta produkter](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Vanligt scenario när frisläppta produkter används

Med hjälp av guider på produktnivå kan hjälpa verkstadsarbetarna med instruktioner som rör drift eller hantering av en specifik frisläppt produkt eller artikel.

### <a name="add-a-guide-to-a-released-product"></a>Lägg till en guide till en frisläppt produkt

Lägg till en guide till en frisläppt produkt:

1. Gå till **Produktionsinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna den produkt som du vill tilldela en guide till.
1. I åtgärdsfönstret, öppna fliken **Tekniker** och från gruppen **Vy** välj **Associerade guider**.
1. Sidan **Associerade guider** öppnas för den valda produkten.
1. Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet. 
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en frisläppt produkt](media/instruction-guides-ReleasedProduct-AddGuides.png "Lägg till en guide till en frisläppt produkt")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Associera en guide till en formel

Du kan lägga till en guide för alla [formel](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Vanligt scenario med formler
  
På formelnivå finns guider som ger verkstadsarbetare guidade hanteringsinstruktioner i samband med en formel eller ett recept. Guider kan också tilldelas till en version av en formel.

> [!NOTE]
> Du kan tilldela vägledningar som är relevanta för produktionsprocesser baserade på en formel till ett flöde, flödesversion eller flödesoperationsrelationer.  

> Guider kan för närvarande inte kopplas till enskilda formelrader.

### <a name="add-a-guide-to-a-formula"></a>Lägg till en guide till en formel

Lägg till en guide till en formel:

1. Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.
1. Öppna den formel som du vill tilldela en guide till.
1. Öppna fliken **Rubrik** ovanför den övre snabbfliken.
1. Expandera snabbfliken **Associerade guider**.
1. Välj **Lägg till** från verktygsfältet **Associerade guider**. En ny rad läggs till i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en formel](media/instruction-guides-Formula.png "Lägg till en guide till en formel")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Associera en guide till en formelversion

Du kan lägga till en guide för alla [formelversion](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Vanligt scenario med formelversioner

Guider som är kopplade till en enskild version av en formel ger arbetstagare instruktioner som går igenom produktionen av formelreceptet.

> [!TIP]
> Du kan tilldela vägledningar som är relevanta för produktionsprocesser baserade på en formelversion till ett flöde, flödesversion eller flödesoperationsrelationer.  

> [!NOTE]
> Guider kan för närvarande inte kopplas till enskilda formelrader.

### <a name="add-a-guide-to-a-formula-version"></a>Lägg till en guide till en formelversion

Lägg till en guide till en formelversion:

1. Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.
1. Öppna formeln som innehåller en version som du vill tilldela en guide till.
1. Öppna fliken **Rubrik** ovanför den övre snabbfliken.
1. På snabbfliken **Formelversioner** välj den version som du vill tilldela en guide till.
1. I verktygsfältet **Formelversioner** väljer du **Koppla guider**.
    ![Öppna de guider som associeras med en vald formelversion](media/instruction-guides-FormulaVersion.png "Öppna de guider som associeras med en vald formelversion")
1. Sidan **Associerade guider** öppnas för den valda formelversionen.
1. Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet. 
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en formelversion](media/instruction-guides-FormulaVersionAddGuide.png "Lägg till en guide till en formelversion")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Associera en guide till en strukturlista

Du kan lägga till en guide för en valfri [strukturlista](bill-of-material-bom.md).

### <a name="typical-scenario-using-bills-of-materials"></a>Vanligt scenario vid användning av strukturlistor

Guider som är kopplade till en strukturlista ger arbetstagare instruktioner som förklarar hur material förbereds och hanteras från en strukturlista. Guider kan också tilldelas till en version av en strukturlista.

> [!NOTE]
> Guider kan för närvarande inte kopplas till enskilda strukturlisterader.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Lägg till en guide till en strukturlista

Lägg till en guide till en strukturlista:

1. Gå till **Produktinformationshantering \> Strukturlistor och formler \> Strukturlistor**.
1. Öppna den strukturlista som du vill tilldela en guide till.
1. Öppna fliken **Rubrik** ovanför den övre snabbfliken.
1. Expandera snabbfliken **Associerade guider**.
1. Välj **Lägg till** från verktygsfältet **Associerade guider**. En ny rad läggs till i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en strukturlista](media/instruction-guides-BOM.png "Lägg till en guide till en strukturlista")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Associera en guide till en strukturlisteversion

Du kan lägga till en guide för en valfri [strukturlisteversion](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Vanligt scenario vid användning av strukturlisteversioner

Guider som är kopplade till en enskild strukturlisteversion ger arbetstagare instruktioner som förklarar hur material förbereds och hanteras för en version av en strukturlista som skiljer sig från den allmänna strukturlistan eller andra versioner av den.

> [!NOTE]
> Guider kan för närvarande inte kopplas till enskilda strukturlisterader.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Lägg till en guide till en strukturlisteversion

Lägg till en guide till en strukturlisteversion:

1. Gå till **Produktinformationshantering \> Strukturlistor och formler \> Strukturlistor**.
1. Öppna strukturlistan som innehåller en version som du vill tilldela en guide till.
1. Öppna fliken **Rubrik** ovanför den övre snabbfliken.
1. På snabbfliken **Strukturlisteversioner** välj den version som du vill tilldela en guide till.
1. I verktygsfältet **Strukturlisteversioner** väljer du **Koppla guider**.
    ![Öppna de guider som associeras med en vald strukturlisteversion](media/instruction-guides-BOMVersion.png "Öppna de guider som associeras med en vald strukturlisteversion")
1. Sidan **Associerade guider** öppnas för den valda strukturlisteversionen.
1. Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en strukturlisteversion](media/instruction-guides-BOMVersionAddGuide.png "Lägg till en guide till en strukturlisteversion")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Associera en guide till ett flöde

Du kan lägga till en guide för alla [flöden](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Vanligt scenario med flöden

Flöden används vanligtvis för att ange hur en viss frisläppt produkt ska skapas på grundval av en strukturlista eller strukturlisteversion och med en uppsättning resurser eller resursgrupper.

Tilldela en guide till ett flöde om du vill skapa steg för steg-instruktioner för respektive produktionsprocess.

### <a name="add-a-guide-to-a-route"></a>Lägg till en guide till ett flöde

Lägg till en guide till ett flöde:

1. Gå till **produktionskontroll \> alla flöden**.
1. Öppna det flöde som du vill tilldela en guide till.
1. Expandera snabbfliken **Associerade guider**.
1. Välj **Lägg till** från verktygsfältet **Associerade guider**. En ny rad läggs till i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till ett flöde](media/instruction-guides-Route.png "Lägg till en guide till ett flöde")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Associera en guide till en flödesversion

Du kan lägga till en guide för alla [flödesversion](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Vanligt scenario med flödesversioner

Flödesversioner används vanligtvis för att ange varianter av produktionsprocesser baserade på ett befintligt flöde. Du kan tilldela olika guider till varje flödesversion.

### <a name="add-a-guide-to-a-route-version"></a>Lägg till en guide till en flödesversion

Lägg till en guide till en flödesversion:

1. Gå till **produktionskontroll \> alla flöden**.
1. Öppna det flöde som du vill tilldela en guide till.
1. På snabbfliken **Versioner** välj den version som du vill tilldela en guide till.
1. I verktygsfältet **Versioner** väljer du **Koppla guider**.
    ![Öppna de guider som associeras med en vald flödesversion](media/instruction-guides-RouteVersion.png "Öppna de guider som associeras med en vald flödesversion")
1. Sidan **Associerade guider** öppnas för den valda strukturlisteversionen.
1. Välj **Lägg till** i åtgärdsfönstret för att lägga till en ny rad i rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela.
    ![Lägg till en guide till en flödesversion](media/instruction-guides-RouteVersionAddGuide.png "Lägg till en guide till en flödesversion")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Associera en guide till en flödesoperationsrelation

Du kan lägga till en guide för alla [flödesoperationsrelationer](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Vanligt scenario med flödesoperationsrelationer

Operationsrelationer är det mest specifika sättet att lägga till vägledning för en produktprocess och dess relaterade operationer. Du kan ange vägledning för varje operation i ett flöde och ange olika vägledning för vilken typ av relationskontext som anges för ett flöde, t.ex. för specifika artiklar, konfigurationer med mera. Du kan också ange för vilka faser i operationen som vägledningen gäller (t.ex. inställningar, köhantering, process eller transport).

> [!NOTE]
> Om du anger guider för flera operationsrelationer för ett flöde, bland dessa guider, visas bara guiden från den mest specifika relationen i arbetsstyrningen för det genererade jobbet.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Lägg till en guide till en flödesoperationsrelation

Lägg till en guide till en flödesoperationsrelation:

1. Gå till **produktionskontroll \> alla flöden**.
1. Öppna det flöde som du vill tilldela en guide till.
1. I åtgärdsfönstret, öppna fliken **Flöde** och från gruppen **Underhåll** välj **Flödesdetaljer**.
1. Sidan **Flödesinformation** öppnas för det valda flödet.
1. Välj den operation som du vill ge vägledning för i det övre rutnätet.
1. I det nedre rutnätet väljer du en specifik relation (eller det generiska **Alla** relation).
    ![Välj en operation och sedan en relation](media/instruction-guides-RouteOperationRelation.png "Välj en operation och sedan en relation")
1. Ovanför den nedre rutnätet öppnar du fliken **Kopplade guider**. ![Fliken Kopplade guider](media/instruction-guides-RouteOperationRelation-AddGuide.png "Fliken kopplade guider")
1. Välj **Lägg till** från verktygsfältet högst upp i det nedre rutnätet för att lägga till en ny rad till rutnätet.
1. För den nya raden använder du listrutan i kolumnen **namn** för att välja den guider du vill tilldela. Markera kryssrutan för varje kontext där den valda guiden ska vara tillgänglig i resten av raden.

> [!NOTE]
> Du kan lägga till en eller flera guider för varje steg i varje operation.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Välj guider från gränssnittet för arbetsstyrningskörning

När en arbetare öppnar en jobblista i gränssnittet för arbetsstyrningskörningen, hittar Supply Chain Management relevanta guider för de jobb som visas. Använd knappen **Guider** om du vill visa relevanta guider.

![Knappen guider från gränssnittet för arbetsstyrningskörning](media/instruction-guides-Shopfloor1.png "Knappen guider från gränssnittet för arbetsstyrningskörning")

Sätt sedan på en HoloLens och gå till respektive guide efter att titta på QR-koden och aktivera respektive guide.

![QR-kod för åtkomst till guider med HoloLens](media/instruction-guides-Shopfloor2.png "QR-kod för åtkomst till guider med HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Lösa logiken för att markera guider

Du kan lägga till guider till följande produktionsdata:

- [Resurser](#resources)
- [Resursgrupper](#resource-groups)
- [Frisläppta produkter](#released-products)
- [Formler](#formulas)
- [Formelversioner](#formula-versions)
- [Strukturlista](#bom)
- [Strukturlisteversioner](#bom-versions)
- [Rutter](#routes)
- [Flödesversioner](#route-versions)
- [Flödesoperationsrelation](#route-operation-relations)

När Supply Chain Management genererar jobben för produktionsgolvet, samlar det in relevanta guider från dessa källor. Notera följande viktiga regler.

- Om du kopplar en strukturlisteversion eller en formelversion till ett flöde tillverkningsorder, visas alla guider som är kopplade till den aktuella versionen och även de stödlinjer som är kopplade till den överordnade strukturlistan eller formeln för den versionen, visas i jobbet.
- Om du kopplar ett flöde till en tillverkningsorder, visas alla guider som är kopplade till den aktuella versionen och även de stödlinjer som är kopplade till det överordnade flödet för den versionen, visas i jobbet.
- Om du definierar flera flödesoperationsrelationer som omfattar *alla* relationer och tilldelar guider till dem, visas bara guiderna från den mest specifika relationen för jobbet.  

![Diagram för att lösa relevanta guider](media/instruction-guides-Resolve.png "Diagram för att lösa relevanta guider")
