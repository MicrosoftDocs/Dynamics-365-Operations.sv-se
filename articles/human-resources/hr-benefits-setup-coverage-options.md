---
title: Skapa omfattningsalternativ
description: ''
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010544"
---
# <a name="create-coverage-options"></a>Skapa omfattningsalternativ

[!include [banner](includes/preview-feature.md)]

Omfattningsalternativ i Microsoft Dynamics 365 Human Resources är täckningsgrad för en deltagares val i en förmånsplan eller ett program, t.ex. endast medarbetare för en sjukförsäkringsplan eller 2x lön för en livförsäkringsplan. När du har definierat alternativen för förmånsdisponeringen kan du använda dem igen och du kan associera ett alternativ till en eller flera planer.

När omfattningsalternativ har definierats kopplar du omfattningsalternativen till en förmånsplantyp. Plantypen associeras sedan med en förmånsplan eller ett program. Omfattningsalternativ som är kopplade till en plantyp blir tillgängligt för alla planer som skapas med den aktuella plantypen. 

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Omfattningsalternativ**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Omfattningsalternativ** | Ett unikt namn på omfattningsalternativ. |
   | **Beskrivning** | Ange en beskrivning av omfattningsalternativet. |
   | **Omfattningskod** | Täckningskoder tilldelar minimi- och maximibelopp för varje stödberättigad persontyp. En variantkod anger vem som täcks av eller hur mycket täckningsbelopp som tillåts för en plantyp. Du kan uttrycka beloppet för täckningen som ett dollarbelopp eller en procentsats. Exempel:</br></br>- **Emp+ 1** – för att kvalificeras måste medarbetaren ha ett beroende valt (om fler än en har valts, de är inte längre kvalificerade).</br></br>- **Emp+familj** – som ska kvalificeras måste medarbetaren ha minst två beroenden valda. |
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
