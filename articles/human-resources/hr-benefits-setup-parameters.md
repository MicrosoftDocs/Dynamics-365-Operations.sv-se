---
title: Ställ in parametrar för hantering av förmåner
description: Konfigurera parametrar för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010607"
---
# <a name="set-benefits-management-parameters"></a>Ställ in parametrar för hantering av förmåner

[!include [banner](includes/preview-feature.md)]

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
   | **Årlig löneökning** | Anger om man automatiskt ska beräkna beloppet för **Årlig inkomst av förmåner** i **Information om anställningsförmånen**. Den är baserad på medarbetarens **lönesats för fast kompensation**, **genomsnittliga timmar** och **lönefrekvens**.</br></br>**Genomsnittliga timmar** x **fast lönesats** x **lönefrekvens** (# av löneperioder) = **Årlig inkomst av förmåner** </br></br>Om något värde i fälten **Genomsnittliga timmar**, **Fast lönesats** eller **Lönefrekvens** ändras, beräknar systemet automatiskt om anställdas belopp för **Årlig inkomst av förmåner** baserat på de ändrade värdena. Systemet skapar en post för **Gäller från** för att identifiera exakt datum och tid för ändringen. Du kan redigera beloppet **Årlig inkomst av förmåner** om det behövs. |
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
