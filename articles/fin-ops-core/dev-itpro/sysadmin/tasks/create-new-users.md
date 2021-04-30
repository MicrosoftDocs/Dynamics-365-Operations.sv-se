---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88d3f1fba05d944e78e4595018d190c3dc41e076
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907921"
---
# <a name="create-new-users"></a>Skapa nya användare

[!include [banner](../../includes/banner.md)]

Innan du får åtkomst till Finance and Operations-appar måste du först lägga till på sidan **Användare** (**Systemadministration \> Användare \> Användare**). Användare inkluderar interna medarbetare inom organisationen eller externa kunder och leverantörer. Användare kan importeras eller läggas till manuellt. Alla användare måste ha rätt licens för kompatibel användning.

Mer information om hur du köper och licens för Finance and Operations-appar, se [Microsoft Dynamics 365 licenshandboken](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Tilldela en licens till en användare.
Systemadministratörer kan [tilldela licenser till användare](/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Lägg till en extern användare i Azure AD och tilldela en licens 
Externa användare måste finnas med i klientkatalogen (Azure Active Directory (Azure AD)) så att de kan tilldelas licenser. Dessa externa användare ska läggas till i innehavaren av Azure AD som gästanvändare och sedan tilldelas de lämpliga licenserna. Ett krav för Finance and Operations-appar är att gästanvändarens företag måste använda Azure AD. Mer information finns i [lägga till Azure Active Directory B2B samarbetsanvändare i Azure-portalen](/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importera ny användare från Azure AD 
1. Gå till **Systemadministration** \> **Användare** \> **Användare**.
2. Välj **Importera användare** i åtgärdsfönstret.
3. Välj den användare du vill importera. Listan omfattar användare av Azure AD som för närvarande inte är användare i den här miljön.
4. Välj **Importera användare**.
5. Välj **Nära**.

> [!NOTE]
> Värdet för fältet **Företag** ställs in baserat på det aktuella sessionsföretaget för administratören. Efter importen måste du tilldela roller och organisationer, enligt vad som är tillämpligt. För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md). Enligt vissa villkor kan det även vara obligatoriskt att koppla användaren till en **person** och uppdatera användaralternativ, till exempel språk.

## <a name="manually-add-a-new-user"></a>Lägg manuellt till ny användare
1. Gå till **Systemadministration** \> **Användare** \> **Användare**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Användar-ID** anger du en unik identifierare för användaren.   
4. Ange användarens namn fältet **Användarnamn**.  
5. I fältet **Leverantör**:
 - Använd standardvärdet för interna användare. Till exempel får Azure AD innehavare prefix med https://sts.windows.net/.  
 - För icke-Azure AD-användare som tjänst-2-tjänst konton anger du ett grundläggande textvärde. Till exempel NA. Det här värdet hjälper dig att undvika felaktiga autentiseringssamtal som kan leda till fel om ett giltigt ID-leverantörsvärde används.  
 - För externa eller gästanvändare, lägg till deras Azure AD innehavarnamn efter https://sts.windows.net/.
6. I fältet **E-post** ange användarens fullständiga e-post/användarens huvudnamn.  
7. I fältet **Företag** välj standardstartföretag för användaren. 
8. Välj **Spara**.

Värdena för identitetsleverantör och telemetri-ID kommer att uppdateras baserat på en [Microsoft Graph](/graph/overview)-samtal när användarposten sparas. Telemetr-ID:t baseras på användarens objekt-ID/säkerhetsidentifierare (SID) i Azure AD.

> [!NOTE]
> När du har lagt till en användare måste du tilldela roller och organisationer, enligt vad som är tillämpligt. För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md). Enligt vissa villkor kan det även vara obligatoriskt att koppla användaren till en **person** och uppdatera **användaralternativ**, till exempel språk.

## <a name="change-a-user-id"></a>Ändra ett användar-ID
Om du vill ändra ett användar-ID måste du byta namn på nyckeln i databasen. När du ändrar ett användar-ID genom att använda den här proceduren ändras alla relaterade användarinställningar så att de använder det nya användar-ID:t. Till exempel användarinformationen i tabellen **SysLastValue** uppdateras till att referera till det nya användar-ID:t.

> [!NOTE]
> Användar-ID är den primära nyckeln i tabellen för användarinformation. Att byta namn på primärnyckeln kan ta lite tid för befintliga användare eftersom alla referenser till nyckeln också uppdateras i databasen. 

1. Gå till **Systemadministration \> Användare \> Användare**.
2. Markera en användare i listan och välj **Alternativ\> Postinformation**.
3. Välj **Byt namn**.
4. Ange ett nytt och unikt värde för användar-ID och välj sedan **OK**. 
5. Klicka på **Ja** för att bekräfta.

## <a name="additional-resources"></a>Ytterligare resurser

Fler alternativ för att implementera B2B-användare finns i [Exportera B2B-användare till Azure AD](../implement-b2b.md).

Mer information om förkonfigurerade systemkonton finns i [Förkonfigurerade systemkonton](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]