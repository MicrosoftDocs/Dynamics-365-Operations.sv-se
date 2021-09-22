---
title: Huvudplanering planerar mer än den tillgängliga kapaciteten
description: Huvudplaneringen verkar inte respektera kapacitetsbegränsningarna och tidsplaneringen överstiger den tillgängliga kapaciteten
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477646"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>Huvudplanering planerar mer än den tillgängliga kapaciteten

## <a name="symptoms"></a>Symtom

Huvudplaneringen verkar inte respektera kapacitetsbegränsningarna och tidsplaneringen överstiger den tillgängliga kapaciteten.

När du använder operationsplanering där det finns ändlig kapacitet och där flödet anger en blandning av behov för både en resursgrupp och enskilda resurser, finns det en liten chans att göra en del av med överordningen på grund av det sätt på vilket algoritmen validerar kapacitetskonflikter. Denna bokning kan ske om du använder hjälpprogram för att köra huvudplanering. Det är mest sannolikt att det uppstår om det finns många jobb med en relativt kortkörning.

## <a name="resolution"></a>Lösning

Om det är viktigt att ingen överbokning inträffar för grovplanering kan du göra schemaläggningen till en del av huvudplaneringen genom att aktivera alternativet **Rätt begränsad kapacitet för grovplanering** på sidan **Huvudplaneringsparametrar**. Det här alternativet är inte tillgängligt som standard. Du måste lägga till den manuellt på sidan genom att använda anpassningsfunktioner. När du använder det här alternativet körs tidsplanering långsammare på grund av brist på parallell bearbetning.
