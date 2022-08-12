---
title: Felsöka problem med tillägget Store Commerce
description: I den här artikeln förklaras hur du felsöker problem med tillägg i programmet Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b440183e255e05c4f93a4f11106be2967163ff74
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2022
ms.locfileid: "9169028"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Felsöka problem med tillägget Store Commerce

[!include [banner](../includes/banner.md)]

I den här artikeln förklaras hur du felsöker problem med tillägg i programmet Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="extensions-packages-arent-loaded"></a>Tilläggspaket läses inte in

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>Tilläggspaket visas inte på sidan Kassa \> Inställningar

Commerce runtime (CRT)-utlösare har kanske inte uppdaterats att inkludera tilläggspaketet, eller också är de inte distribuerade. Mer information finns i [Ubyggbarhet och utlösare för Commerce Runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>Tilläggspaket visas på sidan Kassa \> Inställningar, men manifestet läses inte in

Bekräfta att tilläggspaketen finns i mappen **C:\\Program\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Tillägg**. Om paketen finns bör det finnas en **POS-mapp** där som innehåller manifestet.

Om det inte finns någon **POS-mapp** ska du bekräfta att Store Commerce-projektet hänvisar till filnamnstillägget för kassa (POS) korrekt. Validera projektreferenssökvägen och kontrollera att den finns. 

På följande exempelbild har installationsprojektet problem med det refererade tilläggsprojektet.

![Projektreferens för Store Commerce-installationsprogrammet är inte giltig.](media/ReferenceNotValid.png)

Om referensen för tilläggsprojektet läggs till på rätt sätt kommer det inte att finnas några varnings- eller beroendeproblem i installationsprojekten, vilket visas på följande exempelbild.

![Projektreferensen för Store Commerce-installationsprojektet är giltig.](media/ReferenceValid.png)
