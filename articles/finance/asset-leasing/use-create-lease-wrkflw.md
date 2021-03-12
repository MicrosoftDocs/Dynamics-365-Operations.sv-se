---
title: Använda arbetsflöden för leasinggodkännande
description: I det här ämnet beskrivs hur du använder arbetsflöden för att godkänna tillgångsleasing och hur du spårar status och historik för arbetsflödena.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1086231c65a726df5162d3593419a129d6ae5655
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992768"
---
# <a name="use-lease-approval-workflows"></a>Använda arbetsflöden för leasinggodkännande

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du använder arbetsflöden för att godkänna tillgångsleasing och hur du spårar status och historik för arbetsflödena. Arbetsflöden hjälper till att hantera leasinggodkännanden genom att tillhandahålla en standarduppsättning godkännandesteg och tilldela specifika användare som godkänner varje steg i processen. En godkännare kan godkänna en leasing, avvisa den, begära en ändring eller tilldela den till en annan användare för godkännande. Arbetsflöden kan också ge mer insyn i godkännandeprocessen genom att låta deras status och historik spåras. Dessutom kan du visa en centraliserad arbetslista som visar de uppgifter och godkännanden som har tilldelats specifika godkännare.

Innan du använder den här proceduren måste du se till att minst ett arbetsflöde för godkännande har skapats. Om det inte finns något arbetsflöde skapar du ett. Mer information om hur du konfigurerar ett arbetsflöde finns i [Konfigurera arbetsflöden för leasinggodkännande](set-up-lease-wrkflw.md).

1. Skicka en leasing för godkännande. På sidan **Information om bok** för leasingen väljer du **Arbetsflöde** och väljer sedan **Skicka**.
2. I dialogrutan som visas kan du lägga till en kommentar. Den valda godkännaren kommer att se kommentaren tillsammans med leasingen. När du har skrivit kommentaren väljer du **Skicka**. Leasingen skickas till arbetsflödessystemet och godkännaren tar emot den för godkännande.
3. Om du vill visa de leasingar som är avsedda att godkänna går du till **Moduler \> Gemensamt \> Arbetsuppgifter \> Arbetsuppgifter som tilldelats mig**.
4. På sidan **Arbetsuppgifter som tilldelats mig** väljer du länken **Leasing-ID** för den leasing som du vill visa. Vilken sida som visas beror på vilka leasingböcker och leasinguppgifter som du har åtkomst till.
5. När du har slutfört visningen av leasingen väljer du **Arbetsflöde** och bestämmer vilken åtgärd som ska vidtas. Alternativen är **Godkänn**, **Avvisad**, **Begär ändring**, **Delegera** och **Annullerad**. Du kan också välja **Visa historik** om du vill visa godkännandehistoriken för den valda leasingen.
6. När du har valt en åtgärd anger du en kommentar som beskriver åtgärden. När du har skrivit kommentaren väljer du åtgärden **Godkänd** i listan.
7. Om du vill visa godkännandeåtgärderna går du tillbaka till sidan **Leasingdetaljer** från sidan **Sammanfattning av leasing** och väljer **Arbetsflöde \> Visa historik**.

    Du kan visa arbetsflödesaktiviteter på sidan **Arbetsflödeshistorik**. På den här sidan visas de steg i arbetsflödet som har vidtagits för den specifika leasingen. Du kan också använda fältet **Arbetsuppgifter** om du vill visa status för de tilldelade arbetsuppgifterna.

8. Om du vill stoppa ett arbetsflöde väljer du **Återkalla** på sidan **Arbetsflödeshistorik**. I dialogrutan som visas anger du en kommentar och välj **OK**.
9. Om du vill inaktivera ett arbetsflöde, eller aktivera ett arbetsflöde som har skapats tidigare, kan du gå till **Leasing av tillgångar \> Konfigurera \> Leasingarbetsflöde**. På sidan **Leasingarbetsflöde** väljer du **Arbetsflöde \> Versioner**. Om du vill göra ett aktuellt arbetsflöde inaktivt väljer du den aktiva leasingen i dialogrutan för leasingversion och väljer sedan **Inaktivera**. Om du vill göra ett befintligt arbetsflöde aktivt väljer du arbetsflödet och väljer sedan **Aktivera**.
