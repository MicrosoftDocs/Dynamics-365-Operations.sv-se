---
title: Åtkomsträttigheter för en kostnadsobjektcontroller
description: Den här artikeln innehåller information om åtkomsträttigheter för kostnadsobjektcontroller.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c40be758c5e5d1d1fb025630ed8321ae46251892
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903201"
---
# <a name="access-rights-for-cost-object-controllers"></a>Åtkomsträttigheter för en kostnadsobjektcontroller

[!include [banner](../includes/banner.md)]

Arbetsytan **Kostnadskontroll** är en central plats där chefer kan visa prestanda för deras kostnadsobjekt. Den här arbetsytan låter chefer använda kostnadsredovisningsdata även om de inte är kostnadsrevisorer. Av säkerhetsskäl ska chefer endast tillåtas se kostnadsredovisningsdata som hör till ett visst kostnadsobjekt som de ansvarar för.

Det finns fyra unika roller i kostnadsredovisning.

| Rollnamn               | Licens      |
|-------------------------|--------------|
| Kostnadsredovisningschef | Aktivitet     |
| Kostnadsredovisare         | Operations   |
| Ansvarig kostnadsredovisare   | Verksamhet   |
| Kostnadsobjektskontrollant  | Teammedlemmar |

Den här artikeln beskriver hur du tilldelar rollen **kostnadsobjektcontroller** till en chef.

När rollen **kostnadsobjektcontroller** har tilldelats en chef kan denne utföra följande uppgifter:

- Åtkomst till arbetsytan **kostnadskontroll** (i klienten).

    - Gå igenom och ha visningsåtkomst till sidorna som stöder detaljgranskningsupplevelsen.

- Åtkomst till arbetsytan **kostnadskontroll** (i mobilapplikationen).

> [!NOTE]
> Rollen **kostnadsobjektcontroller** styr inte vilka objekt som användaren kan komma åt och visa data för. Säkerhet på radnivå tillhandahålls via dimensionshierarkier och i Hierarki för åtkomstlista.

## <a name="grant-access-rights"></a>Bevilja åtkomstbehörighet
I följande exempel visas hur en dimensionshierarki kan se ut.

**Detaljer om dimensionshierarki**

| Dimensionshierarkins namn | Dimension    | Namn på typ av dimensionshierarki      | Hierarki för åtkomstlista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Kostnadsställen | Hierarki för dimensionsklassificering | **Ja**               |

Du kan använda snabbfliken **användare** i hierarkidesignern för att infoga minst ett användar-ID på varje nod.

|             Noder                 | Användare            | Från dimensionsmedlem     |   Till dimensionsmedlem   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| Organisation                      | Benjamin Claire |                           |                         |
| &nbsp;&nbsp;Admin                 | april            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finansiellt   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Personal        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produktion            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Paketering | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Sammansättning  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> Kostnadsrevisorerna ska tilldelas till den översta nivån i hierarkin, så att de kan se alla poster i kostnadsredovisningen.

Innan Hierarki för åtkomstlista kan användas måste alternativet **Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar** anges till **Ja** på fliken **Allmänt** på fliken **kostnadsredovisningsparametrar** på sidan (**kostnadsredovisning** > **inställningar** > **parametrar**).

Inställningar för Hierarki för åtkomstlista används för att bestämma vilka data som visas i följande områden:

- Arbetsytan **kostnadskontroll** (i klienten):

    - Data på de sidor som används för detaljgranskning

- Arbetsytan **kostnadskontroll** (i mobilapplikationen):

    - Saldon i kort

- Microsoft Power BI:

    - Data som visas i Power BI-visualiseringar
    - Data Power BI-visualiseringar som är inbäddade i Dynamics 365 Finance-klienten

> [!IMPORTANT]
> - Innan Hierarki för åtkomstlista kan påverka data i Power BI måste hierarkiåtkomst och säkerhet på radnivå i Power BI paras ihop. Mer information finns i [ställa in säkerhet för kostnadsredovisningens innehållspaket](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Den här artikeln visar kraven som måste vara på plats innan du kan använda arbetsytan **kostnadskontroll**.

Ytterligare resurser

- [Arbetsyta för kostnadskontroll](cost-control-workspace.md)
- [Dimensionshierarki](dimension-hierarchy.md)
- [Ställa in säkerhet för kostnadsredovisningsinnehållspaket](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
