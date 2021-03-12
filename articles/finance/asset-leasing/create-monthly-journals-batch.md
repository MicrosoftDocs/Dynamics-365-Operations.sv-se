---
title: Skapa månadsvisa poster i redovisningsjournal i en batch
description: I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971338"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Skapa månadsvisa poster i redovisningsjournal i en batch

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras. Batchbearbetning kan användas för att skapa journalposter från flera planer. Dessa journalposter kan vara leasingbetalningar, skuldamorteringar, amortering av ROU-tillgångar samt utgifter för verkställighetskostnader. Du kan också använda batchbearbetning för att utföra den första redovisningen av flera leasingar samtidigt, eller för att skapa övergångsjusteringar för flera leasingar samtidigt.

Om du vill konfigurera ett batchjobb eller bearbeta betalningsfakturor, avskrivningar eller räntor för flera leasingar går du till **Leasing av tillgångar \> Periodisk \> Batchgenerering av journal**. I dialogrutan som visas kan du välja den plan som journalposterna ska skapas från. Du kan även ange om batchprocessen ska köras för specifika entiteter, leasinggrupper eller leasingböcker.

> [!NOTE]
> Efterföljande transaktioner, till exempel skuldamorteringsplaner, betalningar, avskrivningar och utgifter bokförs först efter det att första redovisningstillfället för motsvarande leasingar har bokförts.
>
> Journalposterna skapas men bokförs inte förrän du väljer kommandot **Kör**.
