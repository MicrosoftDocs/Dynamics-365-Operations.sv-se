---
title: Dela ER-konfigurationer i RCS/den globala databasen med externa organisationer
description: Den här artikeln innehåller information om hur du delar elektroniska rapporteringskonfigurationer (ER) i Microsoft Regulatory Configuration Services (RCS)/den globala databasen direkt med externa organisationer.
author: kfend
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
ms.openlocfilehash: d9400ffcede9924a01391a433b570651d3f0c5e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284828"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Dela elektroniska rapporteringskonfigurationer (ER) i Microsoft Regulatory Configuration Services (RCS)/den globala databasen med externa organisationer

[!include [banner](../includes/banner.md)]

Du kan använda Microsoft RCS (Regulatory Configuration Services) för att dela konfigurationer för elektronisk rapportering (ER) och sedan publicera dem i externa organisationer.

Följande procedurer förklarar hur en RCS-användare kan dela en version av en ER-konfiguration som har konfigurerats i en RCS-instans med en extern organisation. Innan du kan slutföra dessa procedurer måste du först uppfylla följande förutsättningar:

- Öppna en RCS-instans.
- Skapa en aktiv konfigurationsleverantör. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Skapa och överför en ny version av en ER-konfiguration. Mer information finns i [Skapa och överföra en ny version av en konfiguration för elektronisk rapportering (ER)](rcs-global-repo-upload.md).

Du måste också säkerställa att en RCS-miljö har etablerats för ditt företag.

1. I appen för ekonomi och drift, gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services – extern konfiguration** och följer sedan instruktionerna för att etablera en.

Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt den genom att välja alternativet för inloggning.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Kontrollera konfigurationen du vill dela

Följ dessa steg för att kontrollera att konfigurationen som du vill dela redan har överförts till den globala databasen.

1. I arbetsytan **Elektronisk rapportering** väljer du **Databaser** för din konfigurationsleverantör.

    ![Konfigurationsleverantörer.](media/1_RCS_Repo_for_config_provider.JPG)

2. Välj **Global databas** \> **Öppna**.
3. Sök efter den konfiguration du vill dela. Du kan använda filterfältet för att begränsa sökresultatet. Om du inte kan hitta konfigurationen i den globala databasen följer du stegen i [Skapa och ladda upp en ny version av en konfiguration för elektronisk rapportering (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Dela ER-konfigurationer med externa organisationer

När en konfiguration har skapats i din konfigurationsleverantör kan du dela den direkt med externa organisationer genom att använda snabbfliken **Delas med** på sidan **Global konfigurationsdatabas**.

1. I arbetsytan **Elektronisk rapportering** väljer du **Databaser** för din konfigurationsleverantör.
2. Välj **Global databas** \> **Öppna**. 
3. Välj den konfiguration du vill dela.
4. I snabbfliken **Delas med** väljer du **Organisation**.

    ![Delas med snabbfliken.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. I dialogrutan anger du domännamnet för den externa organisationen och väljer sedan **OK**.

    ![Dela konfigurationsversion med dialogrutan för extern organisation.](media/1_RCS_Repo_for_Share_with_form.JPG)

Konfigurationen delas med den externa organisationen och är tillgänglig för den organisationen i den globala databasen. Därifrån kan den importeras till organisationens instans av RCS eller till dess instanser av appar för ekonomi och drift.

6. Om du vill ta bort delning av en konfiguration som tidigare har delats med en extern organisation, markerar du konfigurationen och klickar på **Ta bort delning** innan du väljer **OK**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
