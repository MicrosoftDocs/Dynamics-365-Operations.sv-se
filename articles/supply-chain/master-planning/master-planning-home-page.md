---
title: "Startsida för Huvudplanering"
description: "Med huvudplanering kan ett företag fastställa och balansera sitt framtida behov av råmaterial och sin kapacitet att uppfylla företagets mål."
author: YuyuScheller
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a24f75bf7e27702505d8a61ae3db83d03fe4a933
ms.openlocfilehash: a2e91cd2b72ffed78669fe3cc83b141db6f26aa2
ms.contentlocale: sv-se
ms.lasthandoff: 11/29/2017

---

# <a name="master-planning-home-page"></a>Startsida för Huvudplanering

[!include[banner](../includes/banner.md)]


Det huvudplanering i grund och botten gör är att låta företag fastställa och balansera sitt framtida behov av råmaterial och sin kapacitet att uppfylla företagets mål. Huvudplanering utvärderar följande: 

-  Vilka råmaterial och vilken kapacitet finns att tillgå i nuläget? 
-  Vilka råmaterial och vilken kapacitet krävs för att slutföra produktionen? Vad måste exempelvis tillverkas, köpas, överföra eller sparas som säkerhetslager innan man kan slutföra produktionen?

Huvudplaneringen använder denna information för att beräkna behoven och skapa planerade order.

Det finns tre processer för huvudplanering:

-  **Huvudplanering** - Huvudplanen beräknar nettobehoven. Den är baserad på aktuella, faktiska order och gör det möjligt för företag att styra lagerpåfyllningen på kortfristig, daglig basis. En annan term som beskriver den är det *nettobehovsplan*. Mer information finns i [Huvudplanering](master-plans.md). 

-  **Prognosplanering** -Prognosschemat beräknar bruttobehoven. Den baseras på framtida prognoser och gör det möjligt att genomföra långsiktig planering av material och kapacitet. Mer information finns i [Prognosplanering](introduction-demand-forecasting.md). 

-  **Koncernintern huvudplanering** -Den koncerninterna huvudplanen beräknar nettobehov över juridiska personer. Den sammanför tillgång och efterfrågan mellan företag inte bara för kortfristig, konkret tillgång och efterfrågan utan även för långsiktig, planerad (dvs. ännu inte bekräftad) tillgång och efterfrågan. Mer information finns i [Koncernintern huvudplanering](https://mbspartner.microsoft.com/AX/CourseOverview/1276)  (eLearning) (kräver CustomerSource-konto). 

Företag kan ändra planresultatet. De kan köra regenerativ, nettoförändring eller båda. Regenerativa planer uppdaterar alla krav, medan nettoförändringsplaner endast uppdaterar planen för artiklar med nya behov som har kommit in sedan den senaste schemaläggningskörningen.

Huvudplaneringsplaner innebär vanligen på kort sikt, vilket kan vara allt från en vecka till sex månader. Modulen Huvudplanering bestämmer vilka tillgångs- (material) och kapacitetsbehov (resurser) som uppfyller aktuell efterfrågan (nettobehov). I de flesta företag förlängs detta till att omfatta den längsta ackumulerade ledtiden bland de produkter som ska tas emot.

## <a name="learning-map"></a>Inlärningskarta

Följande utbildningsöversikt anger de huvudsakliga koncept och uppgifter som utgör ramverket för huvudplaneringsmodulen. Klicka på länkarna i avsnittet [Snabblänkar](#quick-links) för information om hur du använder modulen.

[![Utbildningsöversikt för huvudplanering](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Snabblänkar
|      |   |
|------|---|
|        [Huvudplaner](master-plans.md)       |     [Generera en begränsad plan](./tasks/constrained-plan.md)  |
| [Skapa en materialplan för samprodukter](./tasks/create-material-plan-co-products.md)   |  [Huvudplanering och multisitefunktioner](master-plan-multisite-functionality.md)  |
| [Skapa en koncernintern plan](./tasks/create-intercompany-plan.md) | [Översikt för efterfrågeprognosticering](introduction-demand-forecasting.md)  | 
|[Reduceringsnycklar](reduction-keys.md)| [Grundläggande om huvudplanering](https://mbspartner.microsoft.com/AX/CourseOverview/1275) (eLearning) (kräver CustomerSource-konto)     |
|  [Huvudplanering för processtillverkning](https://mbspartner.microsoft.com/D365E/CourseOverview/1514) (eLearning) (kräver CustomerSource-konto) | [Koncernintern huvudplanering](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (kräver CustomerSource-konto)|
                                  
## <a name="additional-resources"></a>Ytterligare resurser

### <a name="roadmaps"></a>Översikter
Öppna [översikten till Microsoft Dynamics 365](https://roadmap.dynamics.com/) för att visa vilka nya funktioner som har lanserats och nya funktioner under utveckling.

### <a name="blogs"></a>Bloggar
Du hittar åsikter, nyheter och annan information om huvudplanering och andra lösningar i [teambloggen Dynamics AX Manufacturing R&D](https://blogs.msdn.microsoft.com/axmfg) och [teambloggen Supply Chain Management in Dynamics AX R&D](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Uppgiftsguider
Mer hjälp är tillgänglig som uppgiftsguider i Finance and Operations. Klicka på knappen **Hjälp** på valfri sida för att få åtkomst till uppgiftsguiderna.

### <a name="webinars"></a>Webbseminarier
[Använd Azure-maskininlärning för efterfrågeprognosticering](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)





