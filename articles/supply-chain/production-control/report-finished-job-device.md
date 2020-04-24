---
title: Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten
description: I det här avsnittet beskrivs processen för att slutföra färdiga produkter i en tillverkningsorder till lagret när en registreringsskylt kontrollerar platsen.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: f5863202facc83afb91b380ba5666334783ccbcf
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211179"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten 

Processen som kallas rapportera som färdig slutför färdiga produkter i en tillverkningsorder till lagret. Om den färdiga produkten är aktiverad för de avancerade lagerprocesserna rapporteras produkten som färdig till en plats som kallas för produktionsutleveransplats. Information om hur du ställer in produktionsutleveransplats finns i [Plats för produktionsutleverans](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location)plats för produktions utmatning.

Om produktionens utgångsplats styrs av registreringsskylt, måste en registreringsskylt tillhandahållas vid rapportering som färdigt. Fältet **Registreringsskylt** visas i **Rapportera förlopp** på sidan **Jobbkortenhet**. Fältet visas bara på frågan **rapportstatus** när du rapporterar om den senaste operationen i produktionsordern och artikeln för tillverkningsordern är aktiverad för lagerstyrningsprocesserna. 

Det finns två alternativ för att tillhandahålla registreringsskylten
- Användaren väljer en befintlig registreringsskylt i fältet registreringsskylt.
- Registreringsskylten genereras automatiskt från en nummerserie och fallerar till fältet registreringsskylt.

Alternativet att låta registreringsskylten genereras automatiskt konfigureras genom att välja alternativet **Generera registreringsskylt** på sidan **konfigurera jobbkort för enheter**.
