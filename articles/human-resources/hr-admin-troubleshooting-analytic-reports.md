---
title: Felsöka analysrapporter
description: Detta avsnitt beskriver hur du felsöker och diagnostiserar problem om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ea04c06858cc98b0e233b9133d9dfbebfe59fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067739"
---
# <a name="troubleshoot-analytic-reports"></a>Felsöka analysrapporter


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

En kunds data visas inte på fliken **Analys** av någon av kundens arbetsytor.

**Orsak**

Som standard uppdateras Microsoft Power BI-rapporter var fjärde timme enligt schemat för batchjobbet Distribuera mått.

**Upplösning**

Det här problemet kanske bara är fråga om tidmätning. Följ dessa steg om du vill starta batch-jobbet och uppdatera analysarbetsytorna.

1. Öppna sidan **Batchjobb** på **Systemadministration \> Länkar \> Batchjobb \> Batchjobb**. Alternativt använder du Sök och anger **Batchjobb**.
1. Hitta jobbet **Distribuera mätning** i listan.
1. Välj **Redigera** överst på sidan och ange det schemalagda startdatumet/tiden som uppdaterar analysen närmare till aktuell tid.

![Batchjobb.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
