---
title: Skapa organisationsmodelleringshierarkier för B2B-organisationer
description: I detta ämne beskrivs hur du skapar organisationsmodellhierarkier för B2B-organisationer (business-to-business).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91cb01637faa69bd3c7fefefae69c60cb948510e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211235"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Skapa organisationsmodelleringshierarkier för B2B-organisationer

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du skapar organisationsmodellhierarkier för B2B-organisationer (business-to-business) i Microsoft Dynamics 365 Commerce.

I Commerce-administrationen representeras affärspartner-organisationerna av kund- och kundhierarkientiteter. Partnerorganisationen och dess användare representeras som kunder, och kundhierarkier används för att koppla dessa kunder till varandra.

När en affärspartners begäran om att ansluta till en B2B-näthandelssajt godkänns, utförs följande åtgärder:

- Två nya kundposter skapas i systemet: en kundpost av typen **Organisation** för affärspartnerorganisationen, samt en kundpost av typen **Person** för begäranden (dvs. den affärspartneranvändare som skickade in begäran).
- En ny kundhierarkipost skapas under **Kund \> Kundkundhierarki**. Den här posten har följande rubrikegenskaper:

    - **Kundhierarki-ID** – Ett unikt ID för kundhierarkin. Detta ID använder den nummerserie som definierats i delade Commerce-parametrar i Commerce-administrationen.
    - **Namn** – Organisationsnamnet för affärspartnern, enligt vad som angetts i begäran om registrering.
    - **Syfte** – Denna egenskap är inställd på det fördefinierade värdet **B2B-organisation**.
    - **Organisation** – Kund-ID för affärspartnern.

Här finns information om kundhierarkiposten:

- Kundposten för begäranden associerats med kundhierarkin.
- Administratörsrollen associeras med begäranden.

När administratören lägger till fler användare till partnerorganisationen på en B2B-webbplats skapas en ny kundpost för respektive användare i Commerce-administrationen. Denna kundpost läggs också till i den relevanta kundhierarkiposten för affärspartnern och har rollen "användare".

> [!NOTE]
> I de flesta fall ska motsvarande egenskapsvärden för alla kundposter i en hierarki matcha. Eftersom alla affärspartnersanvändare exempelvis ska få liknande priser för produkter, ska deras prisgrupp och associerade konfigurationer matcha. Systemet framtvingar dock inte denna överensstämmelse. Därför ansvarar relevanta Commerce-administrationsanvändare för att egenskapsvärden och konfigurationer ska matcha för alla kunder i en given hierarki.

Användare av Commerce-administrationen kan även söka efter egenskapsvärden för alla kundposter i hierarkin i en vy sida vid sida. Välj relevanta egenskaper för kundposten genom att välja fliknamnen i listrutan. Användarna kan visa och redigera egenskapsvärdena direkt från den här vyn. Om du vill tillämpa alla värden från administratörskundposten på alla användarkundposter kan du också välja **Åsidosätt** i kundhierarkidetaljerna.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en B2B-näthandelssajt](set-up-b2b-site.md)

[Hantera affärspartneranvändare på B2B-näthandelssajter](manage-b2b-users.md)

[Konfigurera betalsätt för kundkonto för B2B-näthandelssajter](payment-method.md)

[Ange produktkvantitetsgränser för B2B-näthandelssajter](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]