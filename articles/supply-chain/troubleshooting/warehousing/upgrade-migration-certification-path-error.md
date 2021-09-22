---
title: Certifieringssökvägsfel vid uppgradering eller migrering till WMS
description: Om felmeddelandet "Förtroendeankare för certifieringssökväg hittas inte" visas i appen när du uppgraderar eller migrerar till WMS, ger den här sidan information om hur du löser problemet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477606"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Förtroendeankare för certifieringssökväg hittas inte när du uppdaterar och migrerar till WMS

## <a name="symptoms"></a>Symtom

När du uppgraderar och migrerar till WMS (advanced warehouse management) kan Warehouse Management-appen visa följande felmeddelande:

> java.security.cert.certPathValidatorException: Förtroendeankare för certifieringsväg hittades inte.

## <a name="cause"></a>Orsak

Detta inträffar eftersom självsignerade certifikat inte är betrodda på Android 8+ i lokala miljöer.

## <a name="resolution"></a>Lösning

Använd en extern (offentlig) certifikatutfärdare (CA). En korrigering för det här problemet finns tillgänglig i version 1.9.0.0 av Warehouse Management-appen. Mer information om det här problemet och hur du korrigerar det finns i [Förtroendeankare för certifieringssökväg hittas inte när du ställer in appanslutning](certification-path-app-connection-error.md).
