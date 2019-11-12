---
title: Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten
description: I det här avsnittet beskrivs processen för att slutföra färdiga produkter i en tillverkningsorder till lagret när en registreringsskylt kontrollerar platsen.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572139"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten 

Processen som kallas rapportera som färdig slutför färdiga produkter i en tillverkningsorder till lagret. Om den färdiga produkten är aktiverad för de avancerade lagerprocesserna rapporteras produkten som färdig till en plats som kallas för produktionsutleveransplats. Information om hur du ställer in produktionsutleveransplats finns i [Plats för produktionsutleverans](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location)plats för produktions utmatning.

Du måste välja ett befintligt ID-nummer för att slutföra uppgiften. Om produktionsutleveransplatsen har ställts in för spårning via registreringskylten måste ett ID-nummer inkluderas vid rapportering av produktionsutleveransplatsen när den är färdig. Fältet **Registreringsskylt** visas i **Rapportera förlopp** på sidan **Jobbkortenhet**. Fältet visas bara i meddelandet **rapportförlopp** när du rapporterar om den senaste operationen för tillverkningsordern. Fältet visas endast om artikeln för tillverkningsordern är aktiverad för lagerstyrningsprocesserna. 
