---
title: Skicka fakturor till arbetsflödessystemet och matcha produktinleveransrader
description: I den här artikeln förklaras hur du skickar leverantörsfakturor till arbetsflödessystemet och automatiskt matchar bokförda produktinleveranser på leverantörsfakturor.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 960a08eb5e98cac034bbd41335b616ff41bf6fd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861630"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Skicka fakturor till arbetsflödessystemet och matcha produktinleveransrader

[!include [banner](../includes/banner.md)]

I den här artikeln förklaras hur du skickar leverantörsfakturor till arbetsflödessystemet och automatiskt matchar bokförda produktinleveranser på leverantörsfakturor.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Skicka importerade leverantörsfakturor till arbetsflödessystemet och matcha bokförda inleveransrader till pågående leverantörs fakturarader

Som en del av en uppdelad faktureringsprocess för leverantörsreskontra en importerad faktura kan skickas automatiskt till arbetsflödessystemet. Du kan konfigurera processen för att skicka importerade fakturor till arbetsflödessystemet på fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**). Sändning till arbetsflödesprocess körs i bakgrunden med en frekvens som du anger (antingen per timme eller per dag).

När du skickar fakturor automatiskt till arbetsflödessystemet måste du börja med en importerad faktura. Om du vill vara säker på att fakturan kan bearbetas från början till slut utan manuell ingrepp, måste du inkludera en automatisk bokföringsuppgift i arbetsflödeskonfigurationen. Fakturor som är relaterade till inköpsorder och fakturor som innehåller en anskaffningskategori som inte ingår i inköpsordern och som inte finns i lager, kan automatiskt skickas till arbetsflödessystemet. Fakturor som anges manuellt måste skickas manuellt till arbetsflödessystemet.

Värdet **Skickade av** i arbetsflödet är det användar-ID som angavs för bakgrundsaktiviteten **Skicka leverantörsfakturor till arbetsflöde** på sidan **Processautomatisering**. Den användare som har det användar-ID:t kommer att kunna återkalla fakturan från arbetsflödessystemet efter behov.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Matcha bokförda produktinleveranser mot fakturarader som har en policy för trevägsmatchning

Som en del av en beröringsfri faktureringsprocess för leverantörsreskontra kan bokförda produktkvitton automatiskt matchas mot fakturarader. En policy för trevägsmatchning princip måste definieras för den här uppgiften. Den här funktionen är tillgänglig om funktionen **Automatisering av leverantörsfakturor** har aktiverats på sidan **Funktionshantering**.

Matchningsprocessen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med faktura antalet. Om det däremot finns flera produktinleveranser för en enda fakturarad måste du köra processen flera gånger för att få hela kvantiteten att matcha. Du kan ange det maximala antalet gånger för att försöka med automatisk matchning – Välj det antal gånger som systemet ska försöka matcha produktinleveranser mot en fakturarad innan det finner att processen misslyckades. Processen kommer att köras i bakgrunden, antingen varje timme eller per dag. 

Du kan köra den automatiska matchningen som en del av processen för att skicka fakturor till arbetsflödessystemet. Du kan också köra den som en fristående process. Du kan konfigurera processen matcha produktinleveranser till fakturarader på fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**).

Fakturarader som har en policy för trevägsmatchning där den avstämda inleveranskvantiteten är mindre än den fakturerade kvantiteten, kommer att inkluderas i den automatiska processen matcha till produktinleverans.

Om du vill visa statusen **senaste matchning** för fakturor som inte ingår i den automatiserade processen skicka till arbetsflöde öppnar du fakturan från sidan **Leverantörsfakturor**. När du visar fakturan uppdateras den matchande valideringsinformationen. Statusvärdet för **Senaste matchning** an uppdateras automatiskt med hjälp av bakgrundsuppgiften **Validera fakturamatchning**. Du kan konfigurera automatisk uppdatering av statusvärdet **Senaste matchning** på fliken **Bakgrundsprocesser** på sidan **Processautomatiseringar** (**Systemadminstration\> Inställningar\> Processautomatiseringar**).

En fakturarad exkluderas från den automatiska bearbetningen om något av följande villkor uppfylls:

- Värdet **Status för automatisk inleveransmatchning** för fakturaraden är **misslyckades**.
- Fakturan används.
- Fakturan är i arbetsflödessystemet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
