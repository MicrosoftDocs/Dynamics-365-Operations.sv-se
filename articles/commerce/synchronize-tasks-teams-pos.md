---
title: Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS
description: I det här avsnittet beskrivs hur du synkroniserar uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce kassa (POS).
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020637"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du synkroniserar uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce kassa (POS).

Ett av huvudsyftena med Teams-integration är att aktivera synkronisering av uppgiftshantering mellan kassaprogrammet och Teams. På det här sättet kan butiksanställda använda antingen kassaprogrammet eller Teams för att hantera uppgifter och behöver inte byta program.

Eftersom Planner används som databas för uppgifter i Teams måste det finnas en länk mellan Teams och Dynamics 365 Commerce. Den här länken upprättas genom att ett specifikt plan-ID för ett givet butikteam används.

Följande procedurer visar hur du ställer in synkronisering av uppgiftshantering mellan kassa- och Teams-programmen.

## <a name="publish-a-test-task-list-in-teams"></a>Publicera en testuppgiftslista i Teams

I följande procedur förutsätts det att dina butiksgrupper använder Microsoft Teams uppgiftshanteringsintegrering med Commerce för första gången.

Publicera en testuppgiftslista i Teams genom att följa dessa steg.

1. Logga in i Teams som kommunikationschef. Kommunikationschefer är vanligtvis användare med rollen **Regionchef** i Commerce.
1. I det navigeringsfönstret, välj **Uppgifter av Planner**.
1. På fliken **Publicerade listor**, välj **Ny lista** längst ned till vänster och namnge den nya listan **Testuppgiftslista**.
1. Markera **Skapa**. Den nya listan visas under **Utkast**.
1. Under **Uppgiftsrubrik**, ge den första uppgiften rubriken **Testa Teams-integration**. Välj sedan **Retur**.
1. I listan **Utkast**, välj uppgiftslistan. Välj  **Publicera**  i det övre högra hörnet.
1. I dialogrutan **Välj som ska publiceras till**, välj de team som ska få testuppgiftslistan.
1. Välj **Nästa** om du vill granska publiceringsplanen. Om du måste göra ändringar väljer du  **Bakåt**. 
1. Välj **Bekräfta om du vill fortsätta** och välj **Publicera**.
1. När publiceringen är klar visas ett meddelande överst på fliken **Publicerade listor** om huruvida uppgiftslistan kunde levereras.

Mer information finns i [Publicera uppgiftslistor om du vill skapa och spåra arbete i organisationen](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Koppla kassa och Teams för uppgiftshantering

Om du vill koppla kassa och Microsoft Teams-program för uppgiftshantering i Commerce-administration följer du dessa steg.

1. Gå till **Butik och handel \> Uppgiftshantering \> Uppgifter integration med Microsoft Teams**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange alternativet **Aktivera integration av uppgiftshantering** till **Ja**.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Uppgiftskonfiguration** i åtgärdsfönstret. Du bör få ett meddelande som anger att ett batchjobb som heter **Teams-etablering** skapas.
1. Gå till **Systemadministration \> Förfrågningar \> Batch-jobb** och hitta det senaste jobbet som har beskrivningen **Teams-etablering**. Vänta tills körningen är klar för det här jobbet.
1. Kör **CDX job 1070** för att publicera plan-ID och lagra referenser till Retail Server.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce och Microsoft Teams-integrering, översikt](commerce-teams-integration.md)

[Aktivera Dynamics 365 Commerce och Microsoft Teams-integration](enable-teams-integration.md)

[Provision Microsoft Teams från Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Mappa butiker och team om det finns befintliga team i Microsoft Teams](map-stores-existing-teams.md)

[Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration](teams-integration-faq.md)
