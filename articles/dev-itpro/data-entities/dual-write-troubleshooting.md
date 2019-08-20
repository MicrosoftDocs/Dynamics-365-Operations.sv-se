---
title: Felsökningsguide för dataintegrering
description: Det här avsnittet innehåller felsökningsinformation om dataintegrering mellan Microsoft Dynamics 365 for Finance and Operations och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797285"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Felsökningsguide för dataintegrering

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Möjliggöra plugin-spårning i Common Data Service och kontrollera den dubbelriktade skrivning plugin-feldetaljer

Om du står inför ett problem eller ett fel med synkronisering av dubbelriktad skrivning kan du inspektera felen i spårningsloggen:

1. Innan du kan inspektera felen måste du aktivera plugin-spårning med hjälp av instruktionerna i [registrera plugin-program](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) för att aktivera spårning av plugin-spårning. Nu kan du inspektera felen.
2. Logga in på Dynamics 365 for Sales.
3. Klicka på inställningsikonen (ett kugghjul) och välj **avancerade inställningar**.
4. I menyn **inställningar** väljer du **anpassning > spårningslogg för plugin-program**.
5. Klicka på typnamnet **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** för att vVisa felinformationen.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Kontrollera synkroniseringsfel med dubbelriktade skrivningar i Finance and Operations

Du kan kontrollera felen under testningen genom att följa dessa steg:

+ Logga in på LifeCycle Services (LCS).
+ Öppna LCS-projektet som du valde att utföra testning av dubbelriktad skrivning.
+ Gå till molnstyrda miljöer.
+ Fjärrskrivbord till Finance and Operations VM med lokalt konto som visas i LCS.
+ Öppna händelsevisningsprogrammet. 
+ Navigera till **program- och tjänstloggar > Microsoft > Dynamics > AX-DualWriteSync > Drift**. Felen och detaljerna visas.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Ta bort länken till och länka en annan Common Data Service-miljö från Finance and Operations

Du kan uppdatera länkarna genom att följa dessa steg:

+ Navigera till Finance and Operations-miljön.
+ Öppna datahantering.
+ Klicka på **Länkatill CDS för appar**.
+ Markera alla mappningar som körs och klicka på **stoppa**. 
+ Markera alla mappningar och klicka på **ta bort**.

    > [!NOTE]
    > Alternativet **ta bort** visas inte om mallen **CustomerV3-konto** har valts. Avmarkera om det behövs. **CustomerV3-konto** är en äldre etablerad mall och fungerar med lösningen potentiell kund till kontanter. Eftersom den släpps globalt visas den under alla mallar.

+ Klicka på **Ta bort länk till miljö**.
+ Klicka på **ja** för bekräftelse.
+ Följ stegen i [installationsguiden](https://aka.ms/dualwrite-docs) om du vill länka den nya miljön.

