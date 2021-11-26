---
title: Konfiguration för Finance Insights
description: I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.
author: ShivamPandey-msft
ms.date: 1/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 5668d3ddff777645b4f1c6608f025d0c5a63208a
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752988"
---
# <a name="configuration-for-finance-insights"></a>Konfiguration för Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen. I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter. För att slutföra procedurerna i detta ämne måste du ha åtkomst för Systemadministratör och Systemanpassare i [administratörscentret för Power Portal](https://admin.powerplatform.microsoft.com/), systemadministratörsåtkomst i Dynamics 365 Finance samt åtkomst till att skapa miljöer i Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Följande procedurer för hur du konfigurerar Finance Insights gäller för Dynamics 365 Finance-version 10.0.21 och senare.

## <a name="deploy-dynamics-365-finance"></a>Distribuera Dynamics 365 Finance

Följ dessa steg för att distribuera miljöerna.

1. Skapa eller uppdatera en Dynamics 365 Finance-miljö i LCS. Miljön kräver appversion 10.0.21 eller senare.

    > [!NOTE]
    > Miljön måste vara en miljö med hög tillgänglighet (HA). (Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Om du konfigurerar Finance Insights i en sandbox-miljö måste du kanske kopiera produktionsdata till den miljön för att förutsägelser ska fungera. I modellen för förutsägelse används flera års data för att skapa förutsägelser. Contoso-demodatan innehåller inte tillräckligt med historiska data för på ett adekvat sätt mata förutsägelsemodellen. 

## <a name="configure-dataverse"></a>Konfigurera Dataverse

Följ dessa steg för att konfigurera Dataverse för Finance Insights.

- I LCS öppnar du miljösidan och bekräftar att avsnittet **Power Platform-integrering** redan har konfigurerats.

    - Om detta redan har konfigurerats ska namnet på den Dataverse-miljö som kopplats till Finance-miljön listas.
    - Om detta ännu inte har konfigurerats väljer du **Inställningar**. Konfiguration av Dataverse-miljön kan ta upp till 1 timme. När konfigurationen har slutförts bör namnet på den Dataverse-miljö som är kopplad till Finance-miljön visas.

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

När tillägget har installerats kan det ta upp till en timme innan du kan aktivera ekonomiin Finance Insights-funktionerna i arbetsytan **Funktionshantering** i Dynamics 365 Finance. Om du inte vill vänta så länge kan du köra processen **Statuskontroll för Insights-etablering**. 

1. I Dynamics 365 Finance går du till **Systemadministration \> Inställningar \> Processautomatisering**.
2. På fliken **Bakgrundsprocesser** letar du upp **Statuskontroll för Insights-etablering** och väljer **Redigera**.
3. Ange fältet **Nästa körning** till 30 minuter före den aktuella tiden.

   Denna ändring bör tvinga processen **Statuskontroll för Insights-etablering** att köras direkt.

   När processen **Statuskontroll för Insights-etablering** har körts kan du aktivera funktioner Finance Insights-funktioner i arbetsytan **Funktionshantering**.

## <a name="feedback-and-support"></a>Feedback och support

Om du är intresserad av att lämna feedback, eller om du behöver support, skicka då ett e-postmeddelande till [Finance Insights (förhandsversion)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
