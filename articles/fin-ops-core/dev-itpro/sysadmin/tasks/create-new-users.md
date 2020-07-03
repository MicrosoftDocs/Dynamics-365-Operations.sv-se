---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d126b449074663772549b96b86acb53db971a5d4
ms.sourcegitcommit: 7d943499f302298c6ff127f56cecc34af6cee289
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435594"
---
# <a name="create-new-users"></a>Skapa nya användare

[!include [banner](../../includes/banner.md)]

Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associera en användare med en licens (endast nya licenstyper)
För kunder som finns på en av de nya licenstyperna som lades till i oktober 2019, måste användarna associeras med en licens. Användare som associeras med en licens läggs automatiskt till som systemanvändare som inte har några roller första gången de loggar in.

Systemadministratörer kan [tilldela licenser till användare](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Associera en extern användare med en licens (endast nya licenstyper)
Användare som är externa till innehavaren som miljön distribuerades till måste representeras i värdbaserade klientkatalogen (Azure Active Directory (Azure AD)) så att de kan tilldelas licenser. Dessa externa användare ska läggas till i innehavaren av Azure AD som gästanvändare och sedan tilldelas de lämpliga licenserna. Mer information finns i [lägga till Azure Active Directory B2B samarbetsanvändare i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Lägg till ny användare
1. Gå till **Systemadministration \> Användare \> Användare**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Användar-ID** anger du en unik identifierare för användaren. Ett användar-id krävs.  
4. Ange användarens namn fältet **Användarnamn**.  
5. Ange användarens domän i fältet **Domän**.  
6. Ange användarens alias i fältet **alias**.  
7. Välj önskat företag i fältet **Företag**. 
8. På snabbfliken **användarens roller** välj **tilldela roller** tilldela användare till säkerhetsroller. För mer information, se [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).
9. Välj **OK**.
10. Välj **Spara**.

## <a name="import-users"></a>Importera användare
1. Gå till **Systemadministration \> Användare \> Användare**.
2. Välj **Importera användare** i åtgärdsfönstret.
3. Markera vald rad i listan.
4. Välj **Importera användare**.
5. Välj **Nära**.

