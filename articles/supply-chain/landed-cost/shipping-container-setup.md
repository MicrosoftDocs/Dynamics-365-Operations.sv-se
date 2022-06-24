---
title: Fraktcontainrar
description: I denna artikel beskrivs hur du konfigurerar leveransbehållare för modulen Hemtagningskostnad.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 345f815a4f85db30db18aba3f8a4d41835c2e3f2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860854"
---
# <a name="shipping-container-setup"></a>Inställningar för leveransbehållare

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar leveransbehållare för modulen **Hemtagningskostnad**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Ange typer av leveransbehållare

Typer av leveransbehållare definierar de typer av leveransbehållare som är tillgängliga för användning vid frakt och leverans.

För att arbeta med typer av leveransbehållare, gå till **Hemtagningskostnad \> Inställning av behållare \> Typer av leveransbehållare**. Där kan du visa, lägga till och ta bort poster för behållartyperna. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Typ av fraktcontainer | Ange ett unikt ID-namn/nummer för typen av leveransbehållare. |
| beskrivning | Ange en beskrivning av typen av leveransbehållare. |
| Volym | Ange den maximala volym som är tillåten i leveransbehållare av den här typen. |
| Vikt | Ange den maximala vikt som är tillåten i leveransbehållare av den här typen. |
| Returnerbara | Ange om leveransbehållare av den här typen kan returneras till leverantören när de har använts under en sådan tid. Om det här alternativet ställs in på *Ja*, kan ytterligare kostnader gälla för retur av leveransbehållare av den här typen till ursprungsporten. |

## <a name="set-up-shipping-containers"></a>Konfigurera leveransbehållare

Du använder poster för leveransbehållare för att identifiera varje behållare som du använder under färder. När du skapar en färd kan du välja en specifik behållare för den i listan över alla leveransbehållarposter som du har definierat här. Den här funktionen är särskilt användbar om ditt företag äger sina egna leveransbehållare.

Du behöver inte ange behållarnummer för leverans av behållare som bara används en gång. I stället kan du lägga till leveransbehållarnumret när du skapar en färd.

Poster för leveransbehållare används bara i hemtagningskostnad. De är inte tillgängliga i standardmodulen för **transporthantering** (TMS).

För att arbeta med leveransbehållare, gå till **Hemtagningskostnad \> Inställning av behållare \> Leveransbehållare**. Där kan du visa, lägga till och ta bort poster för dina leveransbehållare. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Fraktcontainer | Ange ett unikt ID-namn/nummer för leveransbehållare. |
| Typ av fraktcontainer | Välj typ av leveransbehållare. För mer information, se avsnittet [Konfigurera typer av leveransbehållare](#shipping-container-types) tidigare i denna artikel. |

> [!NOTE]
> - Inställningarna för leveransbehållare är valfria. Vanligtvis använder du det bara om ditt företag äger sina egna leveransbehållare eller ofta återanvänder samma leveransbehållare.
> - Inga kontrollsiffror beräknas för leveransbehållarens nummer.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Ställa in enhetstyper

Enhetstyper skapar ytterligare grupperingar och identifieringsmetoder för leveransbehållare. Enhetstypen används normalt för att identifiera vilken typ av behållare som gods förpackas i, till exempel lastpallar eller trummor. Du kan välja en enhetstyp när du konfigurerar en behållare på sidan **Alla leveransbehållare**.

Enhetstyper används bara för hemtagningskostnad. De är inte tillgängliga i TMS.

För att arbeta med enhetstyper, gå till **Hemtagningskostnad \> Inställning av behållare \> Enhetstyper**. Där kan du visa, lägga till och ta bort poster för enhetstyperna. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Enhetstyp | Ange ett unikt ID-namn/nummer för enhetstypen. |
| beskrivning | Ange en beskrivning av enhetstyp. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Ställa in kyltyper

Kyltyper skapar ytterligare grupperingar och identifieringsmetoder för leveransbehållare (vanligtvis kylbehållare). Du kan välja en kyltyp när du konfigurerar en behållare på sidan **Alla leveransbehållare**.

För att arbeta med kyltyper, gå till **Hemtagningskostnad \> Inställning av behållare \> Kyltyper**. Där kan du visa, lägga till och ta bort poster för kyltyperna. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Kylningstyp | Ange ett unikt ID-namn/nummer för kyltypen. |
| beskrivning | Ange en beskrivning för kyltypen. |
