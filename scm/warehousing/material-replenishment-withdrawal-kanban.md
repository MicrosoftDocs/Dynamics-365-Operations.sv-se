---
title: "Lagerpåfyllnad med uttags-kanbans | Microsoft Docs"
description: "Det här avsnittet beskriver hur uttags-kanban används för materialpåfyllnad för tillverkning."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: abac5e05f40132844cf1817be533151cbf238d95
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="replenishment-with-withdrawal-kanbans"></a>Lagerpåfyllnad med uttags-kanbans

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur uttags-kanban används för materialpåfyllnad för tillverkning.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Arbetsflöde för materialpåfyllnad som använder uttags-kanban
-------------------------------------------------------------------

Uttags-kanban kan användas för att flytta en kanban för ett enskilt objekt mellan olika lager och produktionsplatser där material förbrukas. Uttags-kanban stöder en pull-baserad lösning för materialpåfyllnad, där en pull-signal krävs för att initiera tillförsel för en viss efterfrågan. 

I följande scenario visas pull-baserat påfyllningssystem där en pull-signal utlöser skapandet av ett kanban för att fylla på material för en produktionsprocess. 

[![Pull-signalen utlöser skapandet av en kanban för att fylla på material för en produktionsprocess](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Uttags-kanban
2.  "Från"- och "till"-kanbanplatser för arbete på lagerställe
3.  "Till"-plats och plats för produktionsinleverans för kanban
4.  Tillverkningsprocess
5.  Lagerställesarbete för kanbanplockning
6.  Lagerställen för råmaterial
7.  Lagerställe för material
8.  Lagerställe för tillverkning

I det här scenariot förbrukar tillverkningsprocessen (4) material från en plats för produktionsinleverans (3) i lagerstället för tillverkning (8). När en enhet för hantering av material (kanban) förbrukas, registreras den som tom. En påfyllnadssignal skapas för artikelns ursprung, och en ny kanban (1) skapas. I detta fall består artikels ursprung av platserna i lagerstället för material (7). Material för kanban plockas och läggs på en plats (2) på samma lagerställe. När materialet plockas är det redo att överföras från plats 2 till platsen för produktionsinleverans (3) i lagerstället för tillverkning (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Konfigurera lagerställesarbete för kanbanplockning för uttags-kanban

Om du vill aktivera plockning av råmaterial för uttags-kanban, konfigurera då påfyllnadsmallar, arbetsmallar och platsdirektiv arbetsordertypen **Kanbanplockning**. Denna arbetsordertyp stöder inte bara plockningsprocessen för uttags-kanban. Den stöder också plockningsprocessen för tillverkningskanban. Du kan dock konfigurera en separat plockningsprocess för respektive kanbantyp genom att avgränsa påfyllnadsmallar, arbetsmallar och platsdirektiv. För att avgränsa påfyllnadsmallar, arbetsmallar eller platsdirektiv, ange önskade kriterier för aktivitetstypen (**Process** eller **Överföring**) i frågorna för dessa enheter.

## <a name="configure-the-withdrawal-kanban"></a>Konfigurera uttags-kanban

Den överföringsaktivitet som används för uttags-kanban har konfigurerats som en del av en aktiverad aktivitetsplanen i ett lean-produktionsflöde. Som ett led i konfigurationen av överföringsaktiviteten måste du ange ”från”- och ”till”-platser för överföringen. När du konfigurerar överföringsaktiviteten kan du tilldela den till en kanban-regel för typen **Uttag**. Kanban-regeln anger policyer och konfigurationer för uttags-kanban. Kvantiteten för kanban definierar hur många enheter av materialhanteringsenheten som kanban har under överföringen. Den fasta kanban-kvantiteten används när fast lagerpåfyllnadsstrategi väljs. Denna kvantitet definierar hur många kanban som krävs för att förhindra att lager eller bygglager tar slut vid behovskällan. Fast kvantitet kan beräknas baserat på faktiskt behov, historisk efterfrågan samt servicenivåer. Följande två scenarier beskriver hur du hanterar materialpåfyllnad som använder uttags-kanban.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Scenario 1: Fyll på en plats för produktionsinleverans genom att använda en fast uttags-kanban

En tillverkningsprocess förbrukar ett inköpt råmaterial från en plats för produktionsinleverans som finns i lagerstället för produktion. När råmaterialet anländer från leverantören lagras det på platser i materiallagerstället. Eftersom efterfrågan på materialet anses stabilt under en period, har materiallagerstället konfigurerats i syfte att förse produktionen via ett fast antal kanban-flöde. När en kanban har förbrukats på platsen för produktionsinleverans registreras en tom signal, och en ny kanban av samma typ läggs till i flödet. 

Den tomma signalen kan konfigureras så att den utförs automatiskt när en kanban har slutförts. Den tomma signalen kan också anges som en manuell interaktion som ges från antingen en kanban-överföringstavla eller en meny en bärbar enhet. Kanban-överföringstavlan är den arbetsyta där alla aktiviteter i kanban-livscykeln hanteras. 

En påfyllnadsrad för råmaterial läggs till i en kanbanpåfyllnad för materiallagerstället när kanban skapas. I avsnittet för plockningslista på kanban-överföringstavlan kan du övervaka statusen för material och relaterade lagerställesprocesser - från påfyllnadens början till arbetsuppgiftens skapande - tills materialet finns att tillgå på ”överför från”-platsen och är redo att överföras till produktionsinleveransplatserna. Kanban kan slutföras från antingen kanban-överföringstavlan eller från en meny i den bärbara enheten. 

I det här scenariot bearbetas plockarbetet i materiallagerstället som en enda aktivitet. Överföringsaktiviteten mellan materiallagerstället och produktionslagerstället behandlas som en separat aktivitet. Den här metoden kan vara användbar om det till exempel finns en stort fysiskt avstånd mellan de två lagerställena. I det här fallet kan kanban-överföringsaktiviteten representera en lastbilslast. 

Om avståndet mellan lagerställena och platsen för produktionsinleverans är litet kan vara det mer effektivt att inkludera överföringsaktiviteten vid plockning. Sedan, när materialet plockas, kan det hämtas direkt till platsen för produktionsinleverans. Som stöd för den här processen kan du konfigurera överföringsaktiviteten så att denna slutförs automatiskt när plockningsarbetet för uttags-kanban bearbetas.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Scenario 2: Komplettera automatiskt överföringsaktiviteten när kanban-plockningsarbete bearbetas

I följande scenario konfigureras överföringsaktiviteten för uttags-kanban att överföras mellan två platser på samma lagerställe. Överföringsaktiviteten för uttags-kanban ställs in så att den fylls i automatiskt. 

[![Överföringsaktiviteten fylls i automatiskt när kanban-plockarbetet bearbetas](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Delat lagerställe för råmaterial och produktion
2.  Lagerställen för råmaterial
3.  "Från"- och "till"-kanbanplatser för arbete på lagerställe
4.  Uttags-kanban
5.  Plats för produktionsinleverans
6.  Tillverkningsprocess

När en kanban har förbrukats på platsen för produktionsinleverans rapporteras den som tom, och en ny kanban läggs till i flödet. En påfyllnadsrad läggs till i en kanban-påfyllnad när en kanban skapas. När kanban-påfyllnaden bearbetas, skapas lagerställearbete för kanban-plockning. Lagerarbetaren bearbetar arbetet för kanban-plockning och dirigeras av arbetet för att plocka material för kanban på ett lagerställe. När denna lagerarbetare bekräftar plockningen slutförs kanban automatiskt, och lagerarbetaren vägleds för att förflytta materialet till produktionsinleveransplatsen.


