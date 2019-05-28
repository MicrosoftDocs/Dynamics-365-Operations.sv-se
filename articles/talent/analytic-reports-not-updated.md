---
title: Analysrapporter uppdateras inte
description: Det här avsnittet beskriver vad du ska göra om en kunds dataändringar inte visas i någon av kundens arbetsytor.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6a6487b50908093f876237ffef840a3144b3fe6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519163"
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
