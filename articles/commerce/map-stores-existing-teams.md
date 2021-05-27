---
title: Mappa butiker och team om det finns befintliga team i Microsoft Teams
description: Detta ämne beskriver hur man kan kartlägga butiker och motsvarande team i Dynamics 365 Commerce-administration om din organisation redan har skapat team i Microsoft Teams före Commerce-integration.
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
ms.openlocfilehash: ccc2cbf11e405facf310d93e5458cfe12a43146d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020229"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mappa butiker och team om det finns befintliga team i Microsoft Teams

[!include [banner](includes/banner.md)]

Detta ämne beskriver hur man kan kartlägga butiker och motsvarande team i Dynamics 365 Commerce-administration om din organisation redan har skapat team i Microsoft Teams före Commerce-integration.

Din organisation kanske har team skapade för några eller alla av butikerna innan de kan integrera Dynamics 365 Commerce och Microsoft Teams. Om detta är fallet ska du skapa uppgiftssynkronisering mellan Commerce POS och Microsoft Teams måste du ange mappningen av butiker och motsvarande team i Commerce-administration.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mappa butiker och motsvarande team i Commerce-administration 

Mappa butiker och motsvarande team i Commerce-administration, följer dessa steg.

1. Gå till **Systemadministration \> Arbetsyta \> Datahantering**.
1. Välj **Exportera**. 
1. Klicka på **Ny** i åtgärdsfönstret.
1. Under **Gruppnamn** anger du "Exportera Teams-mappning".
1. På snabbfliken **Vald entiteter**, välj **Lägg till entitet**. Dialogrutan **Lägg till enhet** visas.  
1. I listrutan **Entitetsnamn**, välj **Teams-mappning mellan källa och team**.
1. I listrutan **Måldataformat**, välj **CSV**.
1. Välj **Lägg till** och sedan **Stäng**.
1. Längst upp till vänster under åtgärdsfönstret, välj **Exportera nu**.
1. Under **Bearbetningsstatus för entitet**, välj **Hämta fil**.
1. I den exporterade CSV-filen, ange värden för **SOURCETYPE**, **SOURCEID** och **TEAMID** enligt följande:
    - För **SOURCETYPE**, ange "RetailStore". 
    - För **SOURCEID**, ange butiksnumret (till exempel "000135" för San Francisco-butiken). Du hittar butiksnummer på **Butik och handel \> Kanaler \> Butiker**.
    - För **TEAMID** anger du motsvarande team-ID från Microsoft Teams (till exempel "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c"). Du hittar ID-information på [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Spara CSV-filen på den lokala datorn.
1. Gå till **Systemadministration \> Arbetsyta \> Datahantering** och välj sedan **Importera**.
1. På snabbfliken **Vald entiteter**, välj **Lägg till fil**. Dialogrutan **Lägg till fil** visas.
1. I listrutan **Entitetsnamn**, välj **Teams-mappning mellan källa och team**.
1. I listrutan **Källdataformat**, välj **CSV**.
1. Välj **Ladda upp och lägg till**, välj den CSV-fil du sparade tidigare och välj sedan **Öppna**.
1. I dialogrutan **Lägg till**, välj **Stäng**.
1. I åtgärdsrutan väljer du **Spara** och välj sedan **Import**.

Följande exempelbild visar **Exportera Teams-mappning** gruppen i Commerce med **Lägg till enhet** och de exporterade CSV-filrubrikerna markerade.

![Exportera Teams-mappning gruppen i Commerce med Lägg till enhet och de exporterade CSV-filrubrikerna markerade.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> När du har slutfört föregående steg följer du stegen i [Synkronisera uppgiftshantering mellan Microsoft Teams och kassa](synchronize-tasks-teams-pos.md) för synkronisera för uppgiftshantering. 

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce och Microsoft Teams-integrering, översikt](commerce-teams-integration.md)

[Aktivera Dynamics 365 Commerce och Microsoft Teams-integration](enable-teams-integration.md)

[Provision Microsoft Teams från Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration](teams-integration-faq.md)
