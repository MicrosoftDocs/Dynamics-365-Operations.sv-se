---
title: Använda prissättningsmotorn för Dynamics 365 Commerce med Dynamics 365 Sales
description: I det här avsnittet beskrivs hur du använder prissättningsmotorn i Microsoft Dynamics 365 Commerce för att skapa offerter i Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: fa93b1262049d80148ff23b3d7223ec0f6c2fe68
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941176"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Använda prissättningsmotorn för Dynamics 365 Commerce med Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du använder prissättningsmotorn i Microsoft Dynamics 365 Commerce för att skapa offerter i Dynamics 365 Sales.

Prissättningsmotorn i Dynamics 365 Commerce har stöd för de flesta B2C (Business-to-Consumer) prisvarianter, till exempel pris på butiksnivå, partnerbaserade och förmånbaserade priser, mixa och-matcha-rabatter, mängdrabatter och tröskelrabatter. Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order.

När du använder [dubbelriktad skrivning](./dual-write-overview.md) har du tre alternativ för dina prissättningsbehov. Du kan använda den statiska prissättningen från prislistan i Dynamics 365 Sales, prissättningsmotorn i Dynamics 365 Supply Chain Management eller prissättningsmotorn i Dynamics 365 Commerce. Av de här alternativen är prissättningsmotorn i Commerce bäst lämpad för B2C-scenarier.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Använda prissättningsmotorn i Commerce i Sales

> [!NOTE]
> För närvarande kan prissättningsmotorn i Commerce bara användas för att skapa offerter i Sales. Integration av försäljningsorder med prissättningsmotorn i Commerce är inte tillgänglig ännu.

När användarna initierar en offert i Sales kopieras offertinformationen till Commerce med ramverket för dubbelriktad skrivning. Alla ändringar av befintliga offertrader eller eventuella nyligen tillagda offertrader i Sales kopieras till Commerce. När användarna vill använda prissättningsmotorn i Commerce för att prissätta offerten kan de välja **Prisoffert** för att uppdatera offertens priser, baserat på prissättningsmotorn i Commerce. Priserna uppdateras sedan automatiskt i både Sales och Commerce.

## <a name="prerequisites"></a>Förutsättningar

- Innan du kan använda prissättningsmotorn i Commerce i Sales måste du följa stegen i [Potentiell kund till kontanter vid dubbelriktad skrivning](./dual-write-prospect-to-cash.md).
- Du måste stänga av utvärdering av handelsavtal för manuell registrering genom att utföra följande steg:

    1. I Commerce-miljön går du till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
    1. på fliken **Priser** på FastTab **Utvärdering av handelsavtal** avmarkerar du kryssrutan **Manuell registrering**.

## <a name="additional-resources"></a>Ytterligare resurser

[Potentiell kund till kontanter vid dubbel skrivning](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]