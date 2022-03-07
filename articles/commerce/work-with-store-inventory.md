---
title: Lagerhantering
description: Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.
author: rubencdelgado
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 293040ccbe99c07b15373b92d64d086227de9d3f09c8feba700648b320cd8c74
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762558"
---
# <a name="commerce-inventory-management"></a>Hantering av Commerce-lager

[!include [banner](includes/banner.md)]

När du arbetar med lager i Microsoft Dynamics 365 Commerce och använder några av Commerce-programmen som är anslutna till en Commerce Scale Unit (CSU) är det viktigt att veta att orderbearbetningslogiken i CSU ger begränsat stöd för vissa lagerdimensioner och vissa lagerartikeltyper. DCommerce-program har inte stöd för alla funktioner för artikelkonfiguration som finns tillgängliga via alternativen för artikelkonfiguration i Dynamics 365 Supply Chain Management.

De Commerce-program som körs på CSU stöder för närvarande inte följande produktdimensioner och artikelkonfigurationer:

- Konfigurationsdimensioner för produkt samt strukturlisteartiklar (Bill of Materials, eller BOM) – förutom produkter i detaljhandelspaket, som använder vissa komponenter i strukturlistan
- Fångstviktartiklar
- Produktdimension och styrda artiklar för version

De Commerce-program som körs på CSU stöder för närvarande inte följande spårningsdimensioner:
- Ägardimension

- Kassaprogrammet (POS) kan erbjuda begränsat stöd för följande dimensioner. Med andra ord kan POS komma att automatiskt ange vissa av dessa dimensioner i lagertransaktioner, baserat på konfigurationen för lagerställe eller butik. POS stöder emellertid inte dimensionerna fullt ut i den mening att de stöds om en säljtransaktion anges manuellt i Commerce-administrationen. 

- **Plats för lagerställe** – När användarna använder de nya [inkommande](./pos-inbound-inventory-operation.md) och [utgående funktionerna](./pos-outbound-inventory-operation.md) för kassa kan de välja en lagerplats för lagerställe som de vill ta emot artiklar i eller skicka utgående orderartiklar från. Om de använder den föråldrade åtgärden **Välja och ta emot** finns begränsat hanteringsstöd att tillgå på plats för att ta emot och skicka utgående överföringar. Detta stöd är endast tillgängligt om alternativet **Använd hanteringsprocess för lagerställe** har aktiverats för artikeln samt för butikens lagerställe. En lagerplats kan för närvarande inte användas med åtgärderna **Inventering** eller **Lagersökning**.

- **Registreringsskylt** – Registreringsskyltar gäller endast när alternativet **Använd lagerhanteringsprocess** har aktiverats för artikeln och den butikslagerstället. I POS: Om lagerinlevereras sker till ett butikslagerställe med hjälp av åtgärden **Inkommande åtgärd** eller **Plockning och inleverans** där lagerstyrningsprocessen har aktiverats, och om den plats som har valts för att ta emot artikeln i är kopplad till en platsprofil som kräver kontroll av registreringsskylt, använder kassaprogrammet (POS) systematiskt en registreringsskylt för den mottagande raden. Kassaanvändare (POS) kan inte ändra eller hantera denna information om registreringsskylten. Om fullständig hantering av registreringsskyltar krävs, rekommenderar vi att affären använder [appen](../supply-chain/warehousing/install-configure-warehousing-app.md) för lagerställe eller backoffice-klienten för att hantera mottagningen av dessa artiklar.

- **Serienummer** – Kassaprogrammet ger begränsat stöd för registrering av ett enda serienummer på en försäljningstransaktionsrad för order som skapas i POS och omfattar serialiserade artiklar. Det här serienumret valideras inte mot registrerade serienummer som redan finns i lagret. Om en försäljningsorder skapas i kundtjänstkanalen eller expedieras genom ERP (enterprise resource planering; resursplanering för företag) och flera serienummer registreras på en enda försäljningsrad under expedieringsprocessen i ERP, kan dessa serienummer inte användas eller valideras om en retur behandlas i POS för ordern. När lagret tas emot med hjälp av åtgärden **Inkommande åtgärd** kan användarna [registrera eller bekräfta serienumren som har mottagits](./pos-serialized-items.md).

- **Batch-ID** - POS-programmet ger begränsat stöd vid utdragsbokföring om en batchkontrollerad artikel säljs, men POS-användare kan inte definiera det batch-ID som säljs eller plockas när de använder POS-programmet.

- **Lagerstatus** – För artiklar som använder lagringshanteringsprocessen och kräver en lagerstatus kan det här statusfältet inte ställas in eller ändras via kassaprogrammet. Standardlagerstatus som definierats i konfigurationen för lagerställe används när artiklar inlevereras till lagret.

> [!NOTE]
> Alla organisationer måste testa artikelkonfigurationer via Commerce-appar i utvecklings- eller testmiljöer innan man distribuerar konfigurationerna till tillverkningsmiljöer. Testa dina artiklar genom att använda dem för att utföra vanliga kassaförsäljningstransaktioner i POS och skapa kundorder (om tillämpligt) via POS, kundtjänst eller näthandel för att validera att de kan stödjas fullt ut. Du bör även testa POS-uppfyllelse och lagerprocesser (t.ex. åtgärder för lagermottagning och orderuppfyllelse) innan du distribuerar nya artikelkonfigurationer, detta för att se till att kassaprogrammet (POS) har stöd för dem. Testerna måste inkludera en fullständig bokföringsprocess för utdrag/order i testmiljön och verifiera att inga bokföringsproblem uppstår när order för dessa artiklar skapas och bokförs i Commerce-administrationen.
>
> Om artiklar konfigureras på ett sätt som inte stöds av Commerce-programmen och passande tester inte utförs, kan datafel uppstå som antingen är svåra att korrigera eller inte kan korrigeras alls.

## <a name="purchase-orders"></a>Inköpsorder

Inköpsorder skapas i Commerce Headquarters. Om ett lagerställe för butik ingår i inköpsorderns rubrik eller på inköpsorderrader, kan raderna tas emot i butiken genom att använda åtgärden [Inkommande åtgärd](./pos-inbound-inventory-operation.md) i POS. 

## <a name="transfer-orders"></a>Överföringsorder

Överföringsorder kan skapas i Commerce Headquarters eller genom antingen den [inkommande åtgärden](./pos-inbound-inventory-operation.md) eller den [utgående åtgärden](./pos-outbound-inventory-operation.md) i POS. Använd kassaåtgärden (POS) **Inkommande åtgärd** för att skapa en överföringsorderbegäran om att lagret ska skickas till butiken från ett annat lagerställe eller en annan lagerplats. Använd kassaåtgärden (POS) **Utgående åtgärd** för att skapa en överföringsorderbegäran om att lagret ska levereras från butiken från ett annat lagerställe eller en annan lagerplats. När en överföringsorder för en butik har skapats kan denna butik hantera mottagandet av lager för överföringsordern via åtgärden **Inkommande åtgärd** i POS. Om butiken levererar lager till en annan plats, används åtgärden **Utgående åtgärd** i POS för att hantera butikens utgående leveransprocess.

## <a name="stock-counts"></a>Lagerinventeringar

Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade. Planerade lagerinventeringar skapas via Commerce Headquarters genom att ett dokument för inventeringsjournal skapas som är kopplat till butikens lagerställe. Den här journalen innehåller de artiklar som måste inventeras. Butiken kan sedan komma åt dessa fördefinierade inventeringsjournaler och arbeta med dem med hjälp av åtgärden **Lagerinventering** i POS. Butiksanvändare initierar en icke-planerad lagerinventering eftersom denna krävs när de använder åtgärden **Lagerinventering** i POS. Till skillnad från schemalagda lagerinventeringar har icke-schemalagda inventeringar ingen fördefinierad lista över artiklar. När en lagerinventering oavsett typ utförs i POS allokeras den och skickas till huvudkontoret. På huvudkontoret måste antalet valideras och bokföras i Commerce Headquarters som ett separat steg.

## <a name="inventory-lookup"></a>Lagersökning

Den aktuella produktkvantiteten som för tillfället finns att tillgå för flera butiker och lagerställen kan beskådas på sidan **Lagersökning**. Utöver det aktuella saldot kan framtida ATP-kvantiteter ("available-to-promise") visas för varje enskild butik. Välj butiken som du vill visa ATP-kvantiteter för och välj sedan **Visa tillgänglighet för butik**. Mer information om vilka konfigurationsalternativ som är tillgängliga finns i [Beräkna lagertillgänglighet för butikskanaler](./calculated-inventory-retail-channels.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]