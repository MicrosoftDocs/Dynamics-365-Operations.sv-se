---
title: Konfigurera TDS-parametrar i Leverantörsreskontra och Kundreskontra
description: I det här avsnittet beskrivs hur du ställer in parametrar i leverantörsreskontra och kundreskontra för att stödja skatteavdrag vid källa (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d2cb434346dbbe5487522fe9f7110716c3a8c761
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725161"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Konfigurera TDS-parametrar i Leverantörsreskontra och Kundreskontra

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in parametrar i leverantörsreskontra och kundreskontra för att stödja skatteavdrag vid källa (TDS).

1. Gå till **Skatt \> Konfiguration \> Parametrar \> Parametrar för kundreskontra**.
2. Under fliken **Uppdateringar** väljer du **Uppdatera orderrader** för att öppna dialogrutan **Uppdatera orderrader**.
3. I avsnittet **TDS-grupp**, i fältet **Uppdatera TDS-grupp**, anger du metoden som ska användas för att uppdatera TDS-gruppen på radnivå. Den här inställningen används när TDS-gruppen uppdateras i en orderrubrik. Följande alternativ är tillgängliga:

    - **Aldrig** – TDS-gruppen är inte uppdaterad på orderraderna när den uppdateras i orderrubriken.
    - **Alltid** – TDS-gruppen uppdateras automatiskt på orderraderna när den uppdateras i orderrubriken.
    - **Uppmaning** – Användarna får ett meddelande som uppmanar dem att uppdatera TDS-gruppen på orderraderna.
4. Välj **OK**.

    [![Dialogrutan Uppdatera orderrader.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Gå till **Skatt \> Konfiguration \> Parametrar \> Parametrar för leverantörsreskontra**.
6. Under fliken **Allmänt**, under snabbfliken **Dela upp baserat på leveransinformation**, ställer du in alternativet **Produktinleverans** på **Ja** för att bokföra och dela upp en produktinleverans som har olika leveransadresser och skattekontonummer (TAN). Om det här alternativet är inställt på **Nej**, kan du inte bokföra en inköpsföljesedel som har olika leveransadresser och TAN.
7. Ställ in alternativet **Faktura** på **Ja** för att bokföra och dela upp en inköpsfaktura som har olika leveransadresser och TAN.

    [![Snabbfliken Dela upp baserat på leveransinformation.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Stäng sidan.
