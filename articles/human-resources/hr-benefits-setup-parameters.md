---
title: Ställ in parametrar för hantering av förmåner
description: Konfigurera parametrar för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229773"
---
# <a name="set-benefits-management-parameters"></a>Ställa in parametrar för förmånshantering

Innan du kan ställa in tjänstledighetsplaner i Microsoft Dynamics 365 Human Resources måste du konfigurera parametrar för hantering av förmåner. Dessa parametrar ställer in standardvärden, orsakskoder och andra alternativ.

## <a name="configure-general-parameters"></a>Konfigurera allmänna parametrar

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.

2. På fliken **Allmänt**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Land/region** | Fältet **land/region** bestämmer visningsordningen för postnummer och stater. Det valda landet visas först i den nedrullningsbara listan. |
   | **Orsakskod för anmälan** | Välj en standardorsakskod som ska användas när medarbetares planer skapas när du öppnar registreringsprocessen. |
   | **Orsakskod för annullering** | Orsakskoden som ska användas när en förmånsplanen för medarbetare annulleras. Den visas i en dialogruta under annulleringsprocessen. Användare kan ändra **Orsakskod för annullering** vid behov. |
   | **Öppna orsakskod igen** | Orsakskoden som ska användas när en förmånsplanen för medarbetare öppnas igen. Den visas i en dialogruta under annulleringsprocessen. Användare kan ändra **Orsakskod för öppnas igen** vid behov. | 
   | **Orsakskod för livshändelse** | Orsakskoden som ska användas när en livshändelse inträffar. |
   | **Orsakskod för prisändring** | Orsakskoden som ska användas vid annullering och öppnande av en förmånsplan för medarbetare under uppdateringsprocessen av prisändringen. Den visar vilka poster som ändrades under uppdatering av prisändring. |
   | **Berättigad till nyanställning** | Anger om nya anställningar är berättigade. |
   | **Period för ny anställningsanmälan** | Den tidsperiod då den nya anställningsanmälan är tillåten.</br></br>**Obs**! den här inställningen åsidosätter eventuella nya anställningsperioder för anställningsanmälan som du ställer in i berättiganderegler för planen. | 
   | **Livshändelser har aktiverats** | Aktiverar livshändelser. |
   | **Dölj formulären för tidigare förmåner** | Gör att du kan dölja äldre förmånsformulär. |

3. Välj **Spara**.

## <a name="configure-employee-self-service-parameters"></a>Konfigurera anställdas självbetjäningsparametrar

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **parametrar**.

2. På fliken **Självbetjäning för medarbetare** ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Förmånsverifiering** | Verifieringstext under utcheckningen från självbetjäningen för förmåner. |
   | **Välj befullmäktigade automatiskt** | Anger om man automatiskt ska välja beroende och stödmottagare baserat på deras berättigande till planalternativ. |

3. Välj **Spara**.
