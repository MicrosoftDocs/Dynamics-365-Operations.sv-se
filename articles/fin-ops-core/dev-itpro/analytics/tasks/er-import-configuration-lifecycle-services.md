---
title: Importera en konfiguration från Lifecycle Services
description: I den här artikeln beskrivs hur du importerar en ny version av konfiguration av elektronisk rapportering (ER) från Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
ms.openlocfilehash: 92c5d010430b38cb6c11a87283a2f7d4c29484f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290377"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importera en konfiguration från Lifecycle Services

[!include [banner](../../includes/banner.md)]

Detta ämne förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en [konfiguration för elektronisk rapportering (ER)](../general-electronic-reporting.md#Configuration) från [Tillgångsbibliotek på projektnivå](../../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> Användningen av LCS som en lagringsdatabas för ER-konfigurationer är [inaktuell](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Mer information finns i [Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)

I det här exemplet ska du välja önskad version av ER-konfigurationen och importera den för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i proceduren [Överföra en konfiguration till Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). Du måste också ha tillgång till LCS.

1. Logga in på programmet med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. Välj **konfigurationer**.

<a name="accessconditions"></a>
> [!NOTE]
> Kontrollera att den aktuella Dynamics 365 Finance användaren är medlem i det LCS-projekt som innehåller det resursbibliotek som användaren vill kunna få [åtkomst](../../lifecycle-services/asset-library.md#asset-library-support) till för att importera ER-konfigurationer.
>
> Du har inte åtkomst till ett LCS-projekt från en ER-databas som representerar en annan domän än den domän som används i Finance. Om du försöker kommer en tom lista med LCS-projekt att visas, och du kan inte importera ER-konfigurationer från tillgångsbiblioteket på projektnivå i LCS. Om du vill komma åt tillgångsbibliotek på projektnivå från en ER-databas som används för att importera ER-konfigurationer loggar du in på Finance genom att använda referenserna för en användare som tillhör den innehavare (domän) som den aktuella Finance-instansen har etablerats för.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Ta bort en delad version av konfiguration av datamodell

1. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Konfiguration av exempelmodell**.

    Du skapade den första versionen av en konfigurationsmodell för en datamodell och publicerade den till LCS när du slutförde stegen i [Överför en konfiguration till Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). I den här proceduren kommer du ta bort den här versionen av ER-konfigurationen. Därefter ska du importera den versionen från LCS senare i den här artikeln.

2. Hitta och markera önskad post i listan.

    I det här exemplet väljer du den version av konfigurationen som har status **Delad**. Statusen visar att konfigurationen har publicerats till LCS.

3. Välj **Ändra status**.
4. Välj **Upphör**.

    Genom att ändra status för den valda versionen från **Delad** till **Upphörd** måste du göra versionen tillgänglig för radering.

5. Välj **OK**.
6. Hitta och markera önskad post i listan.

    I det här exemplet väljer du den version av konfigurationen som har status **Upphörd**.

7. Välj **Ta bort**.
8. Välj **Ja**.

    Observera att den enda utkastversionen 2 i den valda konfigurationen av datamodell nu är tillgänglig.

9. Stäng sidan.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importera en delad version av konfiguration av datamodell från LCS

1. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.

2. I avsnittet **Konfigurationsleverantörer** väljer du panelen **Litware, Inc.**.

3. I panelen **Litware, Inc.** väljer du **Databaser**.

    Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.

4. Välj **Öppen**.

    I det här exemplet väljer du databasen **LCS** och öppnar den. Du måste ha [åtkomst](#accessconditions) till LCS-projektet och till tillgångsbiblioteket som du öppnar med den valda ER-databasen.

5. Markera vald rad i listan.

    Välj till exempel den första versionen av **Konfiguration av exempelmodell** i versionslistan.

6. Välj **Importera**.
7. Välj **Ja** för att bekräfta importen av den valda versionen från LCS.

    Ett informationsmeddelande bekräftar att den valda versionen har importerats utan fel.

8. Stäng sidan.
9. Stäng sidan.
10. Välj **konfigurationer**.
11. Välj **Konfiguration av exempelmodell** i trädet.
12. Hitta och markera önskad post i listan.

    I det här exemplet väljer du den version av konfigurationen som har status **Delad**.

    Observera att den enda delade versionen 1 i den valda konfigurationen av datamodell nu också är tillgänglig.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
