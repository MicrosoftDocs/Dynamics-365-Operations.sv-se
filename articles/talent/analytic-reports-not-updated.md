---
title: Analysrapporter uppdateras inte
description: Det här avsnittet beskriver vad du ska göra om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 46f426a4b0012e87b4d9d21032870ac7fc33c4ae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306229"
---
# <a name="analytic-reports-are-not-updated"></a>Analysrapporter uppdateras inte

[!include [banner](includes/banner.md)]

**Utleverans**

En kunds data visas inte på fliken **Analys** av någon av kundens arbetsytor.

**Orsak**

Som standard uppdateras Microsoft Power BI-rapporter var fjärde timme enligt schemat för batchjobbet Distribuera mått.

**Upplösning**

Det här problemet kanske bara är fråga om tidmätning. Följ dessa steg om du vill starta batch-jobbet och uppdatera analysarbetsytorna.

1. Öppna sidan **Batchjobb** på **Systemadministration \> Länkar \> Batchjobb \> Batchjobb**. Alternativt använder du Sök och anger **Batchjobb**.
1. Hitta jobbet **Distribuera mätning** i listan.
1. Välj **Redigera** överst på sidan och ange det schemalagda startdatumet/tiden som uppdaterar analysen närmare till aktuell tid.

![Batchjobb](media/batch-jobs.png)
