---
title: Postmallar – översikt
description: Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81a878fccf2b544ffe94edac2c7c41be78bade3f
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864754"
---
# <a name="record-templates-overview"></a>Postmallar – översikt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information.

Bokföringsmallar hjälper dig att skapa poster snabbare i Microsoft Dynamics 365 for Finance and Operations. Du kan skapa postmallar för bara en del av posttyper i Microsoft Dynamics 365 for Finance and Operations.

Till exempel, tänk dig att du anger hyrbilsinformation för ett hyrbilsföretag som ligger i San Francisco. Eftersom de flesta kunder är sannolikt från San Francisco, vore det trevligt om du kunde automatiskt fylla i värden för **delstaten**, **land** och **stad** fält i hyresformuläret.

> [!NOTE]
> Du kan använda mallar endast för de områden inom Finance and Operations som du har åtkomst till. Men alla malltitlar är synliga för dig när du skapar en ny post, och andra användare också, om du skapar mallar som kommer att vara tillgängliga för alla användare. Beaktar detta när du namnger mallar. Undvik att använda namn som innehåller ord som ”provision”, om det konfidentiellt att vissa medarbetare inom företaget provision-harbaserat lön.

När en eller flera mallar som du har tillgång till finns för ett specifikt formulär och du försöker skapa en ny post i formuläret, visas sidan **Välj en mall för**. När du väljer en mall i listan skapas den nya posten med standardinformation som är baserad på mallen du valde. Om du inte vill använda mallar när du skapar nya poster, markerar du kryssrutan **Fråga inte igen** på sidan **Välj en mall för**. Om du vill visa dialogrutan för val av mall igen högerklickar du på en post, klickar på **Postinfo** och klickar sedan på **Visa mallval**.
