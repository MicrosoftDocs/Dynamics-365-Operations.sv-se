---
title: Skapa disponeringsalternativ
description: Täckningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program.
author: andreabichsel
ms.date: 06/25/2021
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 447317d0e9cb23bea21dae448048d05a3d989c89df17e4b8ea836201c20aefff
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741439"
---
# <a name="create-coverage-options"></a>Skapa disponeringsalternativ

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Disponeringsalternativen avgör vem som ska omfattas eller hur mycket täckning som är tillgänglig i en försäkringsplan. För en medicinsk plan kan det till exempel bara finnas ett alternativ **endast medarbetaren**, ett alternativ **medarbetare + 1** och alternativet **familj**. För life insurance kan du erbjuda täckning för **1 x lön** eller **2 x lön**.

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
   | **Status** | Status för omfattningsalternativ. Om omfattningsalternativets status är inaktiverat kan omfattningsalternativet inte väljas på plantyper. |
   | **Procent** | Procentbeloppet. Det här fältet är bara aktivt om % x lön har valts i fältet Disponeringskod. |
   | **Divisor** | Divisorn som ska användas i beräkningen när du väljer disponeringskoden % x lön. |
   | **Lägsta procentandel** | Den lägsta procentsatsen när du väljer koden för procent disponeringskoden. |
   | **Högsta procentandel** | Den högsta procentsatsen när du väljer koden för procent disponeringskoden. |

4. Under **Berättigandealternativ för personlig kontakt**, bifoga lämpligt alternativ för personliga kontakters valbarhet till varje täckningsalternativ.

5. Under **Självbetjäning**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Tillåt medarbetartilläggsbelopp** | Anger om medarbetare ska kunna ändra bidragsbeloppet för självbetjäning för förmåner när de väljer förmåner. Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det bidragsbelopp som medarbetaren registrerar sig på självbetjäning för förmåner. |
   | **Tillåt medarbetarförsäkringsbelopp** | Anger om medarbetare ska kunna ändra försäkringsbeloppet för självbetjäning för förmåner när de väljer förmåner. Om du markerar den här kryssrutan kommer systemet att beräkna förmånplanparametrar baserat på det försäkringsbelopp som medarbetaren registrerar sig på i Självbetjäning för medarbetare. |

6. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
