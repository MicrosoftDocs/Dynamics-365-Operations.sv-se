---
title: Felsöka delvis frisläppning och delleverans
description: Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 5534099f81a97a1dcf4908784fd71dd03cf94eaf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828164"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Felsöka delvis frisläppning och delleverans

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med delvis frisläppning och delleveranser i Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Frisläppningsstatusen för en försäljningsorder förblir delvis frisläppt även när försäljningsordern har fakturerats.

### <a name="issue-description"></a>Problembeskrivning

En försäljningsorder är en leveransorder, men en eller flera artiklar på den har ett annat leverans sätt. När ordern har fakturerats har den fortfarande frisläppningsstatus som *delvis släppts*.

En försäljningsorder har till exempel två artiklar: en för leverans och en för upphämtning. Både leveransen och upphämtningen har utförts. Därför har båda raderna fakturerats. Frisläppnings status visas fortfarande som *delvis utsläppt*, vilket är missvisande.

### <a name="issue-resolution"></a>Problemlösning

Frisläppningsstatus gäller bara för orderrader där artiklarna är aktiverade för lagerstyrning. Därför fortsätter frisläppningsstatusen att vara *delvis släppts* i det här scenariot. Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. Ett tillägg kan läggas till som en del av följesedeln och faktureringsprocessen för att uppdatera frisläppningsstatus.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]