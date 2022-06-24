---
title: Servicemallar
description: Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850508"
---
# <a name="service-templates"></a>Servicemallar

[!include [banner](../includes/banner.md)]

Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.

## <a name="example"></a>Exempel

En kund som du tillhandahåller en tjänst för har identiska servicehissar på fem olika platser.

Du vill konfigurera fem serviceavtal för kunden, en för varje site.
För att minska inställningsarbetet, och vara säker på att inställningsinformationen i serviceavtalen blir identisk, skapar du ett serviceavtal och anger den som en mall för servicearbetet på hissarna.

Du kan nu kopiera mallraderna till fem nya serviceavtal, så att varje serviceavtal fylls i med raderna från mallen.

## <a name="create-a-template"></a>Skapa en mall

När du skapar en servicemall skapar du ett serviceavtal, skapar de rader som behövs och kopplar sedan serviceavtalet till en servicemallgrupp.

> [!NOTE]
> Ett serviceavtal kan definieras som en mall bara om det inte har några serviceorder kopplade. Inga serviceorder kan heller skapas från ett serviceavtal som definierats som en mall.

## <a name="copy-template-lines"></a>Kopiera mallrader

Du kan kopiera mallrader från en servicemall till ett annat serviceavtal eller till en serviceorder.

När du kopierar mallrader till dina serviceorder eller serviceavtal visas mallgrupperna i en trädvy där varje grupp kan utvidgas. I den här vyn kan du visa alla mallar och mallrader.

Det är enklare att ta reda på vilka mallrader som du bör kopiera om du grupperar mallarna enligt namn som beskriver hur de ska användas.

## <a name="related-articles"></a>Relaterade artiklar

[Kopiera servicemallsrader](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]