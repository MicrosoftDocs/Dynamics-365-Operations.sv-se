---
title: Aktivera Dynamics 365 Commerce och Microsoft Teams-integration
description: I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842745"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Aktivera Dynamics 365 Commerce och Microsoft Teams-integration

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.

Att förse Teams med information från Dynamics 365 Commerce och synkronisera uppgiftshanteringsfunktionerna mellan Teams och kassaappen, måste du aktivera integrationsfunktionerna i Commerce-administration.

> [!NOTE]
> När du aktiverar Teams-integration godkänner du att du delar dina data med Team. Data som delas med Teams kanske finns i ett annat land än dina Commerce-data, och kan tillämpas på andra efterföljande standarder. För mer information, se [Microsoft Trust Center](https://www.microsoft.com/trust-center). Mer information om sekretesspolicy för Microsoft finns i [Microsoft sekretesspolicyn](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Aktivera Teams-integration

Innan du kan aktivera Microsoft Teams-integreringen med Commerce måste du registrera programmet Teams med din innehavare i Azure-portal.

Registrera Teams-programmet hos din innehavare i Azure-portal genom att följa dessa steg.

1. Följ stegen i [Snabbstart: Registrera en app i Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) för att registrera Teams-applikationen med din klient i Azure-portalen.
1. Kopiera värdet **App (klient) ID** från **Översikt** för den registrerade appen. Det här värdet använder du när du aktiverar Teams-integration i Commerce-administration.
1. Kopiera intygsvärdet som angavs när du [lade till ett intyg](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) i steg 1. Certifikatet kallas också för offentlig nyckel eller programnyckel. Det här värdet använder du när du aktiverar Teams-integration i Commerce-administration.

För att möjliggöra Teams-integrering i Commerce-administration.

1. Öppna **Retail och Commerce \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange alternativet **Aktivera Microsoft Teams-integration** till **Ja**.
1. I fälten **Program-ID** och **Programnyckel**, ange de värden du fick när du registrerade Teams-appen i Azure-portalen.
1. Klicka på **Spara** i åtgärdsfönstret.

I följande bild visas ett exempel på konfigurationen av Teams-integration i Commerce-administration.

![Konfiguration av Teams-integration i Commerce-administration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Inaktivera Teams-integration

För att inaktivera Microsoft Teams-integrering i Commerce-administration.

1. Öppna **Retail och Commerce \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.
1. I åtgärdsfönstret väljer du **Redigera**.
3. Ange alternativet **Aktivera Microsoft Teams-integration** till **Nej**.
4. Rensa värdena från fälten för **program-ID** och **programnyckel**.
1. Klicka på **Spara** i åtgärdsfönstret.

> [!NOTE]
> När du inaktiverar Teams-integration med Commerce visar kassaterminaler inte längre uppgifter som har publiceras från Teams-programmet.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce och Microsoft Teams-integrering, översikt](commerce-teams-integration.md)

[Provision Microsoft Teams från Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Mappa butiker och team om det finns befintliga team i Microsoft Teams](map-stores-existing-teams.md)

[Vanliga frågor och svar om Dynamics 365 Commerce och Microsoft Teams-integration](teams-integration-faq.md)
