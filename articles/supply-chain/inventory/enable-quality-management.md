---
title: Aktivera kvalitets- och avvikelsehantering
description: Detta ämne innehåller en översikt över processen för att ställa in och konfigurera kvalitet och avvikelsehanteringsfunktioner i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956264"
---
# <a name="enable-quality-and-nonconformance-management"></a>Aktivera kvalitets- och avvikelsehantering

[!include [banner](../includes/banner.md)]

Detta ämne innehåller en översikt över processen för att ställa in och konfigurera kvalitet och avvikelsehanteringsfunktioner i Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Aktivera kvalitets- och avvikelsehantering

Följ stegen nedan om du vill aktivera kvalitetshantering i systemet.

1. Gå till **Lagerhantering \> Inställningar \> Parametrar för hantering av lager och lagerstyrning**.
1. På fliken **Kvalitetshantering** anger du alternativet **Använd kvalitetshantering** som *Ja*.
1. Ange timlön i den lokala valutan i fältet **Timtariff**. Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse. Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse. De påverkar inte andra funktioner.
1. Välj **Rapportinställningar**.
1. Lägg till nya rader för de olika rapporttyperna och välj sedan den typ av dokument som ska användas för respektive rapport.
1. Stäng sidan.
1. Stäng sidan.

## <a name="quality-management-configuration-process"></a>Konfigurationsprocess för kvalitetshantering

Innan du kan börja använda funktionerna för kvalitetshantering och generera kvalitetsorder, måste du konfigurera systemet och förutsättningarna. Här finns en lista med de steg som måste utföras för att konfigurera kvalitetshanteringen.

1. [Aktivera kvalitets- och avvikelsehantering](#enable-qm).
1. Valfritt: [Konfigurera testinstrument](quality-test-instruments.md).
1. [Konfigurera tester](quality-tests.md).
1. [Konfigurera testvariabler och resultat](quality-test-variables.md).
1. [Konfigurera testgrupper](quality-test-groups.md).
1. Valfritt: [Konfigurera kvalitetsgrupper och länka till produkter](quality-groups.md).
1. Valfritt: [Konfigurera kvalitetsassociationer](quality-associations.md).

När konfigurationen är klar kan du börja skapa och bearbeta kvalitetsorder. Mer information om hur du skapar och arbetar med kvalitetsorder finns i [Kvalitetsorder](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Konfigurationsprocess för avvikelsehantering

Innan du kan börja använda hanteringsfunktionerna för avvikelse och generera avvikelser måste du konfigurera systemet och förutsättningarna. Här finns en lista med de steg som måste utföras för att konfigurera avvikelsehanteringen.

1. [Aktivera kvalitets- och avvikelsehantering](#enable-qm).
1. [Konfigurera medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md).
1. [Konfigurera problemtyper](quality-problem-types.md).
1. [Konfigurera karantänzoner](quality-quarantine-zones.md).
1. [Konfigurera diagnostyper](quality-diagnostic-types.md).
1. [Konfigurera funktioner](quality-operations.md).
1. Valfritt: [Konfigurera kvalitetsavgifter](quality-charges.md).

När konfigurationen är klar kan du börja skapa och bearbeta avvikelser. Mer information om hur du skapar och arbetar med avvikelser finns i [Skapa och bearbeta avvikelser](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
