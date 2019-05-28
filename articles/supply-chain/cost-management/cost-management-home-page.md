---
title: Startsida för kostnadshantering
description: Med kostnadshantering kan du hantera värdering och redovisning av råmaterial, färdiga varor, delvis färdiga varor och tillgångar i pågående arbete.
author: AndersGirke
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd94ae4c5ea855139fd1c41060de7db455ffab06
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557665"
---
# <a name="cost-management-home-page"></a>Startsida för kostnadshantering

[!include [banner](../includes/banner.md)]

Med [kostnadshantering (video)](https://www.youtube.com/watch?v=vXzlC-mOBcg&feature=youtu.be) kan du hantera värdering och redovisning av råmaterial, färdiga varor, delvis färdiga varor och tillgångar i pågående arbete. Det är processen för att definiera, hantera och rapportera [lagerredovisning](cost-object.md) och [tillverkningsredovisning](bom-calculations.md).

Du kan definiera kostnadsprinciper inom följande områden: 
-  [Fördefinierad kostnad](costing-versions.md)
-  [Lagerredovisning](cost-object.md)
-  [Tillverkningsredovisning](bom-calculations.md)
-  [Indirekt kostnadsredovisning](costing-sheets.md)
-  [Redovisningsintegrering](production-order-cost-analysis.md)

Exempelvis kan du definiera vilka modeller för lagervärdering, t ex [FIFO](fifo-physical-value-marking.md), [viktat medelvärde](weighted-average-physical-value-marking.md), [standardkostnad](prerequisites-standard-costs.md), eller [rörligt genomsnitt](moving-average.md) som ska tillämpas på produkter i [artikelmodellgrupp](../inventory/reserve-inventory-quantities.md) vid redovisning av lager.

Du når lagerredovisning och tillverkningsredovisning från arbetsytorna **kostnadsadministration** och **kostnadsanalys**. Dessa arbetsytor innehåller en omfattande översikt över aktuell status, prestationsindikatorer (KPI: er) och identifiering av avvikelse. 

Tillverkningsredovisning låter dig hantera [kostnadsberäkning för jobborder](production-order-cost-analysis.md) i tillverkningsorder och batchorder samt [kostnadskalkylering med automatisk lageravräkning](backflush-costing.md) i lean manufacturing.

[Innehållet i Power BI kostnadshantering](../../dev-itpro/analytics/cost-management-content-pack.md) ger ledare inblick i lager och PIA-lager (projekt i arbete), samt hur kostnader flödar genom dem per kategori och över tid. Informationen kan också användas som ett detaljerat komplement till bokslutet.

### <a name="additional-resources"></a>Ytterligare resurser

#### <a name="whats-new-and-in-development"></a>Vad är nytt och under utveckling

Öppna [översikten till Microsoft Dynamics 365](https://roadmap.dynamics.com/) för att visa vilka nya funktioner som har lanserats och nya funktioner under utveckling. 

#### <a name="white-paper"></a>Dokumentation
[BOM calculation by using a costing sheet](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/white-papers/365operationsbomcalsheet) beskriver hur man ställer upp ett kostnadsredovisningsblad med material och tillverkning och hur inställningar påverkar resultat från strukturlisteberäkningar. För att bättre förstå ämnena tillhandahålls konkreta scenarier och data som visar effekten av olika inställningar och konfigurationer. Vi tror inte att du kommer att använda alla de här scenarierna eftersom dokumentet inte innehåller tillräckligt med information för att konfigurera dem. Men om du har grundläggande kunskaper kan du ändå försöka öppna (spela upp) uppgiftsguiderna som beskrivs nedan i den ordning de presenteras. Använd den kunskap som du har fått från det här dokumentet för att analysera strukturlisteberäkningar. 

-  [Skapa en färdig produkt](tasks/create-finished-product-2016-02.md)
-  [Skapa en halvfärdig produkt](tasks/create-semi-finished-product-2016-02.md)
-  [Skapa råmaterial](tasks/create-raw-materials-2016-02.md)
-  [Skapa strukturlistor](tasks/create-boms-2016-02.md)
-  [Skapa rutter](tasks/create-routes-2016-02.md)
-  [Beräkna en strukturlista med en enda nivå (februari 2016)](tasks/calculate-bom-single-level-structure-2016-02.md)
-  [Beräkna en strukturlista genom att använda en enda nivå (februari 2016)](tasks/calculate-bom-multilevel-structure-2016-02.md)


#### <a name="blogs"></a>Bloggar
Du hittar åsikter, nyheter och annan information om kostnadshantering i [teambloggen Dynamics AX Manufacturing R&D](https://blogs.msdn.microsoft.com/axmfg) och [teambloggen Supply Chain Management in Dynamics AX R&D](https://blogs.msdn.microsoft.com/dynamicsaxscm). En del av inläggen skrevs för den föregående versionen av kostnadshantering, men samma begrepp gäller fortfarande och procedurerna är likartade i den aktuella versionen.

#### <a name="task-guides"></a>Uppgiftsguider
Mer hjälp är tillgänglig som uppgiftsguider i Finance and Operations. Klicka på knappen Hjälp på valfri sida för att få åtkomst till uppgiftsguiderna.

