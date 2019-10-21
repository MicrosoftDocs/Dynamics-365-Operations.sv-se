---
title: Lagerhantering
description: Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c5da94e02b2381bbd058221567172cd428931c45
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024693"
---
# <a name="store-inventory-management"></a>Hantering av butikslager

[!include [banner](includes/banner.md)]

När du arbetar med lager i Dynamics 365 Retail och använder kassaprogrammet är det viktigt att komma ihåg att kassan ger begränsat stöd för lagerdimensioner och vissa lagerartikeltyper.

Kassalösningen stöder inte följande artikelkonfigurationer:

- Strukturlisteartiklar (utom produktpaket som använder vissa komponenter i strukturlisteramverk)
- Fångstviktartiklar
- Batch-kontrollerade artiklar

Kassaprogrammet stöder för närvarande inte följande spårningsdimensioner i kassan:

- Spårningsdimensionsgrupp
- Ägardimension

Kassalösning ger begränsat stöd för följande dimensioner. Begränsat stöd anger att kassan som standard några av dessa dimensioner till lagertransaktioner baserat på grossistförsäljning/installationsprogrammet automatiskt. Kassan stöder inte helt dimensionerna på ett sätt som de stöds om en försäljningstransaktion anges manuellt i ERP. 

- **Lagerställe** – användarna kan inte hantera det mottagande lagerstället för artiklar som inlevererats till ett butikslagerställe när butiken inte har konfigurerats för att använda processen för lagerstyrningsprocesser. En standardmottagningsplats definierad i butikslagret kommer att användas för dessa artiklar Om lagringshanteringsprocessen har aktiverats för affären utlöses begränsat stöd som uppmanar användaren att välja mottagningsplats för hela kvittot. Artiklar som säljs från butiken kommer alltid att säljas från standardplatsen för butikslager, enligt definitionen i inställningarna för butikslagerstället. Platsen för hantering av returlager kan styras via standard avsändarplatsens definition på butikslager stället eller baserat på returorsakskoder enligt definitionen i returplatspolicyn.
- **Registreringsskylt** - Registreringsskylt gäller endast när **Använda lagerhanteringsprocessen** har aktiverats på artikeln och den butikslagerställe. I kassan kommer lagret att tas emot i en lagerlokal där lagringshanteringsprocessen har aktiverats och platsen som valts för att ta emot artikeln är kopplad till en platsprofil som kräver kontroll av registreringsskylt, kommer kassaprogrammet systematiskt att använda en registreringsskylt till mottagningsraden. Användare i kassa har inte möjlighet att ändra eller hantera denna registreringsskyltinformation. Om fullständig hantering av registreringsskyltar krävs, föreslås att affären använder WMS-mobilapplikationen eller ERP-klientens backoffice för att hantera mottagning av dessa artiklar.
- **Serienummer** - Kassaprogrammet har begränsat stöd för ett enda serienummer som ska registreras på en transaktionsförsäljningsrad för order som skapas i kassan med serialiserade artiklar. Det här serienumret valideras inte mot registrerade serienummer som redan finns i lagret. Om en försäljningsorder skapas i kundtjänstkanal eller om den expedieras genom ERP och flera serienummer registreras på en enda försäljningsrad under expedieringsprocessen i ERP, kan dessa serienummer inte användas eller valideras om en retur behandlas i kassan för dessa order.
- **Lagerstatus** - för artiklar som använder lagringshanteringsprocessen och kräver en lagerstatus kan det här statusfältet inte ställas in eller ändras via kassaprogrammet. Standardlagerstatus som definierats i konfigurationen av lagerplats används när artiklar inlevereras till lagret.

> [!NOTE]
> Alla organisationer måste testa artikelkonfigurationer via kassan i utvecklings- eller testmiljöer innan du distribuerar dem till produktion. Testa dina objekt genom att utföra regelbundna hämtköp genom att genomföra och skapa kundorder (om tillämpligt) till kassan med dina artiklar. Testning måste inkludera en fullständig process för bokföring av utdrag i en testmiljö och kontrollera att det inte finns några problem.
>
> Konfigurera artiklar på ett sätt som inte stöds av kassaprogrammet utan lämplig testning kan resultera i att processen för bokföring av utdrag misslyckas i produktionen, utan ett enkelt sätt att lösa problem. Partner eller kundanpassningar av programmet kan också anses låta dessa bokföringsprocesser slutföras. Om du inte behöver göra anpassningar måste organisationen säkerställa att produktkonfigurationen för produkterna har gjorts på ett sätt som stöds som standard kassaprogram/skapande av order/bokföringsprocessen för utdrag.

## <a name="purchase-orders"></a>Inköpsorder

Inköpsorder skapas på huvudkontoret. Om ett lagerställe ingår i inköpsorderrubriken kan ordern tas emot i butiken med hjälp av Modern POS (MOPS) eller Cloud POS i via åtgärden **plocka/ta emot**. När de kvantiteter som har inlevererats i butiken har angetts i fältet **Inleverera nu** i kassan inköpsorderdokumentet, kan de sparas lokalt eller på ett dedikerat sätt. Om dessa data sparas lokalt påverkas inte lagerinventeringen. Spara bör endast ske om användaren inte är redo att skicka kvittot till huvudkontor och behöver bara ett sätt att tillfälligt lagra den tidigare inmatade **Inleverera nu**-data. Detta sparar informationen för Inleverera nu lokalt i användarens kanaldatabas. När dokumentet har bearbetats med alternativet **Utfäst** skickas data **Ta emot nu** till huvudkontor och inleveransen för inköpsordern bokförs. 

## <a name="transfer-orders"></a>Överföringsorder

En överföringsorder kan ange att en viss butik är den plats där artiklarna kan levereras från eller den plats där lagret ska inlevereras till. Om kassaanvändaren är leveranslagerställe för en överföringsorder kommer de att kunna ange **Skicka nu**-kvantiteter från kassan. Data som anges av leveranslagret kan sparas lokalt eller utföras. När det sparas lokalt görs inga uppdateringar av överföringsorderdokumentet i huvudkontor. Spara bör endast ske om användaren inte är redo att skicka leveransen till huvudkontor och behöver bara ett sätt att tillfälligt lagra den tidigare inmatade **Skicka nu**-data. När butiken är klar för att bekräfta leveransen ska alternativet **Utfäst** väljas. Detta bokför leverans av överföringsordern i huvudkontor så att det mottagande lagerstället kan ta emot mot det. 

Om kassaanvändaren är mottagande lagerställe för en överföringsorder kommer de att kunna ange **mottag nu**-kvantiteter från kassan. Data som anges av mottagande lagret kan sparas lokalt eller utföras. Spara bör endast ske om användaren inte är redo att skicka kvittot till huvudkontor och behöver bara ett sätt att tillfälligt lagra den tidigare inmatade **Inleverera nu**-data. Detta sparar informationen för Inleverera nu lokalt i användarens kanaldatabas. När dokumentet har bearbetats med alternativet **Utfäst** skickas data **Ta emot nu** till huvudkontor och inleveransen för överföringsordern bokförs. Det är viktigt att notera att det mottagande lagret begränsas till att endast kunna genomföra mottagna kvantiteter som är lika med eller mindre än levererade kvantiteter. Ett försök att ta emot kvantiteter på en överföringsorder som inte tidigare har levererats leder till fel och inleveransen bekräftas inte i huvudkontor.

## <a name="stock-counts"></a>Lagerinventeringar

Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade. Tidsplanerad inventering initieras på huvudkontoret och anger vilka artiklar som måste inventeras. Huvudkontoret skapar ett inventeringsdokument som kan inlevereras till butiken, där de faktiska lagerkvantiteterna förs in i MPOS eller Cloud POS. Ej schemalagda lagerinventeringar initieras i butiken och de faktiska lagerkvantiteter uppdateras antingen i MPOS eller Cloud POS. Till skillnad från schemalagda inventeringar har ej schemalagda inventeringar inte en fördefinierad lista över artiklar. När en lagerinventering oavsett typ utförs utfästs den och skickas till huvudkontoret. På huvudkontoret valideras och bokförs inventeringen. som ett separat steg.

## <a name="inventory-lookup"></a>Lagersökning

Den aktuella produktkvantiteten för flera butiker och lagerställen kan visas på sidan **Lagersökning**. Utöver det aktuella lagersaldot kan framtida ATP-kvantiteter visas för varje enskild butik. Välj den butik du vill visa ATP för och klicka sedan på **Visa tillgänglighet i butiken**.
