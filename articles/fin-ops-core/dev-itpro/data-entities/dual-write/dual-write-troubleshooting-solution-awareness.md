---
title: Felsöka problem relaterade till lösningsmedvetenhet
description: Den här artikeln innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c70287cb8ec29fb622f3aefff971b884339e4205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289437"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Felsöka problem relaterade till lösningsmedvetenhet

[!include [banner](../../includes/banner.md)]





Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. Det här avsnittet innehåller specifikt information som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="error-on-the-dual-write-page"></a>Fel på sidan dubbelriktad skrivning

På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:

*Entiteten med namnet 'msdyn\_dualwriteentitymap' with namemapping='Logical' hittades inte i MetadataCache.*

Lös problemet genom att kontrollera att kärnlösningen för dubbelriktad skrivning är installerad i Dataverse. Kärnlösningen för dubbelriktad skrivning är en förutsättning för lösningsmedvetenhet.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
