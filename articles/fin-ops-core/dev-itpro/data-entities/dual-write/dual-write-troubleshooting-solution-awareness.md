---
title: Felsöka problem relaterade till lösningsmedvetenhet
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b53e07f69992a567d5b300ae1f2b24b74541d176
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416362"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Felsöka problem relaterade till lösningsmedvetenhet

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse. Det här avsnittet innehåller specifikt information som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="error-on-the-dual-write-page"></a>Fel på sidan dubbelriktad skrivning

På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:

*Entiteten med namnet 'msdyn\_dualwriteentitymap' with namemapping='Logical' hittades inte i MetadataCache.*

Lös problemet genom att kontrollera att kärnlösningen för dubbelriktad skrivning är installerad i Dataverse. Kärnlösningen för dubbelriktad skrivning är en förutsättning för lösningsmedvetenhet.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]