---
title: NF-e anpassad certifikatvalidering
description: Det här avsnittet innehåller information om hur du aktiverar och använder det anpassade NF-e-certifikatet.
author: gionoder
ms.date: 10/06/2020
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
ms.openlocfilehash: 895513f51798a797ebf59f8a5be4f5cde006726d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813978"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e anpassad certifikatvalidering

[!include [banner](../includes/banner.md)]

När du aktiverar funktionen för verifiering av anpassat NF-e-certifikat kan du använda anpassade valideringar för att ansluta till webbtjänsterna. Den här anslutningen krävs för att överföra NF-e och få behörighet från SEFAZ.

Egenskapen **Serverns syfte att autentiseras** från certifikat V5 utfärdas av den brasilianska rotcertifikatsmyndigheten. Den här egenskapen är som standard inaktiverad och måste aktiveras manuellt. I vissa fall kan den automatiska certifikatuppdateringen växla egenskapen till att inte längre aktiveras. Om detta inträffar, påverkas TLS-anslutningen och den är inte längre betrodd. Möjligheten att utfärda NF-e i produktionsmiljöer för stater i Minas Gerais (MG) och Paraná (PR) påverkas också.

Den här uppdateringen möjliggör en alternativ lösning för certifikat validering, vilket innebär att det är möjligt att upprätta en säker kommunikation.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]