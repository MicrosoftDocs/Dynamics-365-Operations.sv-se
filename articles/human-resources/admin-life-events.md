---
title: Ställa in administratörsbehörighet för livscykelhändelser
description: I denna artikel beskrivs hur du konfigurerar administratörsbehörighet för livscykelhändelser i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229917"
---
# <a name="set-administrator-rights-for-life-events"></a>Ställa in administratörsbehörighet för livscykelhändelser

[!include [banner](../includes/preview-banner.md)]

Administratörer kan uppdatera alternativen för livscykelhändelse, beroende på konfigurationsinställningarna. På sidan **Personalparametrar** kan du konfigurera parametrar som gör att administratörer kan ändra planval. Du kan också begränsa administratörerna helt från att göra ändringar.

På sidan **Personalparametrar** kan du ställa in begränsningar för planändring för bekräftade planer och alternativ för livscykelhändelse.

Om alternativet **Bekräftade planer** har valts kan ändringar endast göras om en anmälningsperiod är aktiv. (Exempel på anmälningsperioder inkluderar öppna anmälningsperioder, nya anställningsperioder och perioder för registrering av livstidshändelse.) Om detta alternativ inte är valt kan du göra ändringar när som helst.

Om alternativet **Livshändelsealternativ** är valt begränsas planändringar under en livshändelse av alternativen för livshändelser som är definierade på plantypen. Om det här alternativet inte är valt kan du ändra planurvalet under en livscykel.

## <a name="set-plan-change-restrictions"></a>Ange begränsningar för planändring

På sidan **Personalparametrar** på fliken **Förmånshantering** är följande fält tillgängliga.

| Fält | Beskrivning |
|-------|-------------|
| Bekräftade planer | Välj det här alternativet om ändringar i en plan endast är tillåtna om en anmälningsperiod är aktiv. Om detta alternativ inte är valt kan du göra ändringar när som helst. |
| Livshändelsealternativ | Välj det här alternativet om planerna ändras under en livshändelse av alternativen för livshändelser som är definierade på plantypen. Om det här alternativet inte är valt kan du ändra planurvalet under en livscykel. |
