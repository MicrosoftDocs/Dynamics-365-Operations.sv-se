---
title: Härledda räkenskapsböcker
description: Den här artikeln ger en översikt över funktionerna för härledda böcker.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32abfce013d0daa208138cf698b2abd1f96462f6
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674512"
---
# <a name="derived-books"></a>Härledda räkenskapsböcker

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över funktionerna för härledda böcker.

Ändamålet med härledda böcker att att förenkla bokföringen av transaktioner för anläggningstillgångar som planeras med jämna mellanrum.  Du kan välja en bok som primär bok. Denna är vanligtvis boken som används för redovisningsavskrivning. Du kopplar sedan andra böcker till den som har ställts in för bokföring av transaktioner med samma intervaller som den primära boken. Böcker för momsavskrivning anges ofta som härledda böcker. 

De vanligaste transaktionerna att ställas in för redovisning i härledda böcker är anskaffningar, anskaffningsjusteringar och avyttringar. 

## <a name="example"></a>Exempel

Bok B och C ställs in som härledda böcker för bok A för typen anskaffningstransaktion. I bok A anger du en anskaffningstransaktion för tillgång 123 på 1 500,00. 

Vid bokföringen av transaktionen genereras en anskaffningstransaktion som bokförs i tillgång 123 för bok B, samt i tillgång 123 för bok C på 1 500,00. När du förbereder transaktionerna för den primära boken för bokföring i Anläggningstillgångsjournalen, kan du också visa och ändra transaktionerna för de härledda böckerna. Om du förbereder transaktionerna för den primära boken i en annan journal, visas inte transaktionerna för det härledda värdet. De bokförs dock på tillämpliga konton och bokföringsskikt när du bokför transaktionerna för den primära boken.

> [!NOTE]                                                                                                                               
> Böcker som ställs in för att bokföra transaktioner med andra intervall än de primära bokintervallen måste kopplas till anläggningstillgången som separata böcker och inte som härledda böcker.  

Mer information finns i [Bokföring med härledda böcker](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
