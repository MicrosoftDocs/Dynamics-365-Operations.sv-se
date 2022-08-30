---
title: Skapa disponeringsalternativ
description: Detta ämne beskriver täckningsalternativen i Microsoft Dynamics 365 Human Resources för en deltagares val i en förmånsplan eller ett program.
author: twheeloc
ms.date: 08/24/2021
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
ms.openlocfilehash: f9c107e31e58ba1302cd02e2e82aa405dda0fdef
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337087"
---
# <a name="create-coverage-options"></a>Skapa disponeringsalternativ


Disponeringsalternativen avgör vem som ska omfattas eller hur mycket täckning som är tillgänglig i en försäkringsplan. För en medicinsk plan kan till exempel alternativen **Endast medarbetare**, **Medarbetare + 1** samt **Familj** finnas. För life insurance kan du erbjuda täckning för **1 x lön** eller **2 x lön**.

När alternativ för förmånstäckning har definierats kan du återanvända dem. Du kan associera ett alternativ med en eller flera planer.

> [!IMPORTANT]
> När du definierar omfattningsalternativ kopplar du dem till en förmånsplantyp. Plantypen associeras sedan med en förmånsplan eller ett program. Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella typen.

## <a name="create-coverage-options"></a>Skapa disponeringsalternativ
1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Omfattningsalternativ** | Ett unikt namn på omfattningsalternativ. |
   | **Beskrivning** | Ange en beskrivning av omfattningsalternativet. |
   | **Omfattningskod** | Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp. En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp. Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats. Exempel:<ul><li>**Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</li><li>**Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda.</li></ul> |
   | **Maximalt antal** | Det högsta antalet beroenden. |
   | **Status** | Status för omfattningsalternativ. Om statusen för alternativet Omfattning är **inaktiverad** kan alternativet Omfattning inte väljas för plantyper. |
   | **Procent** | Procentbeloppet. Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod. |
   | **Divisor** | Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön. |
   | **Lägsta procentandel** | Den lägsta procentsatsen när du väljer koden för procent disponeringskoden. |
   | **Högsta procentandel** | Den högsta procentsatsen när du väljer koden för procent disponeringskoden. |

4. Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.

5. Under **Självbetjäning**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Tillåt medarbetartilläggsbelopp** | Anger huruvida medarbetare ska kunna ändra bidragsbeloppet för Självbetjäning för förmåner när de väljer förmåner. Om du markerar den här kryssrutan kommer systemet att beräkna parametrar för förmånsplan baserat på det bidragsbelopp som medarbetaren anger i självbetjäningen för förmåner. |
   | **Tillåt medarbetarförsäkringsbelopp** | Anger om medarbetare ska kunna ändra disponeringsbeloppet för självbetjäningen för förmåner när de väljer förmåner. Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare. |

6. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
