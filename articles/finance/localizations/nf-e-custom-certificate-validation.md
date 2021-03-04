---
title: NF-e anpassad certifikatvalidering
description: Det här avsnittet innehåller information om hur du aktiverar och använder det anpassade NF-e-certifikatet.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447942"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e anpassad certifikatvalidering

[!include [banner](../includes/banner.md)]

När du aktiverar funktionen för verifiering av anpassat NF-e-certifikat kan du använda anpassade valideringar för att ansluta till webbtjänsterna. Den här anslutningen krävs för att överföra NF-e och få behörighet från SEFAZ.

Egenskapen **Serverns syfte att autentiseras** från certifikat V5 utfärdas av den brasilianska rotcertifikatsmyndigheten. Den här egenskapen är som standard inaktiverad och måste aktiveras manuellt. I vissa fall kan den automatiska certifikatuppdateringen växla egenskapen till att inte längre aktiveras. Om detta inträffar, påverkas TLS-anslutningen och den är inte längre betrodd. Möjligheten att utfärda NF-e i produktionsmiljöer för stater i Minas Gerais (MG) och Paraná (PR) påverkas också.

Den här uppdateringen möjliggör en alternativ lösning för certifikat validering, vilket innebär att det är möjligt att upprätta en säker kommunikation.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]