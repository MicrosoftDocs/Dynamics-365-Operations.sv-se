---
title: Annullerade produktinleveranser uppdaterar inte transaktionsstatus till registrerad
description: När du har annullerat produktinleveranser för en inkommande beläggning, uppdaterar systemet automatiskt lagertransaktionens status från Inleverans till Beställd.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eae703ce0b2c981518b18c4badd4f90031b902ece62f3ca0837427b306d618b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731113"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Annullerade produktinleveranser uppdaterar inte transaktionsstatus till registrerad

## <a name="symptoms"></a>Symtom

När du har kört åtgärden **annullera produktinleveranser** för en inkommande beläggning, uppdaterar systemet automatiskt lagertransaktionens status från *Inleverans* till *Beställd*.

## <a name="resolution"></a>Lösning

När följesedlar annulleras för utgående lastning förblir statusen för lagertransaktionerna *Plockad*. När produktinleveranser från en inkommande belastning annulleras, återställs dock statusen för lagertransaktionerna till *Registrerad*. När en produktinleverans från en inkommande belastning har annullerats måste lagerarbetaren därför registrera artikelkvantiteterna på nytt för inläsningen.

Mer information finns i [Registrera artikelkvantiteter som inkommer till en inkommande last](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
