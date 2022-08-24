---
title: Välj bort insamling av webbaktivitetshändelser
description: I denna artikel beskrivs hur du kan låta besökare på webbplatsen välja bort insamling av webbaktivitetshändelser i Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: 81343f5033366484140f73fcc313ecd9f35e7d47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286736"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Välj bort insamling av webbaktivitetshändelser
[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du kan låta kunderna välja bort insamling av webbaktivitetshändelser i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce låter webbplatsadministratörer analysera webbaktiviteten bland användarna av deras näthandelssidor. På så sätt kan de bättre förstå hur deras webbplatser används och kan optimera webbplatserna så att dessa ger en förbättrad användarupplevelse och uppfylla affärsmål.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Sätt för administratörer att implementera en avanmälningsupplevelse

Administratörer har tre sätt att implementera en avanmälningsupplevelse.

### <a name="opt-out-on-behalf-of-users"></a>Avanmälning för användarnas räkning

Under Kontohantering i Commerce headquarters (HQ) kan administratörer avanmäla sig för användarnas räkning.

1. Sök efter samt välj en kund på sidan **Alla kunder** i HQ-klienten.
1. I snabbfliken **Detaljhandel** på sidan för kundinformation, i avsnittet **Sekretess**, anger du alternativet **Spåra inte webbaktivitet** som **Ja**.

    ![Sekretessinställningar.](media/Disablepersonalizationpart2.png)

1. Markera **Spara** och stäng sedan sidan.

### <a name="module-based-opt-out-experience"></a>Modulbaserad avanmälningsupplevelse

Administratörer kan låta autentiserade användare själva säga upp insamling av webbaktivitetshändelser. För att tillhandahålla den här avanmälningsupplevelsen lägger du till avanmälningsmodulen i profilsidor för kundkonton.

### <a name="custom-extensions"></a>Anpassade tillägg

Administratörer kan skapa sina egna tillägg för att hantera användarnas avanmälningsfunktioner. Mer information finns i [anropa API:er för Butik](e-commerce-extensibility/call-retail-server-apis.md) och [Utbyggbarhet av onlinekanal](e-commerce-extensibility/overview.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
