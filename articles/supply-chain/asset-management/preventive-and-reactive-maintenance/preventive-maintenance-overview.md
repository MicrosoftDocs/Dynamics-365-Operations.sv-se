---
title: Översikt över förebyggande underhåll
description: I det här avsnittet beskrivs förebyggande underhåll i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b43c795426f40cb43962976824c44a7702d91b7
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875892"
---
# <a name="preventive-maintenance-overview"></a>Översikt över förebyggande underhåll

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I det här avsnittet beskrivs förebyggande underhåll i Tillgångshantering. Förebyggande underhåll är en disciplin som involverar planerade underhållsjobb, t.ex. regelbunden service, kalibrering och inspektioner. I **Tillgångshantering** kan du skapa underhållsplaner och ställa in dem för tillgångar och funktionsplatser. Du kan också ställa in underhållsomgångar för funktionsplatser. Underhållsplaner för tillgångar är aktiva oavsett var tillgången har installerats. Underhållsplaner och underhållsomgångar på funktionsplats är aktiva för de tillgångar som för närvarande är installerade på platsen. Istället för att ställa in underhållsplaner på tillgångar, eller genom att ställa in underhållsomgångar på funktionsplatser, kan du skapa underhållsomgångar som innehåller flera tillgångar som du behöver för att utföra relaterade typer av underhållsjobb i samma arbetsrutin. Underhållsomgångar skapade från till gångar – istället för att skapas på funktionsplatser – innebär att du kan välja ett antal tillgångar för en underhållsomgång, som inte är installerade på samma funktionsplats.

Underhållsplaner används för att förebyggande och reaktivt underhåll av enskilda tillgångar. Underhållsomgångar används för förebyggande underhåll av en grupp eller en uppsättning tillgångar. Underhållsplaner och underhållsomgångar används för att generera arbetsorderförslag. Arbetsorderförslag sparas som underhållsschemarader som kan buntas samman och omvandlas till arbetsorder.

Bilden nedan ger en översikt över arbetsflödet från att skapa underhållsplaner och underhållsomgångar till att skapa arbetsorder för tillgångar, baserat på dessa underhållsplaner och underhållsomgångar.

![Figur 1](media/01-preventive-maintenance.png)
