---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180954"
---
# <a name="create-new-users"></a>Skapa nya användare

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associera en användare med en licens (endast nya licenstyper)
För kunder som finns på en av de nya licenstyperna som lades till i oktober 2019, måste användarna associeras med en licens. Användare som associeras med en licens läggs automatiskt till som systemanvändare som inte har några roller första gången de loggar in. Användare som inte är kopplade till någon licens får ett varningsmeddelande.

Systemadministratörer kan [tilldela licenser till användare](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) i [Microsoft 365 administrationscenter](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide)

## <a name="add-a-new-user"></a>Lägg till ny användare
1. Gå till **Systemadministration \> Användare \> Användare**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Användar-ID** anger du en unik identifierare för användaren. Ett användar-id krävs.  
4. Ange användarens namn fältet **Användarnamn**.  
5. Ange användarens domän i fältet **Domän**.  
6. Ange användarens alias i fältet **alias**.  
7. Välj önskat företag i fältet **Företag**. 
8. På snabbfliken **användarens roller** väljer du **tilldela roller** för att [tilldela användare till säkerhetsroller](assign-users-security-roles.md)
9. Välj **OK**.
10. Välj **Spara**.

## <a name="import-users"></a>Importera användare
1. Välj **Importera användare** i åtgärdsfönstret.
2. Markera vald rad i listan.
3. Välj **Importera användare**.
4. Välj **Nära**.

