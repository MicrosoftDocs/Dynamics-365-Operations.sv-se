---
title: "Personliga rekommendationer Produktöversikt"
description: "I Dynamics 365 för operationer visas produktrekommendationer på enheten (PO) för försäljning. Rekommendationerna är artiklar som kunden kan vara intressanta baserat på deras tidigare inköp, artiklar i deras önskelista och artiklar som andra kunder köpt online och på bankkontor och andra butiker. För återförsäljare med stora kataloger hjälp rekommendationer med av kunden identifiering av produkten. Presenterar produkterna till en kunds intresse och inköp vanor produktrekommendationer återförsäljare kan hjälpa till med skapar merförsäljning och mellan kund och kan förbättra innehållet belopp från kund. I Dynamics 365 för operationer, är produktrekommendationer utrustade med kognitiva tjänster och Microsoft Azure maskin utbildning."
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
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Personliga rekommendationer Produktöversikt

I Dynamics 365 för operationer visas produktrekommendationer på enheten (PO) för försäljning. Rekommendationerna är artiklar som kunden kan vara intressanta baserat på deras tidigare inköp, artiklar i deras önskelista och artiklar som andra kunder köpt online och på bankkontor och andra butiker. För återförsäljare med stora kataloger hjälp rekommendationer med av kunden identifiering av produkten. Presenterar produkterna till en kunds intresse och inköp vanor produktrekommendationer återförsäljare kan hjälpa till med skapar merförsäljning och mellan kund och kan förbättra innehållet belopp från kund. I Dynamics 365 för operationer, är produktrekommendationer utrustade med kognitiva tjänster och Microsoft Azure maskin utbildning.

<a name="scenarios"></a>Scenarier
---------

Produktrekommendationer har aktiverats för följande scenarier POS. De är tillgängliga i molnbaserad kassa eller Modern POS (MOPS).

1.  I den **produktinformation** sida:

-   Om du kopplar en butik Besök en **produktinformation** när du tittar på tidigare transaktioner via olika kanaler rekommendation motor föreslår ytterligare artiklar som kan köpas tillsammans.
-   Om butiken associerar lägger till en kund i transaktionen och besök sedan en **produktinformation**, rekommendation motorn ger personliga rekommendationer som gjorts på kundens transaktionshistorik.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  I den **transaktionen** sida:

-   Rekommendation motor föreslår artiklar baserat på hela listan över artiklar i varukorgen.
-   Om butiken associera lägger till en kund i transaktionen, rekommendation motorn ger personliga rekommendationer med kundens transaktionshistorik och listan över artiklar i varukorgen.

**Observera** ska visas rekommendationer i den **transaktionen** återförsäljaren behöver uppdatera skärmlayout i Dynamics 365 för operationer på sidan. Den **rekommendationer** kontroll måste tas bort i den **transaktionen** sida. [![transactionscreenmultipleproductslargemessengersbag 5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  I den **kunduppgifter** sida:
    -   Rekommendation motor föreslår artiklar baserat på användar-ID och artiklar i kundens önskelista.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Konfigurera Dynamics 365 att aktivera rekommendationer i kassa
Om du vill ställa in produktrekommendationer måste du göra följande.

1.  Kontrollera att du har valt rätt **juridisk person**.
2.  Gå till **enhet butiken**markerar **Retail försäljning**, och klicka sedan på **uppdatera**. ** ** tas använder demodata (eller data) från databasen fungerar och flyttas det till arkivet för enheten.
3.  Valfritt: Rekommendationer på skärmen transaktionen visas går du till ** skärmlayout, **väljer du ditt skärmlayout, starta den **Layoutdesigner för skärm**,** ** och släpper den ** rekommendationer kontrollen ** vid behov.
4.  Gå till **RETUR**Välj **maskin-utbildning**väljer ** Ja ** under **POS aktivera rekommendationer**.
5.  Kör jobbet för global konfiguration om du vill se rekommendationer för kassa **1110**. Kör kanal konfiguration jobbet så att det avspeglar ändringar i kassa Layoutdesigner för skärm **1070**.

## <a name="how-does-it-work"></a>[]()Hur fungerar det?
När du uppdaterar den **enhet butiken** entitet följande åtgärder utföras.

-   Data i det format som krävs av kognitiva framställd Dynamics 365 för operationer fungerande databas och skickas till butiken entitet.
-   Informationen används av Azure Data Factory (ADF) för att rengöra data med hjälp av skript i strukturen som en del av ADM-aktiviteter. Rengörs data lagras i blob-lagring.
-   Data från blob-lagring används av kognitiva services API för att utbilda en rekommendation modell.

När du har aktiverat **aktivera rekommendationer för** och kör jobb konfiguration, följande åtgärder utföras.

-   Förlaga autentiseringsuppgifter och -ID hämtas från API och lagras i Dynamics 365 för operationer fungerande databas i web.config för AOS och även i retail-servern.
-   Förlaga autentiseringsuppgifter och ID görs tillgängliga för CRT så att samtal för produktrekommendationer molnbaserad kassa och MOPS i onlineläge kan värderas.


<a name="see-also"></a>Se även
--------

[Lägga till en kontroll med rekommendationer på sidan transaktionen på en POS-enhet](add-recommendations-control-pos-screen.md)


