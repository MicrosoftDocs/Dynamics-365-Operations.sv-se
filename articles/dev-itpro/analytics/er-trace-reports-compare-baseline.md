---
title: Spåra skapade rapportresultat och jämföra dem med baslinjevärden
description: Det här avsnittet innehåller information om hur du kan jämföra resultaten av skapade ER-rapporter med baslinjerapportvärden.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 7f7877ccaa0c45ab5f0032d6808280e3c47a43ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "317946"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Spåra skapade rapportresultat och jämföra dem med baslinjevärden

[!include[banner](../includes/banner.md)]

Du kan spåra resultatet av ER-format som skapar utgående elektroniska dokument. När genereringen av spårning är aktiverad (ER-användarparametrar **Kör i felsökningsläge**), skapas en ny spårningspost i körningslogg för ER-format varje gång en ER-rapport körs. Följande information lagras i respektive spår som skapas:

- Alla varningar som skapades av valideringsregler
- Alla fel som skapades av valideringsregler
- Alla skapade filer som lagras som bilagor till spårningsposten

Du kan lagra enskilda baslinjeprogramfiler för alla ER-format. Filer betraktas som baslinjefiler när de beskriver de förväntade resultaten av rapporterna som körs. Om det finns en baslinjefil för ett ER-format som kördes när spårgenereringen aktiverades, kommer spårningen, utöver informationen som nämndes tidigare, att lagra resultatet av jämförelsen av det skapade elektroniska dokumentet tillbaslinjefilen. Med ett klick kan du också få det skapade elektroniska dokumentet och dess baslinjefil i en enda zip-fil. Sedan kan du göra detaljerad jämförelse med hjälp av ett externt verktyg såsom Windiff.exe.

Du kan utvärdera spårningen för att analysera om elektroniska dokument som skapas innehåller förväntade innehåll. Du kan göra en sådan utvärdering i ett acceptanstestet för användare (UAT) – när kodbasen har ändrats (till exempel när du migrerar till en ny instans av programmet, installerar snabbkorrigeringspaket eller distribuerar kodändringar). På så sätt kan se du till att utvärderingen inte påverkar genomförandet av ER-rapporter som används. Utvärderingen för många ER rapporter kan göras i obevakat läge.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna **ER Skapa rapporter och jämföra resultat (del 1)** och **ER Skapa rapporter och jämföra resultat (del 2)** som ingår i affärsprocessen **7.5.4.3 Testa IT-lösningar och tjänster (10679)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Dessa uppgiftsguider går igenom processen att konfigurera ER-ramverket för att använda basfiler till att utvärdera skapade elektroniska dokument.
