---
title: Arbetsflöde för leverantör
description: Ändra leverantörsinformationen och använd arbetsflöde för att godkänna den.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 00cdc657fa075e84e62682e33ed3c1bace3f4ad0
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4448234"
---
# <a name="vendor-workflow"></a>Arbetsflöde för leverantör

[!include [banner](../includes/banner.md)]

När leverantörens arbetsflöde används skickas ändringar som görs i specifika fält till arbetsflödet för godkännande innan de kan läggas till leverantören.

## <a name="set-up-the-vendor-workflow"></a>Ställ in arbetsflöde för leverantör

Innan du kan använda funktionen för arbetsflöde måste du aktivera den.

1. Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2. På fliken **Allmän** på snabbfliken **Allmänt**, ange alternativet **"Leverantörsgodkännande** som **Ja**.
3. I fältet **Beteende för datatabell** väljer du vad som ska användas när du importerar data:

    - **Tillåta ändringar utan godkännande** – datatabellen kan uppdatera leverantörsposten utan att bearbeta den genom arbetsflödet.
    - **Ignorera ändringar** – Ändringar kan inte göras till leverantörsposten. Importen misslyckas för fält som är aktiverade för arbetsflödet.
    - **Skapa förslag för ändring** – Alla fält ändras förutom fält som är aktiverade för arbetsflödet. De nya värdena för dessa fält läggs till leverantören som föreslagna ändringar och arbetsflödet startas automatiskt.

4. I listan över leverantörsfält, markera kryssrutan **Aktivera** för alla fält som måste godkännas innan de kan ändras.
5. Gå till **Leverantörsreskontra \> Inställningar \> Arbetsflöden för leverantörsreskontra**.
6. Markera **Nytt**.
7. Välj **Arbetsflöde för föreslagna leverantörsändringar**. 
8. Konfigurera arbetsflödet så att det matchar din godkännandeprocess. Arbetsflödeselementet **Arbetsflödesgodkännande för föreslagen ändring av leverantör** kommer att tillämpa ändringarna på leverantören.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Ändra leverantörsinformation och skicka ändringarna till arbetsflödet

När du ändrar ett fält som är aktiverat för arbetsflödet visas sidan **föreslagna ändringar**. På den här sidan visas det ursprungliga värdet i fältet och det nya värdet som du angav. Fältet som du har ändrat återställs till originalvärdet. Ett statusmeddelande informerar också vilka ändringarna som inte har skickats. 

Varje gång du ändrar ett fält som är aktiverat för arbetsflödet läggs det fältet till i listan på sidan **föreslagna ändringar**. Om du vill ångra det föreslagna värdet för ett fält använder du knappen **Ignorera** bredvid fältet i listan. Om du vill ignorera alla ändringar, använd knappen **Ignorera alla ändringar** längst ned på sidan. Välj **OK** om du vill stänga sidan.

När du har minst en föreslagen ändring visas två ytterligare flikar i åtgärdsfönstret: **föreslagna ändringar** och **arbetsflöde**.

1. Välj **föreslagna ändringar** för att öppna sidan **föreslagna ändringar** och granska ändringarna.
2. Välj **Arbetsflöde \> Skicka för att skicka ändringarna till arbetsflödet**.

    Sidans status ändras till **Ändringar som väntar på godkännande**.

Arbetsflödet följer standard i arbetsflödesprocessen. Godkännaren dirigeras till sidan **Leverantör** där ändringarna kan granskas på sidan **Föreslagna ändringar** och sedan välja **Arbetsflöde \> Godkänn** för att godkänna arbetsflödet. När alla godkännanden har slutförts uppdateras fälten med de värden du har föreslagit.
