---
title: 'Felsökning: lagerpåfyllning'
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e4d87e85520c2b6f2346fddf3b985d4e17fe35cb
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644883"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Felsökning: lagerpåfyllning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Jag får följande felmeddelande: "Arbete %1 kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".

### <a name="issue-description"></a>Problembeskrivning

Plocknings arbetet spärras på grund av beroende återanskaffningsarbete.

### <a name="issue-resolution"></a>Problemlösning

När du använder lagerpåfyllnadsbegäran om en plockplats måste fyllas på skapar systemet både påfyllningsarbetet och plockningsarbetet om en plockplats måste fyllas på för att uppfylla källorderns behov. Men det blockerar plockningsarbetet tills påfyllningsarbetet har slutförts. Det här beteendet är avsiktligt eftersom plockplatsen inte har tillräckligt med lager om inte lagerpåfyllnadsarbetet har slutförts. Slutför påfyllningsarbetet och bearbeta sedan plockningsarbetet.
