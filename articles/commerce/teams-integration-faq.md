---
title: Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration
description: Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.
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
ms.openlocfilehash: 3fc7cff0a3f8d0fbfb196ec5951b138088afece7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019480"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Vanliga frågeställningar och svar om Dynamics 365 Commerce och Microsoft Teams-integration

[!include [banner](includes/banner.md)]

Det här avsnittet finns svar på vanliga frågeställningar som rör Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Vem i butiken blir ägare till ett team när Teams etableras från Commerce? 

Alla butikschefer läggs automatiskt till som ägare till motsvarande grupp så att de kan utföra åtgärder som till exempel att lägga till en privat kanal och lägga till eller ta bort medlemmar. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Hur tilldelar jag rollen "kommunikationsansvarig" till en medarbetare i Commerce-administration? 

Kommunikationschefer i Microsoft Teams har förmågan att skapa och publicera uppgiftslistor. Organisationsanställda som måste bli kommunikationsansvariga måste ha rollen "butiksuppgiftschef" tilldelad till sig i Commerce-administration.

Om du vill tilldela en medarbetare rollen som butiksuppgiftschef i Commerce-administration följer du dessa steg.

1. Gå till **Butik och handel \> Anställda \> Användare**.
1. Välj en medarbetare.
1. På snabbfliken **Användarens roller** klicka på **Tilldela roller**.
1. I dialogrutan **Tilldela roller till användare**, välj rollen **butikshanterarens roll** och klicka sedan på **OK**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Hur gör jag en specifik organisationshierarki tillgänglig för överföring till Microsoft Teams?

I Commerce-administration är varje organisationshierarki kopplad till ett eller flera syften. Se till att den hierarki som du vill tillhandahålla Microsoft Teams har **Butiksrapportering** syfte associerat med det, som visas i följande exempelbild. 

![Exempel på ett organisationshierarkisyfte i Commerce-administration](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Hur aktiverar jag att butiksarbetare ska logga in i Commerce kassa med hjälp av Azure Active Directory (Azure AD)?

För information om hur du konfigurerar Commerce POS inloggningsupplevelse för att använda Azure AD autentisering finns i [Aktivera Azure Active Directory autentisering för kassainloggning](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Hur mappar jag butiker och motsvarande team i Commerce-administration om min organisation redan har skapat team i Microsoft Teams?

Information om hur du mappar butiker och team om det finns befintliga team finns i [Kartlägg butiker och motsvarande team om din organisation har befintliga team i Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Hur tar jag bort den Microsoft Graph API-token som lagrats i sessionslagringen?

En användare som har loggat in på kassan med ett Azure Active Directory (Azure AD) konto ska logga ut från kassan eller stänga appen för att rensa sessionslagring. 

> [!TIP]
> Vi rekommenderar att butiksarbetare alltid låser kassaterminalen eller loggar ut från en session när de inte använder terminalen. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>Vad händer om en butik inte har butikschefer?

Om en butik inte har några chefer skapas ingen teamgrupp för butiken eller i Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>Vad händer om en butikschef lämnar företaget?

Alla med ägarrollen kan lägga till en ny butikschef i Commerce-administration och ometablera Teams så att den nya chefen får de behörigheter som den nya chefen behöver i Teams för gruppen. 

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce och Microsoft Teams-integrering, översikt](commerce-teams-integration.md)

[Aktivera Dynamics 365 Commerce och Microsoft Teams-integration](enable-teams-integration.md)

[Provision Microsoft Teams från Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS](synchronize-tasks-teams-pos.md)

[Hantera användarroller i Microsoft Teams](manage-user-roles-teams.md)

[Mappa butiker och team om det finns befintliga team i Microsoft Teams](map-stores-existing-teams.md)
