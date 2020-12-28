---
title: Ställa in förmånshantering och medarbetarnas självbetjäningsparametrar för alla företag
description: Konfigurera parametrar för förmånshantering och medarbetarnas självbetjäning i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692707"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Ställa in förmånshantering och medarbetarnas självbetjäningsparametrar för alla företag

Innan du kan konfigurera förmånsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner. Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ. 

## <a name="configure-general-parameters"></a>Konfigurera allmänna parametrar

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Dela personalparametrar**.

2. På fliken **Hantering av förmåner**, ange värden för följande fält:

   | Fält | beskrivning |
   | --- | --- |
   | **Land/region** | Fältet **land/region** bestämmer visningsordningen för postnummer och stater. Det valda landet visas först i den nedrullningsbara listan. |
   | **Orsakskod för anmälan** | Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen. |
   | **Orsakskod för annullering** | Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras. Den visas i en dialogruta under annulleringsprocessen. Användare kan ändra **Orsakskod för annullering** vid behov. |
   | **Öppna orsakskod igen** | Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen. Den visas i en dialogruta under annulleringsprocessen. Användare kan ändra **Orsakskod för öppnas igen** vid behov. | 
   | **Orsakskod för livshändelse** | Orsakskoden som ska användas när en livshändelse inträffar. |
   | **Orsakskod för prisändring** | Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen. Den visar vilka poster som ändrades under uppdatering av prisändring. |
   | **Årlig inkomst av förmåner** | Gör att du kan ställa in ett belopp för **Årslön** för en medarbetare. Personal kommer att använda beloppet **Årslön** vid fastställande av täckningsbelopp, istället för det årliga beloppet för fast ersättning. |
   | **Berättigad till nyanställning** | Anger om nya anställningar är berättigade. |
   | **Period för ny anställningsanmälan** | Den tidsperiod då den nya anställningsanmälan är tillåten.</br></br>**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen. |
   | **Standardvärde för lönefrekvens** | Standard lönefrekvensen som används när nya arbetare läggs till. |
   | **Livshändelser har aktiverats** | Aktiverar livshändelser. |
   | **Dölj formulären för tidigare förmåner** | Gör att du kan dölja äldre förmånsformulär. |
   | **Förmånsverifiering** | Verifieringstext under utcheckningen från självbetjäningen för förmåner. |
   | **Välj befullmäktigade automatiskt** | Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ. |

3. Välj **Spara**.

## <a name="configure-employee-self-service-parameters"></a>Konfigurera anställdas självbetjäningsparametrar

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.

2. På fliken **Hantering av förmåner**, ange värden för följande fält:

   | Fält | beskrivning |
   | --- | --- |
   | **Förmånsverifiering** | Verifieringstext under utcheckningen från självbetjäningen för förmåner. |
   | **Välj befullmäktigade automatiskt** | Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ. |

3. Välj **Spara**.


