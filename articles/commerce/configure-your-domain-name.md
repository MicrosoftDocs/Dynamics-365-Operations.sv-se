---
title: Konfigurera ditt domännamn
description: I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a988f533757cc3f8555fcf4fb724a22a5b014f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770468"
---
# <a name="configure-your-domain-name"></a>Konfigurera ditt domännamn

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats. 

## <a name="add-domains-during-e-commerce-initialization"></a>Lägg till domäner vid näthandelsinitiering

Om du vill associera domäner med näthandelsmiljön initierar du e-handel enligt beskrivningen i [distribuera en ny näthandelsplats](deploy-ecommerce-site.md). Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din e-handelsmiljö. I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön. Flera domäner måste skiljas åt med semikolon. På det här sättet konfigureras domänerna i alla nödvändiga komponenter för e-handel och de är klara att användas när du byter trafik från ditt innehållsleveransnätverk (CDN) eller webbservern och pekar den på näthandelns klientdel.

## <a name="add-domains-after-e-commerce-initialization"></a>Lägg till domäner efter näthandelsinitiering

Om du vill koppla nya domäner till din e-handelsmiljö efter initieringen av e-handel måste du skicka en tjänstbegäran.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över onlinebutik](online-store-overview.md)

[Skapa en näthandelsplats](create-ecommerce-site.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)
