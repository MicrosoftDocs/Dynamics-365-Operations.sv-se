---
title: Felsöka problem vid konfiguration och installation av Store Commerce
description: I den här artikeln förklaras hur du felsöker konfigurations- och installationsproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 92d4a9d78485b681b4e802f695d54f44ecd7c5de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870476"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Felsöka problem vid konfiguration och installation av Store Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln förklaras hur du felsöker konfigurations- och installationsproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Jag kan inte aktivera programmet och får ett meddelande om anslutningsfel

När du har angett en giltig URL för molnkassa (Cloud Point of Sale, CPOS) kan du komma att få ett meddelande om anslutningsfel som ser ut ungefär som följande exempel:

> Ett anslutningsfel har inträffat och enheten kan inte ansluta till CPOS. Angiven CPOS-URL kan ha fel.

Granska i så fall URL-adressen för typografiska fel eller försök avgöra huruvida CPOS inte kan nås eftersom det är offline.

Kontrollera dessutom att CSU-versionen (molnbaserad skalningsenhet) är 10.0.25 (9.35.\*.\*) eller senare. CPOS-version 10.0.25 eller senare krävs för att du ska kunna använda programmet Store Commerce.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Jag kan inte installera programmet eftersom Modern POS redan har installerats

I samband med installation kan du komma att erhålla ett flemeddelande liknande det i följande exempel:

> En version (9.\*.\*.\*) av denna produkt (Modern POS) har tidigare installerats via det gamla installationsprogrammet.

Om du vill åtgärda felet måste du avinstallera appen Modern Point of Sale (MPOS) för alla användare på datorn och sedan försöka igen. Du kan bekräfta att MPOS har tagits bort för alla användare genom att köra följande PowerShell-kommando.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Jag kan inte aktivera programmet på grund av en ogiltig URL eller ett feltillstånd

Om den CPOS-URL som du angav är ogiltig och du vill ändra den, eller om Store Commerce-programmet befinner sig i feltillstånd under aktiveringen, kan du starta om processen genom att återställa programmet. Programmet Store Commerce sparar bara en giltig CPOS-URL.

Återställ programmet Store Commerce genom att följa dessa steg.

1. På **Start**-menyn i Windows väljer och håller du inne (eller högerklickar) programmet innan du väljer **Mer \> Programinställningar**.
2. Rulla nedåt på appinställningssidan tills du hittar knappen **Återställ**.
3. Välj **Återställ**. När du sedan uppmanas till det bekräftar du att du vill återställa appen.
