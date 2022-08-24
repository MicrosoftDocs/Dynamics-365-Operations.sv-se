---
title: Etablera en Dynamics 365 Commerce sandbox-miljö
description: I den här artikeln förklaras hur du reserverar en Microsoft Dynamics 365 Commerce sandbox-miljö för demo- eller sandbox-användning av förbrukning med inbyggda demodata.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 1fc50f98055f1df72d255a5be6e863570564b183
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283652"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Etablera en Dynamics 365 Commerce sandbox-miljö

[!include [banner](includes/banner.md)]

I den här artikeln förklaras hur du reserverar en Microsoft Dynamics 365 Commerce sandbox-miljö för demoanvändning av förbrukning med inbyggda demodata. Processen för inställning av en produktionsmiljö liknar den, men mer utvecklande eftersom många av sandbox-miljö förutsättningarna redan finns i demodata.

Innan du börjar rekommenderar vi att du skummar igneom denna artikel i syfte att få en uppfattning om vad processen kräver.

Om du ska kunna ställa in en Commerce sandbox-miljö måste du ange vissa parametrar för den miljö och Commerce Scale Unit (CSU) som ska användas när du reserverar Commerce senare. Instruktionerna i denna artikel beskriver alla nödvändiga steg för att slutföra tillhandahållandet, samt de parametrar som du måste använda.

När du har tillhandahållit din Commerce-miljö måste du slutföra några steg efter etablering för att förbereda den. Vissa steg är valfria, beroende på vilka delar av systemet du vill använda. Du kan alltid slutföra de valfria stegen senare.

Information om hur du konfigurerar Commerce-miljö efter att du har konfigurerat den finns i [Konfigurera en sandbox-miljö för Commerce](cpe-post-provisioning.md). Information om hur du konfigurerar valfria funktioner för Commerce-sandbox finns i [Konfigurera valfria funktioner för Commerce sandbox-miljö](cpe-optional-features.md).

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara på plats innan du kan etablera din Commerce-miljö:

- Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).
- Du är en befintlig Microsoft Dynamics 365-partner eller kund och har ett implementeringsprojekt som redan skapats och är tillgängligt för användning i LCS.  
- Du har skapat en Azure Active Directory (Azure AD) säkerhetsgrupp som kan användas som ett Commerce systemadministratörsgrupp och du dess ID tillgänglig.
- Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt. (Den här säkerhetsgruppen kan vara samma som administratörsgruppen för Commerce-system.)
- Du har distribuerat en huvudkontorsinstans inom LCS. Mer information finns i [Distribuera en ny miljö](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Observera att listan inte är uttömmande. Om du har problem kontakta din Microsoft-partnerkontakt för hjälp.

## <a name="provision-your-commerce-environment"></a>Etablera en Commerce-miljö

Följande procedurer förklarar hur du etablerar en Commerce-miljö. När du har slutfört stegen kommer din Commerce-miljö att vara redo för konfigurering. Alla steg som beskrivs nedan utförs i LCS-portalen.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Initiera Commerce Scale Unit (moln)

Gör så här om du vill initiera CSU:n.

1. I LCS, välj din miljö i listan.
1. I vyn **MILJÖER** till höger, välj **Fullständiga detaljer**. Vyn miljöinformation visas.
1. I avsnittet **Hantera miljö** section under **MILJÖFUNKTIONER**, välj **Hantera**.
1. På fliken **Commerce Scale Units**, välj **Initiera**. Vyn **Lägg till skalningsenhet** visas.
1. I fältet **REGION** väljer du den region som är densamma eller nära den region som du har distribuerat miljön till.
1. I listrutan **Version** väljer du senaste den tillgängliga versionen.
1. Välj **initiera**.
1. I varningsdialogrutan där du uppmanas att bekräfta initieringen av Commerce Scale Unit väljer du **Ja**. CSU har nu ställts i kö för etablering.
1. Innan du fortsätter bör du kontrollera att status för din CSU är **LYCKADES**. Initieringen tar ungefär två till fem timmar.

Om du inte hittar länken **hantera** i vyn miljödetaljer kontaktar du din Microsoft-kontakt för att få hjälp.

### <a name="initialize-e-commerce"></a>Initiera näthandelsplattform

Gör så här om du vill initiera Commerce.

1. På fliken **näthandel** välj **inställningar**.
1. I fältet **miljönamn för näthandel**, ange ett namn. Tänk på att det här namnet kommer att visas i några av webbadresserna som pekar mot din näthandelsinstans.
1. I fältet **Namn på Commerce Scale Unit** välj din CSU i listan. (Listan bör bara ha ett alternativ.)

    Fältet **geografi för näthandel** ställs in automatiskt.

1. Klicka på **Nästa** när du vill fortsätta.
1. I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.
1. I fältet **AAD-säkerhetsgruppen för systemadministratör**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten. Välj korrekt säkerhetsgrupp i listan.
1.  I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på den säkerhetsgrupp som du vill använda och välj sedan förstoringsglassymbol för att se sökresultaten. Välj korrekt säkerhetsgrupp i listan.
1. Lämna alternativet **tjänsten aktivera klassificering och granska** till **Ja**.
1. Välj **initiera**. Vyn **Hantering av handel** visas igen, där fliken **näthandel** väljs. Initieringen av näthandel har påbörjats.
1. Innan du fortsätter väntar du tills initieringsstatus för Commerce är **INITIALISERING HAR SLUTFÖRTS**.
1. Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:

    * **näthandelssajt** – länken till roten på din näthandelssajt.
    * **Commerce webbplatsskaparen** – länken till webbplatshanteringsverktyget.

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen med att tillhandahålla och konfigurera din Commerce-miljö, se [Konfigurera en sandbox-miljö för Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en Dynamics 365 Commerce sandbox-miljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce sandbox-miljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce sandbox-miljö](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (moln)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
