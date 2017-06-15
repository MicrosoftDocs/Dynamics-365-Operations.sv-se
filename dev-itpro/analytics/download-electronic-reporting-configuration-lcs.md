---
title: "Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services"
description: "Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1e73cd38c33d88feaba825abb64721bc332a4d6e
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services

[!include[banner](../includes/banner.md)]


Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).

Denna guide vägleder dig genom processen att hämta den senaste versionen av elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).

1.  Logga in på Dynamics 365 for Operations med någon av följande roller:
    -   Utvecklare för elektronisk rapportering
    -   Konsult för funktionen för elektronisk rapportering
    -   Systemadministratör

2.  Navigera tilll **Organisationsadministrering** &gt; **Elektronisk rapportering**.
3.  I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.
4.  I panelen **Microsoft** väljer du **Databaser**. [![uppdatera-er-från-lcs-för-ms-öppna-lista-över-ms-databaser](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **LCS**-typen. Om denna databas inte visas i rutnätet, följ då nedanstående steg:
    1.  Klicka på Click **Lägg till** för att lägga till en ny databas.
    2.  Välj **LCS** som databastyp.
    3.  Klicka på **Skapa databas**.
    4. Följ autoriseringsinstruktionerna om du uppmanas.
    5.  Skriv ett namn och en beskrivning för databasen.
    6.  Klicka på **OK** för att bekräfta den nya databasposten.
    7.  I rutnätet väljer du den nya databasen för **LCS**-typen.

6.  Klicka på **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen. [![uppdatera-er-från-lcs-för-ms-skapa-lcs-databas](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  I konfigurationsträdet i det vänstra fönstret väljer du erforderlig ER-konfiguration.
8.  I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.
9.  Klicka på **Importera** för att hämta den valda versionen från LCS till den aktuella Dynamics 365 for Operations-instansen. **Obs!** Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella Dynamics 365 for Operations-instansen. [![uppdatera-er-från-lcs-för-ms-hämta-konfiguration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Obs!** Beroende på ER-inställningarna valideras konfigurationerna när de har importerats. Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks. Du måste lösa dessa problem innan du kan använda den importerade konfigurationsversionen. Mer information finns i listan över relaterade artiklar för detta avsnitt.

<a name="see-also"></a>Se även
--------

[Översikt över elektronisk rapportering](general-electronic-reporting.md)



