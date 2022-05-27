---
title: Bokföringskonton för anskaffning av anläggningstillgång
description: Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93cbfc46fb41e47fba8b6cecf7811c0cf838e7d3
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719832"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Bokföringskonton för anskaffning av anläggningstillgång

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.

Konton som används för bokföring av anskaffning kan variera beroende på metoden som används för anskaffning av tillgången. På sidan Bokföringsprofiler för anläggningstillgångar, på fliken Redovisningskonto, välj Anskaffnings och anskaffningsjustering för att ställa in Anläggningstillgångskontona som bokförs i redovisningen. 

I journaler och inköpsorder debiteras den nya anläggningstillgångens anskaffningsvärde vanligtvis på balansräkningskontot. Det här kontot visas inte i journalen och kan inte ersättas i transaktioner. 

Motkonto är också ett balansräkningskonto. I den allmänna journalen och i Anläggningstillgångsjournalen är det här kontot ofta bankkontot som används för att betala anskaffningen av tillgången. Motkontot är ett standardkonto som föreslås i journalerna. Det kan ändras i journalen till ett annat konto från kontoplanen eller till ett leverantörskonto, om anläggningstillgången har köpts från en leverantör. 

När Fakturajournal eller Inköpsorder i Leverantörsreskontra används för anskaffningar av anläggningstillgångar ersätts motkontot för Anläggningstillgångstransaktionen med ett leverantörskonto som valts för transaktionen.

För anskaffningar som bokförs med journalen Lager till anläggningstillgångar i Huvudbok köps inte anläggningstillgången från externa källor, utan överförs från företagets eget lager. Därför är motkontot ett lagerutleveranskonto för lagerartikeln i lagerhanteringen.

Mer information finns i [Förvärv av tillgångar genom upphandling](acquire-assets-procurement.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
