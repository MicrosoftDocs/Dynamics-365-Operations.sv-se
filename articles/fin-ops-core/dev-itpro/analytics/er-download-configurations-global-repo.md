---
title: Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster
description: I det här avsnittet beskrivs hur du hämtar konfigurationer av elektronisk rapportering (ER) från den globala lagringsplatsen för konfigurationstjänsten.
author: NickSelin
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 6923954e2d287a16425a9f823e8f8800503735ec0b3837cff764cf8d6e752039
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724427"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du hämtar [konfigurationer av elektronisk rapportering](general-electronic-reporting.md#Configuration) från den globala lagringsplatsen för konfigurationstjänsten. Mer information finns i [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, konfigurationstjänst](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Öppna konfigurationsdatabas

1. Logga in på programmet Dynamics 365 Finance med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.
3. I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.
3. I panelen **Microsoft** väljer du **Databaser**.

    ![Arbetsytan för elektronisk rapportering.](./media/er-download-configurations-global-repo-er-workspace.png)

4. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typen. Om denna databas inte visas i rutnätet, följ då nedanstående steg:

    1. Välj **Lägg till** för att lägga till en ny databas.
    2. Välj **Global** som databastyp och välj sedan **skapa databas**.
    3. Följ autoriseringsinstruktionerna om du uppmanas.
    4. Ange ett namn och en beskrivning för databasen och välj sedan **OK** för att bekräfta den nya databasposten.
    5. I rutnätet väljer du den nya databasen för **Global**-typen.

5. Välj **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen.

    ![Sidan Konfigurationsdatabaser.](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importera en enda konfiguration

1. På sidan **Konfigurationsdatabas** i konfigurationsträdet, välj den ER-konfiguration du vill ha.
2. I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.
3. Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.

    > [!NOTE]
    > Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella Finance-instansen.

    ![Sidan Konfigurationsdatabas.](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importera filtrerade konfigurationer

1. På sidan **konfigurationsdatabaser** i konfigurationsträdet expanderar du snabbfliken **Filter**.
2. I rutnätet **Taggar** som behövs i taggarna.
3. I fältet **Tillämplighet för land/region**, välj lämpliga land/regionskoder och sedan **Använd filter**.

    > [!NOTE]
    > På snabbfliken **konfigurationer** visas alla konfigurationer som uppfyller de angivna villkoren för urval.

4. På snabbfliken **konfigurationer** välj **Importera** om du vill hämta de filtrerade konfigurationerna från den globala databasen till den aktuella instansen.
5. På snabbfliken **konfigurationer** välj **Återställ filter** för att rensa de angivna villkoren för urval.

    ![Sidan Konfigurationsdatabas.](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> Beroende på ER-inställningarna valideras konfigurationerna när de har importerats. Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks. Innan du kan använda den importerade konfigurationsversionen måste du lösa problemen. Mer information finns i listan över relaterade resurser för detta avsnitt.

> [!NOTE]
> ER-konfigurationer kan konfigureras som beroende på andra konfigurationer. Tillsammans med en vald konfiguration kan även andra konfigurationer importeras automatiskt. Mer information om konfigurationsberoenden finns i [definiera beroendet för ER-konfigurationer i andra komponenter](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]