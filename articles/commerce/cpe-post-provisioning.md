---
title: Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce
description: Detta ämne förklarar hur du konfigurerar förhandsversionsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ad05996eaabd3965308370649a27b8bc3080c7ce
ms.sourcegitcommit: f72e90dccc80718e99cab2752eaf8931dcbb915e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "3534077"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a>Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

Detta ämne förklarar hur du konfigurerar förhandsversionsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.

## <a name="overview"></a>Översikt

Slutför procedurerna i det här avsnittet först när förhandsversionsmiljö för Commerce har etablerats. Information om hur du konfigurerar etablerar förhandsversionsmiljö för Commerce, se [Etablera en förhandsversionsmiljö för Commerce](provisioning-guide.md).

När din förhandsversionsmiljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön. Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.

## <a name="before-you-start"></a>Innan du börjar

1. Logga in på [LCS-portal](https://lcs.dynamics.com).
1. Gå till ditt projekt.
1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Välj i miljöinformation till höger **Fullständig information**.
1. Välj **Logga in** för att öppna en meny och välj sedan **Logga in på miljön**.
1. Kontrollera att **USRT** juridisk person har valts i övre högra hörnet.

## <a name="configure-the-point-of-sale-in-lcs"></a>Konfigurera kassan i LCS

### <a name="associate-a-worker-with-your-identity"></a>Associera arbetare med din identitet

Om du vill associera en anställd med din identitet i LCS, följ dessa steg.

1. Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> arbetare**.
1. Hitta och markera följande post: **000713 - Andrew Collette** i listan.
1. Klicka på **butik** i åtgärdsfönstret.
1. Välj **Associera befintlig identitet**.
1. I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.
1. Välj **Sök**.
1. Markera posten med ditt namn.
1. Välj **OK**.
1. Välj **Spara**.

### <a name="activate-cloud-pos"></a>Aktivera molnbaserad kassa

Om du vill aktivera Cloud POS i LCS, följ dessa steg.

1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Välj i miljöinformation till höger **Fullständig information**.
1. Välj **logga in** för att öppna en meny och välj sedan **Logga in på Cloud Point of Sale** för att öppna kassan (POS).
1. Välj **Nästa**.
1. Logga in med ditt Microsoft Azure Active Directory (Azure AD)-konto.
1. Under **Butiksnamn**, välj **San Francisco**.
1. Välj **Nästa**.
1. Under **Register och enhet**, välj **SANFRAN-1**.
1. Välj **aktivera**. Du är utloggad och tagen till kassainloggningssidan.
1. Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.

## <a name="set-up-your-site-in-commerce"></a>Ställ in din webbplats i Commerce

Följ dessa steg om du vill börja konfigurera din förhandsgranskningswebbplats i Commerce.

1. Logga in på platshanteringsverktyget med hjälp av den URL som du antecknade när du initierade e-handel under etableringen (se [initiera e-handel](provisioning-guide.md#initialize-e-commerce)).
1. Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.
1. Välj den domän som du angav när du initierade e-handel.
1. Som standardkanal väljer du **Fabrikam utökade online-butik**. (Se till att välja den **utökade** onlinebutiken)
1. För standardspråk väljer du **sv-SE**.
1. Lämna värdet i fältet **sökväg** som det är.
1. Välj **OK**. Listan över sidor på webbplatsen visas.

## <a name="enable-jobs"></a>Aktivera jobb

Gör så här om du vill aktivera jobb i Commerce.

1. Logga in på miljön (HQ).
1. Gå till menyn till vänster **Retail och Commerce \> Förfrågningar och rapporter \> Batch-jobb**.

    De återstående stegen i den här proceduren måste slutföras för vart och ett av följande jobb:

    * Bearbeta butikorders e-postmeddelande
    * Produkttillgänglighet
    * P-0001
    * Synkronisera orderjobb

1. Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn.
1. Utför följande steg om status för jobbet är **Undanhåll**:

    1. Välj posten.
    1. I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.
    1. Välj **Väntar**och välj sedan **OK**.

### <a name="run-full-data-synchronization"></a>Kör fullständig datasynkronisering

Om du vill köra fullständig datasynkronisering i Commerce, följ dessa steg.

1. Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas**.
1. **Standard** kanalen väljs i listan till vänster. Välj den andra tillgängliga kanalen. Den här kanalen heter **scXXXXXXXXX**.
1. I åtgärdsfönstret, välj **Fullständig datasynkronisering**.
1. Ange **9999** som distributionsschema.
1. Välj **OK**.
1. Välj **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testa kreditkortsinformation för att utföra testinköp

För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:

- **Kortnummer:** 4111-1111-1111-1111
- **Utgångsdatum:** 10/20
- **Kortverifieringsnummer (CVV) kod:** 737

> [!IMPORTANT]
> Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.

## <a name="next-steps"></a>Nästa steg

När etablerings- och konfigurationsstegen är slutförda är du redo att utvärdera din förhandsversionsmiljö. Använd URL:en för hanteringsverktyg för näthandelsplats för att gå till redigeringsupplevelsen. Använd URL:en för hanteringsverktyg för näthandelsplats för att gå till näthandelsplats för butikskunden.

För att konfigurera valfria funktioner för Commerce efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för förhandsversionsmiljö för Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce förhandsversionsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce förhandsversionsmiljö](provisioning-guide.md)

[Konfigurera valfria funktioner för en förhandsversionsmiljö för Dynamics 365 Commerce](cpe-optional-features.md)

[Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)
