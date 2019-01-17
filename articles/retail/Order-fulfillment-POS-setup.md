---
title: "Ställ in orderuppfyllande för butiker"
description: "Det här ämnet ger en översikt över hur du ställer in orderuppfyllelse i butik."
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: c8c2e56a1f65d28991dca3e1da4159efe81f2bf3
ms.contentlocale: sv-se
ms.lasthandoff: 01/04/2019

---


# <a name="set-up-order-fulfillment-for-stores"></a>Ställ in orderuppfyllande för butiker

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Översikt

Många återförsäljare vill optimera orderuppfyllelse genom att låta butiker fylla i order. Orderuppfyllelse på butiksnivå hjälper dig att förenkla scenarier med överlager för en specifik butik eller kan behövas från en logistisk synvinkel i de fall som en butik har extra kapacitet eller ligger inom närmare avstånd för leverans till kunden. För att tillgodose detta behov är ett enhetligt utförande av orderuppfyllelse tillgängligt i kassan.

Order för uppfyllelse i en specifik butik har butikens lagerstället tilldelat på rubriken eller raderna på ordern.

Utförande av orderuppfyllelse i butiken ger en enskild arbetsyta i kassan som kan användas för att bearbeta order. Detta inkluderar allt från att acceptera ordern, till att markera den som levererad eller påbörja upphämtning i butik.

## <a name="set-up-the-order-fulfillment-operation"></a>Ställa in utförandet av orderuppfyllelse.

Orderuppfyllande [Operations-ID 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations), kan användas för åtkomst till butikens orderuppfyllelsearbete i kassan.

Följ instruktionerna i [lägga till åtgärden i en knappsats](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) för att ange vilken parameter som ska användas vid åberopande av orderuppfyllelse i kassan. Som standard när du har angett åtgärden för orderuppfyllelse väljs **alla order**. När de konfigureras med den här parametern kommer åtgärden att lista alla orderrader för uppfyllelse i den aktuella butiken. **order ska levereras** finns också tillgänglig som kan tilldelas till en knapp och användas när användaren bara vill visa order som levereras från lager. Slutligen finns det **order för upphämtning**. När detta anropas i kassan listar detta bara order som ska hämtas i butiken. De olika parametrarna kan tilldelas till olika knappar för att ge användaren en mängd olika sätt att visa orderuppfyllelse.

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Ge användare åtkomst till orderuppfyllelse i kassan.

Utförande av orderuppfyllelsen har inte sin egen inte har sin egen färdiga behörighet, men användare kommer i framtiden att kunna använda behörigheten **Tillåt hämta order** för att starta en åtgärd från kassan.

På butiksnivå finns en konfigurationsinställning tillgänglig för att bestämma om en orderrad måste godkännas manuellt inifrån kassan eller inte. Om det alternativet inte anges godtas orderrader som standard. Om det alternativet är aktiverat kommer användarna i kassan behöva ha behörigheten **Tillåt acceptera order** för att ta emot order inifrån kassan.

### <a name="enable-manual-order-acceptance"></a>Aktivera manuellt godkännande av ordern

Som standard är orderrader som tilldelats en butik markerade som **accepterade**. Detta innebär att det antas att de uppfylls från den tilldelade butiken och omfattas inte av ytterligare tilldelning. I vissa fall behöver återförsäljare acceptera order manuellt innan de kan uppfyllas. Om till exempel en butik har brist på personal och inte kan uppfylla order kommer butikschefen endast att acceptera så många order för bearbetning som enligt deras uppfattning kan behandlas på ett tillfredsställande sätt en viss dag. Till dess att en order har accepteras kan den omtilldelas av backoffice till en annan butik. På så sätt ger dessutom ordergodkännande ett sätt att ange att en order redan har godkänts av en butik och kommer att uppfyllas.

Orderrader för butiksupphämtning markeras som **pågående** och är inte föremål för godkännande.

Om du vill aktivera manuellt godkännande för orderrader, gå till **Butik** \> **Kanaler** \> **Butiker** \> **Alla butiker**. Välj butiken och klicka i butiks-ID för att visa information om butiken. Klicka på **Redigera**. På snabbfliken **Allmän**, sök efter underrubriken **orderuppfyllande** och ändra **Manuellt godkännande** från **Nej** till **Ja**.

### <a name="enable-reject-order-line-capability"></a>Aktivera funktionen för avvisa orderrad

Orderrader kan också avvisas från kassan. Om du avvisar en orderrad anger du att den inte ska uppfyllas i den här butiken och skickar tillbaka orderraden för tilldelning till en annan butik eller lagerställe. Behörighet att avvisa orderrad tilldelas via behörigheten **Tillåt avvisa order** i den kassabehörighetsgrupp som associeras med medarbetaren. När du avvisar en rad kan återförsäljarna bestämma att deras anställda motiverar avvisandet. Du kan göra detta med hjälp av infokoder av typen **Infokod för aktivitet**, **orderuppfyllande** och tilldela infokoden till **avvisa orderraden** i funktionsprofilen som är associerad med kanalen.

> [!NOTE]
> Endast infokoderna för typen **Infokod för aktivitet**, **orderuppfyllande** kan tilldelas åtgärden **”avvisa orderrad**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synkronisera ändringar i kanaldatabasen

När åtgärden har tilldelats en knappsats och de rätta behörigheterna har tilldelats och kanalen har konfigurerats måste ändringarna synkroniseras till kanaldatabasen. För att göra detta, gå till **Butik** \> **Butikens IT** \> **Distributionsschema**. Välj schemalägg ”1090 register” för att synkronisera ändringar av knappsatsen och klicka sedan på **kör nu**. Synkronisera sedan behörighetsändringar genom att markera ”1060 personal” och sedan välja **kör nu**. Synkronisera sedan kanaländringar genom att markera ”1070 kanalkonfiguration” och sedan välja **kör nu**. Synkronisera slutligen den nyskapade infokoden för avvisningsorsak genom att välja ”1110 global konfiguration” och klicka på **kör nu**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Använd orderuppfyllande vid kassan

Öppna kassan och markera utförandet av orderuppfyllelse. Beroende på hur den konfigureras visas alla rader, orderrader för upphämtning, eller orderraderna som ska levereras.

### <a name="order-fulfillment-view"></a>Orderuppfyllelsevy

Orderuppfyllelsevyn listar orderrader för uppfyllelse i butiken och innehåller följande kolumner:

- Ordernummer
- Produktnummer
- beskrivning
- Beställd kvantitet
- Begärt leveransdatum
- Kundnamn
- Uppfyllelsestatus

Ytterligare information för en viss orderrad kan visas genom att välja orderraden och sedan öppna den utfällda menyn precis under den inloggade användar-/skiftinformation som visas i kassarubriken. Den här menyn innehåller 2 flikar: en för detaljer och en annan för orderdetaljer. Fliken för orderdetaljer inkluderar följande information:

- Beställd kvantitet
- Återstående kvantitet som ska levereras/hämtas
- Hämtad kvantitet
- Packad kvantitet
- Fakturerad kvantitet (redan hämtad eller levererad)
- Leveranssätt
- Leveransadress

Den utfällda informationsmenyn har även en flik som ger mer information på ordernivå inklusive:

- Kundnamn
- Kund-ID
- Ordernummer
- Ordersumma
- Ordersaldo

Längst ned i orderuppfyllandevyn är ett åtgärdsfönster. Denna innehåller alla de åtgärder som kan vidtas mot en orderrad. Om en åtgärd inte är tillgänglig baserat på orderns status blir åtgärden inte tillgänglig.

Som standard har ordern statusen **accepterad**. Orderstatus kan visas som en kolumn i listan över orderrader. Om **Manuellt godkännande** konfigureras på kanalnivån visas alla rader som ska levereras som **väntande** och måste godkännas innan de kan uppfyllas. Order för butiksupphämtning är som standard **väntande** och behöver inte godkännas.

### <a name="order-fulfillment-line-actions"></a>Åtgärder för orderuppfyllelserad

- **Redigera** - Om en orderstatus väntar den redigeras vid kassan. Order som redan har delvis plockats, packats eller fakturerats kan inte redigeras från orderuppfyllandevyn.
- **Godkänn** - Om **Manuellt godkännande** är konfigurerad på kanalnivå måste rader först godkännas innan de kan förflytta genom uppfyllandet av orderprocessen.
- **Välj** - Alternativet plockning stöder flera åtgärder. Först uppdaterar **plockning** status för orderraden så att andra i butiken inte försöker välja samma rad. Nästa **Skriv ut plocklista** skriver ut en plocklista för den valda raden eller raderna och deras status ska uppdateras även **plockning**. Plocklisteformat styrs som en del av kvittoformat. Mer information om hur du ställer in kvittoformat finns i [Kvittomallar och utskrift](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing). Slutligen indikerar **Markera som plockad** att raden har plockats. **Markera som plockad** initierar motsvarande lagertransaktioner i backoffice. Plockåtgärder kan utföras samtidigt för flera rader på en order och för alla leveranssätt.
- **Avslå** - Rader eller delvisa rader avslås. Detta gör att de kan skickas vidare från backoffice till en annan butik eller lagerställe. Raderna kan bara avvisas om de har ännu inte plockats eller förpackats. Om du vill avvisa en rad som redan har plockats eller förpackats måste den raden upphävas eller packas upp från backoffice.
- **Packa** - Alternativet packa stöder två åtgärder: **Skriv ut följesedel** skriver ut en följesedel för de valda raderna och **markerad som packad** kommer att markera raderna som du packade och markerar raderna som levereras i backoffice. Endast orderrader som tillhör samma order och har samma leveranssätt kan packas samtidigt. Följesedelformat styrs som en del av kvittoformat. Mer information om hur du ställer in kvittoformat finns i [Kvittomallar och utskrift](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).
- **Leverera** Åtgärden leverera markerar de valda raderna som **levererad** i backoffice. När en rad har levererats visas den inte längre i orderuppfyllelsevyn.
- **Upphämtning** - Åtgärden för upphämtning lägger till rader i transaktionsvyn för upphämtning. Om det inte finns andra rader för order som för närvarande inte tas upp kommer de att läggas till i transaktionsvyn med kvantiteten noll. När en rad har hämtats helt visas den inte längre i orderuppfyllelsevyn.

### <a name="order-fulfillment-filtering"></a>Orderuppfyllelsefiltrering

Orderuppfyllelse i kassan innehåller filter för att hjälpa användaren att enkelt hitta vad de behöver. Filter kan ändras via åtgärdsfönstret längst ned på skärmen **Kassa**. Som standard tillämpas filtret **leveranstyp** beroende på hur operationen ställs in. Om operationen ställs in med parametern **alla order** och filtret används vid åtkomst av orderuppfyllelse. Detsamma gäller för parametrarna **Butiksupphämtning** och **Leverans från butik**. Andra filter kan tillämpas på orderuppfyllelsen:

- Kundnummer
- Kundnamn
- Kundens e-postadress
- Ordernummer
- Leveranssätt
- Inleveransnummer
- Kanalreferens-ID
- Ursprungligt butiksnummer
- Radstatus
- Skapades den
- Leveransdatum
- Inleveransdatum

