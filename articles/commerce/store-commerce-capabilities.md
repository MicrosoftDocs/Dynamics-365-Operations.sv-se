---
title: Funktioner i appen Store Commerce
description: I den här artikeln beskrivs funktionerna som är tillgängliga i appen Store Commerce för Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: d713cc0e9537ae20ffddee6e77779a16e74bd779
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725644"
---
# <a name="store-commerce-app-capabilities"></a>Funktioner i appen Store Commerce

[!include [banner](includes/banner.md)]

Appen Store Commerce är ett modernt kassaprogram för Microsoft Dynamics 365 Commerce. Det gör det möjligt för företag att bearbeta transaktioner i butiken och hantera backoffice-åtgärder som bearbetning av lager och order. Med programmet kan företag också hantera kundrelationer med lojalitet och kundhantering. 

Programmet Store Commerce Scale Unit (CSU) är en komplett lösning i flera kanaler. En kund kan till exempel köpa en produkt online och hämta den i en närliggande butik och på så sätt fortsätta handla i olika kanaler utan att förlora data. 

Denna artikel innehåller en översikt över funktioner i appen Store Commerce.

## <a name="platform"></a>Plattform

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Flera kanaler | Dynamics 365 Commerce ger en omfattande lösning i flera kanaler där backoffice, butik, kundtjänst och digitala upplevelser samordnas. | [Översikt](index.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Fjärradministrerad handel | Commerce Scale Unit är värd för konsollös Commerce-motor. Den konsollösa Commerce-motorn fungerar som en central plats för all affärslogik i handel och utgör en komplett lösning i flera kanaler. | <p>[Arkitekturöversikt](commerce-architecture.md)</p><p>[Fjärradministrerad arkitektur](dev-itpro/retail-server-architecture.md)</p> | [Tekniksnack](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce headquarters | Commerce headquarters innehåller backoffice-funktioner som gör det möjligt att konfigurera produkter, medarbetare, affärsprocesser, priser och andra funktioner som krävs för verksamheten. | [Arkitekturöversikt](commerce-architecture.md) | |
| Kassa (POS) | Programmet Store Commerce är POS-erfarenhet för Dynamics 365 Commerce. Den levererar funktionsriktiga och omfattande kassafunktioner som hjälper försäljare, kassörer och chefer att tillhandahålla högsta kundservice. Dessutom ger programmet flera distributionsalternativ till återförsäljare, hjälper till att förbättra prestandan och erbjuder förbättrad livscykelhantering för program (ALM). | [Store Commerce-app](dev-itpro/store-commerce.md) | <p>[Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Video](https://youtu.be/7B332XH_zfs)</p><p>[Migrering från MPOS till Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Molndistribution | Det går att använda flera instanser av Commerce Scale Units för belastningsfördelning och avstånd. | [Molndistribution](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| Lokal distribution | Med en lokal datadistribution kan Commerce-kunder få större ägarskap och hantering av en Dynamics 365-miljö. | [Lokal distribution](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Enhetshantering

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Flera formulärfaktorer |  Store Commerce-appen stöds av flera formulärfaktorer, till exempel datorer, surfplattor och mobila enheter. Det responsiva användargränssnittet (UI) gör det möjligt att ändra storlek på och justera layouten automatiskt efter skärmstorlek. | [Visuella konfigurationer](pos-screen-layouts.md) | |
| Flera plattformar | Store Commerce-appen stöds på webben, Windows, iOS och Android-plattformar. | [Plattformar](dev-itpro/hybridapp.md) | |
| Profilering | Med hjälp av skärmdesignern kan du anpassa skärmlayouterna så att de uppfyller företagets krav. Dessutom kan teman, layouter, färger och bilder skapas utifrån medarbetarroller och sedan delas mellan användarna för konsekventa och användarvänliga funktioner. | [Visuella konfigurationer](pos-screen-layouts.md) | [Video](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topologi | Olika topologier i butikerna stöds, baserat på nätverkets tillgänglighet. | <p>[Topologi](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Informationsgrafik](dev-itpro/retail-in-store-topology.md)</p> | |
| Hantering av flera enheter | Det är enkelt att hantera flera enheter mellan butiker från Commerce headquarters. | [Aktivering](set-up-activation-accounts-validate-devices-hq.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Personalhantering

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Logga in | Varje butiksmedarbetare kan ha en dedikerad inloggning. Inloggningstyperna inkluderar användarnamn, streckkod, kortläsare (MSR), biometri och Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Förlängd inloggning](extended-logon.md)</p> | |
| Behörighet | Olika nivåer av behörigheter stöds för medarbetare, till exempel behörighet att skapa order och behörighet att redigera order. | [Behörighet](tasks/create-pos-permission-groups.md) | |
| Tids- och närvarohantering | Närvaro kan hanteras med funktionen Tidsstämplar. Närvarodata kan bearbetas i lön med hjälp av Dynamics 365 Human Resources programmet. | [Tidshantering](retail-time-attendance.md) | |
| Försäljningsprovision | Försäljning kan spåras av säljare för att beräkna provisioner eller andra incitament. | [Provision](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Kringprodukter

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Sortimenthantering | Marknadsföringschefer kan använda olika produkter så att de blir tillgängliga för försäljning i en specifik kanal och under en viss period. | [Sortiment](assortments.md) | |
| Kataloger | Marknadsföringschefer kan hantera kataloger och identifiera produkter som du vill erbjuda med katalogspecifika priser. | [Kataloger](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Produkt- och kategorihantering | I Commerce headquarters kan marknadsföringschefer skapa produkter som har varianter, attribut, en måttenhet och så vidare. De kan också definiera en kategorihierarki för att organisera produkter. | [Produkt](retail-hierarchies.md) | |
| Buntar | Marknadsföringschefer kan gruppera produkter så att de säljs som en bunt eller ett kit. | [Paket](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Infokoder | Använd informationskoder om du vill uppmana kassören att ange information under olika åtgärder i POS, till exempel artikelförsäljningar, artikelreturer eller val av kunder. | [Infokoder](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Länkade artiklar | Använd länkade artiklar för att skapa produkter uppåt när en artikel läggs till i en transaktion. | [Länkade artiklar](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garantier | Utökade garantier kan säljas tillsammans med produkter. | [Garanti](extended-warranty.md) | |
| Etikettutskrift | Etiketter kan genereras som innehåller produktinformation som batchnummer, serienummer och utgångsdatum. | [Etikettutskrift](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Assisterad försäljning

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Produktsökning | Bläddra i produkter efter kategori. | [Produkthierarki](retail-hierarchies.md) | |
| Produktsökning | Sök produkter efter namn och begränsa sökningar med hjälp av produktattribut som märke, pris och material. Den här kapaciteten tillhandahålls av Azure Cognitive Search. | [Molnbaserade sökning](cloud-powered-search-overview.md) | |
| Sidan Produktinformation | Sidor för omfattande produkter kan innehålla bilder, en beskrivning, produktattribut och rekommenderade produkter. Rekommendationer drivs av tjänsten Rekommendationer. | | |
| Jämför produkter | Jämför flera produkter, och hjälpa kunder att välja en och lägga till dem i en transaktion. | | |
| Ändlös gång | Du kan enkelt söka efter lager i andra butiker och skapa order. | [Lagersökning](pos-inventory-lookup-operation.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Rekommendationer | Merförsäljning och korsförsäljning av produkter med hjälp av tjänsten Rekommendationer. Denna tjänst använder patenterad teknik för att föreslå rekommendationer, baserat på inköpstrender och egenskaper som nya, liknande utseende och bästsäljande. Dessa rekommendationer finns på produktinformationssidorna, sidan **Kundinformation** och sidan **Transaktioner**. | [Rekommendationer](product-recommendations.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Kundrelation

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Kundhantering | Skapa, redigera och hantera kundkonton. Kundkonton kan hanteras i asynkront läge för att undvika bearbetning i realtid. | [Hantering](customer-mgmt-stores.md) | |
| Kundattribut | Med ramverket för kundattribut kan ytterligare kundrelaterade data samlas in baserat på affärsbehov. | [Attribut](dev-itpro/customer-attributes.md) | |
| Sidan för kundinformation | En detaljsida för en detaljerad kund innehåller en vy i flera kanaler av kundens interaktioner mellan alla kanaler. Dessa interaktioner omfattar inköp, önskelistor och förmånspoäng. | | |
| Molndriven kundsökning | Sök kunder efter namn, telefonnummer, e-postadress, förmånskort, adress och så vidare. | [Molnbaserade sökning](pos-search-improvements.md#customer-search) | |
| Bonusar och belöningar | Kunder kan delta i bonusprogram och få och lösa in förmånspoäng i olika kanaler. | [Förmåner](set-up-customer-loyalty-program.md) | |
| Kundhantering | Hantera nyckelkunder med hjälp av en klientbok och spåra aktiviteter och noteringar på kundprofilen. Med Dynamics 365 Customer Insights-integration kan vi butiksanställda få stackikoner för nästa bästa åtgärd för varje kund. | [Kundhantering](clienteling-overview.md#activities-and-notes) | |

## <a name="pricing-and-discounts"></a>Prissättning och rabatter

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Handelsavtal | Prissättningschefer kan använda handelsavtal för att definiera specialpriser, baserat på långsiktiga erbjudanden för vissa kunder. | [Priser](price-management.md)| [Video](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Försäljningsavtal | Prissättningschefer kan använda försäljningsavtal när de definierar kontraktsbaserade priser i B2B-handelsscenarier (business-to-business). | [Priser](price-management.md) | |
| Prisjusteringar | Prissättningschefer kan använda möjligheten för prisjusteringar för att skapa, spåra och hantera prissänkning för sina produkter på längre sikt. | [Prisjusteringar](price-adjustments-discounts.md) | |
| Rabatter | Prissättningschefer kan ställa in flera typer av rabatter för att köra olika erbjudanden. Dessa rabatter innehåller enkla rabatter, kvantitetsrabatter, tröskelrabatter, mixa och matcha-rabatter, betalningsmedelsbaserade rabatter och manuella rabatter. | [Rabatter](retail-discounts-overview.md) | |
| Kuponger | Prissättningschefer kan ställa in kupongkoder eller streckkoder, koppla dem till rabatter och distribuera dem till kunder. Säljarna kan lägga till kuponger i försäljningstransaktioner eller ta bort dem. | [Kuponger](coupons.md) | |
| Prisgrupper | Prissättningschefer kan använda prisgruppsfunktionerna när de vill definiera kontextuella priser, baserat på kanaler, kataloger, anknytningar eller förmånsprogram. | [Priser](price-management.md) | |
| Tillgängliga erbjudanden | Säljare kan enkelt söka efter tillgängliga erbjudanden för produkter i butiken, produkter som har lagts till i en transaktion och så vidare. | [Prissättningsfunktioner](pos-pricing-functions.md) | |
| Priskontroller | Säljare kan snabbt kontrollera aktiva försäljningspriser för produkter i butiken. | [Prissättningsfunktioner](pos-pricing-functions.md) | |
| Prisåsidosättningar | Säljare som har den behörighet som krävs kan åsidosätta systemkonfigurerade eller beräknade priser. | [Prissättningsfunktioner](pos-pricing-functions.md) | |
| Manuella rabatter | Säljare som har den behörighet som krävs kan tillämpa manuella rabatter på försäljningstransaktioner eller försäljningsrader. | [Prissättningsfunktioner](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Elektroniska betalningar

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Kredit och debet | Store Commerce-appen har stöd för stora kreditkorts- och betalkortsbetalningar via Adyen betalningsgateway och orderuppfyllelse via PayPal. Payments SDK tillåter externa gateway-anslutningar som stöds av ISV-integrationer (oberoende programvaruleverantör). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Betalningar](payment-methods.md)</p> | <p>[Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Stöd för digital plånbok | Store Commerce-appen har stöd för betalningar med digitala betalningsmetoder som inte använder BIN-intervall (bankidentifieringnummer) som traditionella kredit- och betalkort gör. Betalningsmetoder kan mappas till digitala betalningar som Adyen. | [Plånbok](wallets.md) | |
| Stöd för presentkort | Bank-ID-nummer Dynamics 365 presentkort, Stored Value Solutions (SVS) och Givex presentkort. Presentkort kan köpas in och lösas in i en order. | [Presentkort](dev-itpro/gift-card.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Bedrägeriskydd | Dynamics 365 Fraud Protection hjälper dig att förhindra aktiviteter som inte är olästa och identifiera platser där dessa inte är olästa. | [Bedrägeriskydd](dev-itpro/dfp.md) | [Video](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Skatter och avgifter

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Skatter | Store Commerce-appen stöder många typer av indirekta skatter, till exempel moms/mervärdesskatt, skatt på varor och tjänster (GST), enhetsbaserade avgifter och källskatt. | [Skatter](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Avgifter | Tillägg kan konfigureras på radnivå, på huvudnivå, som automatiska avgifter, per kanal och så vidare. | [Avgifter](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Orderbearbetning och uppfyllelse

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Ordergenerering | En order kan skapas för försändelse eller för upphämtning i en närliggande butik. Tidsautomat kan anges för upphämtning. | [Översikt](customer-orders-overview.md) | |
| Orderändring | En order kan ändras, returneras, annulleras och så vidare. | <p>[Avbryt](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Returer](pos-returns.md)</p> | |
| Sök efter order | Sök efter och filtrera order med orderspecifik information. | [Sök efter order](enhancedorderrecall.md) | |
| Orderattribut | Med ramverket för orderattribut kan ytterligare orderrelaterad information samlas in baserat på affärsbehov. | [Attribut](dev-itpro/order-attributes.md) | |
| Direktleverans | Artiklar kan markeras för direktleverans av en leverantör till en kundadress. Direktleverans kallas också för direktleverans. | [Direktleverans](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Offert | Butiksanställda kan skapa offerter för kunder och kan ange ett särskilt pris, manuella rabatter och ett giltighetsdatum för offerten. | [Offert](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Uppfyllelse | Butikerna kan plocka, packa och leverera order. En följesedel kan läggas till i de paket som är klara för leverans. | [Uppfyllelse](order-fulfillment-overview.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021) |
| Fördelad orderhantering | Store Commerce-appen stöder optimering av orderuppfyllelse där affärsstrategier kan konfigureras utifrån företagets karaktär, kundtyp, ordertyp och leveransmetod. | [DOM](dom.md) | |

## <a name="inventory-management"></a>Lagerhantering

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Centraliserad distribution | Göra det enklare att distribuera tillgängligt lager från ett distributionscenter till flera butiker eller lagerställen. | [Centraliserad distribution](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Direktleverans | Effektivisera distributionen av lager på inkommande inköpsorder till flera butiker eller lager. | [Direktleverans](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Inkommande lager | Ta emot lager från en leverantör via en inköpsorder eller från ett annat lagerställe via en överföringsorder. Skapa en inkommande inköpsorder eller överföringsorderförfrågan. | [Inkommande](pos-inbound-inventory-operation.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Utgående lager | Leverera lager till ett annat lagerställe via en överföringsorder och skapa en utgående överföringsorderbegäran. | [Utgående](pos-outbound-inventory-operation.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Lagersökning | Kontrollera lagerbehållning för produkter mellan butiker och lagerställen och kontrollera tillgängligt disponibelt att lova (ATP) vid framtida datum. | [Lagersökning](pos-inventory-lookup-operation.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Lagerjustering | Justera lagret till eller från ett butikslagerställe för att uppfylla särskilda affärsbehov utan att använda en försäljning, inleverans eller omräkning. | [Lagerjustering](work-with-store-inventory.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Lagerinventeringar | Räkna fysiskt lager och justera systemets bokföringslager så att det matchar det. | [Inventering](work-with-store-inventory.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Lagerförflyttning | Flytta lager mellan platser i en butik. | [Rörelse](work-with-store-inventory.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |

## <a name="financials"></a>Ekonomi

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Kontanthantering | Store Commerce-appen har stöd för hantering av kontanter och andra angivna funktioner i butiken. Avstämning av skift i butiken kan dessutom aktiveras för avancerad kassahantering. | [Kontanter](cash-mgmt.md) | |
| Bokslut och avstämning | Kassa- och transaktionstransaktioner för en butik registreras i Commerce headquarters genom utdragsbokföringsprocessen. | [Uppgifter](retail-statements.md) | |
| Intäkts- och utgiftstransaktioner | Bearbeta ringa kontanttransaktioner i butiken och registrera inkomster som inte kommer på traditionellt sätt, till exempel förlorade och hittade pengar, andelen av intäkterna från ett kafé på ditt hotell och städning. | [Uppgifter](retail-statements.md) | |
| Fakturabetalningar | Fånga in betalningar mot fakturor. | [Faktura](payinvoice.md) | |

## <a name="employee-productivity"></a>Medarbetarproduktivitet

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Uppgiftshantering | Skapa uppgiftslistor och uppgifter och tilldela dem till butiker och medarbetare. Spåra status för uppgifter mellan butiker. Sömlös integration med Microsoft Teams tillhandahålls. | <p>[Uppgiftshantering](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Video](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Maskinvara och kringutrustning

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Ansluta kringutrustning | Ansluta till kringutrustning som skrivare, kassaapparater, skanner och betalningsenheter till en kassaterminal. | [Kringutrustning](retail-peripherals-overview.md) ||
| Dela kringutrustning | Kvittoskrivare, kassalåda och betalningsenheter kan delas mellan många terminaler genom att koppla dem till en delad maskinvara. | <p>[Maskinvarustation](retail-peripherals-overview.md) ||
| Kassa och kringutrustningssimulator | Kringutrustningssimulatorn underlättar när du testar scenarier där vanligtvis fysisk kassakringutrustning behövs. Den innehåller även kassasimulatorn som kan användas för att testa om den fysiska kringutrustningen är kompatibel utan att behöva distribuera kassaklienten. | [Simulator](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Inleveranser

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Skriv ut kvitton | Kvitton av olika typer, till exempel försäljningskvitton, kreditkortskvitton, presentkort och fakturor, kan skrivas ut som standard eller efter kassörens bekräftelse i kassan. De kan också skrivas ut på ny tid från journalen. | [Skriver ut](receipt-templates-printing.md) | |
| E-postkvitton | Kvitton kan skickas via e-post från kassan när utcheckningen är klar. | [E-postmeddelande](email-receipts.md) | |
| Designa kvitton | Butikskvitton kan anpassas så att de visar de data och layouter som är lämpliga för återförsäljaren och transaktionstypen. Kvitton kan också utökas så att de visar anpassade data som återförsäljaren behöver. | [Design](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Offline-support

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Sömlös offline | Sömlös offline gör att du kan fortsätta att göra göra även om internetanslutningarna är begränsade eller inte är tillgängliga. Med data exkludering kan du minska datastorleken för offlinedatabaserna och maximera prestanda. | [Offline](pos-operations.md) | |
| Prestandabaserad växling | Växla till offline när prestandan är tillgänglig när den upptäcks. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Video](https://youtu.be/sQU-2pgHToI) |
| Offline-instrumentpanelen | Instrumentpanelen **Offline-status** visar offlinestatus, fel och detaljer för data för varje enhet. Därför är det enkelt att hantera status för många enheter. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Video](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Utbyggbarhet

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Commerce headquarters | Du kan anpassa Commerce headquarters-lösningar genom att lägga till eller ändra affärsprocesser. Commerce headquarters stöder metadata och en kodbaserad anknytningsmodell för att lägga till anpassade funktioner. Den kan enkelt integreras i externa lösningar. | [Översikt](dev-itpro/extend-customer-cdx-package.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Fjärradministrerad handel | Ramverket utbyggbar flerkanals-API kan användas för att anpassa och lägga till affärslogik. API:er som har anförfrågningshanterare och tilläggsmönster för förutlösare och efterutlösare. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Commerce SDK | Commerce SDK innehåller den kod, kodexempel, mallar och verktyg som krävs för att utöka eller anpassa Dynamics 365 Commerce-funktioner. SDK publiceras i olika databaser (hantlar) i GitHub, beroende på tilläggskomponenterna. | [SDK](dev-itpro/retail-sdk/sdk-github.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Kassa | Store Commerce-appen kan utökas oberoende av varandra genom att använda anknytningsfunktionen för kassa i Commerce SDK. Ramverket stöder anpassning av användarupplevelsen (UX), arbetsflöden och affärslogik. | [POS](dev-itpro/pos-extension/pos-extension-overview.md) | [Tekniksnack](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Rapportering

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Försäljningsrapporter | Försäljningsrapporter per personal, kassa, betalningstyp, returer, produkter och så vidare, är tillgängliga för butikschefer. Chefer kan visa de här rapporterna och använda dem för att fördela provision och identifiera produkttrender. | | |

## <a name="diagnostics"></a>Diagnostik

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Operational Insights | Tillförlitlighet och prestandamått som används för butiksbaserade tjänster är tillgängliga i kundens Application Insights abonnemang. Det finns avancerade funktioner för notifiering och övervakning. | | |
| Hälsokontroll | Tillgängligheten till kringutrustning som är ansluten till en kassa kan verifieras genom att du kör hälsokontrollåtgärden. Enskilda kringutrustningproblem kan sedan fastställas och verifieras. | [Hälsokontroll](pos-healthcheck.md) | [Video](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalisering

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Flermarknadssupport | Marknadsspecifika funktioner som skatteintegrering, GST, avancerad fakturering och förskottsbetalningar stöds från början. Den här kapaciteten omfattar flera marknader i Europa, Nordamerika, Ryssland, Asien, Saudiarabien och så vidare. | [Globalisering](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Regelefterlevnad

| Funktion | Beskrivning | Dokumentation | Tilläggsinnehåll |
|---|---|---|---|
| Microsoft-standarder | Store Commerce-appen uppfyller Microsoft-standarder för säkerhet, sekretess, åtkomlighet, allmän dataskyddsförordning (GDPR), Europeiska unionen (EU) datagräns, osv. | | |

