---
title: Bokföringskonton för anskaffning av anläggningstillgångar
description: Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d4c1b4de2e58b964bcf6ab07929897083f4c826
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822019"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Bokföringskonton för anskaffning av anläggningstillgångar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.

Konton som används för bokföring av anskaffning kan variera beroende på metoden som används för anskaffning av tillgången. På sidan Bokföringsprofiler för anläggningstillgångar, på fliken Redovisningskonto, välj Anskaffnings och anskaffningsjustering för att ställa in Anläggningstillgångskontona som bokförs i redovisningen. 

I journaler och inköpsorder debiteras den nya anläggningstillgångens anskaffningsvärde vanligtvis på balansräkningskontot. Det här kontot visas inte i journalen och kan inte ersättas i transaktioner. 

Motkonto är också ett balansräkningskonto. I den allmänna journalen och i Anläggningstillgångsjournalen är det här kontot ofta bankkontot som används för att betala anskaffningen av tillgången. Motkontot är ett standardkonto som föreslås i journalerna. Det kan ändras i journalen till ett annat konto från kontoplanen eller till ett leverantörskonto, om anläggningstillgången har köpts från en leverantör. 

När Fakturajournal eller Inköpsorder i Leverantörsreskontra används för anskaffningar av anläggningstillgångar ersätts motkontot för Anläggningstillgångstransaktionen med ett leverantörskonto som valts för transaktionen.

För anskaffningar som bokförs med journalen Lager till anläggningstillgångar i Huvudbok köps inte anläggningstillgången från externa källor, utan överförs från företagets eget lager. Därför är motkontot ett lagerutleveranskonto för lagerartikeln i lagerhanteringen.

Mer information finns i [Förvärv av tillgångar genom upphandling](acquire-assets-procurement.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]