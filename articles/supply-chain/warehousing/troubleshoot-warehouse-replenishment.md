---
title: 'Felsökning: lagerpåfyllning'
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8940f729e1115405e8d6e50eccc92d9fffe37f3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828092"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Felsökning: lagerpåfyllning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerpåfyllning i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Jag får följande felmeddelande: "Arbete %1 kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".

### <a name="issue-description"></a>Problembeskrivning

Plocknings arbetet spärras på grund av beroende återanskaffningsarbete.

### <a name="issue-resolution"></a>Problemlösning

När du använder lagerpåfyllnadsbegäran om en plockplats måste fyllas på skapar systemet både påfyllningsarbetet och plockningsarbetet om en plockplats måste fyllas på för att uppfylla källorderns behov. Men det blockerar plockningsarbetet tills påfyllningsarbetet har slutförts. Det här beteendet är avsiktligt eftersom plockplatsen inte har tillräckligt med lager om inte lagerpåfyllnadsarbetet har slutförts. Slutför påfyllningsarbetet och bearbeta sedan plockningsarbetet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]