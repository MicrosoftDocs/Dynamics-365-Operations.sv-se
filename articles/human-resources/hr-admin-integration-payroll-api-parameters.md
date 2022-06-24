---
title: Parametrar för löneintegrering
description: Detta ämne beskriver Dynamics 365 Human Resources-parametrar för löneintegrering.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d784909fc8c5fa05557566b62b19802cd2acece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896117"
---
# <a name="payroll-integration-parameters"></a>Parametrar för löneintegrering


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Innan du använder löneintegrering för Dynamics 365 Human Resources måste du konfigurera de parametrar som beskrivs i detta ämne.

## <a name="enable-payroll-address"></a>Aktivera löneadress

Om du vill kunna använda löneadressen måste du aktivera den från [formuläret för delade parametrar](hr-setup-shared-parameters.md) på fliken Löneintegrering.

## <a name="define-the-identification-type"></a>Definiera identifieringstypen

Om du vill visa ID:t för identifiering i [entiteten för lönemedarbetare](hr-admin-integration-payroll-api-payroll-employee.md) måste du konfigurera [parametrar för personalresurser](hr-setup-shared-parameters.md) för respektive företag.

1. I arbetsytan **Kompensationshantering**, under länkarna, väljer du **Parametrar för personal**. 
2. Ange värdet för följande fält i fliken **Löneintegrering**.

| Fält | beskrivning |
| --- | --- |
| Använd identifieringstyper i lönebearbetning | När detta alternativ är markerat visas det valda typ-ID:t i entiteten för lönemedarbetare. |
| ID-typ | ID-typen som ska visas i fältet **mshr_payrollemployeeentityid** i [entiteten för lönemedarbetare](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
