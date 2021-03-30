---
title: Skicka fakturor till arbetsflödessystemet och matcha produktinleveransrader
description: I det här avsnittet förklaras hur du skickar leverantörsfakturor till arbetsflödessystemet och automatiskt matchar bokförda produktinleveranser på leverantörsfakturor.
author: abruer
manager: AnnBe
ms.date: 09/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 534b5dbc54a516fea0b3f7090042d247c1076737
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231552"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Skicka fakturor till arbetsflödessystemet och matcha produktinleveransrader

[!include [banner](../includes/banner.md)]

I det här avsnittet förklaras hur du skickar leverantörsfakturor till arbetsflödessystemet och automatiskt matchar bokförda produktinleveranser på leverantörsfakturor.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Skicka importerade leverantörsfakturor till arbetsflödessystemet och matcha bokförda inleveransrader till pågående leverantörs fakturarader

Som en del av en uppdelad faktureringsprocess för leverantörsreskontra kan du låta systemet automatiskt skicka in en importerad faktura till arbetsflödessystemet. Du kan konfigurera processen för att skicka importerade fakturor till arbetsflödessystemet på fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**). Sändning till arbetsflödesprocess körs i bakgrunden med en frekvens som du anger (antingen per timme eller per dag).

När du skickar fakturor automatiskt till arbetsflödessystemet måste du börja med en importerad faktura. Om du vill vara säker på att fakturan kan bearbetas från början till slut utan manuell ingrepp, måste du inkludera en automatisk bokföringsuppgift i arbetsflödeskonfigurationen. Fakturor som är relaterade till inköpsorder och fakturor som innehåller en anskaffningskategori som inte ingår i inköpsordern och som inte finns i lager, kan automatiskt skickas till arbetsflödessystemet. Fakturor som anges manuellt måste skickas manuellt till arbetsflödessystemet.

Värdet **Skickade av** i arbetsflödet är det användar-ID som angavs för bakgrundsaktiviteten **Skicka leverantörsfakturor till arbetsflöde** på sidan **Processautomatisering**. Den användare som har det användar-ID:t kommer att kunna återkalla fakturan från arbetsflödessystemet efter behov.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Matcha bokförda produktinleveranser mot fakturarader som har en policy för trevägsmatchning

Som en del av en beröringsfri faktureringsprocess för leverantörsreskontra kan systemet automatiskt matcha bokförda produktinleveranser mot fakturarader. En policy för trevägsmatchning princip måste definieras för den här uppgiften. Den här funktionen är tillgänglig om funktionen **Automatisering av leverantörsfakturor** har aktiverats på sidan **Funktionshantering**.

Processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med faktura antalet. Som en del av denna process kan du ange det maximala antalet gånger för att försöka med automatisk matchning – Välj det antal gånger som systemet ska försöka matcha produktinleveranser mot en fakturarad innan det finner att processen misslyckades. Processen kommer att köras i bakgrunden, antingen varje timme eller per dag. Du kan köra den automatiska matchningen som en del av processen för att skicka fakturor till arbetsflödessystemet. Du kan också köra den som en fristående process. Du kan konfigurera processen matcha produktinleveranser till fakturarader på fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**).

Fakturarader som har en policy för trevägsmatchning där den avstämda inleveranskvantiteten är mindre än den fakturerade kvantiteten, kommer att inkluderas i den automatiska processen matcha till produktinleverans.

Om du vill visa statusen **senaste matchning** för fakturor som inte ingår i den automatiserade processen skicka till arbetsflöde öppnar du fakturan från sidan **Leverantörsfakturor**. När du visar fakturan uppdateras den matchande valideringsinformationen. Statusvärdet för **Senaste matchning** an uppdateras automatiskt med hjälp av bakgrundsuppgiften **Validera fakturamatchning**. Du kan konfigurera automatisk uppdatering av statusvärdet **Senaste matchning** på fliken **Bakgrundsprocesser** på sidan **Processautomatiseringar** (**Systemadminstration\> Inställningar\> Processautomatiseringar**).

En fakturarad exkluderas från den automatiska bearbetningen om något av följande villkor uppfylls:

- Värdet **Status för automatisk inleveransmatchning** för fakturaraden är **misslyckades**.
- Fakturan används.
- Fakturan är i arbetsflödessystemet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]