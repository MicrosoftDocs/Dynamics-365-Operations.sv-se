---
title: Ställ in en kanal för onlinebutik
description: Den här artikeln innehåller information om onlinebutikskanaler för detaljhandel och hur du ställer in dem i Dynamics 365 Commerce.
author: kfend
manager: AnnBe
ms.date: 03/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelManagementWorkspace, RetailOnlineStoreList
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b719e40720b091eec879edf332ab63db710a1ebc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096904"
---
# <a name="set-up-an-online-store-channel"></a>Ställ in en kanal för onlinebutik

[!include [banner](includes/banner.md)]

Den här artikeln innehåller information om onlinebutikskanaler för detaljhandel och hur du ställer in dem i Dynamics 365 Commerce.

Handel stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). En onlinebutik ger en återförsäljare onlinenärvaro så att deras kunder kan köpa produkter från deras onlinebutik såväl som från deras fysiska butik. Om kunder köper produkter från onlinebutiken kan dessa produkter levereras till sig eller så kan kunden hämta produkterna från en lokal butik. 

Du skapar en onlinebutik på handelsklienten. Denna onlinebutik publiceras sedan till en tredje parts onlinebutik som har integrerats med Handel. Tredje parts onlinebutik fungerar som skyltfönstret (användargränssnitt) för onlinebutiken och får du ett urval av kundhanteringsystem (CMS) och UI-kapaciteter. Flera integrationer av den här typen är tillgängliga. 

De egenskaper som du definierar för onlinebutiken styr hur onlinebutiken fungerar. Till exempel definierar du navigeringskategorihierarkin och tilldelar den till onlinebutiken. När du publicerar onlinebutiken i en tredje parts onlinebutik kommer navigeringskategorihierarkin att visas i butikens onlineversion. Shoppare använder navigeringskategorihierarkin för att bläddra i onlinebutiken och för att söka efter produkter. 

Om du vill skapa onlinebutiken måste du ställa in de komponenter som aktiverar transaktioner som ska bearbetas för butiken. Till exempel måste du lägga till sortiment, tillämpa attribut och ställa in betalningsmetoder och leveranssätt. Du kan också ange priser, rabatter, kampanjer, handelsavtal och sändningstermer som är specifika för storen online. 

När du har publicerat onlinebutiken på tredje partens onlinebutik kan du skapa produktkataloger för onlinebutiken. Produkterna i katalogen blir produktlistor i onlinebutiken. När en shoppare köper produkter från onlinebutiken, synkroniseras och uppdateras tillgängligt lager i klienten. Försäljningsorder skapas för inköpen och skickas till klienten för orderbehandling och bearbetning.

## <a name="set-up-an-online-store"></a>Konfigurera en onlinebutik

Om du vill ställa in en onlinebutik måste du göra följande.

1. Skapa onlinebutik.
2. Lägg till onlinebutiken i lämpliga organisationshierarkier.
3. Lägg till sortiment som innehåller de produkter som är tillgängliga i onlinebutiken.
4. Tilldela eller skapa prisgrupper för onlinebutiken.
5. Ställa in leveranssätt som är tillgängliga i onlinebutiken.
6. Tilldela de betalningsmetoder som har godkänts för onlinebutiken.
7. Om du tillåter shoppare att beställa produkter online och sedan plocka upp dem i en lokal butik, tilldela butikslokaliserargrupper till onlinebutiken.
8. Tilldela attribut för kanaler, produkter och försäljningsorder till onlinebutiken. Kanalattribut gäller för hela onlinebutiken, produktattribut gäller för de produkter som erbjuds i onlinebutiken och försäljningsorderattribut gäller för försäljningsorder som skapas från onlinebutiken.
9. Mappa attribut när du vill definiera de egenskaper som bestämmer hur dessa attributen uppför sig i onlinekanalen. Du kan till exempel definiera attribut som ska vara obligatoriska eller sökbara.
10. Publicera onlinebutiken för att skapa butikstrukturen på ditt val av tredje parts onlinebutik.

    > [!IMPORTANT]
    > Innan du publicerar onlinebutiken måste du ställa in en distributionsplats för onlinebutiken.

## <a name="commerce-channel-navigation-hierarchies"></a>Navigeringshierarkier för handelskanal

Innan du kan skapa en onlinebutik måste du skapa en navigeringshierarki för handelskanal som du vill använda för den. Navigeringshierarkin för kanaler representerar kategorihierarkin som visas i onlinebutiken efter att den har publicerats. När du publicerar produktkataloger för onlinebutiken kommer produkter i katalogen att mappas till kategorier i navigeringshierarkin för kanalen. Shoppare kan sedan använda hierarkin när de navigerar i onlinebutiken.

## <a name="organization-hierarchies"></a>Organisationshierarkier

Organisationshierarkier används för att strukturera handelskanaler och för att representera relationerna mellan de organisationer som finns i företaget. När du ställer in onlinebutiker kan du lägga till dem till en organisationshierarki. Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering. 

När du skapar en organisationshierarki måste du tilldela ett syfte till den. Syftet anger hur hierarkin används i affärsstrukturen. Du kan skapa en organisationshierarki för dina Butiksåtgärder och användning som hierarkin för sortiment, påfyllnad och rapportering. 

Alternativt kan du skapa en separat organisationshierarki för varje syfte. Du kan även skapa flera hierarkier som har samma syfte, och tilldela en separat kanal för var och en. Om du vill publicera produktkataloger i onlinebutiken, ska du åtminstone lägga till onlinebutiken i en organisationshierarki för sortiment. Produkterna i en katalog väljs från de sortiment som tilldelats till onlinebutiken. När katalogen publiceras, jämför publiceringsprocessen giltighetsdatum för sortimentet som tilldelats onlinebutiken med de produkter som ingår i katalogen för att avgöra vilka produkter som ska vara tillgängliga i onlinebutiken.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Skapa en e-handelsplats](create-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överföring av URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)