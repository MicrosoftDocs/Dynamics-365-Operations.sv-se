---
title: Aktivera Dynamics 365 Commerce och Microsoft Teams-integration
description: I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dfada577ab97fdb9912c22d2399529f934b25d54
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695744"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Aktivera Dynamics 365 Commerce och Microsoft Teams-integration

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar Microsoft Dynamics 365 Commerce och Microsoft Teams-integrerar.

Att förse Teams med information från Dynamics 365 Commerce och synkronisera uppgiftshanteringsfunktionerna mellan Teams och kassaappen, måste du aktivera integrationsfunktionerna i Commerce-administration.

> [!NOTE]
> När du aktiverar Teams-integration godkänner du att du delar dina data med Team. Data som delas med Teams kanske finns i ett annat land än dina Commerce-data, och kan tillämpas på andra efterföljande standarder. För mer information, se [Microsoft Trust Center](https://www.microsoft.com/trust-center). Mer information om sekretesspolicy för Microsoft finns i [Microsoft sekretesspolicyn](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Aktivera Teams-integration

Innan du kan aktivera Microsoft Teams-integreringen med Commerce måste du registrera programmet Teams med din innehavare i Azure-portal.

Registrera Teams-programmet hos din innehavare i Azure-portal genom att följa dessa steg.

1. Följ stegen i [Snabbstart: Registrera en app i Microsoft identitetsplattform](/azure/active-directory/develop/quickstart-register-app) för att registrera Teams-applikationen med din klient i Azure-portalen.
1. På fliken **Appregistrering** väljer du programmet som du skapade i det föregående steget. På fliken **Autentisering**, välj **Lägg till plattform**.
1. I dialogrutan, välj **Webb**. Sedan i fältet **omdirigerings-URL** anger du en URL i formatet **\<HQUrl\>/oauth**. Ersätt **\<HQUrl\>** med din Commerce-administration URL (till exempel `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. På sidan **Översikt** för den registrerade appen, kopiera värdet **App (klient) ID**. Du måste ange detta värde när du aktiverar Teams-integration i Commerce-administration i nästa avsnitt.
1. Följ instruktionerna i [Lägg till en klienthemlighet](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) för att lägga till en klient. Kopiera sedan ett värde för **Hemligt värde** för klienten. Du måste ange detta värde när du aktiverar Teams-integration i Commerce-administration i nästa avsnitt.
1. Välj **API-behörighet**, välj **Lägg till behörighet**.
1. I dialogrutan **Begär API-behörigheter**, välj **Microsoft Graph**, välj **Delegerade behörigheter**, expandera **Grupp**, välj **Group.ReadWrite.All** och sedan **Lägg till behörigheter**.
1. I dialogrutan **Begär API-behörigheter** välj **Lägg till behörighet**, välj **Microsoft Graph**, välj **Appbehörigheter**, expandera **Grupp**, välj **Group.ReadWrite.All** och sedan **Lägg till behörigheter**.
1. I dialogrutan **Begär API-behörigheter**, välj **Lägg till en behörighet**. På fliken **API:er som min organisation använder**, sök efter **Microsoft Teams Retail Service** och välj den.
1. Välj **Delegerade behörigheter**, expandera **TaskPublishing**, välj **TaskPublising.ReadWrite.All** och välj sedan **Lägg till behörigheter**. Mer information finns i [Konfigurera ett klientprogram för åtkomst till ett webb-API](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

För att möjliggöra Teams-integrering i Commerce-administration.

1. Öppna **Butik och handel \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange alternativet **Aktivera Microsoft Teams-integration** till **Ja**.
1. I fältet **Program-ID** ange värdet **Program-ID (klient)** som du fick när du registrerade Teams-appen i Azure-portalen.
1. I fältet **Programnyckel** ange värdet **Hemlighets värde** som du fick när du lade till klienthemlighet i Azure-portalen.
1. Klicka på **Spara** i åtgärdsfönstret.

I följande bild visas ett exempel på konfigurationen av Teams-integration i Commerce-administration.

![Konfiguration av Teams-integration i Commerce-administrationen.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Inaktivera Teams-integration

För att inaktivera Microsoft Teams-integrering i Commerce-administration.

1. Öppna **Butik och handel \> Kanalinställningar \> Microsoft Teams integrationskonfiguration**.
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

[Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration](teams-integration-faq.md)
