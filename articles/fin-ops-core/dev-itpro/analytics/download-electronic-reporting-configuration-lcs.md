---
title: Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services
description: Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 719b277fb828ea2085ea80bc4a36c2af3412f66b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683315"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Hämta konfigurationer för elektronisk rapportering från Lifecycle Services

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du hämtar den senaste versionen av dina [Elektronisk rapportering (ER) konfigurationer](general-electronic-reporting.md#Configuration) från [biblioteket med gemensamma tillgångar](../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).

1. Logga in på programmet med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration** &gt; **Arbetsytor** &gt; **Elektronisk rapportering**.
3. I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.
4. I panelen **Microsoft** väljer du **Databaser**.

    [![Microsoft-panel på sidan lokaliseringskonfiguration](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **LCS**-typen. Om denna databas inte visas i rutnätet, följ då nedanstående steg:

    1. Välj **Lägg till** för att lägga till en databas.
    2. Välj **LCS** som databastyp.
    3. Välj **Skapa databas**.
    4. Om du tillfrågas om auktorisering följer du instruktionerna på skärmen.
    5. Skriv ett namn och en beskrivning för databasen.
    6. Klicka på **OK** för att bekräfta den nya databasposten.
    7. I rutnätet väljer du den nya databasen för **LCS**-typen.

6. Välj **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen.

    [![Sidan Konfigurationsdatabas](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Om du har problem med att komma åt LCS-databasen för hämtning av konfigurationer från biblioteket med gemensamma tillgångar i LCS kan du i stället hämta konfigurationer från den [globala databasen](er-download-configurations-global-repo.md) .

7. I konfigurationsträdet i det vänstra fönstret väljer du erforderlig ER-konfiguration.
8. I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.
9. Klicka på **Importera** för att hämta den valda versionen från LCS till den aktuella instansen.

    > [!NOTE]
    > Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella instansen.

    [![Sidan Konfigurationsdatabas](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Beroende på ER-inställningarna valideras konfigurationerna när de har importerats. Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks. Du måste lösa dessa problem innan du kan använda den importerade konfigurationsversionen. Mer information finns i listan över relaterade artiklar för detta avsnitt.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](er-download-configurations-global-repo.md)
