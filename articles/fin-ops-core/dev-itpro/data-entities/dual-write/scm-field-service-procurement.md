---
title: Integrera anskaffning mellan Supply Chain Management och Field Service
description: I det här avsnittet beskrivs hur integration av nedskrivningsfrågor stöder upprättande av inköpsorder och uppdateringar från både Supply Chain Management och Field Service.
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 4a2420981553957b6b234fe56747bc6f3568acf6b8ad77366c33caeae63b4faf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716769"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Integrera anskaffning mellan Supply Chain Management och Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management tillhandahåller robusta anskaffningsfunktioner. Dynamics 365 Field Service erbjuder liknande funktioner som stöder inköpsprocesserna som hör till serviceprocessen. Funktionerna i de här två programmen integreras med skrivfunktionen, och de resulterande korsfunktionella användningsfallen aktiveras med tabellmappningar, lösningslogik, vyer och formulär.

Denna integration stöder skapande av inköpsorder och i de flesta fall uppdateringar från båda programmen. Supply Chain Management kontrollerar dock priser, adresser och produktinleverans. Flera kraftfulla korsfunktionella användningsfall är aktiverade för organisationer som använder både Field Service och Supply Chain Management. Med hjälp av dessa fall kan anskaffningar initieras och spåras mellan båda systemen.

I följande illustration visas registren i båda systemen och hur de mappas till varandra. Inköpsorder i Field Service refererar till *kontorad* medan inköpsorder i Supply Chain Management refererar till en *leverantörsrad*. För att lösa integrationen använder dubbelriktad skrivning en referens för att länka *leverantörsrader* till *kontorader*. Mer information finns i [Integrerat leverantörshuvud](vendor-mapping.md).

![Mappning för anskaffning.](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Förutsättningar

Om du vill integrera Supply Chain Management med Field Service måste du installera följande komponenter:

- Field Service version 8.8.31.60 senare, för omfattande integrering av inköpsorder
- Supply Chain Management version 10.0.14 eller senare
- Dubbelriktad skrivning för att köra OneFSSCM-lösningen

## <a name="installation-guidelines"></a>Riktlinjer för installation

### <a name="prerequisites"></a>Förutsättningar

- **Dubbelriktad skrivning** – För mer information, se [Startsidan för dubbelriktad skrivning](dual-write-home-page.md#dual-write-setup).
- **Dynamics 365 Field Service** – För mer information, se [Hur du installerar Dynamics 365 Field Service](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

När de har aktiverats i Microsoft Dataverse introducerar dubbelriktad skrivning och Field Service flera lösningsskikt som utökar miljön med nya metadata, formulär, vyer och logik. Dessa lösningar kan aktiveras i valfri ordning, även om du vanligtvis installerar i den ordning som anges här:

1. **Field Service Common** – Field Service Common är installerad när Field Service installeras i miljön.
2. **Field Service (Förankra)** – Field Service (Förankra) är installerad när Field Service installeras i miljön. 
3. **Utökad Supply Chain Management** – Utökad Supply Chain Management installeras automatiskt när nedskrivning aktiveras i en miljö. 
4. **OneFSSCM-lösning** – OneFSSCM installeras automatiskt av den lösning (Field Service eller Supply Chain Management) som har installerats sist.

    - Om Field Service redan har installerats i miljön, och du aktiverar dubbelriktad skrivning, som installerar utökad Supply Chain Management installeras OneFSSCM.
    - Om utökad Supply Chain Management har installerats i miljön, och du installerar Field Service installeras OneFSSCM.

## <a name="initial-synchronization"></a>Initial synkronisering

Om du vill skapa nya inköpsorder och arbeta med befintliga inköpsorder måste du synkronisera referensdata mellan Supply Chain Management och Dataverse. Du använder den ursprungliga skrivfunktionen när du vill söka efter tabellrelationer och hitta de tabeller som du måste aktivera för en given mappning.

Du måste synkronisera följande tabeller:

- Produktmallar

    När du kör den ursprungliga skrivning visas en fullständig lista över de tabeller som behövs. Här följer några exempel på dessa mallar:

    - Alla produkter
    - Frisläppta produkter V2
    - Dataverse frisläppta specifika produkter

- Sites
- Lagerställen
- Mallar för anskaffningskategorier

    Här följer några exempel på dessa mallar:

    - Anskaffningskategorier
    - Pro
    - Produktkategorihierarki
    - Produktkategoritilldelningar

- Leverantörsmallar, t.ex. Leverantör V2
- Kontaktpersonmallar, t.ex. Dataverse Kontakter V2
- Arbetsmallar, t.ex. Arbetare

Genom synkronisering av registren ser du till att alla dokument (inköpsorder och produktinleveranser) i Supply Chain Management finns tillgängliga i Dataverse.

### <a name="account-and-vendor-tables"></a>Tabellerna Konto och Leverantör

Inköpsorder i Field Service är beroende av kontoregistret för att spåra leverantörer. Därför använder Dataverse-tabeller för inköpsorder konton för att spåra leverantörer. För att hantera denna viktiga skillnad måste följande fyra arbetsflöden aktiveras för att hålla kontona och leverantörerna synkroniserade: 

- Skapa leverantörer i tabellen Konton
- Skapa leverantörer i tabellen Leverantörer
- Uppdatera leverantörer i tabellen Konton
- Uppdatera leverantörer i tabellen Leverantörer

Om OneFSSCM är installerat, eftersom både Field Service och utökad Supply Chain Management är installerade, aktiveras dessa arbetsflöden automatiskt. Om Field Service inte är installerat, men du vill integrera inköpsordertabeller med Dataverse måste du aktivera dessa arbetsflöden. I båda fallen, om du inte börjar från grunden, kan du behöva se till att alla leverantörer skapas som konton i Dataverse innan du skapar inköpsorder. Annars kan fel uppstå.

### <a name="initial-synchronization"></a>Initial synkronisering

När alla förutsättningar är uppfyllda måste du göra en ursprunglig synkronisering av följande mallar om du vill att befintliga inköpsorder och produktinleveranser ska vara tillgängliga i båda systemen:

- Inköpsorderrubrik V2
- CDS inköpsorderrad
- Mjuk borttagning av CDS-inköpsorderrad
- Inleverans av inköpsorder
- Inköpsorder – produktinleverans

## <a name="mappings-with-logic"></a>Mappningar med logik

Inköpsintegrationen utökar produktmappningen med följande logik för att säkerställa att kolumnen **Produkttypen Field Service** är korrekt inställd i produkttabellen i Dataverse:

- Om **Produkttyp** är inställd på *Produkt* och **Artikelmodellgrupp, produkt i lager** är inställd på *Sant* är inställd **Produkttypen Field Service** är inställd *Lager*.
- Om **Produkttyp** är inställd på *Produkt* och **Artikelmodellgrupp, produkt i lager** är inställd på *Falsk* är inställd **Produkttypen Field Service** är inställd *Inte i lager*.
- Om **Produkttyp** är inställd på *Tjänst*, ställs **Produkttypen Field Service** in på *Tjänst*.

Dessutom innehåller Dataverse logik som mappar leverantörer med deras relaterade konton. Den här logiken ställer in standardkontot för fakturaleverantörer. Vid skapa ställer serversidans inbetalningslogik in standardkontot för fakturaleverantörer från den leverantör som är kopplad till kontot. Leverantören har en referens till fakturakontot som används för att ställa in det här värdet.

## <a name="supported-scenarios"></a>Stödda scenarier

- Inköpsorder kan skapas och uppdateras av Dataverse-användare. Processen och data styrs dock av Supply Chain Management. Begränsningarna i uppdateringar av inköpsorderkolumner i Supply Chain Management gäller när uppdateringar kommer från Field Service. Du kan till exempel inte uppdatera en inköpsorder om den har slutförts. 
- Om inköpsordern kontrolleras genom ändringshantering i Supply Chain Management kan en Field Service-användare endast uppdatera inköpsordern om godkännandestatus för Supply Chain Management är *Utkast*.
- Flera kolumner hanteras bara av Supply Chain Management och kan inte uppdateras i Field Service. Du tar reda på vilka kolumner som inte kan uppdateras genom att granska mappningsregistren i produkten. För att göra webbsidorna mer användarvänliga är de flesta av dessa kolumner inställda på skrivskyddade på Dataverse-sidor. 

    Kolumnerna för prisinformation hanteras till exempel av Supply Chain Management. Supply Chain Management har handelsavtal som Field Service kan ha nytta av. kolumner som **Enhetspris**, **Rabatt** och **Nettobelopp** kommer endast från Supply Chain Management. Om du vill vara säker på att priset synkroniseras till Field Service bör du använda funktionen **Synkronisera** på sidorna **Inköpsorder** och **Inköpsorderprodukt** i Dataverse när inköpsorderdata har angetts. Mer information finns i [Synkronisera med Dynamics 365 Supply Chain Management anskaffningsdata på begäran](#sync-procurement).

- Kolumnen **Summor** är bara tillgänglig i Field Service eftersom det inte finns några uppdaterade summor för inköpsordern i Supply Chain Management. Summorna i Supply Chain Management beräknas baserat på flera parametrar som inte är tillgängliga i Field Service.
- Inköpsorderrader där endast en anskaffningskategori är angiven, eller där den angivna produkten är en artikel av produkttypen *Tjänst* eller Field Service kan kan endast initieras i Supply Chain Management. Raderna synkroniseras sedan till Dataverse och visas i Field Service.
- Om endast Field Service är installerat och inte Supply Chain Management, är kolumnen **Lagerställe** obligatorisk på inköpsordern. Om Supply Chain Management installeras är installerad detta krav friare, eftersom Supply Chain Management tillåter inköpsorderrader där inget lagerställe angetts i vissa situationer.
- Produktinleveranser (inköpsorderinleveranser i Dataverse) hanteras av Supply Chain Management och kan inte skapas från Dataverse om Supply Chain Management är installerat. Produktinleveranserna från Supply Chain Management synkroniseras från Supply Chain Management till Dataverse.
- Underleverans är tillåtet i Supply Chain Management. OneFSSCM-lösningen lägger till logik så att när produktinleveransraden (eller produktorderinleverans i Dataverse) skapas eller uppdateras, skapas en lagerjournalrad i Dataverse för att justera återstående kvantitet som är på beställning för scenarier med underleverans.

## <a name="unsupported-scenarios"></a>Scenarier som inte stöds

- Field Service förhindrar att rader läggs till i en annullerad inköpsorder i Supply Chain Management. Som en lösning kan du ändra systemstatusen för inköpsordern i Field Service och sedan lägga till den nya raden i antingen Field Service eller Supply Chain Management.
- Anskaffningsrader påverkar lagernivåer i båda systemen, men den här integrationen säkerställer inte lagerjusteringen i hela Supply Chain Management och Field Service. Både Field Service och Supply Chain Management har andra processer som uppdaterar lagernivåer. Dessa processer ligger utanför anskaffningsområdet.

## <a name="status-management"></a>Statusledning

Statusvärdet för inköpsorder i Field Service avviker från statusen i Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Status för Field Service inköpsorder och inköpsorderprodukter

| Rubrik – Systemstatus | Rubrik – Godkännandestatus | Artikelstatus |
|---|---|---|
| <ul><li>Utkast</li><li>Skickade</li><li>Avbröts</li><li>Produktinleverans</li><li>Fakturerat</li></ul> | <ul><li>Null</li><li>Godkänd</li><li>Avvisad</li></ul> | <ul><li>Väntar</li><li>Inlevererade</li><li>Avbröts</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Status för inköpsorder- och inköpsorderraderna i Supply Chain Management

Radgodkännandestatus är bara aktiva när det finns ett radarbetsflöde.

| Rubrik – dokumentstatus | Rubrik – Godkännandestatus | Radstatus | Radgodkännandestatus |
|---|---|---|---|
| <ul><li>Öppen order (restorder)</li><li>Inlevererade</li><li>Fakturerad</li><li>Avbröts</li></ul> | <ul><li>Utkast</li><li>Under granskning</li><li>Godkänd</li><li>Avvisad</li><li>I extern granskning</li><li>Bekräftat</li><li>Slutlig version</li></ul> | <ul><li>Öppen order (restorder)</li><li>Inlevererade</li><li>Fakturerad</li><li>Avbröts</li></ul> | <ul><li>Har inte skickats</li><li>Under granskning</li><li>Godkänd</li><li>Avvisad</li></ul> |

Följande regler används för statuskolumnerna:

- Statusen i Supply Chain Management kan inte uppdateras från Field Service. I vissa fall uppdateras dock statusen i Field Service när inköpsorderstatusen i Supply Chain Management ändras.
- Om en inköpsorder i Supply Chain Management är under ändringshantering och en ändring bearbetas, blir godkännandestatus *Utkast* eller *Under granskning*. I detta fall kommer godkännandestatus för Field Service approval att anges till *Null*.
- Om status för inköpsordergodkännande i Supply Chain Management anges till *Godkänd*, *I extern granskning*, *Bekräftad* eller *Slutförd* kommer godkännandestatus för Field Service inköpsorder att anges till *Godkänd*.
- Om status för inköpsordergodkännande i Supply Chain Management anges till *Avvisad*, kommer godkännandestatus för Field Service inköpsorder anges till *Avvisad*.
- Om dokumentrubrikens status i Supply Chain Management ändras till *Öppen order (restorder)* och Field Service inköpsorderstatus är *Utkast* eller *Annullerad*, Field Service inköpsorderstatus kommer att ändras till *Skickad*.
- Om dokumentrubrikens status i Supply Chain Management ändras till *Annullerad* och inga produkter för inköpsorderinleverans i Field Service är associerade med inköpsordern (via inköpsorderprodukter), sätts Field Service systemstatus anges till *Annullerad*.
- Om status för inköpsorderraden i Supply Chain Management är *Annullerad*, ställs inköpsorderproduktstatusen i Field Service in på *Annullerad*. Om inköpsorderradens status i Supply Chain Management ändras från *Annullerad* till *Restorder*, ställs artikelstatus för inköpsorderprodukt i Field Service in på *Väntar*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Synkronisera med Supply Chain Management anskaffningsdata på begäran

Supply Chain Management innehåller anskaffningsdata som hanterar handelsavtal, rabatter och andra scenarier som är beroende av sekundära processer i Supply Chain Management. Anskaffningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller inköpsorder. När du använder dubbelriktad skrivning synkroniseras inte alltid data i de två miljöerna, särskilt i scenarier där raden har skapats eller uppdaterats från Dataverse och kan utlösa uppföljningsprocesser i Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Synkronisera anskaffningsdata med Supply Chain Management

1. I Dataverse, gå till **Lager \> Inköpsorder**.
2. Välj **Ny** för att skapa en ny inköpsorder eller välj raden för en befintlig inköpsorder.
3. Från inköpsordern eller inköpsorderraden.
4. I åtgärdsfönstret väljer du **Synkronisera**.

Alla kolumner från Dataverse och Field Service som delas av Supply Chain Management synkroniseras.

Här är de situationer där du kan använda funktionen **synkronisera**:

- Om du gör flera på varandra följande ändringar i samma rad från Dataverse kör funktionen **Synkronisera**.
- Om du inte är säker på om en ändring kan vara den andra på varandra följande ändringen från Dataverse, kan det vara vettigt att köra funktionen **Synkronisera**.
- Om ett felmeddelande visas om uppdatering av ett värde från Supply Chain Management, kör funktionen **Synkronisera** och gör sedan ett nytt försök att uppdatera i Dataverse.

## <a name="cancelling-the-posting-process"></a>Annullera bokföringsprocessen

Om bokföringsprocessen för produktinleverans avbryts under bearbetningen kan det hända att dubbelriktad skrivning skapar en produktinleveransrad i Dataverse, men inte skapar en rad för i Supply Chain Management. Det inträffar eftersom dubbelriktad skrivning finns det inte stöd för distribuerade transaktioner.

## <a name="templates"></a>Mallar

Följande mallar finns tillgängliga för integrering av anskaffningsrelaterade dokument.

| Hantering av underleverantörer | Field Service | beskrivning |
|---|---|---|
| [Inköpsorderrubrik V2](mapping-reference.md#183) | msdyn\_Purchaseorders | Den här tabellen innehåller de kolumner som representerar inköpsorderrubriken. |
| [Entiteten inköpsorderrad](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | Den här tabellen innehåller de rader som representerar rader på en inköpsorder. Produktnumret används för synkronisering. Detta identifierar produkten som en lagerhållningsenhet (SKU), inklusive produktdimensioner. Mer information om produktintegration med Dataverse finns i [Enhetlig produkterfarenhet](product-mapping.md). |
| [Produktinleveranshuvud](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | Den här tabellen innehåller rubrikerna för produktinleverans som skapas när en produktinleverans bokförs i Supply Chain Management. |
| [Produktinleveransrad](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | Den här tabellen innehåller rader för produktinleverans som skapas när en produktinleverans bokförs i Supply Chain Management. |
| [Inköpsorderrad mjukt borttagen enhet](mapping-reference.md#182) | msdyn\_purchaseorderproducts | Den här tabellen innehåller information om inköpsorderrader som är mjukraderade. En inköpsorderrad i Supply Chain Management kan bara tas bort mjukt när inköpsordern har bekräftats eller godkänts, om ändringshanteringen är aktiverad. Raden finns i Supply Chain Management-databasen och markeras som **IsDeleted**. Eftersom Dataverse inte har något begrepp för mjukradering är det viktigt att den här informationen synkroniseras till Dataverse. Rader som är mjukraderade i Supply Chain Management kan på detta sätt automatiskt raderas från Dataverse. I det här fallet finns logiken för att radera en rad i Dataverse som finns i utökad Supply Chain Management. |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
