---
title: Kunddelning med faktureringsschema
description: I den här artikeln beskrivs hur du delar en kund när prenumerationsfakturering används.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746322"
---
# <a name="customer-split-on-billing-schedules"></a>Kunddelning med faktureringsschema

I ett faktureringsschema är *fakturakonto* den kund som får försäljningsorderfakturan så att de kan betala fakturan. I vissa fall kan fler än en kund betala en faktura. Med funktionen **Kunddelning** kan du lägga till fler kunder som kan faktureras för samma faktureringsschema. Om du vill aktivera funktionen går du till **Prenumerationsfakturering \> Återkommande kontraktsfakturering \> Inställningar \> Parametrar för återkommande kontraktsfakturering** och anger alternativet **Kunddelning** till **Ja**.

## <a name="customer-split-on-the-billing-schedule-header"></a>Kunddelning på sidhuvud för fakturaschema

När ett faktureringsschema har skapats kan ytterligare kunder läggas till i sidhuvud för fakturaschema.

Följ dessa steg för att lägga till en kund.

1. På fliken **Faktureringsschema** välj **Kunddelning**. Fälten **Kundkonto** och **Namn på kundkonto** högst upp anger den kund som är tilldelad som kund för **Fakturaschemakund**.

    > [!NOTE]
    > Kundkontot som du lägger till kan inte vara samma som fakturakontot.

2. På fliken **Delad rad för kund** välj **Lägg till rad**.
3. Välj en kund och ange sedan procentandelen av varje faktura för den kunden.
4. Som standard används start- och slutdatumen för faktureringsplanen som start- och slutdatum. Ange olika start- och slutdatum om den nya kunden bara betalar den angivna procentsatsen för en del av faktureringsschemat. Om faktureringsplanen till exempel har startdatumet den 1 januari och slutdatumet är 31 december och den nya kunden faktureras 40 procent för de första nio månaderna, anger du 1 januari som startdatum och den 30 september som slutdatum och skriver **40,00** som procentsats.

Du kan inte att lägga till mer än en kund för delad rad för kund. I det här fallet får den totala angivna procentsatsen inte överstiga 100 procent. Ange en kundreferens och kundrekvisition som informationsfält som ska visas på försäljningsorderraden under processen **Generera faktura**.

Raddetaljerna visar kontaktinformation, leveransadress, faktureringsadress och betalningsinformation för tillagda kunder. Denna information visas även på kundernas försäljningsorder.

När du lägger till kunddelningsinformation i faktureringsschemats huvud, får du följande meddelande som uppmanar dig att rulla ned ändringarna om det finns ofördelade faktureringsschemarader i faktureringsplanen: "Vill du rulla ned ändringen från rubriken till raderna? Ändringarna uppdaterar endast de faktureringsschemaraden som inte har fakturerats." Välj **Ja** om du vill uppdatera kundens uppdelade information på faktureringsschemaraden. Ändringarna uppdateras inte om faktureringsschemaraden redan har fakturerats.

Om ett faktureringsschema skapas med alternativet **Kopiera schema** anges standardinformation på kunddelningens rubrikrader. Det kan inte vara samma som kundkontot.

När processen **Generera faktura** är klar skapas flera försäljningsorder. (Flera försäljningsfakturor skapas också om automatisk bokföring används.) Dessa försäljningsorder och försäljningsfakturor kan visas på fliken **Faktura** på snabbfliken **Raddetaljer** på sidan **Visa faktureringsinformation**. **Flera** visas på faktureringsinformation raden för att visa att flera försäljningsorder och försäljningsfakturor har skapats.

## <a name="customer-split-on-billing-schedule-lines"></a>Kunddelning med faktureringsschemarader

Kunddelningen kan läggas till enskilda faktureringsschemarader om du bara vill dela upp specifika faktureringsschemarader. Markera kryssrutan **Kunddelning** på raden och markera sedan **Kunddelning** på menyn för faktureringsschemaraden som ska uppdatera eller ange information om kunddelning.

Granskningsinformationen uppdateras om faktureringsschemat redan har fakturerats, men procenttalet ändrades på raden i faktureringsplanen. Alla rader som faktureras efter den ändringen kommer att använda den nya procentsatsen.

> [!NOTE]
> - Kundens uppdelade option kan inte användas med lagerprodukter.
> - Om kryssrutan **Ej fakturerad intäkt** är markerad går det inte att markera kryssrutan **Kunddelning**.
> - Om du bara använder alternativet **Endast intäktsdelning** har den överordnade raden alternativet **Kunddelning** men inte de underordnade radartiklarna.
