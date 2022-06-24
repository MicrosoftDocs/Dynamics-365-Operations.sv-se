---
title: Avbryta ett huvudplaneringsjobb
description: I denna artikel beskrivs hur du avbryter ett aktivt planeringsjobb som använder inbyggd planeringsfunktion.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6a9667be9921fdde7e1ca5de68c7f51d48905ac8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860795"
---
# <a name="cancel-a-master-planning-job"></a>Avbryta ett huvudplaneringsjobb

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics 365 Supply Chain Management finns det flera alternativ för att avbryta ett huvudplaneringsjobb. Du kanske till exempel vill avbryta ett huvudplaneringsjobb om det startades av misstag eller körs längre än förväntat och du vill avsluta det. Det bästa sättet att avbryta ett planeringsjobb är från sidan **oavslutade planeringsprocesser**. Andra alternativ från sidorna **Batch-jobb** och **Förbättrade batch-jobb** bör endast användas om du avbryter huvud planerings jobbet från sidan **oavslutade planeringsprocesser** inte slutfördes inom några minuter.

## <a name="preferred-cancel-option"></a>Önskat alternativ för Avbryt
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Avbryt huvudplaneringsjobb från sidan **ej avslutade planeringsprocesser**
1. Gå till **Huvudplanering > Förfrågningar och rapporter > Huvudplanering > Oavslutade planeringsprocesser**.
2. Välj raden med planeringsprocessen som du vill avbryta.
3. Klicka på **Avbryt**.

## <a name="additional-cancel-options"></a>Ytterligare alternativ för avbryta
Dessa bör endast användas om avbryt huvudplaneringsjobbet från sidan **oavslutade planeringsprocesser** inte slutfördes inom några minuter.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Ta bort huvudplaneringsjobb från sidan **batchjobb**
1. Gå till **Systemadministration > Förfrågninger > Batchjobb**.
2. Välj raden med planeringsjobb som du vill ta bort.
3. Klicka på **Ta bort**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Ta bort huvudplaneringsjobb från sidan **Förbättrade batchjobb**
1. Gå till **Systemadministration > Förfrågninger > Batchjobb**.
2. Om jobb-ID inte visas i listan klickar du på **växla till utökat formulär**, annars fortsätter du med nästa steg.
3. Öppna batch-jobb. Klicka på **jobb-ID** för batch-jobbet med aktiviteter som du vill avsluta.
4. I **Batchaktiviteter**, välj aktiviteterna som ska avslutas.
5. Klicka på **Ändra status**, välj **Avbryt** och klicka på **OK**.
6. På snabbfliken **batchuppgifter** klickar du på **Avbryt**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]