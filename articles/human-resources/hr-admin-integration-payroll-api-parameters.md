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
ms.openlocfilehash: 0c489b99d5d05ddac46d222e701512288aeb10583a5e829212e0e1c924622f16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712083"
---
# <a name="payroll-integration-parameters"></a>Parametrar för löneintegrering

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
