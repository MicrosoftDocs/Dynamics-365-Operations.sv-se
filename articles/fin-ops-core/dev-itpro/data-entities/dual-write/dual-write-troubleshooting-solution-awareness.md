---
title: Felsöka problem relaterade till lösningsmedvetenhet
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 7f1a6e424996201ecae1b624c13cfc573745dc0a
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997288"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Felsöka problem relaterade till lösningsmedvetenhet

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det här avsnittet innehåller specifikt information som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="error-on-the-dual-write-page"></a>Fel på sidan dubbelriktad skrivning

På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:

*Entiteten med namnet 'msdyn\_dualwriteentitymap' with namemapping='Logical' hittades inte i MetadataCache.*

Lös problemet genom att kontrollera att kärnlösningen för dubbelriktad skrivning är installerad i Common Data Service. Kärnlösningen för dubbelriktad skrivning är en förutsättning för lösningsmedvetenhet.
