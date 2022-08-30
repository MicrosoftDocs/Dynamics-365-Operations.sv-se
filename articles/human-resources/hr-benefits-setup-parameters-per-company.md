---
title: Konfigurera parametrar för förmånshantering per företag
description: I denna artikel beskrivs hur du konfigurerar parametrar för förmånshantering per företag i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 8/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f3f8625a8ebbe6812d2f051649ff2a608ed4b54
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323911"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Konfigurera parametrar för förmånshantering per företag


För varje organisation som erbjuder förmåner måste du konfigurera inställningar för förmånsbekräftelsemeddelanden.

## <a name="configure-confirmation-email-settings"></a>Konfigurera e-postinställningar för bekräftelse

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.

2. På fliken **Hantering av förmåner**, ange värden för följande fält: 

   | Fält | beskrivning |
   | --- | --- |
   | **Skicka bekräftelsemeddelande** | När den här funktionen är aktiverad skickas ett bekräftelsemeddelande via e-post till medarbetarna när dessa checkar ut från förmånsregistreringen i **medarbetarnas självbetjäning**. |
   | **Mall för bekräftelsemeddelande** | Välj den organisations-e-postmall som du vill använda när du skickar anmälningsbekräftelsen. Om du inte väljer en mall skickas följande allmänna e-postmeddelande:<br><br>%EmployeeFirstName%.<br><br>Grattis! Du har slutfört en förmånsanmälan.<br><br>Tack<br><Company/Org name> förmåner. |
   | **E-postavsändarens standardadress** | E-postadressen som ska användas när bekräftelsemeddelandet skickas. |

3. Välj **Spara**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
