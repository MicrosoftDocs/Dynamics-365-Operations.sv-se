---
title: Konfigurera självbetjäning för medarbetare
description: I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i Självbetjäning för medarbetare.
author: twheeloc
ms.date: 12/06/2021
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
ms.openlocfilehash: cdc82c23635cc99c37aa770b996d9d2df43f5059
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324651"
---
# <a name="configure-employee-self-service"></a>Konfigurera självbetjäning för medarbetare

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I Microsoft Dynamics 365 Human Resources kan du konfigurera paneler för navigering på högsta nivå i **Självbetjäning för medarbetare**. Paneler för förmånsplaner dirigerar användare till förmånsplaner som de berättigar till.

## <a name="set-up-a-benefit-plans-tile"></a>Ställa in panel för förmånsplan

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.

2. Välj fliken **Inställning av paneler för förmånsplaner** och välj **Ny**.

3. Ange värden för de följande fälten.

   | Fält | Beskrivning |
   | --- | --- |
   | **Kod för plantyp** | Plantypen som visas när den här panelen väljs i **Självbetjäning av förmåner**. |
   | **Panel-ID** | Unik identifierare för panelen. |
   | **Etikettext för panel** | Den text som visas för panelen i **Självbetjäning av förmåner**. |
   | **Beskrivning** | En beskrivning av panelen. |
   | **Bakgrundsbild för panel** | URL till den bild som ska användas för panelen (valfritt). |
   | **Spåra öppen anmälan** | Välj det här alternativet om du vill spåra det öppna anmälningsförloppet för den här plantypen. Du kanske till exempel har planer som skapats där **Plantyp = Övrigt**. Dessa planer kan vara valfria planer som du inte vill spåra anmälningsförloppet för. Om du inte väljer den här plantypen ignoreras planer av dessa typer när du spårar anmälningsförloppet eller när den slutförts på fliken **Öppen anmälan**. Den här inställningen gäller för den plantyp som valts för alla perioder och juridiska personer. |

4. Välj **Spara**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Inställning av panel för flexkreditplan

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Medarbetarens självbetjäningsparametrar**.

2. Välj fliken **Inställning av panel för flexkreditplan** och välj **Ny**.

3. Ange värden för de följande fälten.

   | Fält | Beskrivning |
   | --- | --- |
   | **ID för förmånens kredit** | Planen för flexkreditprogram som visas när den här panelen väljs i **Självbetjäning av förmåner**. |
   | **Panel-ID** | Unik identifierare för panelen. |
   | **Etikettext för panel** | Den text som visas för panelen i **Självbetjäning av förmåner**. |
   | **Beskrivning** | En beskrivning av panelen. |
   | **Bakgrundsbild för panel** | URL till den bild som ska användas för panelen (valfritt). |
   | **Spåra öppen anmälan** | Välj det här alternativet om du vill spåra det öppna anmälningsförloppet för den här plantypen. Du kanske till exempel har planer som skapats där **Plantyp = Övrigt**. Dessa planer kan vara valfria planer som du inte vill spåra anmälningsförloppet för. Om du inte väljer den här plantypen ignoreras planer av dessa typer när du spårar anmälningsförloppet eller när den slutförts på fliken **Öppen anmälan**. Den här inställningen gäller för den plantyp som valts för alla perioder och juridiska personer. |

4. Välj **Spara**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
