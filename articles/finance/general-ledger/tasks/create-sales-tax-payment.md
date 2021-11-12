---
title: Skapa en momsbetalning
description: Med proceduren Kvitta och bokför moms kvittas momssaldon på momskontona och kompenserar dem till momskvittningkontot för en viss period.
author: twheeloc
ms.date: 10/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54132ca4775482b4a06ff7e73125e804aff40cb4
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700123"
---
# <a name="create-a-sales-tax-payment"></a>Skapa en momsbetalning

[!include [banner](../../includes/banner.md)]

Med proceduren Kvitta och bokför moms kvittas momssaldon på momskontona och motbokar dem till momskvittningkontot för en viss period.

1. Gå till **Moms > Deklarationer > Moms > Kvitta och bokför moms**.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kvittningsperiod**.
3. Klicka på länken på den valda raden i listan.
4. I fältet **Från datum** anger du ett datum.
    - Om du inte väljer alternativet **Inkludera korrigeringar** på sidan **Redovisningsparametrar** kan kvittningen bearbetas för andra versioner. Originalet är den första kvittningen för ett periodintervall och kan bara bearbetas en gång för ett periodintervall. De senaste korrigeringarna kvittar momstransaktioner som har bokförts, efter den ursprungliga versionen har skapats.
5. I fältet **Transaktionsdatum**, ange ett datum.
6. Klicka på **OK**.

## <a name="performance-consideration"></a>Beaktanden av prestanda

Momsbetalningsproceduren kan ta lång tid att slutföra. De huvudfaktorer som påverkar procedurens prestanda är antalet fakturor i kvittningsperioden och antalet poster som måste bokföras i momskvittningsverifikationen. För att förbättra prestandan kan du välja att hoppa över vissa funktioner som inte krävs i processen.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Aktivera funktionen för förbättring av momsbetalningsprestanda

Funktionen för funktionen för **förbättring av momsbetalningsprestanda** kan förbättra prestandan för momsbetalningsproceduren genom att sammanställa, till en rad, beloppet i redovisningsvalutan och rapporteringsvalutabeloppet på momsbetalningsverifikationsrader som har samma huvudkonto, redovisningsdimension och valuta.

1. Gå till **Systemadministration** \> **Arbetsytor** \> **Funktionshantering**.
2. På fliken **Alla** sök efter och välj **förbättring av momsbetalningsprestanda**.
3. Välj **Aktivera**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Förhindra generering av motbokade momstransaktioner

Som standard bokför momsbetalningsverifikationen motbokade momstransaktioner mot varje momstransaktion som kvittas i momsbetalningsproceduren. Dessa motbokade momstransaktioner inkluderas i rapporten **Moms/Redovisningsavstämning**. De visar det utestående saldot för momstransaktionerna som inte kvittas under perioden.

Däremot kan de motbokade momstransaktionerna öka belastningen på momsbetalningsproceduren. Därför kan en förhandsversion med namnet **TaxReportGenOffsetTaxTransPerRecordSetFlighting** aktiveras på begäran. Den här förhandsversionen kan förbättra prestandan för att generera motbokade momstransaktioner för länder och regioner utom Thailand, Polen, Ungern, Litauen, Malaysia, Indien, Italien, Ryssland, Tjeckien, Estland och Lettland.

> [!NOTE]
> Om det finns anpassade fält i momstransaktionsregistret går det inte att aktivera flygbiljetten.

Eftersom rapporten **Moms/Redovisningsavstämning** i allmänhet bara används för intern kontroll och inte krävs i många skatteavstämningar, kan du välja att inte generera motbokade momstransaktioner på momsbetalningsverifikationen.

1. Gå till **Moms** \> **Indirekt moms** \> **Moms** \> **Momskvittningsperioder**.
2. Välj kvittningsperiod.
3. På snabbfliken **Allmänt** ange alternativet **Förhindra att motbokade momstransaktioner genereras** till **Ja**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
