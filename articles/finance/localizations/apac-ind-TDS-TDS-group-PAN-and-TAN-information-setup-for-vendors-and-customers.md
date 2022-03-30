---
title: Ställa in TDS-grupp, PAN- och TAN-information för leverantörer och kunder
description: I det här avsnittet beskrivs hur du ställer in information om gruppen Skatteavdrag vid källa (TDS), permanent kontonummer (PAN) och skattekontonummer (TAN) för leverantörer och kunder.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 808fa7b72651ab274415e48f5e0a356784ca6525
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407546"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>TDS-grupp, PAN- och TAN-information för leverantörer och kunder

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in information om gruppen Skatteavdrag vid källa (TDS), permanent kontonummer (PAN) och skattekontonummer (TAN) för leverantörer och kunder.

1. Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer** eller **Kundreskontra \> Kunder \> Alla kunder**.

    [![Sidan Alla leverantörer.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. I åtgärdsfönstret väljer du **Ny** för att skapa en leverantör eller kund och anger den information som krävs. Du kan även välja en befintlig leverantör eller kund.
3. Under snabbfliken **Faktura och leverans**, i avsnittet **Källskatt**, ställer du in alternativet **Beräkna källskatt** på **Ja** för att beräkna källskatt, TDS eller skatt insamlad vid källan (TCS) för leverantören eller kunden.
4. TDS för en inköpsfaktura beräknas baserat på standardgruppen för TDS som har definierats för leverantören eller kunden. I fältet **TDS-grupp** väljer du standard-TDS-grupp.

    > [!NOTE]
    > När du väljer en TDS-grupp i fältet **TDS-grupp** blir fälten **Källskattegrupp** och **TCS-grupp** otillgängliga.

5. Under snabbfliken **Skatteinformation**, i avsnittet **PAN-information**, i fältet **Status**, väljer du status för permanent kontonummer för leverantören eller kunden:

    - **Inte tillgängligt** – Leverantören eller kunden har inte ett PAN.
    - **Mottaget** – Leverantören eller kunden har PAN.
    - **Ansökt** – Leverantören eller kunden har ansökt om PAN.
    - **Ogiltigt** – Leverantören eller kunden har PAN, men det är ogiltigt.

6. Om du har valt **Mottaget** i fältet **Status** för att indikera att leverantören eller kunden har PAN, anger du PAN i fältet **Nummer**. PAN måste bestå av fem alfabetiska tecken, därefter fyra numeriska tecken och därefter ett alfabetiskt tecken. Här är ett exempel: **ABCDE1260A**.
7. Om du har valt **Ansökt** i fältet **Status** för att indikera att leverantören eller kunden har ansökt om PAN, anger du referensnumret i fältet **Referensnummer**.
8. I fältet **Typ av bedömare** väljer du typen av bedömningskategori som leverantören eller kunden tillhör:

    - Företag
    - HUF
    - Bekräfta
    - Enskild
    - AOP
    - BOI
    - Lokal myndighet
    - Annat

    [![Snabbfliken Skatteinformation.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. I åtgärdsfönstret, under fliken **Leverantör**, i gruppen **Registrering**, väljer du **Registrerings-ID** för att öppna sidan **Hantera adresser**.
10. På sidan **Hantera adresser**, under snabbfliken **Skatteinformation**, väljer du **Lägg till** eller **Redigera** för att öppna sidan **Hantera skatteinformation**, där du kan bibehålla skatteregistreringsposten.
11. På sidan **Hantera skatteinformation**, under snabbfliken **Källskatt**, i fältet **Skattekontonummer (TAN)**, anger du TAN. TAN måste bestå av fyra alfabetiska tecken, därefter fem numeriska tecken och därefter ett alfabetiskt tecken. Här är ett exempel: **AFGH54821T**.
12. Stäng sidan.
