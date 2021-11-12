---
title: Planeringsoptimering, utökningsbarhet
description: Det här ämnet beskriver tilläggsscenarier som stöds i planeringsoptimering.
author: ChristianRytt
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e18801a02ae9e904eb5bc597f9f61ed42c537ab9
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652088"
---
# <a name="planning-optimization-extensibility"></a>Planeringsoptimering, utökningsbarhet

[!include [banner](../../includes/banner.md)]

Det här ämnet beskriver tilläggsscenarier som är relaterade till huvudplanering och planeringsoptimering. Dessa funktioner är tillgängliga från och med Microsoft Dynamics 365 Supply Chain Management version 10.0.13.

## <a name="custom-processing-when-master-planning-is-completed"></a>Anpassad bearbetning när huvudplaneringen är klar

I det vanligaste tilläggsscenario i Planeringsoptimering utförs anpassad bearbetning efter det att planen har uppdaterats. Du kan till exempel lägga till en kolumn i tabellen för planerade orderregister (`ReqPO`), eller så kanske du vill härleda lite statistisk information från den genererade planen. Den huvudsakliga töjbarhetspunkten som möjliggör dessa scenarier är `jobCompletedSuccessfully` metoden i klassen `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Här är ett exempel på ett tillägg som ställer in ett anpassat `CstmOrderPriority` fält på den planerade ordern.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

När du lägger till anpassad logik bör du ta hänsyn till följande begränsningar och bästa metoder:

- Metoden `jobCompletedSuccessfully` anropas utanför transaktionsomfattning. Därför visas planen redan för användaren när den anpassade logiken börjar köras. Om din anpassning ställer in fler fält på planerade order är det viktigt att du låter användarna veta att värdena i dessa fält så småningom blir konsekventa (med andra ord kan de vara inställt direkt efter det att ett planeringsjobb har slutförts).
- Ett annat huvudplaneringsjobb kan starta när `jobCompletedSuccessfully` metoden anropas. Det nya jobbet kan påverka hela planen eller en del av planen. Det nya jobbet kan uppdatera eller ta bort samma planerade order eller kravtransaktioner som skapades eller uppdaterades som en del av planeringsjobbet som hanterades i `jobCompletedSuccessfully`. Uppdateringsundantag måste hanteras när händelsen utökas.
- Undvik att använda ett enda transaktionssområde när du utökar den här metoden. En enskild körning för huvudplanering kan producera miljoner kravtransaktioner och hundratals planerade order. Om alla dessa transaktioner och planerade order bearbetas inom en enskild transaktion, kommer många SQL-lås att uppstå och blockera andra planeringsprocesser. Om transaktionen hålls under längre tid skapas "register med gamla uppgifter men som behålls under viss tid" i SQL-databasen. Dessa register påverkar varje process i systemet negativt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]