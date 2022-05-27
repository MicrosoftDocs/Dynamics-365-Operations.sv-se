---
title: Klienten kopplas från
description: Detta ämne förklarar vad du gör om kunden kopplas bort från miljön.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3093f11b0833812f6420f67a4b8bf405e550e974
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690137"
---
# <a name="client-disconnects"></a>Klienten kopplas från


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Miljöinformation** 

Detta problem kan inträffa i alla miljöer.
 
**Symptom** 

Kunden kopplas från miljön och vet inte varför. Kunden får ett av följande felmeddelanden:

- Anslutningen har kopplats från. Klicka på Stäng om du vill fortsätta arbeta.
- Det verkar som att du tappat anslutningen till nätverket. Klicka på Försök igen.

**Röd flagga**

Det här problemet uppstår ofta när användare befinner sig i implementeringssteget, jämför information mellan produktions- och testmiljöer och har glömt att de flyttar mellan sessioner. Om en användare befinner sig i det här steget kommer de sannolikt uppleva detta problem.

**Utleverans** 

**Webbläsartyper:** Google Chrome, Internet Explorer och Microsoft Edge

Microsoft Dynamics 365 Human Resources kopplar från användare när två olika sessioner öppnas samtidigt för samma användare och samma webbläsartyp. (T.ex. användare A visar både miljö 1 och miljö 2 i Chrome.) Det spelar ingen roll om användarna öppnar olika webbläsarfönster eller olika flikar. Om samma användarautentisering används för att logga in på både miljö 1 och miljö 2 samtidigt och i samma webbläsartyp, kopplar Personal från en av sessionerna.

**Lösning**

Kontrollera att endast en miljö är öppen i taget för en viss webbläsartyp. Användare kan öppna flera sessioner till samma miljö (det vill säga flera flikar i samma webbläsare).

Användare som vill hoppa mellan två miljöer samtidigt ska öppna varje miljö i olika webbläsartyper. (T.ex. användare A kan visa miljö 1 i Chrome och miljö 2 i Microsoft Edge.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
