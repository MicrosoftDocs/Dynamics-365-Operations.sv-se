---
title: Koncerninterna batch- och serienummer
description: I det här avsnittet beskrivs vad som kommer att hända när du registrerar batchnummer och serienummer för koncerninterna order
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9d5e6ddd0bf9ab9dd032e3ab8d1e11d53fba639e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672946"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Koncerninterna batch- och serienummer

[!include [banner](../../includes/banner.md)]

Företag som använder serie- eller partinummer för att spåra sina artiklar behöver också hålla ordning på serienummer och partinummer för plockade artiklar. Den koncerninterna funktionen automatiserar flyttningar av serienummer och partinummer från ett företag till ett annat. När du registrera parti- och serienumren för artiklarna på en koncernintern försäljningsorder kan du ställa in programmet på att flytta dessa nummer automatiskt till den koncerninterna försäljningsordern och den ursprungliga försäljningsordern. Du ställer in relevanta parametrar på sidan **Koncernintern** för försäljningsordern:

- Om du väljer fältet **Partinummer** på sidan **Försäljningsorderpolicyer** synkroniseras partinumret med lagertransaktionerna på de koncerninterna inköpsorderraderna när du bokför följesedeln för den koncerninterna försäljningsordern.
- Om du väljer fältet **Serienummer** synkroniseras serienumret med lagertransaktionerna på de koncerninterna inköpsorderraderna när du bokför följesedeln för den koncerninterna försäljningsordern.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
