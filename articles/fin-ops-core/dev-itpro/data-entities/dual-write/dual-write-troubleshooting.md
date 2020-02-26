---
title: Felsökningsguide för dataintegrering
description: Det här avsnittet innehåller felsökningsinformation för dataintegrering mellan Finance and Operations-appar och Common Data Service.
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
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020021"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Felsökningsguide för dataintegrering

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Möjliggöra plugin-spårningsloggar i Common Data Service och inspektera de dubbelriktade skrivning plugin-feldetaljerna

Om det uppstår ett problem eller fel under en synkronisering med dubbelriktad skrivning följer du stegen nedan för att granska felen i spårningsloggen.

1. Innan du kan undersöka felen måste du aktivera spårningsloggar för plugin-program. Instruktioner finns i avsnittet "Visa spårningsloggar" i [Självstudier: Skriv och registrera ett plugin-program](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Nu kan du inspektera felen.

2. Logga in på Microsoft Dynamics 365 Sales.
3. Välj knappen **Inställningar** (växelsymbolen) och sedan **Avancerade inställningar**.
4. På menyn **Inställningar** väljer du **Anpassning \> spårningslogg för plugin-program**.
5. Välj **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** som typnamn för att visa felinformationen.

## <a name="inspect-dual-write-synchronization-errors"></a>Inspektera synkroniseringsfel vid dubbelriktad skrivning

Följ dessa steg för att inspektera fel under testningen.

1. Logga in på Microsoft Dynamics Lifecycle Services (LCS).
2. Öppna LCS-projektet som du vill dubbelriktad skrivtestning för.
3. Välj **Molnstyrda miljöer**.
4. Gör en fjärrskrivbordsanslutning till den virtuella datorn (VM) för appen med hjälp av ett lokalt konto som visas i LCS.
5. Öppna händelsevisningsprogrammet. 
6. Gå till **Program- och tjänstloggar \> Microsoft \> Dynamics \> AX-DualWriteSync \> Drift**. Felen och detaljerna visas.

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a>Ta bort länken till en Common Data Service-miljö från appen och länka en annan miljö

Följ dessa steg om för att uppdatera länkar.

1. Gå till programmiljön.
2. Öppna datahantering.
3. Välj **Länka till CDS för appar**.
4. Välj alla mappningar som körs och välj sedan **Stopp**.
5. Välj alla mappningarna och välj sedan **Ta bort**.

    > [!NOTE]
    > Alternativet **Ta bort** är inte tillgängligt om mallen **CustomerV3-konto** har valts. Ta bort valet av den här mallen om det behövs. **CustomerV3-konto** är en äldre etablerad mall och fungerar med lösningen potentiell kund till kontanter. Eftersom den släpps globalt visas den under alla mallar.

6. Välj **Ta bort länk till miljö**.
7. Välj **Ja** för att bekräfta åtgärden.
8. Följ stegen i [installationsguiden](https://aka.ms/dualwrite-docs) om du vill länka den nya miljön.
