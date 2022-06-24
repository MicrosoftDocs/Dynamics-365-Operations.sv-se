---
title: Visa resultat från automatisering av leverantörsfakturor (förhandsversion)
description: I den här artikeln beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd9b74d2ed34399aff455563504c296a5a25a874
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895179"
---
# <a name="view-vendor-invoice-automation-results"></a>Visa resultat från automatisering av leverantörsfakturor

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen. Information om automatiseringshistoriken underhålls för varje importerad leverantörsfaktura. Beroende på vilka affärsprocesser du har automatiserat visar sidan **Pågående leverantörsfakturor** värdena **Automatisk mottagningsstatus** och **Automatisk överföring till statusvärden för arbetsflöden**. Du kan visa detaljerna och göra en plan för att fokusera på fakturorna som misslyckades med ett automatiserat steg. När du har korrigerat problemet kan du sedan återuppta den automatiserade processen för den importerade fakturan.

Innan du kan redigera en faktura som har skickats, måste du pausa den automatiska bearbetningen. Om en faktura i den automatiska sändningen till arbetsflödesprocessen måste pausas, ställer du in flöden **inkludera i automatisk bearbetning** till **Nej** på sidan **Leverantörsfakturor**. Automatiseringen körs inte förrän **inkludera i automatisk bearbetning** anges till **Ja**. En faktura kan pausas från ytterligare automatisering om den inte redan finns i arbetsflödessystemet och inte används av den automatiska processen.

Om en importerad faktura omfattas av sändningen av arbetsflödesprocessen kan du visa värdet **automatiseringsstatus** värde på sidan **leverantörsfakturor**. Följande statusvärden spåras:

- **Inkluderat** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** körs på rätt sätt men ännu inte slutförts.
- **Pausad** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** har körts, men minst ett steg i processen misslyckades. Statusen **Pausad** används även om fältet **inkludera i automatisk bearbetning** är inställt på **Nej**. Du kan visa felen genom att välja knappen **Visa senaste resultat**.
- **I arbetsflödet** – den importerade fakturan har skickats till arbetsflödessystemet, antingen genom den automatiska sändningen till arbetsflödesprocessen eller manuellt.
- **Arbetsflödet slutfört** – arbetsflödesprocessen har slutförts för den importerade fakturan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
