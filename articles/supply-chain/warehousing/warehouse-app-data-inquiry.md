---
title: Fråga data med hjälp av omvägar Warehouse Management-mobilappen
description: Den här artikeln beskriver hur du konfigurerar menyalternativ för mobila enheter för dataförfrågan och använder dem som en del av omvägar.
author: perlynne
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cc013e962b4da803764f16e451b1d433666e75c2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336618"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Fråga data med hjälp av omvägar Warehouse Management-mobilappen

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Funktionsintroduktion

Genom att tillhandahålla streckkodsskanning ger Warehouse Management-mobilappen dig ett enkelt och korrekt sätt att fånga data som en del av dina lagerprocesser. Streckkoder skadas dock och blir olästa, eller så kanske den datainformation som krävs inte finns som en streckkod i affärsprocessflödena. I så fall kan manuell inmatning av data ta lång tid och kan till och med medföra att felaktiga data samlas in. Resultatet kan reduceras effektivitet och en lägre servicenivå.

Genom att använda en flexibel dataförfrågningsprocess kan medarbetarna enkelt söka efter den information som krävs som en del av det inbäddade mobilappen Warehouse Management och tillämpa filtreringsalternativ så att endast relevanta data visas. Det manuella urvalet blir därför snabbare och mer exakt.

I till exempel flödet för inleverans av inköpsorder måste ett inköpsordernummer matcha inkommande lager. I den här processen kan du enkelt konfigurera menyalternativ för att skapa en kortlistevy av de relevanta inköpsordernumren. På det här sättet kan du fortsätta det mottagande flödet genom att använda metoden peka för att välja. I den här artikeln finns exempelscenarier, men funktionerna kan också användas inom alla eller alla dina flöden för mobilappen Warehouse Management.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Aktivera flödesfunktionen för dataförfrågan och dess förutsättningar

Innan du kan använda funktionerna som beskrivs i den här artikeln måste du gå vidare med följande procedur för att aktivera funktionerna som behövs.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**. (Mer information om hur du använder arbetsytan **funktionshantering** finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Om du kör Supply Chain Management version 10.0.28 eller tidigare, aktiverar du funktionen som anges på följande sätt:

    - **Modul:** *Warehouse management*
    - **Funktionsnamn:** *Steginstruktioner för lagerapp*

    Den här funktionen är en förutsättning för funktionen *Dataförfrågansflöde i Warehouse Management-appen*. Från och med version 10.0.29 av Supply Chain Management är obligatorisk och kan inte inaktiveras. Mer information om funktionen *Steginstruktioner för lagerställeapp* finns i [Anpassa stegtitlar och instruktioner för Warehouse Management-mobilappen](mobile-app-titles-instructions.md).

1. Aktivera funktionen som visas på följande sätt:

    - **Modul:** *Warehouse management*
    - **Funktionsnamn:** *Omvägar för lagerstyrningsapp*

    Den här funktionen är en förutsättning för funktionen *Dataförfrågansflöde i Warehouse Management-appen*. Från och med version 10.0.29 av Supply Chain Management är denna aktiverad som standard. Mer information om funktionen för *Omvägar för appen Warehouse Management* i [Konfigurera omvägar för steg i menyalternativ för mobila enheter](warehouse-app-detours.md).

1. Om funktionen *Omvägar för appen Warehouse Management* inte redan var aktiverad, uppdatera fältnamnen i mobilappen Warehouse Management genom att gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Namnordning för lagerställeapp** och välja **Skapa standardinställningar**. Upprepa detta steg för varje juridisk person (företag) där du använder mobilappen Warehouse Management. - Mer information finns i [Konfigurera fält för mobilappen för distributionslagerhantering](configure-app-field-names-priorities-warehouse.md).
1. Aktivera funktionen som visas på följande sätt:

    - **Modul:** *Warehouse management*
    - **Funktionsnamn:** *Dataförfrågansflöde i Warehouse Management-appen*

    Den här funktionen är en som beskrivs i denna artikel.

## <a name="example-scenarios"></a>Exempelscenarier

I den här artikeln används exempelscenarier som visar hur du kan använda funktionen *Dataförfrågansflöde i Warehouse Management-appen* för att förbättra flödet för inköpsinleverans. I scenarierna används standardexempeldata, som omfattar ett flöde med namnet *mottagning av inköp*. Det här flödet startar genom att uppmana arbetare att identifiera ett inköpsordernummer som de ska ta emot mot. Om du vill göra det enklare att identifiera inköpsordern kan du förbättra den första sidan i flödet genom att lägga till följande nya frågealternativ som [omvägar](warehouse-app-detours.md):

- **Slå upp inköpsorder per leverantör** – Öppna en sida där arbetare uppmanas att ange ett leverantörsnamn eller en del av ett leverantörsnamn. Du kan använda jokertecken. Till exempel, om en arbetare förväntar sig en inkommande leverans idag från en leverantör som inkluderar *Tailspin* i namnet kan de ange **Tail\*** för att visa uppsättning kort för öppna inköpsorder som innehåller denna text. Varje kort har flera fält som ger information om varje inköpsorder. Förutom leverantörens namn kan du utforma korten så att de visar leverantörens kontonummer, leveransdatum och dokumentstatus.
- **Sök efter programföretag för idag** – Öppna en sida som inte uppmanar medarbetare att ange data utan istället visar förkonfigurerade filter (som dagens datum). På sidan visas sedan en kortuppsättning som matchar filtret. Arbetarna fortsätter med att välja ett kort för inköpsordern som de vill registrera lagerartiklar mot.
- **Slå upp inköpsorder per objekt** – Öppna en sida som uppmanar arbetare att skanna streckkoden för alla artiklar i det införda lagret. Flödet listar sedan alla öppna inköpsorder som innehåller rader för det artikelnummer som skannats. Om du vill täcka situationer där en streckkod inte kan läsas, kan du lägga till en till omställningssökning på den här sidan där medarbetarna kan söka efter artikelnummer inom en viss inköpsorder.

I alla fall identifierar arbetaren en inköpsorder genom att välja ett kort och sedan returneras till första sidan, som visar det valda inköpsordernumret. Arbetaren kan sedan fortsätta det inkommande artikelregistreringsflödet för lager.

## <a name="enable-sample-data"></a>Aktivera exempeldata

För att arbeta igenom exempelscenarier som beskrivs i denna artikel måste du vara i ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) finns installerat. Dessutom måste du välja den *USMF* juridiska personen (företaget) innan du börjar.

## <a name="configure-the-mobile-device-menu-items"></a>Konfigurera mobilenhetsmenyartiklar

Om du vill skapa alla nya frågealternativ som du måste lägga till på den första sidan i flödet måste du ställa in det som ett menyalternativ för den mobila enheten. Senare kommer du att göra frågealternativen tillgängliga som omvägar till flödet *Ta emot inköp*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Skapa menyalternativet "Slå upp inköpsorder per leverantör"

Skapa menyalternativet **Slå upp inköpsorder per leverantör** genom att följa stegen nedan.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till menyalternativ för mobil enhet.
1. Ställ in följande värden för det nya menyalternativet:

    - **Namn på menyalternativet:** *Slå upp inköpsorder per leverantör*
    - **Titel:** *Slå upp inköpsorder efter leverantör*
    - **Läge:** *Indirekt*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivitetskod:** *Dataförfrågan*
    - **Använd processguiden:** *Ja* (Detta värde väljs automatiskt.)
    - **Registernamn:** *PurchTable* (du vill söka efter inköpsordernummer från det här registret.)

1. I åtgärdsfönstret **Redigera fråga** för att definiera en fråga som är baserad på den valda bastabellen (i det här fallet inköpsordertabellen).
1. I frågeredigeraren, på fliken **Intervall** lägg till följande rader i rutnätet.

    | Register | Härlett register | Fält | Villkor |
    |---|---|---|---|
    | Inköpsorder | Inköpsorder | Status för inköpsorder | Öppen order |
    | Inköpsorder | Inköpsorder | Leveransdatum | (dayRange(-10,10)) |
    | Inköpsorder | Inköpsorder | Leverantörsnamn | |

1. Välj **OK**.

    I det här exemplet konfigureras det nya menyalternativet för att hitta öppna inköpsorder som förväntas komma in inom 10 dagar senare än 10 dagar.

    I frågan har kolumn **kriteriet** för *leverantörsnamn* lämnats tom. Därför kan medarbetarna ange det här värdet när de använder mobilappen Warehouse Management.

    Om du vill ange hur listan ska sorteras kan du ställa in sorteringen på fliken **Sortering**.

1. Förutom att definiera frågan måste du välja vilka fält som ska visas på korten på listsidan för förfrågan. Klicka på **Fältlista** i åtgärdsfönstret.
1. Ange följande värden på sidan **Fältlista**:

    - **Visningsfält 1:** *PurchId* (Det här fältet visas som rubrik för varje kort.)
    - **Visningsfält 2:** *PurchStatus*
    - **Visningsfält 3:** *PurchName*
    - **Visningsfält 4:** *OrderAccount*
    - **Visningsfält 5:** *DeliveryDate*
    - **Visningsfält 6:** *displayDocumentStatus()* (Detta värde är en visningsmetod, eftersom "()" i slutet indikerar.)

1. Klicka på **Spara** i åtgärdsfönstret. Stäng sidan.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Skapa menyalternativet "Slå upp inköpsorder idag"

Skapa menyalternativet **Slå upp inköpsorder för idag** genom att följa stegen nedan.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till menyalternativ för mobil enhet.
1. Ställ in följande värden för den nya artikeln:

    - **Namn på menyalternativet:** *Slå upp inköpsorder för idag*
    - **Titel:** *Slå upp inköpsorder för idag*
    - **Läge:** *Indirekt*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivitetskod:** *Dataförfrågan*
    - **Använd processguiden:** *Ja* (Detta värde väljs automatiskt.)
    - **Registernamn:** *PurchTable* (du vill söka efter inköpsordernummer från det här registret.)

1. I åtgärdsfönstret **Redigera fråga** för att definiera en fråga som är baserad på den valda bastabellen (i det här fallet inköpsordertabellen).
1. I frågeredigeraren, på fliken **Intervall** lägg till följande rader i rutnätet.

    | Register | Härlett register | Fält | Villkor |
    |---|---|---|---|
    | Inköpsorder | Inköpsorder | Status för inköpsorder | Öppen order |
    | Inköpsorder | Inköpsorder | Leveransdatum | (Day(0)) |

1. Välj **OK**.

    I det här exemplet konfigureras det nya menyalternativet för att hitta öppna inköpsorder som förväntas ankomma idag.

    Om du vill ange hur listan ska sorteras kan du ställa in sorteringen på fliken **Sortering**.

1. Förutom att definiera frågan måste du välja vilka fält som ska visas på korten på listsidan för förfrågan. Klicka på **Fältlista** i åtgärdsfönstret.
1. Ange följande värden på sidan **Fältlista**:

    - **Visningsfält 1:** *PurchName* (Det här fältet visas som rubrik för varje kort.)
    - **Visningsfält 2:** *PurchId*
    - **Visningsfält 3:** *PurchStatus*
    - **Displayfält 4:** *DlvMode*
    - **Displayfält 5:** *DlvTerm*
    - **Visningsfält 6:** *OrderAccount*
    - **Visningsfält 7:** *VendorName()* (Detta värde är en visningsmetod, eftersom "()" i slutet indikerar.)

1. Klicka på **Spara** i åtgärdsfönstret. Stäng sidan.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Skapa menyalternativet "Slå upp inköpsorder per artikel"

Skapa menyalternativet **Slå upp inköpsorder per artikel** genom att följa stegen nedan.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till menyalternativ för mobil enhet.
1. Ställ in följande värden för den nya artikeln:

    - **Namn på menyalternativet:** *Slå upp inköpsorder per artikel*
    - **Titel:** *Slå upp inköpsorder efter artikel*
    - **Läge:** *Indirekt*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivitetskod:** *Dataförfrågan*
    - **Använd processguiden:** *Ja* (Detta värde väljs automatiskt.)
    - **Registernamn:** *PurchLine* (du vill slå upp inköpsordernummer baserat på artikelnummer via raddata.)

1. I åtgärdsfönstret väljer du **Redigera fråga** för att definiera en fråga som är baserad på den valda bastabellen (i det här fallet, tabellen inköpsorderrader, men du kan använda alla värden som är relaterade till rubriken genom att ansluta till *PurchTable*).
1. I frågeredigeraren, på fliken **Intervall** lägg till följande rader i rutnätet.

    | Register | Härlett register | Fält | Villkor |
    |---|---|---|---|
    | Inköpsorderrader | Inköpsorderrader | Radstatus | Öppen order |
    | Inköpsorderrader | Inköpsorderrader | Leveransdatum | (dayRange(-10,10)) |
    | Inköpsorderrader | Inköpsorderrader | Artikelnummer | |

1. Välj **OK**.

    I det här exemplet konfigureras det nya menyalternativet för att hitta öppna inköpsorderrader som förväntas komma in inom 10 dagar senare än 10 dagar.

    I frågan har kolumn **kriteriet** för *artikelnummer* lämnats tom. Därför kan medarbetarna ange det här värdet när de använder mobilappen Warehouse Management.

    Om du vill ange hur listan ska sorteras kan du ställa in sorteringen på fliken **Sortering**.

1. Förutom att definiera frågan måste du välja vilka fält som ska visas på korten på listsidan för förfrågan. Klicka på **Fältlista** i åtgärdsfönstret.
1. Ange följande värden på sidan **Fältlista**:

    - **Visningsfält 1:** *PurchId* (Det här fältvärdet används som rubrik för varje kort.)
    - **Visningsfält 2:** *VendAccount*
    - **Visningsfält 3:** *PurchQty*
    - **Visningsfält 4:** *PurchUnit*
    - **Visningsfält 5:** *PurchStatus*

1. Klicka på **Spara** i åtgärdsfönstret. Stäng sidan.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Lägg till ny mobilenhet menyalternativ för mobila enheter

Dina tre nya menyalternativ för mobila enheter är nu redo att läggas till i menyn för den mobila enheten. Uppgiften måste slutföras innan menyalternativen kan användas som en del i en omvägsprocess. I det här exemplet skapar du en ny undermeny och lägger till de nya menyalternativen i den.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden i rubriken för den nya posten:

    - **Namn:** *Fråga*
    - **Beskrivning:** *Fråga*

1. I listan **Tillgängliga menyer och menyartiklar** välj det första av menyalternativen för den mobila enheten som du just skapade. Välj sedan högerpilen för att flytta objektet till listan **Menystruktur**.
1. Upprepa föregående steg för de övriga två nya menyalternativen.
1. Välj menyn i listrutan till vänster **Huvud**.
1. I listan **Tillgängliga menyer och menyalternativ**, bläddra ned till avsnittet **Menyer** och välj menyn **Fråga**. Välj sedan högerpilen för att flytta objektet till listan **Menystruktur**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Konfigurera omvägar i stegen för din mobila enhet

För att slutföra installationen måste du nu använda omvägskonfigurationen på sidan **Steg på mobil enhet** för att lägga till de tre nya menyalternativen för mobila enheter till det befintliga inköpsorder identifieringssteget i flödet *Ta emot inköp*.

1. Gå till **Lagerstyrning \> Inställningar > Mobil enhet \> Steg för mobil enhet**.
1. I fältet **Filter** ange *PONum*. Välj sedan *Steg-ID: "PONum"* i listrutan.
1. När den post som hittas är markerad i rutnätet väljer du **Lägg till steg-konfiguration** i åtgärdsfönstret. I rullgardinsmenyn som visas, ställ in fältet **Menyalternativ** till *Ta emot inköp*. Välj **OK** för att stänga dialogrutan.
1. På detaljsidan för den nya stegkonfigurationen (**Inleverans av inköp : PONum**), på snabbfliken **Tillgängliga omvägar (menyalternativ)**, välj **Lägg till** i verktygsfältet.
1. I dialogrutan **Lägg till omväg**, hitta och välj menyalternativet **Slå upp inköpsorder efter leverantör** som du tidigare har skapat.
1. Välj **OK** för att stänga dialogrutan och lägga till det valda menyalternativet i listan över omvägar.
1. Välj den nya omvägen och välj sedan **Välj fält att skicka** på verktygsfältet.
1. I dialogrutan **Välj fält att skicka**, lägg inte till något i avsnittet **Skicka från köp ta emot** eftersom du inte vill skicka några värden till menyalternativet omväg. Men i avsnittet **Ta tillbaka från sökning av inköpsorder efter leverantörer** ställ in följande värde för den tomma raden som redan har lagts till där:

    - **Kopiera från Slå upp inköpsorder efter leverantör:** *Inköpsorder*
    - **Klistra in i Inköpsorder:** *Inköpsorder*

1. Välj **OK** för att stänga dialogrutan.
1. Upprepa steg 4 till och med 9 för de övriga två nya menyalternativen (**Slå upp inköpsorder för idag** och **Slå upp inköpsorder efter artikel**). Vad gäller menyalternativet **Slå upp inköpsorder efter leverantör** vill du inte skicka någon data till dessa omvägar, men du vill returnera ett inköpsordernummer.
1. Stäng sidan.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Testa ett inköpsinleveransflöde som har en dataförfrågan som en del av en omleverans

Följ de här stegen när du vill testa de nya inställningarna för mobilapp.

1. Skapa flera inköpsorder som har rader för lagerställe 51.
1. Gå till en mobil enhet eller emulator som kör mobilappen för distributionslagerhantering och logga in i distributionslager 51 med hjälp av *51* som användar-ID och *1* som lösenord.
1. Välj Inkommande och sedan **Inkommande** och sedan **Inkommande inköpsorder** på mobilmenyn.

    Följande sida, som innehåller de tre nya menyalternativen, visas.

    ![Inköp som tas emot med hjälp av inköpsordernummer.](media/wma-purchase-receive-po-num-with-detours.png "Inköp som tas emot med hjälp av inköpsordernummer")

1. Testa olika möjligheter och observera att du kan skicka tillbaka ett inköpsordernummer genom att välja ett av korten i listan.

    ![Inköpsmottagning med inköpsordersökning efter leverantör, exempel 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Inköpsmottagning med inköpsordersökning efter leverantör, exempel 1")

    ![Inköpsmottagning med inköpsordersökning efter leverantör, exempel 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Inköpsmottagning med inköpsordersökning efter leverantör, exempel 2")

> [!TIP]
> Istället för att köra mottagningsflödet genom att göra en uppslagning från menyalternativet **Ta emot inköp** du kan utgå från ett förfrågningsflöde (**Huvud \> Fråga \> Slå upp inköpsorder efter leverantör**) och anropa en omväg för att köra önskat flöde genom att välja ett av korten i listan. Om du vill använda det här sättet kan du definiera en omväg på sidan **Steg på mobil enhet** för de steg som har ett värde **Steg-ID** för *GenericDataInquiryList*. Eftersom detta flöde är ett omvägsflöde, kan du inte anropa fler omvägar från det. Därför, när du kommer till inmatningsskärmen för artikelnummer, till exempel, kommer uppslagningen inte att vara tillgänglig på den, eftersom systemet för närvarande bara stöder en nivå av omvägar.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
