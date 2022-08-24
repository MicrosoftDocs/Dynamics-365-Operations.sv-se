---
title: Konfigurera ditt domännamn
description: I denna artikel beskrivs hur du konfigurerar ett domännamn för en Microsoft Dynamics 365-näthandelssajt.
author: josaw1
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 298ce84008e60cc82a494320b6a41f35338508c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278635"
---
# <a name="configure-your-domain-name"></a>Konfigurera ditt domännamn


[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar ett domännamn för en Microsoft Dynamics 365-näthandelssajt. 

## <a name="add-domains-during-e-commerce-initialization"></a>Lägg till domäner vid näthandelsinitiering

Om du vill associera domäner med din Dynamics 365 Commerce-näthandelsmiljö initierar du näthandeln enligt beskrivningen i [distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md). Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din näthandelsmiljö. I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön. Flera domäner måste skiljas åt med semikolon. På det här sättet konfigureras domänerna i alla nödvändiga komponenter för näthandel och de är klara att användas när du byter trafik från ditt nätverk för innehållsleverans (CDN) eller webbservern och riktar den mot näthandelsklienterna.

## <a name="add-domains-after-e-commerce-initialization"></a>Lägg till domäner efter näthandelsinitiering

Om du vill koppla nya domäner till din näthandelsmiljö efter näthandelsinitieringen måste du skicka in en tjänstebegäran.

## <a name="additional-resources"></a>Ytterligare resurser

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
