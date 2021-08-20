---
title: NF-e anpassad certifikatvalidering
description: Det här avsnittet innehåller information om hur du aktiverar och använder det anpassade NF-e-certifikatet.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755601"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e anpassad certifikatvalidering

[!include [banner](../includes/banner.md)]

Egenskapen **Serverns syfte att autentiseras** från certifikaten som utfärdats av den brasilianska rotcertifikatmyndigheten är som standard inaktiverad och måste aktiveras manuellt. I vissa fall kan den automatiska certifikatuppdateringen växla egenskapen till att inte längre aktiveras. Om detta inträffar, påverkas TLS-anslutningen och den är inte längre betrodd. Möjligheten att utfärda den brasilianska elektroniska finanspolitiska dokumentmodellen 55 (NF-e) om produktionsmiljöer för delstaterna Minas Gerais (MG) och Paraná (PR) påverkas.

För att aktivera korrigeringen för **NF-e anpassad certifikatvalidering**, gå till **Funktionshantering**. Den här funktionen möjliggör en alternativ lösning för validering av V5- och V10-intyg och tillåter en betrodd anslutning till webbtjänsterna, vilket krävs för säker överföring av NF-e och mottagning av auktorisering från SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
