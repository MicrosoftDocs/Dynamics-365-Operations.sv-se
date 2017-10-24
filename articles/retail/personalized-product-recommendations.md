---
title: "Översikt över anpassade produktrekommendationer"
description: "I Dynamics 365 for Retail kan produktrekommendationerna visas på kassaenheten. Rekommendationerna är artiklar som kunden kan vara intresserad av baserat på sina tidigare inköp, artiklar i önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker. För återförsäljare med stora kataloger hjälper rekommendationer kunden att identifiera produkter. Genom att visa upp produkter riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med merförsäljning och korsförsäljning, och förbättrad kundvård. I Dynamics 365 for Retail drivs produktrekommendationerna genom kognitiva tjänster och Microsoft Azure-maskininlärning."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d727718442f94a2a78a3864741e93439d7c36473
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="personalized-product-recommendations-overview"></a>Översikt över anpassade produktrekommendationer

[!include[banner](includes/banner.md)]


> [!NOTE]
> Denna funktion finns i dagsläget endast för begränsade distributionstopologier samt distributionstopologier för produktion (hög tillgänglighet). 

I Dynamics 365 for Retail kan produktrekommendationerna visas på kassaenheten. Rekommendationerna är artiklar som kunden kan vara intresserad av baserat på sina tidigare inköp, artiklar i önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker. För återförsäljare med stora kataloger hjälper rekommendationer kunden att identifiera produkter. Genom att visa upp produkter riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med merförsäljning och korsförsäljning, och förbättrad kundvård. I Dynamics 365 for Retail drivs produktrekommendationerna genom kognitiva tjänster och Microsoft Azure-maskininlärning.


<a name="scenarios"></a>Scenarier
---------

Produktrekommendationer har aktiverats för följande kassascenarier. De är tillgängliga i Cloud POS och Modern POS (MPOS).

1.  På sidan **Produktdetaljer**:

-   Om en butiksmedarbetare besöker en sida **Produktdetaljer** när han eller hon tittar på föregående transaktioner via olika kanaler, föreslår rekommendationsmotorn ytterligare artiklar som kan köpas tillsammans.
-   Om butiksmedarbetaren lägger till en kund i transaktionen och sedan besöker en **Produktdetaljer**-sida ger rekommendationsmotorn personliga rekommendationer som gjorts på kundens transaktionshistorik.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  På sidan **Transaktion**:

-   Rekommendationsmotorn föreslår artiklar baserat på hela listan över artiklar i varukorgen.
-   Om butiksmedarbetaren lägger till en kund i transaktionen, ger rekommendationsmotorn personliga rekommendationer som gjorts på kundens transaktionshistorik och listan med artiklar i varukorgen.

> [!NOTE]
> Återförsäljaren måste uppdatera skrämlayouten i Dynamics 365 for Retail för att kunna visa rekommendationer på sidan **Transaktion**. Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  På sidan **Kundinformation**:
    -   Rekommendationsmotorn föreslår artiklar baserat på användar-ID och artiklar i kundens önskelista.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a>Konfigurera Dynamics 365 for Retail för att aktivera kassarekommendationer
För att ställa in produktrekommendationer måste du göra följande.

1.  Kontrollera att du har valt rätt **Juridisk person**.
2.  Gå till **Entitetsbutik**, välj **Detaljhandelsförsäljning** och klicka sedan på **Uppdatera**. Då används demonstrationsdatan (eller din data) från din personliga databas och flyttas till entitetsbutiken.
3.  Tillval; Om du vill visa rekommendationer på transaktionsskärmen, gå då till **Skärmlayout**, välj din skärmlayout, starta **Designer för skrämlayout**, och släpp sedan kontrollen **Rekommendationer** där så behövs.
4.  Gå till **Detaljhandelsparametrar**, välj **Maskininlärning** och välj **Ja** under **Aktivera kassarekommendationer**.
5.  Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på kassan. Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.

## <a name="how-does-it-work"></a>[]()Hur fungerar det?
När du uppdaterar **Enhetslagring**-enheten utförs följande åtgärder.

-   Data i det format som krävs av kognitiva tjänster extraheras från Dynamics 365 for Retails driftsdatabas och skickas till enhetslagringen.
-   Informationen används av Azure Data Factory (ADF) för att rensa data med hjälp av Hive-skript som en del av ADM-aktiviteter. Rensade data lagras i blobb-lagring.
-   Data från blobb-lagring används av API för kognitiva tjänster för att utbilda en rekommendationsmodell.

När du har aktiverat **Aktivera rekommendationer** och kör konfigurationsjobb, utförs följande åtgärder.

-   Modellautentiseringsuppgifter och -ID hämtas från API och lagras i Dynamics 365 for Retails driftsdatabas, i web.config för AOS, och även i butiksservern.
-   Modellautentiseringsuppgifter och -ID görs tillgängliga för CRT så att anrop för produktrekommendationer från Cloud POS och MOPS i onlineläge kan utföras.


<a name="see-also"></a>Se även
--------

[Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet](add-recommendations-control-pos-screen.md)




