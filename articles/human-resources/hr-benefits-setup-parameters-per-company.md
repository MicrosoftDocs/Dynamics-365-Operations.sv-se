---
title: Konfigurera parametrar för förmånshantering per företag
description: Konfigurera parametrar för förmånshantering per företag i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2c564f0dfd1cbe44566269c97218450fedf2173
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057632"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Konfigurera parametrar för förmånshantering per företag

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

För varje organisation som erbjuder förmåner måste du konfigurera inställningar för förmånsbekräftelsemeddelanden.

## <a name="configure-confirmation-email-settings"></a>Konfigurera e-postinställningar för bekräftelse

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.

2. På fliken **Hantering av förmåner**, ange värden för följande fält: 

   | Fält | beskrivning |
   | --- | --- |
   | **Skicka bekräftelsemeddelande** | När den här funktionen är aktiverad skickas ett e-postmeddelande till medarbetarna när de checkar ut från förmånsanmälan i medarbetarnas självbetjäning. |
   | **Mall för bekräftelsemeddelande** | Välj den organisations-e-postmall som du vill använda när du skickar anmälningsbekräftelsen. Om du inte väljer en mall skickas följande allmänna e-postmeddelande:<br><br>%EmployeeFirstName%.<br><br>Grattis! Du har slutfört en förmånsanmälan.<br><br>Tack<br><Company/Org name> förmåner. |
   | **E-postavsändarens standardadress** | E-postadressen som ska användas när bekräftelsemeddelandet skickas. |

3. Välj **Spara**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]