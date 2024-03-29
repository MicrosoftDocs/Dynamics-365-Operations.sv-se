---
title: Verifikation genereras inte
description: Detta ämne tillhandahåller felsökningsinformation som kan vara till hjälp när en verifikation borde genereras men inte gör det.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1200fe50bf9be4c6d1ca809ad9a86da2ff3e0ced
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909023"
---
# <a name="voucher-isnt-generated"></a>Verifikation genereras inte

[!include [banner](../includes/banner.md)]

Om en verifikation ska genereras men sidan **Verifikationstransaktioner** inte visar några verifikationer, följer du stegen i följande avsnitt när du felsöker det här problemet.

[![Sida för Verifikationstransaktioner som inte har några verifikationer.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Kontrollera tillämplighet för moms

1. Gå till **Moms** \> **Periodiska uppgifter** \> **Poster i redovisningsjournal som ännu inte har överförts**.
2. Om det finns en journalpost väljer du den och sedan **Överför nu**.

    [![Knappen Överför nu på sidan för poster i redovisningsjournal som ännu inte har överförts.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Öppna sidan **Verifikationstransaktioner** igen om du vill se om verifikationen har skapats.

## <a name="determine-whether-customization-exists"></a>Bestäm om anpassning finns

Om du har utfört stegen i det föregående avsnittet men inte hittat något problem, ska du fastställa om det finns någon anpassning. Om det inte finns någon anpassning skapar du en Microsoft-servicebegäran för ytterligare support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
