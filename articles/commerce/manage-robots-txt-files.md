---
title: Hantera robots.txt-filer
description: I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1f7a779d69bf49d3416de3e92d4414cfabf358eb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983633"
---
# <a name="manage-robotstxt-files"></a>Hantera robots.txt-filer


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Robots-exkluderingsstandarden, eller robots.txt, är en standard som webbplatser använder för att kommunicera med webbrobotar. Den instruerar webbrobotar om alla områden på en webbplats som inte bör besökas. Robotar används ofta av sökmotorer för att indexera webbplatser.

Om du vill utesluta robotar från en server skapar du en fil på servern. I den här filen anger du en åtkomstprincip för robotar. Filen måste vara tillgänglig via HTTP på den lokala URL: **/robots.txt**. Filen robots.txt hjälper sökmotorer att indexera innehållet på din webbplats.

Dynamics 365 Commerce låter dig ladda upp en robots.txt-fil för din domän. För varje domän i din Commerce-miljö kan du ladda upp en robots.txt-fil och associera den med den domänen.

För mer information om robots.txt-filen, besök [sidor för webbrobotar](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Ladda upp en robots.txt-fil

När du har skapat och redigerat filen robots.txt enligt [robots-exkluderingsstandarden](https://www.robotstxt.org/orig.html) kontrollerar du att filen är tillgänglig på den dator där du ska använda Commerce-redigeringsverktygen. Filen måste ha namnet **robots.txt**. För bästa resultat måste det vara i det format som anges i standarden. Varje Commerce-kund ansvarar för att validera och underhålla innehållet i sin robots.txt-fil. För att överföra en robots.txt-file måste du logga in på Commerce som systemadministratör.

Så här överför du en robots.txt-fil i Commerce.

1. Logga in på Commerce som systemadministratör.
2. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.
3. Under **innehavarinställningar** väljer du **Robots.txt**. En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.
4. Välj **hantera** om du vill överföra en robots.txt-fil för en domän i din miljö.
5. På menyn till höger väljer du knappen **Överför** (pilen uppåt) bredvid den domän som är associerad med robots.txt-filen. En dialogruta för filbläddraren visas.
6. Bläddra till och markera den robots.txt-fil som du vill överföra för den associerade domänen i dialogrutan och välj sedan **öppna** för att slutföra överföringen.

> [!NOTE] 
> Under överföringen verifierar Commerce att filen är en textfil, men den validerar inte filens innehåll.

## <a name="download-a-robotstxt-file"></a>Ladda ned en robots.txt-fil

Så här laddar du ned en robots.txt-fil i Commerce.

1. Logga in på Commerce som systemadministratör.
2. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.
3. Under **innehavarinställningar** väljer du **Robots.txt**. En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.
4. Välj **hantera** om du vill ladda ned en robots.txt-fil för en domän i din miljö.
5. På menyn till höger väljer du knappen **Ladda ned** (pilen nedåt) bredvid den domän som är associerad med robots.txt-filen. En dialogruta för filbläddraren visas.
6. Gå till önskad plats på den lokala enheten i dialogrutan, bekräfta eller ange ett filnamn och välj sedan **spara** för att slutföra hämtningen.

> [!NOTE]
> Den här proceduren kan endast användas för att hämta robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.

## <a name="delete-a-robotstxt-file"></a>Ta bort en robots.txt-fil

Så här tar du bort en robots.txt-fil i Commerce.

1. Logga in på Commerce som systemadministratör.
2. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.
3. Under **innehavarinställningar** väljer du **Robots.txt**. En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.
4. Välj **hantera** om du vill ta bort en robots.txt-fil för en domän i din miljö.
5. På menyn till höger väljer du knappen **Ta bort** (papperskorgsymbolen) bredvid den domän som är associerad med robots.txt-filen. Ett filwebbläsarfönster visas.
6. Bläddra till filwebbläsarfönster och markera den robots.txt-fil som du vill ta bort för domänen i dialogrutan och välj sedan **öppna**. En varningsmeddelanderuta visas.
7. I meddelanderutan väljer du **ta bort** för att bekräfta borttagningen av robots.txt-filen.

> [!NOTE] 
> Den här proceduren kan endast användas för att ta bort robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Överföring av URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
