---
title: "Översikt över anpassade produktrekommendationer"
description: "I Dynamics 365 for Operations visas produktrekommendationer på kassaenheten. Rekommendationerna är artiklar som kunden kan vara intresserad av baserat på sina tidigare inköp, artiklar i önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker. För återförsäljare med stora kataloger hjälper rekommendationer kunden att identifiera produkter. Genom att visa upp produkter riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med merförsäljning och korsförsäljning, och förbättrad kundvård. I Dynamics 365 for Operations är produktrekommendationer utrustade med kognitiva tjänster och Microsoft Azure maskininlärning."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: cff74e825b4d61f538ce02f79860413281617354
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="personalized-product-recommendations-overview"></a>Översikt över anpassade produktrekommendationer

[!include[banner](includes/banner.md)]


I Dynamics 365 for Operations visas produktrekommendationer på kassaenheten. Rekommendationerna är artiklar som kunden kan vara intresserad av baserat på sina tidigare inköp, artiklar i önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker. För återförsäljare med stora kataloger hjälper rekommendationer kunden att identifiera produkter. Genom att visa upp produkter riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med merförsäljning och korsförsäljning, och förbättrad kundvård. I Dynamics 365 for Operations är produktrekommendationer utrustade med kognitiva tjänster och Microsoft Azure maskininlärning.

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

**Obs!** För att visa rekommendationer på sidan **Transaktion** måste återförsäljaren uppdatera skärmlayouten i Dynamics 365 for Operations. Kontrollen **Rekommendationer** måste tas bort på sidan **Transaktion**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  På sidan **Kundinformation**:
    -   Rekommendationsmotorn föreslår artiklar baserat på användar-ID och artiklar i kundens önskelista.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Konfigurera Dynamics 365 for Operations att aktivera kassarekommendationer
För att ställa in produktrekommendationer måste du göra följande.

1.  Kontrollera att du har valt rätt **Juridisk person**.
2.  Gå till **Enhetslagring**, välj **Butiksförsäljning** och klicka sedan på **Uppdatera**. ** ** Då används demodata (eller dina data) från din driftsdatabas fungerar och flyttas till enhetslagring.
3.  Valfritt: Om du vill visa rekommendationer på transaktionsskärmen går du till **Skärmlayout, **väljer din skärmlayout, startar **Layoutdesigner för skärm**,** **och släpper **rekommendationskontrollen** där den behövs.
4.  Gå till **Butiksparametrar**, välj **Maskininlärning**,välj **Ja **under **Aktivera kassarekommendationer**.
5.  Kör jobbet **1110** för global konfiguration om du vill se rekommendationer på kassan. Kör kanalkonfigurationsjobbet **1070** för att avspeglar ändringar i kassaskärmens layoutdesigner.

## <a name="how-does-it-work"></a>[]()Hur fungerar det?
När du uppdaterar **Enhetslagring**-enheten utförs följande åtgärder.

-   Data i det format som krävs av kognitiva tjänster extraheras från Dynamics 365 for Operations driftsdatabas och skickas till enhetslagringen.
-   Informationen används av Azure Data Factory (ADF) för att rensa data med hjälp av Hive-skript som en del av ADM-aktiviteter. Rensade data lagras i blobb-lagring.
-   Data från blobb-lagring används av API för kognitiva tjänster för att utbilda en rekommendationsmodell.

När du har aktiverat **Aktivera rekommendationer** och kör konfigurationsjobb, utförs följande åtgärder.

-   Modellautentiseringsuppgifter och -ID hämtas från API och lagras i Dynamics 365 for Operations driftdatabas, i web.config för AOS, och även i butiksservern.
-   Modellautentiseringsuppgifter och -ID görs tillgängliga för CRT så att anrop för produktrekommendationer från Cloud POS och MOPS i onlineläge kan utföras.


<a name="see-also"></a>Se även
--------

[Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet](add-recommendations-control-pos-screen.md)




