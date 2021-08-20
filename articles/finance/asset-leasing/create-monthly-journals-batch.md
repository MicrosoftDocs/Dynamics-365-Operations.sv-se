---
title: Skapa månadsvisa poster i redovisningsjournal i en batch
description: I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cb03ebe316b1655b1d0ad1d2b9108c4ead7fc61f7a25b4f554b574186efa03b7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737735"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Skapa månadsvisa poster i redovisningsjournal i en batch

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du skapar journalposter i ett batchjobb för att öka effektiviteten när månadsutgifter för leasing registreras. Batchbearbetning kan användas för att skapa journalposter från flera planer. Dessa journalposter kan vara leasingbetalningar, skuldamorteringar, amortering av ROU-tillgångar samt utgifter för verkställighetskostnader. Du kan också använda batchbearbetning för att utföra den första redovisningen av flera leasingar samtidigt, eller för att skapa övergångsjusteringar för flera leasingar samtidigt.

Om du vill konfigurera ett batchjobb eller bearbeta betalningsfakturor, avskrivningar eller räntor för flera leasingar går du till **Leasing av tillgångar \> Periodisk \> Batchgenerering av journal**. I dialogrutan som visas kan du välja den plan som journalposterna ska skapas från. Du kan även ange om batchprocessen ska köras för specifika entiteter, leasinggrupper eller leasingböcker.

> [!NOTE]
> Efterföljande transaktioner, till exempel skuldamorteringsplaner, betalningar, avskrivningar och utgifter bokförs först efter det att första redovisningstillfället för motsvarande leasingar har bokförts.
>
> Journalposterna skapas men bokförs inte förrän du väljer kommandot **Kör**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
