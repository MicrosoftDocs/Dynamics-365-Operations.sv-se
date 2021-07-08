---
title: Visa, hantera och godkänna planerade order
description: Detta ämne innehåller information om hur du visar, hanterar och godkänner planerade order i planeringsoptimeringen.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 71ec26bea2063bcf8b6d302a7ece804b3ac934b3
ms.sourcegitcommit: 3673eeca1ada0f3e4ec277176515a946706f8a41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304377"
---
# <a name="view-manage-and-approve-planned-orders"></a>Visa, hantera och godkänna planerade order

[!include [banner](../../includes/banner.md)]

Detta ämne innehåller information om hur du visar, hanterar och godkänner planerade order i planeringsoptimeringen.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Visa och hantera planerade order

Du kan visa och hantera planerade order på samtliga listsidor för planerade order. Gå till någon av följande platser beroende på typen av planerade order som du vill arbeta med:

- Huvudplanering \> Arbetsytor \> Huvudplanering
- Huvudplanering \> Huvudplanering \> Planerade order
- Produktionsstyrning \> Produktionsstyrning \> Planerade produktionsorder
- Anskaffning och källa \> Inköpsorder \> Planerade inköpsorder
- Lagerhantering \> Inkommande order \> Planerade överföringar
- Lagerhantering \> Utgående order \> Planerade överföringar

## <a name="view-and-edit-the-status-of-planned-orders"></a>Visa och redigera statusen för planerade order

Du kan använda fältet **Status** för respektive order i syfte att spåra dina framsteg eller ändra hur en planerad order ska bearbetas. Följande värden för **Status** finns:

- **Ej bearbetad** – När huvudplaneringen genererar planerade order erhåller de denna status. Planerade order som innehar denna status raderas vid nästa planeringskörning.
- **Slutförd** – Denna status visar att den planerade ordern har slutförts. Om du väljer att inte bekräfta en planerad order kan du ändra dess status till *Slutförd* manuellt. Observera att systemet behandlar statusen *Ej bearbetad* och *Slutförd* på samma sätt.
- **Godkänd** – Den här statusen visar att den planerade ordern har godkänts för bekräftelse. Om du vill bekräfta en planerad order kan du ändra dess status till *Godkänd*. Om du vill behålla redigeringarna som har gjorts för en planerad order, eller om du planerar att bekräfta en planerad order, ändrar du dess status till *Godkänd*. Planerade order som har statusen *Godkänd* betraktas som fast och förväntad leverans i huvudplaneringen. De ändras eller tas därför inte bort under senare huvudplaneringskörningar. För att uppnå detta kopierar planeringslogiken de planerade order som har statusen *Godkänd* från den gamla planversionen till den nya planversionen under huvudplaneringen. Observera att planerade order med statusen *Godkänd* endast betraktas som leverans inom den specifika huvudplanen.

Om du vill ändra status för en enskild planerad order [öppnar du en listsida för planerade order](#view-planned-orders), öppnar ordern och följer sedan ett av följande steg:

- I snabbfliken **Allmänt** ändrar du värdet i fältet **Status**.
- I åtgärdsfönstret, på fliken **Planerad order** i gruppen **Process** väljer du **Ändra status**.
- För att markera ordern som godkänd väljer du **Godkänn** i åtgärdsfönstret.

Om du vill ändra status för flera planerade order samtidigt [öppnar du en listsida för planerade order](#view-planned-orders), väljer kryssrutan för varje order som du vill ändra, och följer sedan dessa steg:

- I åtgärdsfönstret, på fliken **Planerad order** i gruppen **Process** väljer du **Ändra status**.
- I åtgärdsfönstret väljer du **Godkänn** för att markera orderna som godkända.

## <a name="approve-planned-orders"></a>Godkänna planerade order

Godkännande av planerade order är ett valfritt steg på vägen för att skapa en bekräftad order från en planerad order.

I följande bild visas hur du kan använda värdet **Status** som tilldelas varje planerad order i syfte att implementera ett godkännandearbetsflöde. Om du vill implementera en godkännandeprocess justerar du värdet **Status** manuellt för varje planerad order enligt beskrivningen i det föregående avsnittet.

![Planerat orderflöde](media/approved-planned-orders-1.png)

> [!TIP]
> Vi rekommenderar att du godkänner ändrade planerade order. I annat fall ignoreras redigeringarna och skrivs över av nästa planeringskörning.

## <a name="additional-resources"></a>Ytterligare resurser

- [Bekräfta planerade order](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
