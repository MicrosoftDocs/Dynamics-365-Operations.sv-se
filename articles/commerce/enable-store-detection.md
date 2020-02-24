---
title: Aktivera platsbaserad butiksdetektering
description: I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.
author: brianshook
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 304d8d2f05916295b9c6320561d6a25ff40df955
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003106"
---
# <a name="enable-location-based-store-detection"></a>Aktivera platsbaserad butiksdetektering


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.

## <a name="overview"></a>Översikt

Med platsbaserad butiksidentifiering i näthandelsbutiken kan du tillhandahålla relevant webbplatsinnehåll för kunderna, baserat på deras plats. När platsbaserad identifiering av lager aktiveras, använder näthandelsbutikens återgivningstjänst information om land/region från IP-adressen till kundens webbläsare för att hänvisa kunden till den bästa tillgängliga konfigurationen för geografisk plats.

## <a name="privacy-notice"></a>Sekretesspolicy

Om du aktiverar den platsbaserade funktionen för identifiering av butiken skickas information från kundens webbläsare till en Microsoft-platstjänst. Denna information används sedan för att ge kundinnehållet som är relevant för sin plats. Både de uppgifter som skickas från kundens webbläsare och den platsbaserade information som returneras till kunden omfattas av policyer för sekretess och cookie-kompatibilitet.

## <a name="turn-on-location-based-store-detection"></a>Aktivera platsbaserad butiksdetektering

Aktivera platsbaserad butiks identifiering i näthandelsbutiken genom att följa stegen nedan.

1. I utvecklingsverktyget går du till webbplatsen.
1. I navigeringsfönstret till vänster, välj **Platshantering**.
1. Välj **Platsinställningar**.
1. Ange alternativet **aktivera platsbaserade butiksidentifiering** till **På**.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)
