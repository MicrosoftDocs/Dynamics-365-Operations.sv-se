---
title: Skapa nya användare
description: Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916494"
---
# <a name="create-new-users"></a>Skapa nya användare

[!include [task guide banner](../../includes/task-guide-banner.md)]

Användare är interna medarbetare i organisationen, eller externa kunder och leverantörer, som behöver åtkomst till systemet för att utföra sitt arbete. Systemadministratörer kan slutföra den här proceduren för att lägga till användare i systemet. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. 


## <a name="add-a-new-user"></a>Lägg till ny användare
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.
2. Klicka på **Nytt** i **Åtgärdsfönstret**.
3. Skriv ett värde i fältet **Användar-id**. Ange en unik identifierare för användaren. Ett användar-id krävs.  
4. Skriv ett värde i fältet **Användarnamn.** Ange användarens namn.  
5. Skriv ett värde i fältet **Domän**. Ange användarens domän.  
6. Ange ett värde i fältet **Alias**. Ange användarens alias.  
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Företag**.
8. Hitta och markera önskad post i listan. 
9. I avsnittet **Användarens roller** klicka på **Tilldela roller**.
10. Hitta och markera önskad post i listan.
11. Klicka på **OK**.
12. Klicka på **Spara**.

## <a name="import-users"></a>Importera användare
1. Klicka på **Importera användare** i **åtgärdsfönstret**.
2. Markera vald rad i listan.
3. Klicka på **Importera användare**.
4. Klicka på **Stäng**.

