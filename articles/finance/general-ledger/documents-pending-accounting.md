---
title: Dokument som väntar på redovisning
description: Den här artikeln beskriver hur du använder funktionerna på sidan Dokument som väntar på redovisning.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709262"
---
# <a name="documents-pending-accounting"></a>Dokument som väntar på redovisning

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du använder funktionerna på sidan **Dokument som väntar på redovisning**.

I Microsoft Dynamics 365 Finance 10.0.30 finns funktionen **Förbättrad prestanda för ramverket för källdokumentredovisning**. Med hjälp av den här funktionen förbättras bokföringsprocesserna för källdokumentaktiverad dokumentbokföring, med start i bokföringsprocessen för fritextfakturor.

När den här funktionen är aktiverad görs bokföring av redovisningsdokumentet separat från genereringen av redovisningen eller *journalföringen* som skapar alla redovisningsdetaljer som överförs till redovisningen. I fritextfakturabokföringen registreras till exempel kundfakturan i modulen **kundreskontra** innan hela redovisningen genereras. Med den här förbättrade prestandafunktionen kan kundfakturor registreras snabbare när redovisningsgenereringen försenas.

Följande knappar är tillgängliga på sidan **Dokument som väntar på redovisning**.

- **Generera redovisning** – Skicka ett dokument som för närvarande väntar på att genereras för journalföring.
- **Visa fördelningar** – Visa redovisningsfördelningarna för ett valt dokument i listan.
- **Visa fellogg** – Visa felmeddelanden som finns för ett dokument där redovisningsstatusen indikerar fel. Du kan visa samma felmeddelandeinformation genom att välja länken **fellogg** på dokumentraden.

Redovisningsgenereringen utförs av en bakgrundsprocess för processautomatisering som kallas **Processor för redovisningsramverk**. Mer information om hur du ställer in och konfigurerar alla processautomatiseringar finns i [Processautomatisering](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
