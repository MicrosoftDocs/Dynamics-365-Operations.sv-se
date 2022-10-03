---
title: Konfiguration för Finance Insights
description: I den här artikeln beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Finance Insights.
author: ShivamPandey-msft
ms.date: 09/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05bf5fe5a5ff86bbf52ed58ee6b1e84c15bf2c1e
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573205"
---
# <a name="configuration-for-finance-insights"></a>Konfiguration för Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights kombinerar funktioner från Microsoft Dynamics 365 Finance med Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen. I den här artikeln beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Finance Insights. För att slutföra procedurerna i detta ämne måste du ha åtkomst för Systemadministratör och Systemanpassare i [administrationscentret för Power Portal](https://admin.powerplatform.microsoft.com/), Systemadministratörsåtkomst i Dynamics 365 Finance och åtkomst för att skapa miljöer i Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Följande procedurer för hur du konfigurerar Finance Insights gäller för Dynamics 365 Finance-version 10.0.21 och senare.

## <a name="deploy-dynamics-365-finance"></a>Distribuera Dynamics 365 Finance

Följ dessa steg för att distribuera miljöerna.

1. I LCS, skapa eller uppdatera en Dynamics 365 Finance-miljö. Miljön kräver appversion 10.0.21 eller senare.

    > [!NOTE]
    > Miljön måste vara en miljö med hög tillgänglighet (HA). (Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

2. Om du konfigurerar Finance Insights i en sandbox-miljö måste du kanske kopiera produktionsdata till den miljön för att förutsägelser ska fungera. I modellen för förutsägelse används flera års data för att skapa förutsägelser. Contoso-demodatan innehåller inte tillräckligt med historiska data för på ett adekvat sätt mata förutsägelsemodellen. 

## <a name="configure-your-azure-ad-tenant"></a>Konfigurera ditt Azure AD innehavare

Azure Active Directory (Azure AD) måste konfigureras så att det kan användas med Dataverse och Microsoft Power Platform programmen. Den här konfigurationen kräver antingen rollen **Projektägare** eller **Miljöchefen** tilldelad användaren i fältet **Projektsäkerhetsroll** i LCS.

Kontrollera att följande inställningar är slutförda:

- Du har åtkomst **systemadministratörer** och **Systemanpassare** i administrationscentret för Power Portal.
- En Dynamics 365 Finance eller motsvarande licens tillämpas på den användare som installerar tillägget Finance Insights.
- Följande Azure AD program är registrerade i Azure AD.

    |  Ansökning                             | App-ID                               |
    |------------------------------------------|--------------------------------------|
    | Microsoft Dynamics ERP Microservices CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |

    Kontrollera att programmet är registrerat Azure AD i listan **Alla program**. Mer information finns i [Visa företagsprogram](/azure/active-directory/manage-apps/view-applications-portal).
  
    Om programmet inte är registrerat i Azure AD kontaktar du support.
  
## <a name="configure-dataverse"></a>Konfigurera Dataverse

Följ dessa steg för att konfigurera Dataverse för Finance Insights.

- I LCS öppnar du miljösidan och bekräftar att avsnittet **Power Platform-integrering** redan har konfigurerats.

    - Om Dataverse har konfigurerats ska namnet på den Dataverse-miljö som kopplats till Finance-miljön listas.
    - Om Dataverse ännu inte har konfigurerats väljer du **Inställningar**. Konfiguration av Dataverse-miljön kan ta upp till 1 timme. När konfigurationen har slutförts bör namnet på den Dataverse-miljö som är kopplad till Finance-miljön visas.
    - Om denna integration har ställts in med en befintlig Microsoft Power Platform miljö bör du kontakta administratören och kontrollera att den kopplade miljön inte är inaktiverad.

        Mer information finns i avsnittet [Aktivera Power Platform-integrering](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Gå till webbplatsen för Microsoft Power Platform administration, gå till <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>Konfigurera tillägget Finance Insights

Om du tidigare installerat tillägget Finance Insights avinstallerar du detta innan du slutför följande procedur.

> [!NOTE]
> Om du redan har installerat Data Lake-tillägget i LCS använder Finance Insights detta för att spara data som krävs för förutsägelser. Om du ännu inte har installerat Data Lake-tillägget i LCS kommer tillägget Finance Insights att skapa en hanterad Data Lake åt dig.

Följ anvisningarna nedan för att installera tillägget Finance Insights.

1. Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.
2. I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.
3. Välj tillägget **Finance insights**.
4. Godkänn villkoren och välj sedan **Installera**.

Tillägget kan ta flera minuter att installera.

## <a name="one-last-thing"></a>En sista sak...

När tillägget har installerats kan det ta upp till en timme innan du kan aktivera Finance Insights-funktionerna i arbetsytan **Funktionshantering** i Dynamics 365 Finance. Om du inte vill vänta så länge kan du köra processen **Statuskontroll för Insights-etablering**. 

1. I Dynamics 365 Finance går du till **Systemadministration \> Konfigurera \> Processautomatisering**.
2. På fliken **Bakgrundsprocesser** letar du upp **Statuskontroll för Insights-etablering** och väljer **Redigera**.
3. Ange fältet **Nästa körning** till 30 minuter före den aktuella tiden.

   Denna ändring bör tvinga processen **Statuskontroll för Insights-etablering** att köras direkt.

   När processen **Statuskontroll för Insights-etablering** har körts kan du aktivera funktioner Finance Insights-funktioner i arbetsytan **Funktionshantering**.

> [!NOTE]
> Om processen **Statuskontroll för Insights-etablering** inte körs, gå till **Systemadministration** > **Frågor** > **Batch-jobb**. I fältet **Systemjobb för processautomatiseringssökning** ändra värdet till **Väntar** för att sätta igång processen. 
> 
## <a name="feedback-and-support"></a>Feedback och support

Om du är intresserad av att lämna feedback, eller om du behöver support, skicka då ett e-postmeddelande till [Finance Insights (förhandsversion)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
