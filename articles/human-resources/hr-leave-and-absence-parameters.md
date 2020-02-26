---
title: Konfigurera tjänstledighets- och frånvaroparametrar
description: Definiera personalparametrar för tjänstledighet och frånvaro i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010581"
---
# <a name="configure-leave-and-absence-parameters"></a>Konfigurera tjänstledighets- och frånvaroparametrar

Innan du ställer in tjänstledighets- och frånvaroplan i Dynamics 365 Human Resources kan det vara en bra idé att kontrollera inställningarna för alla relaterade personalparametrar, t.ex.:

- Nummerserie för tjänstledighetsansökan
- Inställning av Family Medical and Leave Act (FMLA)
- Inställningar för självbetjäning för medarbetare för tjänstledighets- och frånvaroansökningar
- Parametrar för tjänstledighet och frånvaro

## <a name="view-and-change-human-resources-parameters"></a>Visa och ändra personalparametrar

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Personalparametrar**.

3. På fliken **nummerserier** kontrollerar du **nummerseriekod** för **begäran om tjänstledighet-ID** och ändrar vid behov. Den här inställningen avgör vilken sekvens som används för automatiskt tilldelning av ID:n för att lämna förfrågningar.

4. På fliken **FMLA** kontrollera FMLA-inställningar och ändra efter behov.

5. På fliken **Självbetjäning för medarbetare** anger du om chefer kan ange tjänstledighets- och frånvaroansökningar för medarbetarnas räkning.

6. På fliken **tjänstledighet och frånvaro** kontrollera inställningar och ändra efter behov.

7. Välj **Spara**.

## <a name="configure-calendar-parameters"></a>Konfigurera kalenderparametrar

Om du har aktiverat funktionen förhandsgranskning av kalender för tjänstledighet och frånvaro måste du konfigurera ytterligare parametrar. 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> För förhandsversionen från 3 februari 2020 är endast **väntande tjänstledighetsansökan** aktiverade.

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Personalparametrar**.

3. På fliken **Kalender** ändra kalenderinställningar och efter behov.

4. Välj **Spara**.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
