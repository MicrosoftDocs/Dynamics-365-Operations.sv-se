---
title: Visa resultat från automatisering av leverantörsfakturor (förhandsversion)
description: I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
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
ms.openlocfilehash: ec49a621e24b6373532497b499e8b9d45c9bed14
ms.sourcegitcommit: 30c541426cf2037b768e3556e1b170a64991f64a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "4448179"
---
# <a name="view-vendor-invoice-automation-results"></a>Visa resultat från automatisering av leverantörsfakturor

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen. Information om automatiseringshistoriken underhålls för varje importerad leverantörsfaktura. Beroende på vilka affärsprocesser du har automatiserat visar sidan **Pågående leverantörsfakturor** värdena **Automatisk mottagningsstatus** och **Automatisk överföring till statusvärden för arbetsflöden**. Du kan visa detaljerna och göra en plan för att fokusera på fakturorna som misslyckades med ett automatiserat steg. När du har korrigerat problemet kan du sedan återuppta den automatiserade processen för den importerade fakturan.

Innan du kan redigera en faktura som har skickats, måste du pausa den automatiska bearbetningen. Om en faktura i den automatiska sändningen till arbetsflödesprocessen måste pausas, ställer du in flöden **inkludera i automatisk bearbetning** till **Nej** på sidan **Leverantörsfakturor**. Automatiseringen körs inte förrän **inkludera i automatisk bearbetning** anges till **Ja**. En faktura kan pausas från ytterligare automatisering om den inte redan finns i arbetsflödessystemet och inte används av den automatiska processen.

Om en importerad faktura omfattas av sändningen av arbetsflödesprocessen kan du visa värdet **automatiseringsstatus** värde på sidan **leverantörsfakturor**. Följande statusvärden spåras:

- **Inkluderat** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** körs på rätt sätt men ännu inte slutförts.
- **Pausad** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** har körts, men minst ett steg i processen misslyckades. Statusen **Pausad** används även om fältet **inkludera i automatisk bearbetning** är inställt på **Nej**. Du kan visa felen genom att välja knappen **Visa senaste resultat**.
- **I arbetsflödet** – den importerade fakturan har skickats till arbetsflödessystemet, antingen genom den automatiska sändningen till arbetsflödesprocessen eller manuellt.
- **Arbetsflödet slutfört** – arbetsflödesprocessen har slutförts för den importerade fakturan.
