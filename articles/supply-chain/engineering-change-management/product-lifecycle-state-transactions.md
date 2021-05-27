---
title: Produktens livscykeltillstånd och transaktioner
description: Det här avsnittet förklarar hur du kan kontrollera vilka transaktioner som är tillåtna för varje livscykeltillstånd när en teknisk produkt går igenom dess livscykel.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8bb3d5848b7e2c50a8fdaba1c6a1a7c0087d1390
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6016966"
---
# <a name="product-lifecycle-states-and-transactions"></a>Produktens livscykeltillstånd och transaktioner

[!include [banner](../includes/banner.md)]

När en konstruktionsprodukt går igenom sin livscykel är det viktigt att du kan kontrollera vilka transaktioner som tillåts för varje livscykeltillstånd. Produkter som ännu inte är i vuxet tillstånd bör till exempel inte placeras på en försäljningsorder. Om en produkt har nått slutet av livslängden vill du kanske även kontrollera inflödet för den produkten.

För en teknisk produkt är ändringar av livscykeltillstånd kopplade till produktens tekniska versioner. Produktens livscykeltillstånd kan därför också vara anslutet till dess tekniska versioner. När produktens livscykeltillstånd är anslutet till en teknisk version kan du använda livscykeltillstånd för att kontrollera vilka transaktioner som tillåts för teknisk version.

## <a name="create-and-manage-product-lifecycle-states"></a>Skapa och hantera livscykeltillstånd

För att arbeta med livscykeltillstånd för produkt, gå till **Konstruktionsändringshantering \> Inställning \> Livscykeltillstånd för produkt**. Gör sedan något av följande.

- Om du vill skapa ett nytt livscykeltillstånd väljer du **ny** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill redigera ett befintligt livscykeltillstånd markerar du den i listvyn, väljer **Redigera** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill ta bort ett befintlig livscykeltillstånd markerar du den i listrutan och väljer sedan **ta bort** i åtgärdsfönstret.

> [!NOTE]
> Tekniska produkter använder samma livscykeltillstånd som standardprodukter (icke konstruktionsprodukter). Du kan också öppna sidan **Produktens livscykeltillstånd** som beskrivs i detta ämne genom att gå till **produktinformationshanteringen \> inställning \> produktens livscykeltillstånd**. Mer information om produktens livscykeltillstånd finns i [produktens livscykeltillstånd översikt](../pim/product-lifecycle.md).

### <a name="header"></a>Siduvud

Ange följande fält i rubriken för en policy produktens livscykeltillstånd.

| Fält | beskrivning |
|---|---|
| Delstat | Ange ett beskrivande produktens livscykeltillstånd. |
| beskrivning | Ange en beskrivning av produktens livscykeltillstånd. |

### <a name="general-fasttab"></a>Snabbfliken Allmänt

Ställ in följande fält på snabbfliken **Allmänt**.

| Fält | beskrivning |
|---|---|
| Standard vid frisläppning till en juridisk person | För standardprodukter ställer du in det här alternativet på *Ja* om det här livscykeltillståndet ska användas för alla produkter som standard när de släpps. Ställ in det på *Nej* om livscykeltillstånd kommer att användas manuellt senare.<p>Den här inställningen gäller inte för tekniska produkter. Livscykeltillståndet för en teknisk produkt version efter att det har skapats i det tekniska företaget har angivits i kategorin för teknisk ändring. När produkten frisläpps till ett operationellt företag kopieras produktens livscykeltillstånd. Med andra ord har den samma livscykeltillstånd som den hade i det tekniska företaget när en teknisk produkt frisläpps på ett fungerande företag. Livscykeltillståndet kan skrivas över i det operativa företaget.</p> |
| Är aktiv för planering | Ställ in det här alternativet på *Ja* om du vill inkludera produkter i detta livscykeltillstånd i beräkningar vid huvudplanering och strukturlistenivåer. Ställ in det på *Nej* om du vill utesluta produkter som finns i detta livscykeltillstånd från beräkningarna. |

### <a name="enabled-business-processes-fasttab"></a>Snabbfliken aktiverade affärsprocesser

Använd snabbfliken **aktiverade affärsprocesser** för att styra vilka av de tillgängliga affärsprocesserna som kan användas med produkter i det aktuella livscykeltillståndet. Processerna som visas på den här snabbfliken hittas automatiskt på följande sätt:

- Första gången du sparar ett nytt livscykeltillstånd läser sidan de affärsprocesser som är tillgängliga för tillfället.
- Om du lägger till nya affärsprocesser i systemet kan du uppdatera listan på snabbfliken **aktiverade affärsprocesser** för ett befintligt livscykeltillstånd genom att välja **Sök efter uppdateringar** i åtgärdsfönstret.

Följande fält är tillgängliga för varje process som visas på snabbfliken **aktiverade affärsprocesser**.

| Fält | beskrivning |
|---|---|
| Process | Det här skrivskyddade fältet visar namnet på en befintlig affärsprocess. |
| Processområde | Det här skrivskyddade fältet visar namnet på ett befintligt processområde. |
| Policy | Välj ett av följande värden om du vill kontrollera om och hur den aktuella processen kan tillåtas för produkter i detta livscykeltillstånd:<ul><li>**Aktiverad** – affärsprocessen är tillåten.</li><li>**Spärrat** – processen är inte tillåten. Om en användare försöker använda processen för en produkt som är i livscykeltillstånd blockeras försöket och ett felmeddelande visas i stället. Du kan t.ex. blockera produkter som har nått slutet av livslängd från att köpas.</li><li>**Aktiverad med varning** – processen är tillåten, men en varning visas. Du kanske till exempel vill att en prototypprodukt ska placeras på en tillverkningsorder som skapas av avdelningen för forsknings- och utvecklingsavdelningen. Andra avdelningar bör dock vara medvetna om att de inte borde producera produkten än.</li></ul> |

Om du lägger till fler livscykeltillståndsregler som en anpassning kan du visa reglerna i användargränssnittet genom att välja **Uppdatera processer** i det övre fönstret. Knappen **Uppdatera processer** är bara tillgänglig för administratörer.

## <a name="lifecycle-states-for-released-products-and-product-variants"></a>Livscykeltillstånd för frisläppta produkter och produktvarianter

För en produkt som har varianter (huvud och varianter) har produkten (huvud) ett livscykeltillstånd och var och en av varianterna kan också ha ett annat livscykeltillstånd.

För specifika processer, om antingen varianten eller produkten är blockerad, kommer processen också att blockeras. För att avgöra om en process är blockerad kommer systemet att göra följande kontroller:

- För teknikstyrda produkter:
  - Om den aktuella tekniska versionen är blockerad blockerar du processen.
  - Om den aktuella varianten är blockerad blockerar du processen.
  - Om den frisläppta produkten är blockerad blockerar du processen.
- För standardprodukter:
  - Om den aktuella varianten är blockerad blockerar du processen.
  - Om den frisläppta produkten är blockerad blockerar du processen.

Anta till exempel att du bara vill sälja en variant (röd) av en viss produkt (t-shirt) och blockera försäljningen av alla andra varianter för tillfället. Du kan implementera detta med följande inställningar:

- Tilldela produkten ett livscykeltillstånd som tillåter processen. Tilldela till exempel t-shirtprodukten ett livscykeltillstånd *Säljbar*, vilket möjliggör affärsprocessen *Försäljningsorder*.
- Tilldela den säljbara varianten ett livscykeltillstånd som tillåter processen. Tilldela till exempel också den röda varianten ett livscykeltillstånd *Säljbar*.
- Alla andra varianter tilldelas ett annat livscykeltillstånd där processen blockeras. Tilldela till exempel den vita varianten (och alla andra varianter) ett livscykeltillstånd *Inte säljbar*, vilket blockerar affärsprocessen *Försäljningsorder*.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
