---
title: "Onlinebutiksöversikt"
description: "Den här artikeln innehåller information om onlinebutiker för detaljhandel och hur du ställer in dem i Microsoft Dynamics 365 for Operations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40fbf8b4fdfed32dd67013b6b21cc2c8ee3d31e6
ms.lasthandoff: 03/31/2017


---

# <a name="online-store-overview"></a>Onlinebutiksöversikt

[!include[banner](includes/banner.md)]


Den här artikeln innehåller information om onlinebutiker för detaljhandel och hur du ställer in dem i Microsoft Dynamics 365 for Operations.

Detaljhandel och handel i Dynamics 365 for Operations stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). En onlinebutik ger en återförsäljare onlinenärvaro så att deras kunder kan köpa produkter från deras onlinebutik såväl som från deras fysiska butik. Om kunder köper produkter från onlinebutiken kan dessa produkter levereras till sig eller så kan kunden hämta produkterna från en lokal butik. Du skapar en onlinebutik i Dynamics 365 for Operations-klienten. Denna onlinebutik publiceras sedan till en tredje parts onlinebutik som har integrerats med Dynamics 365 for Operations. Tredje parts onlinebutik fungerar som skyltfönstret (användargränssnitt) för onlinebutiken och får du ett urval av kundhanteringsystem (CMS) och UI-kapaciteter. Flera integrationer av den här typen är tillgängliga för Dynamics 365 for Operations. De egenskaper som du definierar för onlinebutiken styr hur onlinebutiken fungerar. Till exempel definierar du navigeringskategorihierarkin i Dynamics 365 for Operations och tilldelar den till onlinebutiken. När du publicerar onlinebutiken i en tredje parts onlinebutik kommer navigeringskategorihierarkin att visas i butikens onlineversion. Shoppare använder navigeringskategorihierarkin för att bläddra i onlinebutiken och för att söka efter produkter. Om du vill skapa onlinebutiken måste du ställa in de komponenter som aktiverar transaktioner som ska bearbetas för butiken. Till exempel måste du lägga till sortiment, tillämpa attribut och ställa in betalningsmetoder och leveranssätt. Du kan också ange priser, rabatter, kampanjer, handelsavtal och sändningstermer som är specifika för storen online. När du har publicerat onlinebutiken på tredje partens onlinebutik kan du skapa butiksproduktkataloger för onlinebutiken. Produkterna i katalogen blir produktlistor i onlinebutiken. När en shoppare köper produkter från onlinebutiken, synkroniseras och uppdateras tillgängligt lager i klienten. Försäljningsorder skapas för inköpen och skickas till klienten för orderbehandling och bearbetning.

## <a name="set-up-an-online-store"></a>Konfigurera en onlinebutik
Om du vill ställa in en onlinebutik måste du göra följande.

1.  Skapa onlinebutik.
2.  Lägg till onlinebutiken i lämpliga organisationshierarkier.
3.  Lägg till sortiment som innehåller de produkter som är tillgängliga i onlinebutiken.
4.  Tilldela eller skapa prisgrupper för onlinebutiken.
5.  Ställa in leveranssätt som är tillgängliga i onlinebutiken.
6.  Tilldela de betalningsmetoder som har godkänts för onlinebutiken.
7.  Om du tillåter shoppare att beställa produkter online och sedan plocka upp dem i en lokal butik, tilldela butikslokaliserargrupper till onlinebutiken.
8.  Tilldela attribut för kanaler, produkter och försäljningsorder till onlinebutiken. Kanalattribut gäller för hela onlinebutiken, produktattribut gäller för de produkter som erbjuds i onlinebutiken och försäljningsorderattribut gäller för försäljningsorder som genereras från onlinebutiken.
9.  Mappa attribut när du vill definiera de egenskaper som bestämmer hur dessa attributen uppför sig i onlinekanalen. Du kan till exempel definiera attribut som ska vara obligatoriska eller sökbara.
10. Publicera onlinebutiken för att generera butikstrukturen på ditt val av tredje parts onlinebutik. **Viktigt:** Innan du publicerar onlinebutiken måste du ställa in en distributionsplats för onlinebutiken.

## <a name="retail-channel-navigation-hierarchies"></a>Navigeringshierarkier för butikskanal
Innan du kan skapa en onlinebutik måste du skapa en navigeringshierarki för butikskanal som du vill använda för den. Navigeringshierarkin för butikskanaler representerar kategorihierarkin som visas i onlinebutiken efter att den har publicerats. När du publicerar butiksproduktkataloger för onlinebutiken kommer produkter i katalogen att mappas till kategorier i navigeringshierarkin för butikskanalen. Shoppare kan sedan använda hierarkin när de navigerar i onlinebutiken.

## <a name="organization-hierarchies"></a>Organisationshierarkier
Organisationshierarkier används för att strukturera butikskanaler. Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag. När du ställer in onlinebutiker kan du lägga till dem till en organisationshierarki. Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering. När du skapar en organisationshierarki måste du tilldela ett syfte till den. Syftet anger hur hierarkin används i affärsstrukturen. Du kan skapa en organisationshierarki för dina Butiksåtgärder och användning som hierarkin för sortiment, påfyllnad och rapportering. Alternativt kan du skapa en separat organisationshierarki för varje syfte. Du kan även skapa flera hierarkier som har samma syfte, och tilldela en separat kanal för var och en. Om du vill publicera butiksproduktkataloger i onlinebutiken, ska du åtminstone lägga till onlinebutiken i en organisationshierarki för sortiment. Produkterna i en katalog väljs från de sortiment som tilldelats till onlinebutiken. När katalogen publiceras, jämför publiceringsprocessen giltighetsdatum för sortimentet som tilldelats onlinebutiken med de produkter som ingår i katalogen för att avgöra vilka produkter som ska vara tillgängliga i onlinebutiken.




