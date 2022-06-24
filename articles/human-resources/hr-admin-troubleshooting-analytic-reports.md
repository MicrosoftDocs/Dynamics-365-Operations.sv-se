---
title: Felsöka analysrapporter
description: Denna artikel beskriver hur du felsöker och diagnostiserar problem om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e6ae8931679feb2103172eb1a21649734acd995
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902239"
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
