---
title: "Översikt över anpassade produktrekommendationer"
description: "Det här avsnittet innehåller information om produktrekommendationer fra Dynamics 365 for Retail som kan visas på kassaenheten."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: c5b9ee57b0b855766628caca239059205c103b86
ms.openlocfilehash: 4a0586324dddc10d64ad6760222f2540f31d6bce
ms.contentlocale: sv-se
ms.lasthandoff: 03/08/2018

---

# <a name="personalized-product-recommendations-overview"></a>Översikt över anpassade produktrekommendationer

[!include[banner](includes/banner.md)]


> [!NOTE]
> Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner. Mer information finns i beskrivningen av [borttagna eller gamla funktioner](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features). Gå längst ned på sidan om du står inför problem med redan aktiverade produktrekommendationer för din miljö. 

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
2.  Gå till **Enhetsbutiken**markerar du **Butiksförsäljning** och klickar sedan på **Uppdatera**. Detta använder demonstrationsdata (eller data) från databasen fungerar och flytta den till enbutiken för enhetslagring.
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

> ## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Felsök problem där du redan produktrekommendationer aktiverade 
>- Gå till **butiksparametrar** > **datorinlärning** > **inaktivera produktrekommendationer** och kör **Globalt konfigurationsjobb [1110]**. Om du inte kan hitta fliken **datorinlärning** kontaktar du Dynamics Support. 

>- Om du har lagt till **rekommendationskontroll** till din transaktionsskärm med **Layoutdesigner för skärm**, ta även bort den. 



<a name="see-also"></a>Se även
--------

[Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet](add-recommendations-control-pos-screen.md)




