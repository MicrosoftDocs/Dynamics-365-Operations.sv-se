---
title: Talent-klienten kopplas från
description: Det här avsnittet beskriver vad du gör om kunden kopplas från sin miljö och inte vet varför.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6d174a8acac3863fb6d9f9431c6bc777cb717470
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008185"
---
# <a name="talent-client-disconnects"></a>Talent-klienten kopplas från

[!include [banner](includes/banner.md)]

**Miljöinformation** 

Detta problem kan inträffa i alla miljöer.
 
**Symptom** 

Kunden kopplas från sin miljö och inte vet varför. Kunden får ett av följande felmeddelanden:

- Anslutningen har kopplats från. Klicka på Stäng om du vill fortsätta arbeta.
- Det verkar som att du tappat anslutningen till nätverket. Klicka på Försök igen.

**Röd flagga**

Det här problemet uppstår ofta när användare befinner sig i implementeringssteget, jämför information mellan produktions- och testmiljöer och har glömt att de flyttar mellan sessioner. Om en användare befinner sig i det här steget kommer de sannolikt uppleva detta problem.

**Utleverans** 

**Webbläsartyper:** Google Chrome, Internet Explorer och Microsoft Edge

Microsoft Dynamics 365 Talent kopplar från användare när två olika sessioner öppnas samtidigt för samma användare och samma webbläsartyp. (T.ex. användare A visar både miljö 1 och miljö 2 i Chrome.) Det spelar ingen roll om användarna öppnar olika webbläsarfönster eller olika flikar. Om samma användarautentisering används för att logga in på både miljö 1 och miljö 2 samtidigt och i samma webbläsartyp, kopplar Talent från en av sessionerna.

**Lösning**

Kontrollera att endast en miljö är öppen i taget för en viss webbläsartyp. Användare kan öppna flera sessioner till samma miljö (det vill säga flera flikar i samma webbläsare).

Användare som vill hoppa mellan två miljöer samtidigt ska öppna varje miljö i olika webbläsartyper. (T.ex. användare A kan visa miljö 1 i Chrome och miljö 2 i Microsoft Edge.)
