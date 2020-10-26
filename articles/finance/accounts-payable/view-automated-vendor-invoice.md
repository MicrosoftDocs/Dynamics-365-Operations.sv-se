---
title: Visa resultat från automatisering av leverantörsfakturor (förhandsversion)
description: I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen.
author: abruer
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 65e7929e612c8465f26a2f3bc7df6f13620e5b4e
ms.sourcegitcommit: 3387595e41fb03e98bb437588f6de78794ae383f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "3930953"
---
# <a name="view-vendor-invoice-automation-results-preview"></a>Visa resultat från automatisering av leverantörsfakturor (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen. Information om automatiseringshistoriken underhålls för varje importerad leverantörsfaktura. Beroende på vilka affärsprocesser du har automatiserat visar sidan **Pågående leverantörsfakturor** värdena **Automatisk mottagningsstatus** och **Automatisk överföring till statusvärden för arbetsflöden**. Du kan visa detaljerna och göra en plan för att fokusera på fakturorna som misslyckades med ett automatiserat steg. När du har korrigerat problemet kan du sedan återuppta den automatiserade processen för den importerade fakturan.

Innan du kan redigera en faktura som har skickats, måste du pausa den automatiska bearbetningen. Om en faktura i den automatiska sändningen till arbetsflödesprocessen måste pausas, ställer du in flöden **inkludera i automatisk bearbetning** till **Nej** på sidan **Leverantörsfakturor**. Automatiseringen körs inte förrän **inkludera i automatisk bearbetning** anges till **Ja**. En faktura kan pausas från ytterligare automatisering om den inte redan finns i arbetsflödessystemet och inte används av den automatiska processen.

Om en importerad faktura omfattas av sändningen av arbetsflödesprocessen kan du visa värdet **automatiseringsstatus** värde på sidan **leverantörsfakturor**. Följande statusvärden spåras:

- **Inkluderat** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** körs på rätt sätt men ännu inte slutförts.
- **Pausad** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** har körts, men minst ett steg i processen misslyckades. Statusen **Pausad** används även om fältet **inkludera i automatisk bearbetning** är inställt på **Nej**. Du kan visa felen genom att välja knappen **Visa senaste resultat**.
- **I arbetsflödet** – den importerade fakturan har skickats till arbetsflödessystemet, antingen genom den automatiska sändningen till arbetsflödesprocessen eller manuellt.
- **Arbetsflödet slutfört** – arbetsflödesprocessen har slutförts för den importerade fakturan.