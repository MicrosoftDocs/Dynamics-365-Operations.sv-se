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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805668"
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