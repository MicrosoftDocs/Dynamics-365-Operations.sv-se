---
title: Koder för påfyllnadssteg
description: Det här ämnet innehåller en översikt över koder för påfyllnadssteg och hur de används.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992367"
---
# <a name="wave-step-codes"></a>Koder för påfyllnadssteg

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a>Om koder för påfyllnadssteg

Koder för påfyllnadssteg är koder som användarna kan ställa in och använda för att länka specifika förekomster av påfyllnadsmetoder till en motsvarande mall. Mallarna innehåller mallar för påfyllning, skapande av behållare, etikettutskrift, lastuppbyggnad och sortering.

När koder för påfyllnadssteg inte används måste användarna ange fritext för att referera till en specifik mall från förekomst av påfyllnadsmetod. Fritext är benägen att bli fel, eftersom användare måste se till att påfyllnadsstegets text de lägger till för en specifik påfyllnadsstegmetoden i en vågmall exakt matchar påfyllnadsstegtexten i målmallen.

Påfyllnadskoderna för en viss typ av påfyllnadsstegtyp ställs in på en separat sida. För varje instans av påfyllnadsstegmetod i en påfyllnadsmall som kräver en kod för påfyllnadssteg, måste koden för påfyllnadssteg väljas i en nedrullningsbar lista. Markeringen i en nedrullningsbar lista ersätter text som är fritext och minskar risken och konsekvenserna av det mänskliga felet. Inställningskoder används för att koppla en påfyllnadsstegmetod i en påfyllnadsmall till en målmall för metoden.

> [!NOTE]
> Användningen av koder för påfyllnadssteg är valfri och upptagning är per juridisk person. Om en viss juridisk person använder funktionen uppgraderas därför alla befintliga koder för påfyllnadssteg i den juridiska personen till den nya strukturen.

## <a name="setup-demo"></a>Demonstration av installation 

För den här demonstrationen måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.

### <a name="enable-wave-step-codes"></a>Aktivera koder för påfyllnadssteg

Följ de här stegen för att aktivera funktionen för koder för påfyllnadssteg.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
2. På fliken **Allmän** på snabbfliken **Påfyllnadsbearbetning**, ange alternativet **Aktivera koder för påfyllnadssteg** som **Ja**.

Alla befintliga fritexter för påfyllnadssteg uppgraderas till den nya strukturen. När den här uppgraderingen har slutförts för en juridisk person är alternativet **Aktivera koder för påfyllnadssteg** inte längre tillgängligt på sidan **Parametrar för lagerstyrning**.

Valideringar görs under uppgraderingen och om uppgraderingen misslyckas visas ett felmeddelande. En uppgradering kan misslyckas på grund av följande konflikter:

- Dubbla fritexter för påfyllnadssteg finns.
- Anpassningar finns.
- En fritext för påfyllnadssteg som hör till en instans för påfyllnadsstegmetod matchar inte den förväntade malltypen.

När du har löst alla konflikter som har identifierats under valideringen kan du köra uppgraderingsprocessen igen.

När uppgraderingen lyckas blir sidan **koder för påfyllnadssteg** (**Lagerstyrning \> Inställning \> Påfyllnad \> Koder för påfyllnadssteg**) tillgänglig. På den här sidan visas de koder för påfyllnadssteg som uppgraderades när funktionen koder för påfyllnadssteg aktiverades.

### <a name="create-new-wave-step-codes"></a>Skapa nya koder för påfyllnadssteg

Du kan använda sidan the **Koder för påfyllnadssteg** för att skapa och ta bort koder för påfyllnadssteg.

Varje ny kod för påfyllnadssteg och dess associerade ID måste vara unika för alla typer av påfyllnadssteg ch de måste definieras för en viss typ av påfyllnadssteg.

### <a name="apply-wave-step-codes"></a>Tillämpa koder för påfyllnadssteg

När du har definierat lämpliga koder för påfyllnadssteg kan de tillämpas på påfyllnadsprocessmetoderna.

Om du vill använda koder för påfyllnadssteg går du till rätt målmall. Nedan visas de målmallar som koder för påfyllnadssteg är avsedda att peka på:

- **Mallar för lagerpåfyllnad:** Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad
- **Lastuppbyggnadsmallar:** Lagerstyrning \> Inställningar \> Last \> Lastuppbyggnadsmallar
- **Sortera mallar:** Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar
- **Mallar för skapande av behållare:** Lagerstyrning \> Inställningar \> Behållare \> Mall för skapande av behållare.
- **Mallar för etikettutskrift:** Lagerstyrning \> Inställningar \> Dokumentflöde \> Mallar för påfyllnadsetikett

Mallarna i den här listan tillämpas när de refereras från en påfyllnadsprocessmetod som är vald i en påfyllnadsmall. När påfyllnadsstegkoden i en påfyllnadsprocessmetod i en påfyllnadsmall matchar påfyllnadsstegkoden i en av malltyperna används mallen.

### <a name="sample-scenario"></a>Exempelscenario

Följande procedur garanterar att den påfyllnadsmall som du har skapat kommer att användas för påfyllnadsmallen.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnad \> Koder för påfyllnadssteg** och skapa en kod för påfyllnadssteg för typen **Lagerpåfyllnad**.
2. Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad** och skapa en mall för lagerpåfyllnad.
3. I mallen för lagerpåfyllnad väljer du koden för påfyllningssteg som du skapade för typen **Lagerpåfyllnad**.
4. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar** och välj den våg som du tänker använda.
5. I mallen, på snabbfliken **Metoder**, välj metoden **Lagerpåfyllnad**.
6. I fältet **Kod för påfyllnadssteg**, välj koden för påfyllningssteg som du valde i lagerpåfyllnadsmallen.