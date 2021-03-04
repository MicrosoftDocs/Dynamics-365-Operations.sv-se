---
title: Konfigurera ditt domännamn
description: I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
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
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517142"
---
# <a name="configure-your-domain-name"></a>Konfigurera ditt domännamn


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats. 

## <a name="add-domains-during-e-commerce-initialization"></a>Lägg till domäner vid näthandelsinitiering

Om du vill associera domäner med din Dynamics 365 Commerce-näthandelsmiljö initierar du näthandeln enligt beskrivningen i [distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md). Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din näthandelsmiljö. I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön. Flera domäner måste skiljas åt med semikolon. På det här sättet konfigureras domänerna i alla nödvändiga komponenter för näthandel och de är klara att användas när du byter trafik från ditt nätverk för innehållsleverans (CDN) eller webbservern och riktar den mot näthandelsklienterna.

## <a name="add-domains-after-e-commerce-initialization"></a>Lägg till domäner efter näthandelsinitiering

Om du vill koppla nya domäner till din näthandelsmiljö efter näthandelsinitieringen måste du skicka in en tjänstebegäran.

## <a name="additional-resources"></a>Ytterligare resurser

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelsplats](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]