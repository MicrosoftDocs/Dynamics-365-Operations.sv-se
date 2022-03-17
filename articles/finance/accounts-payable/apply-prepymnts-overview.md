---
title: Använd förskottsbetalning automatiskt för leverantörsfakturor
description: I det här avsnittet beskrivs möjligheten att automatiskt tillämpa förskottsbetalningar på leverantörsfakturor.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8583962c41a7ac5e27463f325ddc2ccd367331cc
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358229"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Använd automatiskt för leverantörsfakturor

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs möjligheten att automatiskt tillämpa förskottsbetalningar på leverantörsfakturor. En förskottsbetalning kan skapas för en inköpsorder som en del av ett inköpsavtal. När en leverantörsfaktura har mottagits kan förskottsbetalningen användas för att kvitta leverantörsreskontra från leverantörsfakturan. Med den nya funktionen kan systemet automatiskt använda inköpsordernummer på en leverantörsfaktura för att slå upp motsvarande förskottsbetalningar när leverantörsfakturan importeras.

Om förskottsbetalningar hittas och kan användas, läggs rader till på de befintliga fakturaraderna så att förskottsbetalningarna används. Förskottsbetalningsraderna beaktas aldrig under fakturamatchningsprocessen.

Följande poäng beskriver hur förskottsbetalningar tillämpas när olika inköpsprocesser följs:

- **En leverantörsfaktura per inköpsorder** – Förskottsbetalningen på inköpsordern tillämpas på leverantörsfakturan.
- **En leverantörsfaktura för flera inköpsorder** – Förskottsbetalningar på alla inköpsorder tillämpas på leverantörsfakturan.
- **Flera leverantörsfakturor per inköpsorder** – Förskottsbetalningen på inköpsordern tillämpas på den första importerade leverantörsfakturan. Om förskottsbetalningsbeloppet överstiger fakturabeloppet misslyckas förskottsbetalningen och du måste använda förskottsbetalningen manuellt.
- **Flera leverantörsfakturor för flera inköpsorder** – Förskottsbetalningar på inköpsorder tillämpas på den första relevanta fakturan. Om förskottsbetalningsbeloppet överstiger fakturabeloppet misslyckas förskottsbetalningen och du måste använda förskottsbetalningar manuellt. Om några förskottsbetalningar som återstår efter förskottsbetalningar tillämpas på den första fakturan, kan de tillämpas på de fakturor som följer.

Om ett försök till förskottsbetalning kommer inställningen för **Blockera uppföljande automationsprocess om ansökningen om förskottsbetalning inte kan användas** att avgöra nästkommande steg:

- **Ja** – Felmeddelandet "Automatisk användning av förskottsbetalning: Misslyckat" läggs till i automationshistoriken och fakturan finns kvar i listan med pågående leverantörsfakturor. Fakturan spärras tills du tillämpar förskottsbetalningen manuellt.

Om du vill tillämpa förskottsbetalningar manuellt går du till den pågående leverantörsfakturan. På sidan **Fakturainformation** anger du alternativet **Inkludera i automatiserad bearbetning** av den spärrade fakturan till **Nej**. Du kan nu använda förskottsbetalningen manuellt. När förskottsbetalningen har använts ställer du tillbaka alternativet **Inkludera i automatiserad bearbetning** till **Ja** så att fakturan kan bearbetas automatiskt.

Du kan också hoppa över automatisk hantering av förskottsbetalningen genom att ställa in alternativet **Inkludera i automatiserad bearbetning** till **Nej** och sedan ställa tillbaka den till **Ja**. Då visas följande meddelande: "En förskottsbetalning finns redan för inköpsordern. Vill du ignorera det för den valda leverantörsfakturan? Välj **Ja**. Meddelandet "Program för förskottsbetalning kringgås manuellt" läggs till i automationshistoriken och leverantörsfakturan spärras inte när den automatiska processen körs igen.

- **Nej** – Processerna för uppföljningsautomatisering fortsätter. Du kan fortfarande använda förskottsbetalningen under kvittningen.
