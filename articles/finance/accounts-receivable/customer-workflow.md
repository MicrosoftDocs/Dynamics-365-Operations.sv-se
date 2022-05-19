---
title: Kundarbetsflöde
description: Det här avsnittet innehåller information om kundarbetsflödet. Du ändrar specifika fält för en kund och skickar sedan ändringarna för godkännande via arbetsflödet innan de läggs till för kunden.
author: abruer
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ccea0de202ec2f5ab706cb2110110fc9ffdc03ee
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735853"
---
# <a name="customer-workflow"></a>Kundarbetsflöde

[!include [banner](../includes/banner.md)]

Kundarbetsflödet är en nyhet i version 8.0.4. Du kan ändra specifika fält för en kund och sedan skicka ändringarna för godkännande via arbetsflödet innan de läggs till för kunden.

## <a name="set-up-the-customer-workflow"></a>Ställ in kundarbetsflödet

Innan du kan använda funktionen för kundarbetsflöde måste du aktivera den.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
2. Aktivera funktionen genom att gå till fliken **Allmänt** och snabbfliken **Kundgodkännande** där du anger **Aktivera kundgodkännanden** till **Ja**.
3. I fältet **Beteende för datatabell** väljer du ett beteende som datatabellen ska använda när data importeras:

    - **Tillåt ändringar utan godkännande** – En enhet kan uppdatera kundposten utan att den bearbetas genom arbetsflödet.
    - **Avvisa ändringar** – Det går inte att ändra kundposten. Importen går inte att genomföra för fält som är aktiverade för arbetsflödet.
    - **Skapa ändringsförslag** – Alla fält ändras utom de fält som har aktiverats för arbetsflödet. De nya värdena för dessa fält läggs till för kunden som föreslagna ändringar och arbetsflödet startar automatiskt.

4. Gå sedan till listan med kundfält och markera kryssrutan **Aktivera** för alla fält som måste godkännas innan de kan ändras.
5. Gå till **Kundreskontra \> Inställningar \> Arbetsflöden för kundreskontra**.
6. Välj **Nytt**.
7. Välj **Arbetsflöde för föreslagen kundändring**. 
8. Konfigurera arbetsflödet så att det matchar godkännandeprocessen. Godkännandeelementet **Arbetsflödesgodkännande för föreslagen kundändring** i arbetsflödet tillämpar ändringarna på kunden.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Ändra kundinformation och skicka ändringarna till arbetsflödet

När du ändrar ett fält som har aktiverats för arbetsflödet visas sidan **Föreslagna ändringar**. På den här sidan visas det ursprungliga värdet i fältet och det nya värdet som du angav. Fältet som du har ändrat återställs till originalvärdet. Ett statusmeddelande på sidan anger att ändringarna inte har skickats.

Varje gång du ändrar ett fält som är aktiverat för arbetsflödet läggs fältet till i listan över föreslagna ändringar. Om du vill ångra det föreslagna värdet för ett fält använder du knappen **Ta bort** bredvid fältet i listan. Om du vill ignorera alla ändringar använder du knappen **Ignorera alla ändringar** längst ned på sidan. Stäng sidan genom att välja **OK**.

När du har minst en föreslagen ändring visas två extra menyer i åtgärdsfönstret: **Föreslagna ändringar** och **Arbetsflöde**.

1. Välj **Föreslagna ändringar** om du vill öppna sidan **Föreslagna ändringar** och granska ändringarna.
2. Välj **Arbetsflöde \> Skicka** för att skicka ändringarna till arbetsflödet.

    Sidans status ändras till **Ändringar som väntar på godkännande**.

Arbetsflödet följer den vanliga arbetsflödesprocessen i appen. Godkännaren dirigeras till sidan **Kund** där ändringarna kan granskas på sidan **Föreslagna ändringar** och sedan välja **Arbetsflöde \> Godkänn** för att godkänna arbetsflödet. När alla godkännanden har slutförts uppdateras fälten med de värden du har föreslagit.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
