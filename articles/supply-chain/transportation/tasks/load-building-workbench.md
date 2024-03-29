---
title: Workbench för lastuppbyggnad
description: I denna artikel beskrivs hur du arbetar med workbench för beläggningsbyggande.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 12d8c351f84e9045ffa94f3fcf0dbdefc633d2a0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878741"
---
# <a name="load-building-workbench"></a>Workbench för lastuppbyggnad

[!include [banner](../../includes/banner.md)]

Med hjälp av workbench för beläggningsbyggande kan du använda hämtningsstrategier när du skapar laster.

## <a name="create-a-load-building-strategy"></a>Skapa en lastuppbyggnadsstrategi

Du använder lastuppbyggnadsstrategier för att automatiskt skapa laster. Den här funktionen kan vara fördelaktig i följande situationer:

- Om du regelbundet levererar en viss produkt, laststrategier för att spara tid eftersom du inte behöver bygga samma last varje gång.
- Om du vill undvika en halv full last för att maximera effektiviteten kan du med hjälp av laststrategier fylla i varje last så mycket som möjligt.

En klass för lastuppbyggnadsstrategi med namnet `TMSLoadBuildingVolumeStrategy` tillhandahåller en lastuppbyggnadsstrategi med namnet *volymbaserade belastningsbyggnadsstrategi*. Denna strategi låter dig använda de angivna maximivärdena som specificerats för höjd och vikt i lastmallen eller så kan du åsidosätta inställningarna genom att ange nya värden. Denna strategi är den enda strategi som medföljer. (Du kan dock ha vissa anpassade strategier.)

Om du vill använda den medföljande strategin *Volymbaserad lastuppbyggnadsstrategi* välj fältet **Lastuppbyggnadsstrategi** på sidan **Workbench för lastuppbyggnad** (**Transporthantering &gt; Planering &gt; Workbench för lastuppbyggnad**).

Följ dessa steg för att skapa en lastuppbyggnadsstrategi.

1. Gå till **Transporthantering &gt; Installation &gt; Lastuppbyggnad &gt; Lastuppbyggnadsstrategier**.
1. I åtgärdsfönstret, välj **Generera klasslista** för att se till att du har de senaste versionerna av alla tillgängliga klasser.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange ett unikt namn på strategin, välj klass för lastuppbyggnadsstrategi och ange en beskrivning.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Parametrar** i åtgärdsfönstret.
1. På sidan **Parametrar för lastuppbyggnadsstrategi**, välj **Volymkapacitet** i listan och sedan i fältet **Värde** ange procentandelen av lastens totala volymkapacitet som ska tillämpas för den nya lastuppbyggnadsstrategi.
1. Välj **Viktkapacitet** i listan och sedan i fältet **Värde** ange procentandelen av lastens totala viktkapacitet som ska tillämpas för den nya lastuppbyggnadsstrategin.
1. Stäng sidan **parametrar för lastuppbyggnadsstrategi**.
1. Stäng sidan **lastuppbyggnadsstrategier**.

Du kan nu tilldela lastuppbyggnadsstrategin till en lastuppbyggnadsmall. Alternativt kan du använda den direkt i workbench för lastplanering.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Använd en lastuppbyggnadsstrategi i workbench för lastplanering

1. Gå till **Transporthantering &gt; Planering &gt; Workbench för lastuppbyggnad**.
1. Gör något av följande:

    - Välj en strategi i fältet **lastuppbyggnadsstrategi**.
    - Om du har definierat en lastuppbyggnadsmall och tilldelat den lastuppbyggnadsstrategi, i åtgärdsfönstret, på **Hantera mallar** välj **Tillämpa mall**. I den nedrullningsbara dialogrutan **Tillämpa lastuppbyggnadsmall**, välj en mall i fältet **Lastuppbyggnadens mallnamn**.

1. På snabbfliken **Lastmallsekvens**, välj en eller flera [lastmallar](load-template.md). Workbench kommer att försöka få plats med lasten i dessa typer av behållare i den ordning som anges här. Vanligtvis bör du placera de minsta behållarna överst i listan för att se till att den minsta möjliga behållaren väljs först.
1. Välj **Föreslå laster** i åtgärdsfönstret.
1. Granska de föreslagna laster och de föreslagna lastraderna.
1. I åtgärdsfönstret **Skapa laster** för att skapa laster som är baserade på källdokumentraderna på snabbfliken **Föreslagna lastraderna**.
1. Stäng sidan **Workbench för lastuppbyggnad**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]