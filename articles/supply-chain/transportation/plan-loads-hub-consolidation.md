---
title: Planera beläggning med hjälp av navkonsolidering – översikt
description: Den här artikeln beskriver funktionen för att konsolidera försändelser i ett nav när du levererar varor från olika lagerställen till samma kund eller när du tar emot varor från flera leverantörer på samma lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d61527113746e76889d097e963f70ced24fd241
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016434"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Planera beläggning med hjälp av navkonsolidering – översikt

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver funktionen för att konsolidera försändelser i ett nav när du levererar varor från olika lagerställen till samma kund eller när du tar emot varor från flera leverantörer på samma lagerställe.

Det kan vara användbart att konsolidera försändelser i ett nav när du levererar varor från olika lager till samma kund eller när varorna levereras från flera leverantörer till samma lagerställe.

## <a name="building-loads"></a>Bygga laster
Innan du kan använda navkonsolidering måste du aktivera alternativet **Transportplanering** på sidan **Parametrar för transporthantering**. Du måste också skapa nav där konsolideringen ska utföras. Följande diagram visar ett exempel på navkonsolidering. I det här fallet ska försäljningsorder från olika lagerställen till samma kund. Grundläggande laster skapas utifrån försäljningsorder på vanligt sätt med hjälp av sidan **Workbench för lastplanering**. Om du vill konsolidera två laster i ett nav innan de levereras till kunden, gå till sidan **Workbench för lastplanering** , till fältet **Transport** och välj **Navkonsolidering**. Om du väljer rätt nav för varje last kommer lasterna att ha navet som avlämningsmål. Du kommer även att ha två "rader för transportförfrågan" i avsnittet **Tillgång och efterfrågan** på sidan **Workbench för lastplanering**. Du kan sedan lägga till dessa två rader till en ny last. Den nya lasten kommer att ha båda försäljningsorderraderna och kommer även att ha navet som hämtningsadress och kunden A som avlämningsmål. De tre lasterna är sedan klara för klassificering och kan skickas som andra laster. Du kan välja vilket transportföretag systemet ska föreslå för varje last. [![Hubbkonsolidering](./media/hubconsol.jpg)](./media/hubconsol.jpg) Du kan även använda samma metod för att konsolidera laster för flera överföringsorder. I detta fall är kunden A i föregående diagram ett lagerställe. Alternativt kan du konsolidera laster för flera inköpsorder, där lasterna levereras från olika leverantörer till samma lagerställe. Du kan ha fler än ett konsolideringsnav och konsolidera i flera nav för fler laster som kommer från olika lagerställen. När du skapar dina grundlaster och använder navkonsolideringsalternativet kan du skapa nya laster med hjälp av konsoliderade rader för transportförfrågan. Klassificera och skicka sedan dina laster.



