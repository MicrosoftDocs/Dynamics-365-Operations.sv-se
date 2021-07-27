---
title: Konfigurera BOPIS i en Dynamics 365 Commerce-bedömningsmiljö
description: I det här avsnittet beskrivs hur du konfigurerar onlineköp, hämta i butik (BOPIS) i en Microsoft Dynamics 365 Commerce-utvärderingsmiljö efter att den har etablerats.
author: rubendel
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5f96302735e8aa1acf5c81992cb4cb49ff4a03ce
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352504"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurera BOPIS i en Dynamics 365 Commerce utvärderingsmiljö

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar hämta i butik (BOPIS) i en Microsoft Dynamics 365 Commerce-utvärderingsmiljö efter att miljön har etablerats.

## <a name="prerequisite"></a>Förutsättning

Slutför procedurerna i det här avsnittet först när bedömningsmiljö för Commerce har etablerats och konfigurerats. Information om hur du etablerar och konfigurerar din miljö, se [Etablera en bedömningsmiljö av Dynamics 365 Commerce](provisioning-guide.md) och [Konfigurera en bedömningsmiljö av Dynamics 365 Commerce](./cpe-post-provisioning.md).

När hela Commerce-miljön har etablerats och konfigurerats kan du använda det här avsnittet för att aktivera BOPIS-scenarier.

## <a name="configure-the-pos"></a>Konfigurera POS

### <a name="configure-modern-pos"></a>Konfigurera Modern POS

BOPIS-scenarier som involverar en kreditkortsbetalning kräver en maskinvarustation. Maskinvarustationen ingår i Modern POS för Windows och Android-klienter. Om du använder Cloud POS eller Modern POS för iOS måste POS kombineras med en delad maskinvarustation. I det här avsnittet beskrivs hur du konfigurerar BOPIS för Windows och Android-klienter. Mer information om hur du konfigurerar en delad maskinvarustation finns i [Konfiguration och installation av Retail Hardware Station](./retail-hardware-station-configuration-installation.md).

1. Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassor**.
2. Välj kassa **SANFRAN-5** och välj sedan **redigera**.
3. Ändra värdet för fältet **Maskinvaruprofil** från **HW002** till **HW001** och välj sedan **Spara**.
4. För att synkronisera ändringarna, gå till **Retail och Commerce \> Retail och Commerce IT \> Distributionsschema**.
5. Välj distributionsschema **1090** och sedan på åtgärdsfönstret väljer du **Kör nu**.
6. Välj **ja** och sedan **OK** för att initiera datasynkroniseringen. 

### <a name="install-modern-pos"></a>Installera Modern POS

1. Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Enheter**.
2. Välj enhet **SANFRANCIS-5**.
3. I åtgärdsfönstret, välj **Hämta** och välj sedan **konfigurationsfil**.
4. Välj **Hämta** och välj sedan **Retail Modern POS**. 
5. När hämtningen av filen **ModernPOSSetup.exe** är klar väljer du **Öppna fil**.

    ![Öppna fil.](./dev-itpro/media/PAYMENTS/openfile.png)

6. Välj **Nästa** om du vill gå igenom installationsprocessen. När installationen är klar, välj **Stäng**.

### <a name="activate-modern-pos"></a>Aktivera Modern POS

1. På Windows-skrivbordet, välj knappen **Start** och ange **Retail Modern POS**.
2. Välj den **Retail Modern POS**-app som ska initiera aktiveringen.
3. Välj **Nästa**. Fälten **Server-URL**, **Enhets-ID** och **Kassanummer** ska vara förinställda genom att använda information från konfigurationsfilen som du hämtade i föregående procedur.
4. Välj **aktivera**.
5. En dialogrutan för verifiering visas. Välj det konto som använder e-postadressen som tidigare kopplades till medarbetaren **000713 – Anders Collette**.

    > [!NOTE]
    > Om du ännu inte har associerat en medarbetare med din identitet kommer aktiveringen att misslyckas. Följ i så fall instruktionerna under avsnittet "Associera arbetare med din identitet", i ämnet [Konfigurera en bedömningsmiljö för Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. När du uppmanas att låta din organisation hantera enheten väljer du **Endast den här appen**.
7. När aktiveringen är slutförd, välj **Kom igång**.

### <a name="enable-bopis-in-modern-pos"></a>Aktivera BOPIS i Modern POS

1. Logga in på Modern POS genom att använda **000713** som operatörs-ID och **123** som lösenord.
2. Medan den inledande genomgångsvideon spelas upp markerar du de två kryssrutorna i det nedre vänstra hörnet av dialogrutan och stänger sedan dialogrutan.
3. Om du inte uppmanas att stänga skiftet rullar du till höger på **Välkomstsidan**, väljer **Stäng skift** och loggar in igen i POS.
4. När du har loggat in väljer du **Utföra en åtgärd som inte är en lådåtgärd** när du uppmanas.
5. På **Välkomstsidan** bläddra till höger och välj åtgärden **Välj maskinvarustation**.
6. Välj **hantera**, ställ in alternativet **Använd maskinvarustation** till **På** och välj sedan **OK**.
7. Logga ut från POS och logga sedan in igen.
8. När du har loggat in väljer du **Öppna ett nytt skift** och väljer sedan **Kassalåda**.

## <a name="complete-a-bopis-scenario"></a>Slutföra ett BOPIS-scenario

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Skapa en referensbutiken för upphämtning i butik

1. Gå till den URL som du angav i steget [Initiera e-Commerce](./provisioning-guide.md#initialize-e-commerce) under konfigurationen av miljön.
2. Välj en artikel och välj **Lägg till i kundvagn**.
3. På sidan för shoppingväska väljer du **Hämta den här** för den orderrad som du just har lagt till.
4. I dialogrutan **Välj en butik** anger du **San Francisco** och välj sedan knappen **Sök**.
5. Leta reda på San Francisco-butiken i resultat listan och välj **Hämta den här**.
6. På sidan för shoppingväska, välj **Gå till POS som gäst**. 

    > [!NOTE]
    > Om du vill fortsätta till POS måste du acceptera cookie-meddelandet. Det här meddelandet visas som en banderoll högst upp på kassasidan.

7. Ange följande information för betalsättet för kreditkort:

    - **Kortinnehavarens namn**: Ange vilket namn som helst.
    - **Kortnummer:** ange **4111-1111-1111-1111**.
    - **Utgångsdatum:** Ange **10/20**.
    - **Kortverifieringsnummer (CVV) kod:** Ange **737**.

    > [!IMPORTANT]
    > Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.

8. Fortsätt i POS genom att ange information om faktureringsadressen och välj sedan **Spara och fortsätt**.
9. När beställningen är klar att göras, välj **Kassa**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Synkronisera onlinebeställningar till backoffice

Information om hur du synkroniserar onlinebeställningar finns i [bokföra online försäljning och betalningar](./tasks/posting-online-sales-payments.md).

### <a name="pick-up-an-order-in-the-store"></a>Hämta en beställning i butik

1. Logga in i POS.
2. På **Välkomstskärmen**, välj **Orderuppfyllelse**
3. I listan över artiklar för upphämtning markerar du raden från den beställning som gjorts online.
4. När beställningsraden är vald, välj **Hämta**.

    Radartikeln läggs till transaktionsskärmen och **$0,00** visas som saldo som förfaller.

5. Välj saldo som förfaller för **$0,00** eller välj valfri betalningsmetod för att avsluta transaktionen.

## <a name="troubleshooting"></a>Felsökning

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>Onlinebeställningar som hämtas i POS har en skuld som inte är noll

När en beställning ska hämtas i butik, om förfallet saldo inte är 0 (noll), kontrollerar du att Modern POS används och att maskinvarustationen är aktiv. Om Cloud POS eller Modern POS för iOS används ska du kontrollera att en delad maskinvarustation är aktiv. Någon form av aktiv maskinvarustation krävs för att hämta betalningar som har gjorts online.

### <a name="general-issues-with-payment-capture"></a>Allmänna utleveranser vid betalningsregistrering

För alla allmänna problem bör du alltid läsa händelseloggarna i Modern POS-eller Internet Information Services (IIS) maskinvarustation som ett första steg. Dessa loggar finns under följande noder i Windows-händelselogg:

- Program- och tjänstloggar \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Program- och tjänstloggar \> Microsoft \> Dynamics \> Commerce-Maskinvarustation

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)

[Dynamics 365 Commerce bedömningsmiljö – vanliga frågor](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)

[Adyen-betalningskoppling](./dev-itpro/adyen-connector.md?tabs=8-1-3)

[Spara betalningsinstrument online med Adyen-kopplingen](./dev-itpro/adyen-connector-listpi.md)

[Översikt över betalningar i flera kanaler](./omni-channel-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]