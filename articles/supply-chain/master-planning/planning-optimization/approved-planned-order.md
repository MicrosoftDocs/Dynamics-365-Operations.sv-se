---
title: Godkänn planerade order
description: Det här ämnet beskriver godkännande av planerade order som stöds i planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c29ede7ad8916a97b4a04b68f41961f79810e0c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983579"
---
# <a name="approve-planned-orders"></a>Godkänn planerade order

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du uppdaterar status för planerade order i planeringsoptimering.

Observera att godkännande av planerade order är ett valfritt steg, på vägen för att skapa en bekräftad order från en planerad order. Du rekommenderas att godkänna ändrade planerade order, annars ignoreras dessa ändringar och skrivs över vid nästa planeringskörning.

![Planerat orderflöde](media/approved-planned-orders-1.png)

Fältet **Status** hjälper dig att spåra dina framsteg med följande värden:

- **Obearbetad:** När huvudplaneringen genererar planerade order, har planerade order statusen *Obearbetad*. Planerade order med denna status raderas vid nästa planeringskörning.
- **Slutfört:** om du väljer att inte bekräfta en planerad order kan du ändra statusen till *slutförd* för att indikera att du har slutfört utvärderingen av den planerade ordern. Observera att statusen *obearbetade* och *slutförd* behandlas på samma sätt i systemet.
- **Godkänd:** om du vill fortsätta redigera eller planera att bekräfta en planerad order ändrar du statusvärdet till *godkänd* . Planerade order med status *godkänd* anses vara fasta och förväntad leverans av huvudplaneringen, så att de inte ändras eller tas bort under en senare huvudplaneringskörning. För att uppnå detta kopierar planeringslogiken de *godkända* planerade orderna från den gamla planversionen till den nya planversionen under huvudplaneringen. Observera att *godkända* planerade order endast behandlas som leverans inom den specifika huvudplanen.

Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder** och **Planerad överföring**.
