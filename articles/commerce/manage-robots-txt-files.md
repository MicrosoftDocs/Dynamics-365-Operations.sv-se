---
title: Hantera robots.txt-filer
description: I denna artikel beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: b66d6f725c345ff82d3f3f8c33d609fa770addf1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286422"
---
# <a name="manage-robotstxt-files"></a>Hantera robots.txt-filer

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.

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

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Skapa en näthandelssajt](create-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-klientorganisation i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
