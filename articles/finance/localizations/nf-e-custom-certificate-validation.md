---
title: NF-e anpassad certifikatvalidering
description: Den här artikeln innehåller information om hur du aktiverar och använder det anpassade NF-e-certifikatet.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f78fdbd133aecaf9dbf8abe0006abd6deb1b1b15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288557"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e anpassad certifikatvalidering

[!include [banner](../includes/banner.md)]

Egenskapen **Serverns syfte att autentiseras** från certifikaten som utfärdats av den brasilianska rotcertifikatmyndigheten är som standard inaktiverad och måste aktiveras manuellt. I vissa fall kan den automatiska certifikatuppdateringen växla egenskapen till att inte längre aktiveras. Om detta inträffar, påverkas TLS-anslutningen och den är inte längre betrodd. Möjligheten att utfärda den brasilianska elektroniska finanspolitiska dokumentmodellen 55 (NF-e) om produktionsmiljöer för delstaterna Minas Gerais (MG) och Paraná (PR) påverkas.

För att aktivera korrigeringen för **NF-e anpassad certifikatvalidering**, gå till **Funktionshantering**. Den här funktionen möjliggör en alternativ lösning för validering av V5- och V10-intyg och tillåter en betrodd anslutning till webbtjänsterna, vilket krävs för säker överföring av NF-e och mottagning av auktorisering från SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
