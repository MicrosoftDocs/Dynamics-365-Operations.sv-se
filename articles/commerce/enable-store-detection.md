---
title: Aktivera platsbaserad butiksidentifiering
description: I denna artikel beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 38c93e30a606d818d909a4ec014009c18c25e8c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274351"
---
# <a name="enable-location-based-store-detection"></a>Aktivera platsbaserad butiksidentifiering

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du aktiverar platsbaserad identifiering av lager för din Dynamics 365 Commerce-webbplats.

Med platsbaserad butiksidentifiering i näthandelsbutiken kan du tillhandahålla relevant webbplatsinnehåll för kunderna, baserat på deras plats. När platsbaserad identifiering av lager aktiveras, använder näthandelsbutikens återgivningstjänst information om land/region från IP-adressen till kundens webbläsare för att hänvisa kunden till den bästa tillgängliga konfigurationen för geografisk plats.

## <a name="privacy-notice"></a>Sekretesspolicy

Om du aktiverar den platsbaserade funktionen för identifiering av butiken skickas information från kundens webbläsare till en Microsoft-platstjänst. Denna information används sedan för att ge kundinnehållet som är relevant för kundens plats. Både de uppgifter som skickas från kundens webbläsare och den platsbaserade information som returneras till kunden omfattas av policyer för sekretess och cookie-kompatibilitet.

## <a name="turn-on-location-based-store-detection"></a>Aktivera platsbaserad butiksdetektering

Aktivera platsbaserad butiks identifiering i näthandelsbutiken genom att följa stegen nedan.

1. I utvecklingsverktyget går du till webbplatsen.
1. I navigeringsfönstret till vänster, välj **Platshantering**.
1. Välj **Platsinställningar**.
1. Ange alternativet **aktivera platsbaserade butiksidentifiering** till **På**.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
