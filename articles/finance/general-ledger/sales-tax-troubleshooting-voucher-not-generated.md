---
title: Verifikation genereras inte
description: Detta ämne tillhandahåller felsökningsinformation som kan vara till hjälp när en verifikation borde genereras men inte gör det.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947712"
---
# <a name="voucher-isnt-generated"></a>Verifikation genereras inte

[!include [banner](../includes/banner.md)]

Om en verifikation ska genereras men sidan **Verifikationstransaktioner** inte visar några verifikationer, följer du stegen i följande avsnitt när du felsöker det här problemet.

[![Sida för Verifikationstransaktioner som inte har några verifikationer](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Kontrollera tillämplighet för moms

1. Gå till **Moms** \> **Periodiska uppgifter** \> **Poster i redovisningsjournal som ännu inte har överförts**.
2. Om det finns en journalpost väljer du den och sedan **Överför nu**.

    [![Knappen Överför nu på sidan för poster i redovisningsjournal som ännu inte har överförts](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Öppna sidan **Verifikationstransaktioner** igen om du vill se om verifikationen har skapats.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i det föregående avsnittet men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
