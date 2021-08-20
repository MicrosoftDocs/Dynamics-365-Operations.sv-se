---
title: Importera användare från Azure Active Directory
description: Den här proceduren kan användas av systemadministratörer för att manuellt importera valda användare eller att importera ett stort antal användare från Azure Active Directory.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce8c98add0c6d5fb07b3ba5338037d9a12b1d8e50a2d2039b0231d3d305c9ebe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748298"
---
# <a name="import-users-from-azure-active-directory"></a>Importera användare från Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importera valda användare

Den här proceduren kan användas av systemadministratörer för att importera valda användare från Azure Active Directory (Azure AD).

1. Användaren importeras med det aktuella sessionsföretaget som standardföretag. Ändra aktuellt företag vid behov innan användarna importeras.
2. Gå till **Systemadministration > Användare > Användare**.
3. Klicka på **Importera användare**.
4. Markera de användare som ska importeras och välj **Importera användare**.

När importen är klar måste du tilldela användare roller.

## <a name="import-users-in-bulk"></a>Massimportera användare

Den här proceduren kan användas av systemadministratörer för att importera ett stort antal användare från Azure Active Directory.
Observera att det inte är möjligt att välja användare när du använder alternativet för batchimport.

## <a name="run-the-import-as-a-batch-job"></a>Kör importen som ett batchjobb
1. Användaren importeras med det aktuella sessionsföretaget som standardföretag. Ändra aktuellt företag vid behov innan användarna importeras.
2. Gå till **Systemadministration > Användare > Användare**.
3. Klicka på **Batchimport**.
4. Expandera avsnittet **Kör i bakgrunden**.
4. Välj **Ja** i fältet **Batchbearbetning**.
6. Ange eller välj ett värde i fältet **Batchgrupp**. Detta steg är valfritt.  
7. Välj **Ja** i fältet **Privat**. Detta steg är valfritt.  
8. Välj **Ja** i fältet **Kritiskt jobb**. Detta steg är valfritt.  
9. Välj ett alternativ i fältet **Övervakningskategori**.
10. Klicka på **OK**.

När importen är klar måste användare tilldelas roller.

## <a name="run-in-a-sandbox-environment"></a>Kör i ett begränsat läge
1. Välj **Batchimport**.
2. Välj **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]