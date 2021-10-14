---
title: Servicemallar
description: Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.
author: kamaybac
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82a19dbee91f13eb3ef56dfd67a775930170b8e7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576314"
---
# <a name="service-templates"></a>Servicemallar

[!include [banner](../includes/banner.md)]

Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.

## <a name="example"></a>Exempel

En kund som du tillhandahåller en tjänst för har identiska servicehissar på fem olika platser.

Du vill ställa in fem serviceavtal för kunden, en för varje site.
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

## <a name="related-topics"></a>Relaterade ämnen

[Kopiera servicemallsrader](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]